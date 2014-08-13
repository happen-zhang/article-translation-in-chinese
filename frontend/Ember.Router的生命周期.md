
# Ember路由生命周期 #

路由是**Ember**的核心部分。当我们每次访问一个新的URL时，Ember就会对URL进行解析，然后调用相应的Route对象。下面是Route对象中已定义好的钩子函数：

* enter(私有)

* activate：进入路由时将会执行这个操作

* deserialize（私有）

* model：这个钩子会返回一个model，并且会把它设置成当前路由的`currentModel`

* serialize：可以对model进行适当地处理

* setupController：默认情况下它会将`currentModel`设置给控制器的`content`键

* renderTemplate：渲染指定名称的模板，并同时会把当前控制器和模型的实例传递给模板

* deactivate：退出路由时将会执行这个操作（内部会执行`exit`函数）

* exit（私有，必须调用this._super）

Ok，现在我们就来详细地看看它们吧。

## activate / deactivate ##

这两个属性的前身分别是`enter`和`exit`，而现在`enter`和`exit`都已经被修改成私有的了。当用户进入一个路由中时，可以是通过浏览器直接输入URL进入或者是从其它地址过渡（transition）进入的，`activate`都将会被执行，相反地，当用户过渡出路由后，`deactivate`也将会被调用。

`deactivate`的一个常见用法是，我们可以在离开路由时，对某些事务进行回滚。

```Javascript
App.PostNewRoute = Ember.Route.extend({
    devative: function() {
        this.modelFor("postsNew").get("transaction").rollback();
    }
});
```

我发现这个这个用法非常好用，比如，我们有一个新增表单（或者是编辑表单），它表示了一条记录的数据，当用户在未保存数据的情况下离开当前的路由时，我们就可以通过`deactivate`来回滚之前的任何修改了。

## model / serialize ##

为了让Ember能够随着URL的变化作出相应地业务操作，我们需要告诉Ember怎么样去「序列化」和「反序列化」我们的模型。当我们直接从URL进入（或者是重载页面）时，Ember会从URL中取出参数传递给`model`，并调用它。让我们先来看看一个例子吧：

```Javascript
App.Router.map(function() {
  this.resource("post", { path: "/:post_id" });
});

App.PostRoute = Ember.Route.extend({

  model: function(params) {
    return App.Post.find(params.post_id);
  }

});
```

在上面的例子中，我们可以很明显地看出Ember能够为我们提供需要的模型数据，然后再进行序列化该数据：

```Javascript
App.PostRoute = Ember.Route.extend({

  model: function(params) {
    return App.Post.find(params.post_id);
  },

  serialize: function(model) {
    return { post_id: model.id };
  }

});
```

这里需要注意的是，当我们从其它的路由中过渡过来时，`model`钩子是不会被调用的。

## setupController ##

执行过`model`钩子之后，接下来的就是`setupController`了。它可以为控制器预先添加一些额外的属性，或者重写控制器的`content`属性。

但这里需要当心的是，`content`属性不是由`setupController`自动生成的，而是在`setupController`被调用之前就已经存在了，它其实是由`setup`钩子生成的。下面是一个简单的例子：

```Javascript
setupController: function(controller, model) {
  controller.set("content", model);
}
```

我们也可以为控制器添加其它额外的属性，不一定需要指定`content`属性：

```Javascript
setupController: function(controller, model) {
  controller.set("foo", "bar");
}
```

## renderTemplate ##

最后一个钩子是`renderTemplate`，你可以告诉它你需要渲染哪个模板。

`renderTemplate`默认会调用`this.render`方法：

```Javascript
App.PostRoute = App.Route.extend({

  renderTemplate: function() {
    this.render("post", {
      into: "application",
      outlet: "main",
      controller: "post"
    });
  }

});
```

在上面的例子中，`render`会去渲染`post`模板，然后把它放置到`application`模板中的`main` `outlet` （关于`outlet`，可以查看[Ember模板文档](http://www.emberjs.cn/guides/templates/the-application-template/)）中，并把`PostController`作为控制器。

你可以在`render`中设置在哪个 `outlet` 中渲染模板。例如，我们可以把模板渲染到`application`中侧边栏的`outlet`上，`{{outlet sidebar}}`。

```Javascript
App.PostRoute = App.Route.extend({

  renderTemplate: function() {
    // 默认渲染
    this.render();

    // 渲染到侧边栏上
    this.render("similarPosts", {
      into: "application",
      outlet: "sidebar"
    });
  }

});
```

## controllerFor 和 modelFor ##

我们可以调用`controllerFor("posts")`来得到一个`PostsController`实例，调用`modelFor("posts")`**不会**返回`PostsController`的`content`属性。与之相反的是，它会返回`PostsRoute`中的`currentModel`属性。

让我们来看个例子：

```Javascript
App.PostsRoute = Ember.Route.extend({

  setupController: function(controller) {
    controller.set("content", App.Post.find());
  }

});
```

如果我们在上面的例子中使用的是`modeFor`方法的话，那么将会出现问题的。`PostsRoute`中的`currentModel`还没有值，`modelFor`方法返回的就是`currentModel`的值，那么这个值将会是`undefined`的。这样做将会让控制器设置了一个让人感到莫名其妙的值。

<hr />

## 其它 ##

原文地址：[Router Request Lifecycle](http://blog.trackets.com/2013/02/08/router-request-lifecycle.html)
