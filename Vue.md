# Vue

## Getting started

Set up a proxy for backend

- [http-proxy-middleware](https://github.com/chimurai/http-proxy-middleware)
- [Proxy requests to a separate backend server with vue-cli](https://stackoverflow.com/questions/40315451/proxy-requests-to-a-separate-backend-server-with-vue-cli)

## Drop target

[Mozilla > Specifying Drop Targets](https://developer.mozilla.org/en-US/docs/Web/API/HTML_Drag_and_Drop_API/Drag_operations#droptargets)

In order to make the div a drop target, the div's dragenter and dragover events must be canceled. You can invoke Event.preventDefault() on those events with the .prevent event modifier:

```html
<div @drop="dropLink" @dragenter.prevent @dragover.prevent></div>
```