<section align="center" style="display: flex; flex-direction: column">
  <h1>Emmy.js</h1>
  <div>
    <img alt="npm" src="https://img.shields.io/npm/dt/emmy-dom"/>
    <img alt="NPM" src="https://img.shields.io/npm/l/emmy-dom"/>
    <img alt="tests" src="https://github.com/emmyjs/emmy-dom/actions/workflows/vitest.yml/badge.svg"/>
  </div>
  <i>A tiny simple front-end library for building web applications.</i>
</section>
<hr />

## Why Emmy.js?
Emmy.js is a tiny simple front-end library for building web applications. It is based on the [Web Components](https://developer.mozilla.org/en-US/docs/Web/Web_Components) standard.
It is specially designed for building web applications with server-side frameworks like Ruby on Rails, Django, Laravel, etc.

<hr />

## _Experimental_ `npx create-emmy`
[create-emmy](https://www.npmjs.com/package/create-emmy) is a command line tool that allows you to create a new emmy.js project.
It is still in an experimental phase, so it is not recommended to use it in production, but you can try it out and give us your feedback. [More info](https://github.com/emmyjs/create-emmy#readme)

## Example: Counter
```javascript
import { load, html } from 'emmy-dom'

function Counter() {
  const [count, setCount] = this.useState(0)

  this.useEffect(() => {
    this.querySelector('#increment').addEventListener('click', () => {
      setCount(count() + 1)
    })
  }, ['didMount'])

  return () => html`
    <div>
      <h1>Count: ${count()}</h1>
      <button id='increment'>+</button>
    </div>
  `
}

load(Counter, 'Counter')
```
