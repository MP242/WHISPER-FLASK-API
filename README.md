<!-- Improved compatibility of back to top link: See: https://github.com/othneildrew/Best-README-Template/pull/73 -->
<a name="readme-top"></a>
<!-- PROJECT LOGO -->
<br />
<div align="center">
  <!-- <a href="https://austral-energie.com/">
    <img src="./public/austral_groupe_nergie_logo.jpeg" alt="Logo" width="80" height="80">
  </a> -->

  <h3 align="center">Run your local Whisper model with a Flask API</h3>

  <p align="center">
    Enhance your user experience by integrating speech-to-text capabilities into your application.
    <br />
    <a href="https://github.com/MP242/WHISPER-FLASK-API"><strong>Explore the documentation</strong></a>
    <br />
    <br />
    <a href="https://github.com/MP242/WHISPER-FLASK-API">See demo</a>
    ·
    <a href="https://github.com/MP242/WHISPER-FLASK-API/issues">Report a Bug</a>
    ·
    <a href="https://github.com/MP242/WHISPER-FLASK-API/issues">Ask a feature</a>
  </p>
</div>



<!-- TABLE OF CONTENTS -->
<details>
  <summary>Table of Contents</summary>
  <ol>
    <li>
      <a href="#about-the-project">About this project</a>
      <ul>
        <li><a href="#built-with">Built with</a></li>
      </ul>
    </li>
    <li>
      <a href="#getting-started">To get started</a>
      <ul>
        <li><a href="#prerequisites">Prerequisites</a></li>
        <li><a href="#installation">Installation</a></li>
      </ul>
    </li>
    <li><a href="#usage">Usage</a></li>
    <li><a href="#contact">Contact</a></li>
  </ol>
</details>



<!-- ABOUT THE PROJECT -->
## About this project

<br>
Whisper, an advanced automatic speech recognition system developed by OpenAI, stands out due to its open-source nature, despite being a product of OpenAI. Built on 680,000 hours of diverse, multilingual, and multitask supervised data from the web, Whisper demonstrates exceptional accuracy in speech recognition across various accents, in the presence of background noise, and with technical language. It not only supports robust transcription in numerous languages but also offers translation of these transcriptions into English. To harness this potent technology for web application enhancement, we've developed a Flask API that encapsulates Whisper's features, facilitating easy integration and communication with your web applications.

### Built with

This project was developed using several key technologies in the fields of artificial intelligence and web development:

* [Flask](https://flask.palletsprojects.com/en/3.0.x/)
* [Docker](https://docs.docker.com/)
* [Whisper](https://github.com/openai/whisper/)

<p align="right">(<a href="#readme-top">Back to top</a>)</p>



<!-- GETTING STARTED -->
## To get started

To set up the project locally, follow these simple instructions.

### Prerequisites

* Install docker
  ```sh
  brew install docker
  ```

### Installation

1. Clone the repo
   ```sh
   git clone https://github.com/MP242/WHISPER-FLASK-API.git
   ```
1. Docker - image
    ```sh
    docker build -t whisper-api .
    ```
2. Docker - run server
    ```sh
    docker run -p 5000:5000 whisper-api
    ```

<p align="right">(<a href="#readme-top">back to top</a>)</p>

<!-- USAGE EXAMPLES -->
## Route

This Flask API offers two primary routes for easy interaction:

1. GET Request to the Root Path
- Route: GET "/"
- Action: Returns a simple Hello World message.
```sh
fetch('http://localhost:5000/')
    .then(response => response.text())
    .then(data => console.log(data));
```
Response :
```sh
"Hello World"
```


2. POST Request for Speech-to-Text Conversion
- Route: POST "/whisper"
- Input: Form data with an audio file included under the key "file".
- Action: Processes the provided audio file through the Whisper model to perform speech-to-text conversion.

```sh
    // Assuming you have a File object or Blob representing the audio file
    const audioFile = document.querySelector('input[type="file"]').files[0];
    const formData = new FormData();
    formData.append("file", audioFile, "audio.wav");

    fetch('http://localhost:5000/whisper', {
    method: "POST",
    body: formData
    })
    .then(response => response.json())
    .then(data => console.log(data.text));
```

Expected Response:

```sh
  results:[{ "filename":"audio.wav","transcript": "The transcribed text from your audio file." }]
```

These routes enable straightforward interaction with the speech-to-text capabilities provided by the Whisper model through your Flask API. The examples demonstrate how to make requests using JavaScript, facilitating integration into web applications.


<p align="right">(<a href="#readme-top">back to top</a>)</p>

<!-- ROADMAP -->
## Roadmap

- to be defined

<p align="right">(<a href="#readme-top">back to top</a>)</p>

<!-- CONTACT -->
## Contact

Marc POLLET - [@Marc_linkedin](https://www.linkedin.com/in/marcpollet242/) - marc.pollet242@gmail.com

Project Link: [https://github.com/MP242/vocal-chat](https://github.com/MP242/vocal-chat)

<p align="right">(<a href="#readme-top">back to top</a>)</p>
