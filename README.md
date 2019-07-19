<h1 align="center">rasa-nlu-benchmark</h1>
<p align="center">Collection of dataset and corresponding benchmark for Rasa NLU</p>

<p align="center">
  <a href="https://github.com/nghuyong/rasa-nlu-benchmark/stargazers">
    <img src="https://img.shields.io/github/stars/nghuyong/rasa-nlu-benchmark.svg?colorA=orange&colorB=orange&logo=github"
         alt="GitHub stars">
  </a>
  <a href="https://github.com/nghuyong/rasa-nlu-benchmark/issues">
        <img src="https://img.shields.io/github/issues/nghuyong/rasa-nlu-benchmark.svg"
             alt="GitHub issues">
  </a>
  <a href="https://github.com/nghuyong/rasa-nlu-benchmark/">
        <img src="https://img.shields.io/github/last-commit/nghuyong/rasa-nlu-benchmark.svg">
  </a>
  <a href="https://github.com/nghuyong/rasa-nlu-benchmark/blob/master/LICENSE">
        <img src="https://img.shields.io/github/license/nghuyong/rasa-nlu-benchmark.svg"
             alt="GitHub license">
  </a>
</p>

<h2 align="center">Introduction</h2>

[Rasa NLU](https://rasa.com/docs/rasa/nlu/about/) is a powerful and open-source natural language processing tool for intent classification and entity extraction in chatbots.

However, we found that there is no published public dataset and the corresponding benchmark.
This makes it difficult to evaluate the performance of our own NLU system built by Rasa.

Therefore, this project aims to collect and organize datasets and baselines for Task-Oriented Dialogue, which will be in the [data format](https://rasa.com/docs/rasa/nlu/training-data-format/) required by Rasa NLU and you can
directly use them in your Rasa NLU system.



<h2 align="center">Datasets</h2>

**All the datasets have been organized and archived in the [`data`](https://github.com/nghuyong/rasa-nlu-benchmark/blob/master/data) directory**

Following information is included for each dataset:
- Name
- Language
- Task
- Size & Stats
- Intent & Entity nums
- Description & Link (Website Or Paper)

|Name|Language|Task|Size|Intent & Entity nums|Description & Link|
|:----:|:----:|:----:|:----:|:----:|:----:|
|ATIS|en|Airline Travel Information|train(4978)+test(893)+val(500)|26 intent, 129 slot labels|https://www.kaggle.com/siddhadev/atis-dataset
|Snips|en|rasa|train(13802)+val(699)|7 intent 72 slot labels|
|SMP2019|ch|29 domains:app, email, radio, bus, train, cinemas, telephone, contacts, cookbook, epg, flight, health, match, novel, poetry, riddle, stock, video, weather, lottery, story, map, message, music, news, tvchannel, translation, website, joke.|train(2579)|24 intent, 62 slot labels| For rasa natural language understanding
