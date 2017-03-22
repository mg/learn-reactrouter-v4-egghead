# Create Basic Routes with the React Router v4 BrowserRouter
[Video](https://egghead.io/lessons/react-create-basic-routes-with-the-react-router-v4-browserrouter)

- For web development, use ``react-router-dom``. DOM aware elements (BrowserRouter, Link) exists there, not in ``react-router`` proper.

- A **router** can only contain one child, need to wrap routes in a container element.

- ``exact``: A ``Route`` property. Match path exactly, e.g. ``/`` doesn't match ``/about``.

- ``strict``: A ``Route`` property. Be strict about how route ends, e.g. require an ending ``/``.

- Render functions are ``component``, ``render``, and ``children``. Render functions are passed various **React Router** props, such as ``match``, ``location``, etc.

- ``component``: A ``Route`` property. The **component** to render when route is matched.

- ``render``: A ``Route`` property. A function that should return the **JSX** to render when route is matched.

- ``children``: A ``Route`` property. A render function (a function that returns **JSX**) that will **always** run, even if the route does not match. If it does not match, the ``match`` property will not be passed into the function.

```js
import { BrowserRouter as Router, Route } from 'react-router-dom'

const Home = () => <h1>Home</h1>
const AboutStrict = () => <h1>About strict</h1>

const App = () => (
  <Router>
    <div>
      <Route exact path='/' component={Home}/>
      <Route strict path='/about/' component={AboutStrict}/>
      <Route path='/about' render={() => <h1>About</h1>}/>
      <Route path='/children' children=({match}) => match && <h3>Children</h3>}/>
    </div>
  </Router>
)

export default App
```
