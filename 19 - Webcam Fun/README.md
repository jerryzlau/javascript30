# Notes 

## Browser-sync
install browser-sync on package.json to run server
usage:
```json
  "scripts": {
    "start": "browser-sync start --server --files \"*.css, *.html, *.js\""
  }
```

# How to get user video input
Using Promise: 
```javascript 
// grab video tag 
const video = document.querySelector('.player');

// get userMedia
function getVideo(){
  navigator.mediaDevices.getUserMedia({
    video: true,
    audio: false
  }).then(localMediaStream => {
    // translate media object into url so the video tag can read it
    video.src = window.URL.createObjectURL(localMediaStream);
    video.play();
  }).catch(err => {
    console.error('ERROR: ', err);
  });
}
```

Using async/await: 
```javascript
async function getVideo() {
  try{
    const mediaStream = await navigator.mediaDevices.getUserMedia({
      video: true,
      audio: false
    });
  
    video.src = window.URL.createObjectURL(mediaStream);
    video.play();
  }catch(err){
    // throw error if user doesn't give permission
    console.error('ERROR: ', err);
  }
}
```