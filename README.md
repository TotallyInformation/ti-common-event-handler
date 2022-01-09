# ti-common-event-handler

A common, shared event handler used across multiple TotallyInformation packages.
Implemented as a singleton class.

Uses the enhanced EventEmitter2 library for improved performance and support of wildcards

## Installation

```bash
npm install @totallyinformation/ti-common-event-handler
```

## Use as

```js
const tiEvents = require('@totallyinformation/ti-common-event-handler')

const aDataVar = {
    some: 'data'
}

tiEvents.emit('my-event-name', aDataVar)

// NB: Don't use arrow functions if you want to be able to access event name
tiEvents.on('my-event-name', function(data) {
    console.log(`Event ${this.event} triggered: `, data)
})
```

## Event name wildcards

`*` and `**` can be used as wildcards when creating event listeners. `**` will look down all sub-namespaces.

`/` is pre-configured as the namespace separator so as to match the equivalent in MQTT topics.

See the [EventEmitter2](https://github.com/EventEmitter2/EventEmitter2) node for details.

## Current usage

* [node-red-contrib-uibuilder](https://github.com/TotallyInformation/node-red-contrib-uibuilder)
* [node-red-contrib-events](https://github.com/TotallyInformation/node-red-contrib-events)

## Dependencies

* [EventEmitter2](https://github.com/EventEmitter2/EventEmitter2)
