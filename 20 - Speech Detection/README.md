# Notes 

## Speech Recognition

```javascript 
// grabs the browser native speech recognition function
window.SpeechRecognition = window.SpeechRecognition || window.webkitSpeechRecognition;

// create a speech recognition object 
const recognition = new SpeechRecognition();
// this will return all the possible results in between speech analysis 
recognition.interimResults = false;

// now we can addEventLisenter to it to get the speech
recognition.addEventListener('result', e => {
  // the event will contain nested object which has the speech result,
  // we need to get to the transcript level and join them into a string
  const transcript = Array.from(e.results)
    .map(result => result[0])
    .map(result => result.transcript)
    .join(' ');

  // possible usage, hypothetically: 
  // call uber to sfo airport 
  if(transcript.includes('call uber') && transcript.includes('address')){
    const address = transcript.split(' to ')[1];
    callUber(userInfo, address);
  }

});

```