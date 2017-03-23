# Use Regular Expressions with Routes with React Router v4
[Video](https://egghead.io/lessons/react-use-regular-expressions-with-routes-with-react-router-v4)

Add a regular expression to a route parameter to further validate routes.

```js
import { BrowserRouter as Router, Route } from 'react-router-dom'

const App = () => (
  <Router>
    <div>
      <Route path='/:a(\d+)/:b' render={({match}) => (
        <h1>
          paramA: {match.params.a}<br/>
          paramB: {match.params.b}
        </h1>
      )}/>
    </div>
  </Router>
)

export default App
```
