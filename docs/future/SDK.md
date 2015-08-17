# Collab Link SDK

Collab link is a realtime activity streamer for Clients and Node. Clients stay in sync with each other by reporting activities to an activity server, which processes activities and delivers notifications to subscribed clients.


## Communication

### listener({ url }) => EventEmitter

Takes an options object with source URL and optional dispatch function. Returns an EventEmitter. Emits `activity` events.


### transmitter({ url }) => transmit(activity)

Takes an options object with URL. Returns a `transmit()` function which takes an activity object and transmits it to the target.


## See Also

[Object formats](https://github.com/ericelliott/collab-link/blob/master/docs/future/activity-formats.md).
