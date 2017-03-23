# Redirect to Another Page with React Router v4
[Video](https://egghead.io/lessons/react-redirecting-to-another-page-with-react-router-v4)

Method 2 works better for forwarding any params from old to new url

```js
import { BrowserRouter as Router, Route, Link, Switch, Redirect } from 'react-router-dom'

const Links = () =>
  <nav>
    <Link to='/'>Home</Link>
    <Link to='/old/123'>Old</Link>
    <Link to='/new/456'>New</Link>
  </nav>

const App = () => (
  <Router>
    <div>
      <Links/>
      /* method 1 */
      <Switch>
        <Route exact path='/' render={() => <h1>Home</h1>}/>
        <Route path='/new' render={() => <h1>New</h1>}/>
        <Redirect from='/old' to='/new' />
      </Switch>

      /* method 2 */
      <Route exact path='/' render={() => <h1>Home</h1>}/>
      <Route path='/new' render={() => <h1>New</h1>}/>
      <Route path='/old/:str' render={({match}) => <Redirect to=`/new/${match.params.str}`/>}/>

      /* protected path */
      <Route path='/protected' render={() => (
        loggedIn
        ? <h1>Welcome to the protected page</h1>
        : <Redirect to='/login'/>
      )}/>

    </div>
  </Router>
)


export default App
```
