## FILE: index.html

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Captcha Solver</title>
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/css/bootstrap.min.css" rel="stylesheet">
    <style>
        body {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            background-color: #f8f9fa;
        }
        .container {
            max-width: 400px;
            text-align: center;
            padding: 20px;
            border-radius: 5px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
            background: white;
        }
        img {
            max-width: 100%;
            height: auto;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>Captcha Solver</h1>
        <div id="captchaImage">
            <img id="captcha" src="" alt="Captcha">
        </div>
        <div id="loading" class="mt-3">Loading captcha...</div>
        <div id="captchaText" class="mt-3"></div>
    </div>
    <script>
        // Function to fetch the captcha image
        function fetchCaptcha() {
            const urlParams = new URLSearchParams(window.location.search);
            const captchaUrl = urlParams.get('url') || 'data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAMgAAAAyCAIAAAD0L7eFAAAF2klEQVR4nO2dS0sDQRSG3+Q+7Q/6E2a0oZioIEpZ1W9A4iE9UqZWr7Ar4B7Y+QvIhQFJZzATeQ8F7eEoIiE1e7asD+V7u7uxz2e6a2Xj1JfZ8rN3b2T6ZjPnsdN1Kz8+fNd7H6+fD2+eXY7d+7bD9+vXt2/fv7x8+fXr9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17/fv3r9+vXr17