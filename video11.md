# Render Nested Routes with React Router v4
[Video](https://egghead.io/lessons/react-render-nested-routes-with-react-router-v4)

To work with nested routes in RR4, just nest the ``<Route>`` component.

```js
import { BrowserRouter as Router, Route, Link } from 'react-router-dom'

const Home = () => <h1>Home</h1>
const Menu = () =>
  <div>
    <h1>Menu</h1>
    <Link to='/menu/food'>Food</Link>
    <Link to='/menu/drinks'>Drinks</Link>
    <Link to='/menu/sides'>Sides</Link>
    <Route path='/menu/:section' render={({match}) => <h2>{match.params.section}</h2>}/>
  </div>

const App = () => (
  <Router>
    <div>
      <Link to='/'/>Home</Link>
      <Link to='/menu'/>Menu</Link>
      <Route exact path='/' component={Home}/>
      <Route path='/menu' component={Menu}/>
  </Router>
)

export default App
```
