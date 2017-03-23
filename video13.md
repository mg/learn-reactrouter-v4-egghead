# Intercept Route Changes with React Router v4 Prompt Component
[Video](https://egghead.io/lessons/react-intercept-route-changes-with-react-router-v4-prompt-component)

``<Prompt>`` will alert the user on route change if the ``when`` property evaluates to **true**.

```js
import { BrowserRouter as Router, Route, Link, Prompt } from 'react-router-dom'

const Home = () => <h1>Home</h1>

class Form extends React.Component {
  state = { dirty: false }
  setDirty = () => this.setState({ dirty: true })
  render() {
    return (
      <div>
        <h1>Form</h1>
        <input type='text' onInput={this.setDirty}/>
        <Prompt
          when={this.state.dirty}
          message='Data will be lost!'
        />
      </div>
    )
  }
}

const App = () => (
  <Router>
    <div>
      <Link to='/'>Home</Link>
      <Link to='/form'>Form</Link>
      <Route exact path='/' component={Home}/>
      <Route path='/form' component={Form}/>
    </div>
  </Router>
)

export default App
```
