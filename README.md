# TheIndra55/Audioclient
A Minecraft audioclient which implements their own protocol over websockets. 

## Status
This project is currently not maintained, the code should be enough to make a working audioclient. It's only in lack of commands and a webinterface.

## Javascript implementation
There's a current javascript implementation which can be linked from your webpage in `Audioclient/Web/js/Audioclient.js` you can simply use the following code to listen for all "play" packages

```js
// construct a new audioclient object
var ac = new Audioclient("ws://localhost")

// listen for the play package and output the message (url if implemented right)
ac.on("play", function(message){
  console.log(message);
})
		
// we have to send a handshake with the playername before we will receive anything from the server
ac.ws.onopen = function() { 
  ac.send("handshake", "Steve")
}
```
