State
-----

> The state is the minimal representation of the data in your app.

Let's say you're building an app using the geolocation API. Your state tree might look like the following:
```
{
  location: [28.333, 71.221],
  hasLocation: true
}
```
It's quite easy to see that the `hasLocation` property is superfluous here, and any functionality that ever depended on it could just as easily use the `location` property instead. e.g., the check `hasLocation === true` could easily be replaced with something like `location === null`

If we remove the `hasLocation` property, the state of our application can be represented more succinctly, like so:
```
{
  location: [28.333, 71.221]
}
```
With this, everytime the user's location changes, we only need to update the location property while earlier we would've had to update both the location as well as the hasLocation keys. This is what we mean when we say that the state must always be the 'minimal' representation of your app's data.

### State should be immutable
