# Render Multiple Components for the Same Route in React Router v4
[Video](https://egghead.io/lessons/react-rendering-multiple-components-for-the-same-route-in-react-router-v4)

By default, all matching routes are rendered.

```js
import { BrowserRouter as Router, Route, Link } from 'react-router-dom'

const Links = () =>
  <nav>
    <Link to='/home'>Home</Link>
    <Link to='/about'>About</Link>
  </nav>

const App = () => (
  <Router>
    <div>
      <Links/>
      <div className='header'>
        <Route path='/:page' render={({match}) => <h1>{match.params.page} header</h1>} />
      </div>
      <div className='content'>
        <Route path='/:page' render={({match}) => <p>{match.params.page} content</p>} />
      </div>
    </div>
  </Router>
)

export default App
```
