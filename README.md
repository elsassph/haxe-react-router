# React-router externs for Haxe

Simple externs for [react-router](https://github.com/ReactTraining/react-router) 3.0.0+ 
for use with [Haxe react](https://github.com/massiveinteractive/haxe-react) 1.0.0+.

```haxe
  var history = ReactRouter.browserHistory;

  var app = ReactDOM.render(jsx('
  
    <Router history=$history>
      <Route path="/" component=$PageWrapper>
        <IndexRoute component=$HomeView/>
        <Route path="about" component=$AboutView/>
      </Route>
    </Router>
      
  '), rootElement);
```

Using [haxe-modular](https://github.com/elsassph/haxe-modular) it is possible to define asynchronous routes:

```haxe
  var history = ReactRouter.browserHistory;

  var app = ReactDOM.render(jsx('

    <Router history=$history>
      <Route path="/" component=$PageWrapper>
        <IndexRoute getComponent=${RouteBundle.load(HomeView)}/>
        <Route path="about" getComponent=${RouteBundle.load(AboutView)}/>
      </Route>
    </Router>

  '), rootElement);
````
