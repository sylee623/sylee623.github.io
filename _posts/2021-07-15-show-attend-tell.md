---
layout: post
title: "Show, Attend and Tell : Neural Image Caption (2015) 리뷰"
tags: [논문리뷰, DL, CV]
comments: true
---

## Abstract

최근의 machine translation 및 object detection 방법에서 영감을 받아, image 의 contatnt 를 묘사하는 것을 학습하는 attention based model을 제시하겠음.

## Introduction

"Caption generation" 이라는 분야는 scene understanding 즉 computer vision의 매우 기초적인 목표이며, image의 object를 판별하는 것 뿐 아니라, 이들의 관계를 natural language 로 표현해야하기 때문에 상당히 어려운 문제임.
최근의 연구들은, 여러모로 향상된 수준의 caption을 만들어내고 있고 대부분은 CNN을 encoder로 (vectorial representation을 만들어냄.), RNN을 decoder로 (이 representation으로 natural language 문장을 만들어냄.) 쓰는 방식임.

Human visual system에는 attention이라는 것이 존재하고, 두드러지는 feature들을 앞쪽으로 보내버리는 식으로 작동함. goal directed attention, image tracking 에서 확인된 연구들이 있음. 본 연구에서는 이를 image captioning에 적용해 볼 것임. (salient object에 좀 더 가중치를 주는 방식으로)

이 연구에서는, hard attention, soft attention mechanism을 이용해 caption generation 을 하는 방법을 제시할 것임.

연구를 통해 확인한 것은 다음과 같음.
* soft attention은 standard back propagation method를 이용해 training 하고, hard attention은 maximizing 하거나, 강하학습을 이용해 training 시킴.
* 우리가 어떻게 insight를 얻고, 결과를 해석했는지를 어디에, 무엇에, 어디에 집중했는지를 보여줌으로서 확인함.
* 3가지 benchmark dataset을 통해 양적으로 실용도를 확인함.

## Image Caption Generation with Attention Mechanism

### Model Details

이 paper에서 제시하고 있는 attention based model은 2가지 종류가 있는데, 이 둘 사이의 가장 큰 차이점은 φ function의 정의 입니다. 

* Encoder - CNN: Encoder로 사용되는 CNN은, raw image로부터 feature vector를 추출하는데 사용되었습니다. 이전 연구들에서는. FC 상태로 feature vector를 추출했지만 여기서는 2D형태로 추출하도록 하였음. 이렇게 함으로서, 뒤에서 decorder가 이미지의 특정 영역에 집중할 수 있도록 할 수 있습니다.

* Decorder : LSTM은 caption을 만들어내는 단계에서 사용되었습니다.

## Learning Stocahstic "Hard" vs Deterministric "Soft" attention

### Stochastic hard attention
