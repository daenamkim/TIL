# State Not Updated

When I tried codes as below, state in `updateClock()` never updated.
Through console.log I found currentTime was updated well and I don't know why.

```javascript
constructor(props) {
  super(props);
  this.state = this.getTime();
  this.setTimer();
}

getTime() {
  const currentTime = new Date();
  const hours = currentTime.getHours();
  const minutes = currentTime.getMinutes();
  const seconds = currentTime.getSeconds();

  return {
    currentTime: currentTime,
    hours: hours,
    minutes: minutes,
    seconds: seconds,
    ampm: hours >= 12 ? 'pm' : 'am'
  };
}

setTimer() {
  clearTimeout(this.timout);
  this.timeout = setTimeout(this.updateClock.bind(this), 1000);
}

updateClock() {
  const currentTime = new Date();
  this.setState({currentTime: currentTime}, this.setTimer);
}
```

So I fixed `updateClock()` and `getTime()` as below then worked!

```javascript
constructor(props) {
  super(props);
  this.state = this.getTime();
  this.setTimer();
}

getTime() {
  const currentTime = new Date();
  const hours = currentTime.getHours();
  const minutes = currentTime.getMinutes();
  const seconds = currentTime.getSeconds();

  return {
    hours: hours,
    minutes: minutes,
    seconds: seconds,
    ampm: hours >= 12 ? 'pm' : 'am'
  };
}

setTimer() {
  clearTimeout(this.timout);
  this.timeout = setTimeout(this.updateClock.bind(this), 1000);
}

updateClock() {
  this.setState(this.getTime, this.setTimer);
}
```
