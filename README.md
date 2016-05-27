# React Router Native [![CircleCI](https://img.shields.io/circleci/project/jmurzy/react-router-native.svg)](https://circleci.com/gh/jmurzy/react-router-native) [![npm version](https://img.shields.io/npm/v/react-router-native.svg?style=flat-square)](https://www.npmjs.com/package/react-router-native) [![npm](https://img.shields.io/npm/l/react-router-native.svg)](https://github.com/jmurzy/react-router-native/blob/master/LICENSE.md) [![Discord Channel](https://img.shields.io/badge/discord-react--router@reactiflux-738bd7.svg?style=flat-square)](https://discord.gg/0ZcbPKXt5bYaNQ46)

A routing library for [React Native](https://github.com/facebook/react-native) that strives for sensible API parity with [react-router](https://github.com/reactjs/react-router/).

<img align="right" width="360px" src="https://raw.githubusercontent.com/jmurzy/react-router-native/master/docs/screenshot.gif">

### Questions?
Feedback is appreciated, but please keep in mind that the project contains components that are currently under [active](https://github.com/facebook/react-native/commits?author=ericvicenti) [development](https://github.com/facebook/react-native/commits?author=hedgerwang) and considered experimental. Documentation is still a work-in-progress, and pull requests are accepted gratefully!

Feel free to reach out to me on Twitter [@jmurzy](https://twitter.com/jmurzy). If you have any questions, please submit an Issue with the "question" tag or come hang out in the React Router [Reactiflux Channel](https://discord.gg/0ZcbPKXt5bYaNQ46) and post your request there.

### Platform Support

React Router Native is cross-platform. It supports all platforms that [NavigationExperimental](https://github.com/ericvicenti/navigation-rfc) supports.

### Installation

Using [npm](https://www.npmjs.com/):

```sh
$ npm install --save react-router react-router-native
```
### Usage

```javascript
import { Router, Route, render } from 'react-router-native';

const APP_KEY = 'app'

const App = (props) => (/*...*/);
const About = (props) => (/*...*/);
const AboutHeader = (props) => (/*...*/);
const Users = (props) => (/*...*/);
const User = (props) => (/*...*/);
const UserHeader = (props) => (/*...*/);
const NoMatch = (props) => (/*...*/);

render((
  /* Address Bar can be toggled on or off by setting the addressBar prop */
  <Router addressBar>
    <TabsRoute
      path="app"
      component={App}
      transition="horizontal-pager"
    >
      <Route path="/" component={About} overlayComponent={AboutHeader}/>
      <Route path="users" component={Users} overlayComponent={UserHeader}>
        <Route path="/user/:userId" component={User}/>
      </Route>
      <Route path="*" component={NoMatch}/>
    </TabsRoute>
  </Router>
), APP_KEY);
```

### Thanks

React Router Native is based on [React Router](https://github.com/reactjs/react-router). Thanks to Ryan Florence [@ryanflorence](https://twitter.com/ryanflorence), Michael Jackson [@mjackson](https://twitter.com/mjackson) and all the contributors for their work on [react-router](https://github.com/reactjs/react-router) and [history](https://github.com/mjackson/history).

Special thanks to Eric Vicenti [@ericvicenti](https://twitter.com/ericvicenti) and Hedger Wang [@hedgerwang](https://twitter.com/hedgerwang) for their work on [NavigationExperimental](https://github.com/ericvicenti/navigation-rfc).
