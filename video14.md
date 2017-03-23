# Understand the Difference Between the React Router v4 Router Types
[Video](https://egghead.io/lessons/react-understand-the-difference-between-the-react-router-v4-router-types)

- ``<BroswerRouter>``: For environments that support the HTML5 history API. If property ``forceRefresh`` evaluates to true it will force-rerender the whole applicaiton.

- ``<HashRouter>``: For older browser environments, uses the **#** notation for routes. Property ``hashType`` controls the notation (``slash`` (default), ``noslash``, ``hashbang``).

- ``<MemoryRouter>``: No URL bar, only keep location state in memory. Property ``initialEntries`` for initial history stack, ``initialIndex`` for starting position in the stack.

- ``<StaticRouter>``: For SSR. Property ``location`` to set location, ``context`` to represent the URL the server would have received.

- ``<NativeRouter>``: For React Native.

```js
import { BrowserRouter, HashRouter, MemoryRouter, StaticRouter, NativeRouter, Route, Link, Prompt } from 'react-router-dom'

const LinksRoutes = () =>
  <div>
    <Link to='/'>Home</Link>
    <Link to='/about'>About</Link>
    <Route exact path='/' render={() => <h1>Home</h1>}/>
    <Route path='/about' render={() => <h1>About</h1>}/>
  </div>


const BrowserRouterApp = () =>
  <BrowserRouter forceRefresh={() => false}>
    <LinksRoutes/>
  </BrowserRouter>

const HashRouterApp = () =>
  <HashRouter>
    <LinksRoutes/>
  </HashRouter>

const MemoryRouterApp = () =>
  <MemoryRouter
    initialEntries={['/', '/about']}
    initialIndex={1}
  >
    <LinksRoutes/>
  </MemoryRouter>

const StaticRouterApp = () =>
  <StaticRouter location='/about' context={{}}>
    <LinksRoutes/>
  </StaticRouter>

export default App
```
