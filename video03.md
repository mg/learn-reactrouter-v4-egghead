# Use the React Router v4 Link Component for Navigation Between Routes
[Video](https://egghead.io/lessons/react-use-the-react-router-v4-link-component-for-navigation-between-routes)

- ``<Link>`` renders a ``<a>`` tag in the DOM.

- It accepts a ``to`` property that specifies what should go into the ``href`` attribute.

- ``to`` can be a string, or an object with e.g. the ``pathname`` property.

- ``replace``: Don't push the route change on the history stack, but replace the last item in the stack.

```js
import { BrowserRouter as Router, Route, Link } from 'react-router-dom'

const Links = () =>
  <nav>
    <Link to='/'>Home</Link>
    <Link to={{pathname: '/about'}}>About</Link>
    <Link replace to='/contact'>Contact</Link>
  </nav>

const App = () => (
  <Router>
    <div>
      <Links/>
      <Route exact path='/' component={() => <h1>Home</h1>}/>
      <Route path='/about' component={() => <h1>About</h1>}/>
      <Route replace path='/contact' component={() => <h1>Contact</h1>}/>
    </div>
  </Router>
)

export default App
```
