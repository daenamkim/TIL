# Note React render() and socket.io

When I tried send and receive a message through socket.io with React, I got a problem on state update.

## **PROBLEM**

---

```javascript
...
class App extends Component {
  ...
  render() {
    // ===== HERE =====
    // In this case, "socket.on()" is called many times because of "reder()".
    // As of now I don't know why.
    socket.on('newMessage', (message) => this.setState(
      // Append a new message.
      (prevState) => ({ messages: [...prevState.messages, message] })
    ))

    return (
      <div style={{ textAlign: "center"}}>
        ...
        <p>
          <input type="text" autoComplete="off" ref="chatMessage" />
          <button onClick={ () => this.sendMessage() }>Send</button>
        </p>
        <ul>
          { this.state.messages.map((i) => <li key={ Math.random() }>{ i }</li>) }
        </ul>
      </div>
    );
  }
}
```

## **SOLUTION**

---

```javascript
...
class App extends Component {
  ...
  componentDidMount() {
    ...    
    // ===== HERE =====
    socket.on('newMessage', (message) => this.setState(
      // Append a new message.
      (prevState) => ({ messages: [...prevState.messages, message] })
    ))
  }

  render() {
    return (
      <div style={{ textAlign: "center"}}>
        ...
        <p>
          <input type="text" autoComplete="off" ref="chatMessage" />
          <button onClick={ () => this.sendMessage() }>Send</button>
        </p>
        <ul>
          { this.state.messages.map((i) => <li key={ Math.random() }>{ i }</li>) }
        </ul>
      </div>
    );
  }
}
```