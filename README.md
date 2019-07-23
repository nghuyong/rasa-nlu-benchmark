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
- Size(train/test)
- Intent/Entity Nums
- Link (Website Or Paper)

|Name|Language|Task|Size(Train/Test)|Intent/Entity Nums|Link|
|:----:|:----:|:----:|:----:|:----:|:----:|
|ATIS|en|Airline Travel Information|4978/893|26/129|[more detail](https://www.kaggle.com/siddhadev/atis-dataset)|
|Snips|en|7 intents, including:AddToPlaylist, BookRestaurant...|13802/699|7/72|[more detail](https://github.com/snipsco/nlu-benchmark)|
|SMP2019|zh|29 domains, including: app, email...|2063/480|24/62| [more detail](http://conference.cipsc.org.cn/smp2019/evaluation.html) |

Note:
- For the SMP2019 dataset, the official does not divide the training set and test set, we have divided according to 8:2 by ourselves.

<h2 align="center">Benchmark</h2>

### Baseline Pipeline
- For English dataset, we use official [`pretrained_embeddings_spacy`](https://rasa.com/docs/rasa/nlu/choosing-a-pipeline/#pretrained-embeddings-spacy) and [`supervised_embeddings`](https://rasa.com/docs/rasa/nlu/choosing-a-pipeline/#pretrained-embeddings-spacy) as baseline NLU pipeline.
- For Chinese dataset, we use officially recommended Chinese pipeline [`rasa_nlu_chi`](http://www.crownpku.com/2017/07/27/%E7%94%A8Rasa_NLU%E6%9E%84%E5%BB%BA%E8%87%AA%E5%B7%B1%E7%9A%84%E4%B8%AD%E6%96%87NLU%E7%B3%BB%E7%BB%9F.html) as baseline NLU pipeline.

### Result

<table>
   <tr>
      <td rowspan="2" align="center"><b>Dataset</b></td>
      <td rowspan="2" align="center"><b>NLU Pipeline</b></td>
      <td colspan="4" align="center"><b>Intent Classification</b></td>
      <td colspan="4" align="center"><b>Entity Extraction</b></td>
   </tr>
   <tr>
      <td align="center"><b>auc</b></td>
      <td align="center"><b>p</b></td>
      <td align="center"><b>r</b></td>
      <td align="center"><b>f1</b></td>
      <td align="center"><b>auc</b></td>
      <td align="center"><b>p</b></td>
      <td align="center"><b>r</b></td>
      <td align="center"><b>f1</b></td>
   </tr>
   <tr>
      <td rowspan="2">ATIS(en)</td>
      <td >pretrained_embeddings_spacy</td>
      <td>0.91</td>
      <td>0.91</td>
      <td>0.91</td>
      <td>0.91</td>
      <td>0.98</td>
      <td>0.98</td>
      <td>0.98</td>
      <td>0.98</td>
   </tr>
   <tr>
      <td >supervised_embeddings</td>
      <td>1.00</td>
      <td>1.00</td>
      <td>1.00</td>
      <td>1.00</td>
      <td>0.98</td>
      <td>0.98</td>
      <td>0.98</td>
      <td>0.98</td>
   </tr>
   <tr>
      <td rowspan="2">Snips(en)</td>
      <td >pretrained_embeddings_spacy</td>
      <td>0.98</td>
      <td>0.98</td>
      <td>0.98</td>
      <td>0.98</td>
      <td>0.98</td>
      <td>0.98</td>
      <td>0.98</td>
      <td>0.98</td>
   </tr>
   <tr>
      <td >supervised_embeddings</td>
      <td>0.98</td>
      <td>0.98</td>
      <td>0.98</td>
      <td>0.98</td>
      <td>0.98</td>
      <td>0.98</td>
      <td>0.98</td>
      <td>0.98</td>
   </tr>
   <tr>
      <td>SMP2019(zh)</td>
      <td >rasa_nlu_chi</td>
      <td>0.76</td>
      <td>0.83</td>
      <td>0.76</td>
      <td>0.78</td>
      <td>0.79</td>
      <td>0.80</td>
      <td>0.79</td>
      <td>0.77</td>
   </tr>
</table>
