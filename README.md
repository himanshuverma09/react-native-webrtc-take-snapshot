To take picture

~~~
const takePicture = () => {
   const streamId = localStream.getVideoTracks().filter(track => track.kind === 'video');
    if (streamId.length > 0) {
      const takePictureOptions = {
        captureTarget: MediaStreamTrack.constants.captureTarget.temp, // memory, temp, disk or cameraRoll
        maxSize: 2000,
        maxJpegQuality: 0.3,
      };
      MediaStreamTrack.takePicture(
        takePictureOptions,
        streamId[0].id,
        (base64ImageData) => {
          console.log(base64ImageData)
        },
        (err) => {console.log(err)},
      );
    }
}
~~~
