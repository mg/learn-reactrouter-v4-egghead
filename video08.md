# Render Catch-All Routes with React Router v4 using the Switch Component
[Video](https://egghead.io/lessons/react-rendering-catch-all-routes-with-react-router-v4-using-the-switch-component)

- A ``<Route>`` with no ``path`` property will always render.

- Use the ``<Switch>`` component to only render the first route that matches.

```js
import { BrowserRouter as Router, Route, Link, Switch } from 'react-router-dom'

const Links = () =>
  <nav>
    <Link to='/'>Home</Link>
    <Link to='/about'>About</Link>
    <Link to='/contact'>Contact</Link>
  </nav>

const App = () => (
  <Router>
    <div>
      <Links/>
      <Switch>
        <Route exact path='/' render={() => <h1>Home</h1>} />
        <Route path='/about' render={() => <h1>About</h1>} />
        <Route render={() => <h1>Page not found</h1>} />
      </Switch>
    </div>
  </Router>
)

export default App
```
