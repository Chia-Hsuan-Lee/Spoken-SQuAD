# Spoken-SQuAD : A spoken question answering dataset on SQuAD

This repository contains dataset for [Spoken SQuAD: A Study of Mitigating the Impact of Speech Recognition Errors on Listening Comprehension](https://www.isca-speech.org/archive/Interspeech_2018/pdfs/1714.pdf), the first large-scale spoken question answering dataset.

[**Introduction**](#Introduction) | [**Corpus Description**](#Corpus-Description) | [**Paper**](https://www.isca-speech.org/archive/Interspeech_2018/pdfs/1714.pdf) | [**Audio Download Link**](https://dbqapublic.blob.core.windows.net/dbqa/kaggle-dbqa-20210726.zip) | [**Existing Models**](#Existing-Models) | [**Citation**](#Citation-and-Contact)

## Introduction
Reading comprehension has been widely studied. One of the most representative reading comprehension tasks is Stanford Question Answering Dataset ([SQuAD](https://arxiv.org/abs/1606.05250)), on which machine is already comparable with human. On the other hand, accessing large collections of multimedia or spoken content is much more difficult and time-consuming than plain text content for humans. It’s therefore highly attractive to develop machines
which can automatically understand spoken content. Hence, we propose a new listening comprehension task - SpokenSQuAD.

## Corpus Description
In SpokenSQuAD, the document is in spoken form, the input question is in the form of text and the answer to each question is always a span in the document. We conducted the following procedures to generate spoken documents from the original SQuAD dataset. First, we used Google text-to-speech system to generate the spoken version of the articles in SQuAD. Then we utilized CMU Sphinx to generate the corresponding ASR transcriptions. In this study, we left the questions in the text form. We used SQuAD training set to generate the training set of Spoken SQuAD, and SQuAD development set was used to generate the testing set for Spoken SQuAD. If the answer of a question did not exist in the ASR transcriptions of the associated article, we removed the question-answer pair from the dataset.
  
![alt text](https://github.com/chiahsuan156/Spoken-SQuAD/blob/master/example.png)

In this way, we collected 37,111 question answer pairs as the training set (Word Error Rate 22.77%) and 5,351 as the testing set (Word Error Rate 22.73%).

To test the comprehension ability of machine in real life scenario under worse audio quality, we further added two different levels of white noise into the audio files of testing set to obtain different WERs.

| Testing Set   | No noise      | Noise V1  | Noise V2  |
| ------------- |:-------------:| :--------:| :--------:|
| WER(%)        | 22.73         |44.22      | 54.82     |

We also provide the original audio files that were generated by the Google TTS
system. To dowload the audio files of training set and dev set, run the
following script:

## Existing Models
Evaluation metric: F1 on the test set

|                                                                |  F1. on test set  |  AOS  |
|:--------------------------------------------------------------:|:------------------:|
|  [Lee et al. (2019)](https://www.isca-speech.org/archive/Interspeech_2018/pdfs/1714.pdf)  |         58.71       |         38.46       |
|     [Lee et al. (2019)](https://arxiv.org/pdf/1904.07904.pdf)    |         63.11       |                |
|     [Chuang et al. (2019)](https://www.isca-speech.org/archive_v0/Interspeech_2020/pdfs/1570.pdf)     |          71.75       |                |
|     [Su et al. (2020)](https://ieeexplore.ieee.org/document/9053979)    |          77.67       |                |
|     [Chung et al. (2020)](https://arxiv.org/abs/2010.02295)    |          77.67       |         65.90       |

```
sh download_audio.sh
```
Each wav file is indexed by the format
"TopicIndex_ParagraphIndex_SentenceIndex.wav" which follows the structure in the
[SQuAD json file](https://github.com/rajpurkar/SQuAD-explorer/blob/master/dataset/dev-v1.1.json).
-- **Warning:** this is a ~50GB download!


## Citation and Contact
If you use the dataset in your work, please cite the following paper as:

```bib
@article{lee2018spoken,
  title={Spoken SQuAD: A Study of Mitigating the Impact of Speech Recognition Errors on Listening Comprehension},
  author={Lee, Chia-Hsuan and Wu, Szu-Lin and Liu, Chi-Liang and Lee, Hung-yi},
  journal={Proc. Interspeech 2018},
  pages={3459--3463},
  year={2018}
}
```
Please contact Chia-Hsuan Lee (chiahlee[at]uw.edu) for questions and suggestions.
