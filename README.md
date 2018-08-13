# Spoken-SQuAD : A spoken question answering dataset on SQuAD

This repository contains dataset for the paper:
> Spoken SQuAD: A Study of Mitigating the Impact of Speech Recognition Errors on Listening Comprehension

> Chia-Hsuan Li, Szu-Lin Wu, Chi-Liang Liu and Hung-yi Lee

https://arxiv.org/abs/1804.00320
accepted by Interspeech 2018 as an Oral paper.

If you have any questions and suggestions, feel free to contact **chiahsuan.li@gmail.com**

# Introduction
Reading comprehension has been widely studied. One of the most representative reading comprehension tasks is Stanford Question Answering Dataset ([SQuAD](https://arxiv.org/abs/1606.05250)), on which machine is already comparable with human. On the other hand, accessing large collections of multimedia or spoken content is much more difficult and time-consuming than plain text content for humans. It’s therefore highly attractive to develop machines
which can automatically understand spoken content. Hence, we propose a new listening comprehension task - SpokenSQuAD.

# Corpus Description
In SpokenSQuAD, the document is in spoken form, the input question is in the form of text and the answer to each question is always a span in the document. We conducted the following procedures to generate spoken documents from the original SQuAD dataset. First, we used Google text-to-speech system to generate the spoken version of the articles in SQuAD. Then we utilized CMU Sphinx to generate the corresponding ASR transcriptions. In this study, we left the questions in the text form. We used SQuAD training set to generate the training set of Spoken SQuAD, and SQuAD development set was used to generate the testing set for Spoken SQuAD. If the answer of a question did not exist in the ASR transcriptions of the associated article, we removed the question-answer pair from the dataset because these examples are too difficult for listening comprehension machine at this stage. 

In example (A), the original answer Coldplay is recognized as called play and therefore it is not presented in SpokenSQuAD. And example (B) is a selected example in SpokenSQuAD.     
![alt text](https://github.com/chiahsuan156/Spoken-SQuAD/blob/master/example.png)

In this way, we collected 37,111 question answer pairs as the training set (Word Error Rate 22.77%) and 5,351 as the testing set (Word Error Rate 22.73%).

To test the comprehension ability of machine in real life scenario under worse audio quality, we further added two different levels of white noise into the audio files of testing set to obtain different WERs.

| Testing Set   | No noise      | Noise V1  | Noise V2  |
| ------------- |:-------------:| :--------:| :--------:|
| WER(%)        | 22.73         |44.22      | 54.82     |

# Citation
If you use the dataset in your work, please cite the following paper as:

```
@article{li2018spoken,
  title={Spoken SQuAD: A Study of Mitigating the Impact of Speech Recognition Errors on Listening Comprehension},
  author={Li, Chia-Hsuan and Wu, Szu-Lin and Liu, Chi-Liang and Lee, Hung-yi},
  journal={arXiv preprint arXiv:1804.00320},
  year={2018}
}
```

