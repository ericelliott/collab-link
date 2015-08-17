# Activity Formats

For most apps, a format such as the [W3C Activity Streams 2.0 Draft](http://www.w3.org/TR/activitystreams-core/) may be suitable. We'll base our vocabulary loosely on the [W3C Activity Streams vocabulary](http://www.w3.org/ns/activitystreams), but we'll simplify the format as much as possible to make it easy (preferably trivial) to implement clients.

We may deviate from the Activity Streams spec to simplify client implementations.


## Activity Object

The activity object is the data that gets transfered over the wire to inform a client about an activity. Note that this data may be transfered in the form of an array of activities, or it could be streamed one object at a time.

```js
{
  activityId: string,
  activityName: string,   // Past-tense verb for the activity:
                          // e.g., 'commented', 'shared', 'liked', 'listened'
  actor: {
    id: string,           // The id of the user responsible for the activity.
    displayName: string,  // The displayable name of the actor.
    thumbnail: string,    // The URL of a thumbnail image for visual representation.
  },
  target: {
    id: string,           // The id of the object that the activity was performed on.
    displayName: string,  // The displayable name of the object being acted on.
    thumbnail: string,    // The URL of a thumbnail image for visual representation.
  },
  timestamp: dateTime,    // http://www.w3.org/TR/xmlschema-2/#dateTime e.g. 2015-12-11T12:34:56Z
  currentTime: dateTime,  // What time is it on the client right now?
                          // Required to sync times between client and server.
  clientID: clientID,     // The client on which the activity was performed.
  data: object            // An object with activity details. The structure of the data
                          // is determined by the activityType.
}
```


## clientID

The clientID refers to an object like this:

```js
{
  name: string,         // The name of the software
  version: string,      // Software version
  host: string          // Browser, iOS, Android, Node, etc...
}
```
