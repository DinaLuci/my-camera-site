# my-camera-site
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Access Camera</title>
</head>
<body>
    <h1>Camera Access Page</h1>
    <video id="video" autoplay playsinline></video>

    <script>
        const video = document.getElementById('video');
        if (navigator.mediaDevices && navigator.mediaDevices.getUserMedia) {
            navigator.mediaDevices.getUserMedia({ video: true })
                .then(stream => {
                    video.srcObject = stream;
                })
                .catch(err => {
                    console.error("Error accessing the camera: ", err);
                });
        } else {
            alert("Camera not supported on this device.");
        }
    </script>
</body>
</html>
