# Use URL Parameters with React Router v4
[Video](https://egghead.io/lessons/react-use-url-parameters-with-react-router-v4)

- ``:`` identifies an url parameter.

- ``?`` appended to an url parameter marks it as optional.

```js
import { BrowserRouter as Router, Route } from 'react-router-dom'

const App = () => (
  <Router>
    <div>
      <Route path='/:page?/:subpage?' render={({match}) => (
        <h1>
          PAGE: {match.params.page || 'Home'}<br/>
          SUBPAGE: {match.params.subpage}
        </h1>
      )}/>
    </div>
  </Router>
)

export default App
```
