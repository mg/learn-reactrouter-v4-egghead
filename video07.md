# Parse Query Parameters in React Router v4
[Video](https://egghead.io/lessons/react-parsing-query-parameters-in-react-router-v4)

- ``location.search`` contains the query string, ``location.pathname`` contains the path. React Router does not provide functionality to parse the search string.

- ``URLSearchParams`` is an upcoming browser standard to parse query strings.

```js
import { BrowserRouter as Router, Route, Link } from 'react-router-dom'

const Links = () =>
  <nav>
    <Link to='/?id=123'>Inline</Link>
    <Link to={{pathname: '/', search:'id=456'}}>Object</Link>
  </nav>

const App = () => (
  <Router>
    <div>
      <Links/>
      <Route path='/' render={({match, location}) => (
        <div>
          <p>root</p>
          <p>{new URLSearchParams(location.search).get('id')}</p>
        </div>
      )}/>
    </div>
  </Router>
)

export default App
```
