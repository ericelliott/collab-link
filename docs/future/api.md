# Collab Link API

Collab link is a realtime activity streamer for Clients and Node. Clients stay in sync with each other by reporting activities to an activity server, which processes activities and delivers notifications to subscribed clients.


## Communication

### listener({ url = null, eventSource = EventSource }) => ActivityListener

Takes an options object with an optional source URL. Returns an ActivityListener, which emits `activity` events.

By default, `listener()` uses the [EventSource API](https://developer.mozilla.org/en-US/docs/Web/API/Server-sent_events/Using_server-sent_events) if it's available. You can override that behavior by passing in an `eventSource` option. If you leave out the URL, you can trigger events manually by calling `EventEmitter.emit()` on the returned object.

#### ActivityListener Events

The ActivityListener is a node EventListener. It emits the following events:

* `connected`
* `error`


### transmitter({ url }) => transmit(activity)

Takes an options object with URL. Returns a `transmit()` function which takes an activity object and transmits it to the target.


## See Also

[Object formats](https://github.com/ericelliott/collab-link/blob/master/docs/future/activity-formats.md).
