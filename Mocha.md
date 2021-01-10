# Mocha

[11 Best JavaScript Unit Testing Framework and Tools](https://geekflare.com/javascript-unit-testing/)
[Mocha](https://mochajs.org/)

Mocha is a feature-rich JavaScript test framework running on Node.js and in the browser, making asynchronous testing simple and fun. Mocha tests run serially, allowing for flexible and accurate reporting, while mapping uncaught exceptions to the correct test cases.

## Why Mocha

`MochaJS` is the most popular testing framework for Javascript.

- Works for frontend as well as backend
- Support NodeJS debugger
- Provides a clean base to develop tests as per the developer’s convenience
- Supports any browser including headless Chrome library
- Supports object mocking to perform flexible backend tests

## Other tools

`Jasmine` is a user-behavior mimicker that allows you to perform test cases similar to user behavior on your website. Jasmine is useful for a testing frontend for visibility, click clarity as well as the responsiveness of the UI in different resolutions. Jasmine allows to automate user behavior with customs delays and wait time to simulate actual user behavior.

`JEST` is one of the most popular frameworks that is maintained regularly by Facebook. Single framework fit for NodeJS, VueJS, React, Angular and other Babel based projects.

`Karma` is a productive testing environment that supports all the popular test description framework within itself. It provides your application the support to execute tests in different environments. It has wide support for executing tests on different devices and applications.

`AVA` is a minimalistic light-weight testing framework that leverages asynchronous nature of Javascript. It is primarily focused on running tests for NodeJS based code.

`Tape` is pretty similar to AVA in its architecture. Clean light-weight footprint. Provides just bare-metal code and gives the developer complete freedom to write test cases.

`Cypress` is an exciting testing framework that practically runs on the browser. It provides an interactive UI on the browser in the form of a web page.

`Puppeteer` is an excellent test execution framework built by a team at Google. It provides a headless chrome API for NodeJS applications.
Puppeteer is primarily used for applications specific to the browser like crawl test, page structure test, take screenshots and even capture pre-rendered content for single page applications.

`ChaiJS` framework focuses on behavior-driven testing. It can be used in parallel with any other framework.

`Sinon.js` compliments the unit testing framework to fake/mock the real things.

A good alternative to Sinon would be `testdouble.js`.

`Supertest` is an abstraction to test HTTP requests. Can be combined to `Nock` (HTTP server mocking and expectations library) to test modules that perform HTTP requests in isolation.