# Style a Link that is Active with NavLink in React Router v4
[Video](https://egghead.io/lessons/react-styling-a-link-that-is-active-with-navlink-in-react-router-4)

- ``<NavLink>`` is an extends version of ``<Link>``

- Allows us to identify the current route and decide if link should have an active state.

- ``activeClassName`` sets a class on the link if the link is active.

- ``activeStyle`` adds an inline style to the link if it is active.

- ``exact`` is needed to better control when active class should be set.

- ``isActive`` accepts a function to better control the active state.

```js
import { BrowserRouter as Router, Route, NavLink } from 'react-router-dom'

const isActiveFunc = (match, location) => match

const Links = () =>
  <nav>
    <NavLink exact activeClassName='active' to='/'>Home</NavLink>
    <NavLink activeStyle={{color: 'green'}} to='/about'>About</NavLink>
    <NavLink isActive={isActiveFunc} activeClassName='active' to='/contact'>Contact</NavLink>
  </nav>

const App = () => (
  <Router>
    <div>
      <Links/>
      <Route exact path='/' component={() => <h1>Home</h1>}/>
      <Route path='/about' component={() => <h1>About</h1>}/>
      <Route path='/contact' component={() => <h1>Contact</h1>}/>
    </div>
  </Router>
)

export default App
```
