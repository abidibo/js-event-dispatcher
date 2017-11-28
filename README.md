# EventDispatcher

A simple js event dispatcher written following the mediator pattern

## Install

    $ npm install --save eventdispatcher

## Usage

```js
    import EventDispatcher from 'eventdispatcher'

    let mycb = (evtName, param) => console.log(evtName, param)
    EventDispatcher.register('myEvent', mycb)

    EventDispatcher.emit('myEvent', 'lol') // logs 'myEvent', 'lol'

    EventDispatcher.unregister('myEvent', mycb)
```

## Methods

### register

Registers a function to an event

    register(evtName, callback, bind?)

| Param | Type | Description |
| evtName | String | just the event name |
| callback | Function | callback called when the evtName is emitted |
| bind | Object | The object to which will point this keyword inside the callback, if empty callback will binded to EventDispatcher object |

The callback will be called with the following parameters:

    callback(evtName, ...params)

Where `...params` may be injected by who emits the event

### unregister

Unregisters all functions from an event, or just the given one

    unregister(evtName, callback?)

| Param | Type | Description |
| evtName | String | the event name |
| callback | Function | if given only that callback will be unregistered |

### emit

Emits an event

    emit(evtvName, params?)

| Param | Type | Description |
| evtName | String | the event name |
| params | Mixed | other parameters that will be passed to the registered callbacks |

## Testing

Run tests with coverage report

    $ npm tun test

Update html report

    $ npm run coverage-html

