# Collab Link SDK

Collab link is a realtime activity streamer for Clients and Node. Clients stay in sync with each other by reporting activities to an activity server, which processes activities and delivers notifications to subscribed clients.


## Communication

### listener({ url }) => EventEmitter

Takes an options object with source URL and optional dispatch function. Returns an EventEmitter. Emits `activity` events.


### transmitter({ url }) => transmit(activity)

Takes an options object with URL. Returns a `transmit()` function which takes an activity object and transmits it to the target.


### Activity Object


```js
{
  activityType: string, // e.g., 'commented', 'shared', 'liked', 'listened'
  subject: string,      // The id of the user responsible for the activity.
  object: string,       // The id of the object that the activity was performed on.
  activityId: string,
  timestamp: date,      // Epoch time
  currentTime: date,    // What time is it on the client right now?
                        // Required to sync times between client and server.
  clientID: clientID    // The client on which the activity was performed.
  data: object          // An object with activity details. The structure of the data
                        // is determined by the activityType.
}
```


### clientID

The clientID refers to an object like this:

```js
{
  name: string          // The name of the software
  version: string       // Software version
  host: string          // Browser, iOS, Android, Node, etc...
}
```
