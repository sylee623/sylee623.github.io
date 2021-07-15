---
layout: post
title: "Show, Attend and Tell : Neural Image Caption (2015) 리뷰"
tags: [논문리뷰, DL, CV]
comments: true
---

논문 링크 :  https://arxiv.org/pdf/1502.03044.pdf

주어진 이미지에 대한 설명을 제시하는 문제를 image caption 문제라고 한다. 이 문제는 다르게 이해하자면 computer vision의 매우 기초적인 목표라고도 볼 수 있는 "scene understanding"에 대한 문제이다. 이를 위해서는 image의 object를 정확하게 인식할 수 있어야하고, object들 사이의 관계를 추론하고 어떤 상황인지를 알아내야하고, 이 상황을 natural language 로 설명해야한다. 단순히 Computer vision에서의 문제가 아닌, NLP까지도 포괄하는 문제이다.

논문에서 언급하고 있는 기존의 연구들은, 대부분이 CNN을 encoder로, 즉 feature vector 를 만들어내는걸 CNN으로 진행하고, RNN을 decoder로, 즉 이를 통해 natural language로 만들어내는 과정을 RNN으로 진행하며, 사실 이 논문에서 제시하고 있는 방법도 같다.

하지만 이 논문에서 차별성을 둔 점이 무엇이냐? 바로 "attention"의 존재이다.

논문에서는 실제 사람에서의 visual system에서 attention이라는 것이 존재한다는 점을 언급한다. 실제로 사람에서도, 두드러지는 feature를 앞으로 보내버리는 방법으로 attention을 준다고 한다. (사실 이해 못함. 이 논문을 좀 봐야할듯) 사람에서는 goal-directed attention, image tracking에서 이에 대해 확인된 바가 있다고 한다. 이 연구에서는 이 두드러지는(salient) object에 중점을 두는 이 방법을 NN에 적용한다.

이 연구에서는 Attention 개념을 두가지로 구현했는데, **Soft attention**과 **Hard attention**이다. Soft attention은 기존의 back propagation을 통해 학습되고, Hard attention은 몇가지 부분부분에 집중하는데, 이를 강화학습 또는 maximizing approximate variational lower bound (?) 를 통해 구현한다.
