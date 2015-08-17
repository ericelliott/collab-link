# Collab Link SDK

Collab link is a realtime activity streamer for Clients and Node.


## Communication

### listener({url, dispatch() = null}) => RxObservableObject

Takes an options object with source URL and optional dispatch function. Returns an RxObservable.


### transmitter({url}) => transmit({activityType, data})

Takes an options object with URL. Returns a `transmit()` function which takes an activity object and transmits it to the target.
