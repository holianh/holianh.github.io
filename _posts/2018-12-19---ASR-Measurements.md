---
image: http://llcao.net/blog/img/end-to-end-performance.png
instantfeedback: true
description: Cách đo lường khi làm việc với ASR
layout: post
title: ASR measurements
category: Deep-Learning
tags: Deep-Learning, ASR WER
keywords: Deep-Learning, ASR, WER
---

# Liệt kê các phương pháp đo lường kết quả trong các bài báo quốc tế về ASR (Automatic Speech Recognition).

<div style="text-align:center"><img src ="http://llcao.net/blog/img/end-to-end-performance.png" height="300"/></div>

---

## Danh sách:

|Tên bài | Phương pháp|Model liên quan| năm & link| Ảnh|
|--------|------------|-----------    |-----------|-----------|
|SMALL-FOOTPRINT KEYWORD SPOTTING USING DEEP NEURAL NETWORK AND CONNECTIONIST TEMPORAL CLASSIFIER|False Reject Rate - False Alarm Rate|Baseline Deep-KWS (3x128), DNN(3x128)+CTC, DNN(3x256)+CTC, DNN(4x256)+CTC, DNN(6x512)+CTC|[12 Sep 2017](https://arxiv.org/pdf/1709.03665.pdf)|<img src="img_posts/2018-12-19-14-00-56.png" height=120/>|
|END-TO-END MODELS WITH AUDITORY ATTENTION IN MULTI-CHANNEL KEYWORD SPOTTING|False Reject Rate - False Alarm Rate|Baseline, Attention, Attention_map, Transfer, Transfer_map, Tran_Multi_map|[3 Nov 2018](https://arxiv.org/pdf/1811.00350v2.pdf)|<img style='width: 300px;height: 200px' src="img_posts/2018-12-19-14-03-45.png"></img>|
|HIERARCHICAL NEURAL NETWORK ARCHITECTURE IN KEYWORD SPOTTING|Recall rate – Miswake/hour|HNN1/2/3 (allbn, 1bn), baseline|[6 Nov 2018](https://arxiv.org/pdf/1811.02320.pdf)|<img src="../img/img_posts/Screenshot from 2018-12-19 14-10-47.png" height='100' width="100"/>|
|EFFICIENT KEYWORD SPOTTING USING DILATED CONVOLUTIONS AND GATING|False Reject Rate - False Alarm Rate per hour|CNN, LSTM, WaveNet|[19 Nov 2018](https://arxiv.org/pdf/1811.07684.pdf)|<img src="https://raw.githubusercontent.com/holianh/holianh.github.io/master/img/img_posts/Screenshot from 2018-12-19 14-13-21.png" height= width="100"/>|
|QUERY-BY-EXAMPLE KEYWORD SPOTTING USING LONG SHORT-TERM MEMORY NETWORKS|False Reject Rate - False Alarm Rate|Phone DNN/LSTM+DTW, LSTM Feat Extrator|[2015](http://clsp.jhu.edu/~guoguo/papers/icassp2015_myhotword.pdf)|<img src="https://raw.githubusercontent.com/holianh/holianh.github.io/master/img/img_posts/Screenshot from 2018-12-19 14-16-42.png" height= width="100"/>|
|Wav2Letter: an End-to-End ConvNet-based Speech Recognition System|LER- train set size|MFCC, MFCC+AUG, POW, POU+AUG|[13 Sep 2016](https://arxiv.org/pdf/1609.03193v2.pdf)|<img src="https://raw.githubusercontent.com/holianh/holianh.github.io/master/img/img_posts/Screenshot from 2018-12-19 14-20-45.png" height= width="100"/>|
|minimum-word-error-rate-training-for-attention-based-sequence-to-sequence-models|WER-Training Eporchs|Lamda=0/0.01/0.1, Bi-LAS, +MWER, Uni-LAS, MWER, CD-phone (CE + sMBR)|[Dec 05, 2017](https://www.groundai.com/project/minimum-word-error-rate-training-for-attention-based-sequence-to-sequence-models/)|<img src="../img/img_posts/wer_lambda_nbest.png.750x0_q75_crop.jpg" height= width="100"/>|



 















.
.
.
Trao đổi, bình luận, comment, gạch đá,... tất cả tại đây nhé:
Vào nhóm: [facebook comment]()
