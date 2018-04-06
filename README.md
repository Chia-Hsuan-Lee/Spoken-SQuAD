# Spoken-SQuAD : A spoken question answering dataset on SQUAD
This repository contains dataset for the paper:
> Spoken SQuAD: A Study of Mitigating the Impact of Speech Recognition Errors on Listening Comprehension
> Chia-Hsuan Li, Szu-Lin Wu, Chi-Liang Liu and Hung-yi Lee
https://arxiv.org/abs/1804.00320

# Introduction
Reading comprehension has been widely studied. One of the most representative reading comprehension tasks is Stanford Question Answering Dataset (SQuAD), on which machine is already comparable with human. On the other hand, accessing large collections of multimedia or spoken content is much more difficult and time-consuming than plain text content for humans. It’s therefore highly attractive to develop machines
which can automatically understand spoken content. Hence, we propose a new listening comprehension task - SpokenSQuAD.

# Corpus Description
In SpokenSQuAD, the document is in spoken form, the input question is in the form of text and the answer to each question is always a span in the document. We conducted the following procedures to generate spoken documents from the original SQuAD dataset. First, we used Google text-to-speech system to generate the spoken version of the articles in SQuAD. Then we utilized CMU Sphinx to generate the corresponding ASR transcriptions. In this study, we left the questions in the text form. We used SQuAD training set to generate the training set of Spoken SQuAD, and SQuAD development set was used to generate the testing set for Spoken SQuAD. If the answer of a question did not exist in the ASR transcriptions of the associated article, we removed the question-answer pair from the dataset because these examples are too difficult for listening comprehension machine at this stage. In this way, we collected 37,111 question answer pairs as the training set and 5,351 as the testing set.

To test the comprehension ability of machine in real life scenario under worse audio quality, we further added two different levels of white noise into the audio files of testing set to obtain different WERs.
