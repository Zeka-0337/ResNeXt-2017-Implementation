# ResNeXt-2017-Implementation

## 설명
가이드라인에 있던 ResNeXt(2017)을 구현하여, Cifar10 dataset에 대해 image Classification을 시도했습니다.
구현은 [해당 논문](https://arxiv.org/abs/1611.05431v2?utm_campaign=Deep%20Learning%20for%20Computer%20Vision&utm_medium=email&utm_source=Revue%20newsletter)에 기재된 방식을 그대로 구현하는 것을 목표로 했으며, 이후에는 https://github.com/prlz77/ResNeXt.pytorch을 참고하여 learning rate를 수정했습니다.

GPU 환경을 사용하기 위해 Colab 환경에서 진행했습니다.
링크 : https://colab.research.google.com/drive/1ZmrIJ7ky-DC6ngihp4Erxc_1tVE05ZuF?usp=sharing
또한, 해당 ipynb파일을 github에서도 확인하실 수 있습니다.

논문과 동일하게 총 300 epoch 학습시키려 했으나, Colab에서 불규칙하게 런타임 연결이 끊어지는 경향이 있어 checkpoint 저장을 통해서 이어서 학습하는 방향으로 진행했습니다.
하지만, 약 183번째 epoch에서 학습이 중단되었을 때 부득이하게도 google drive 용량 한계 때문에 checkpoint들이 저장되지 않아 이어서 학습을 진행하지 못하였고,
논문과는 다르게 총 120 epoch 중 100번째 epoch에서 learning rate를 감소시킨 checkpoint를 제출하게 되었습니다.

learning curve는 183회 학습 과정에서 제작된 test accuracy score를 plot한 것이기에 제출한 checkpoint와는 다른 학습 결과입니다.

## 개인적인 리뷰
- 면접을 계기로 StyleGAN과 ResNeXt를 열심히 학습할 수 있어서 정말 좋았습니다. 합불 여부와 관계없이 스스로가 앞으로도 이와 같이 열정적으로 학습할 수 있었으면 합니다.
- 구조를 구현하는 것과 성능을 구현하는 것은 조금 다르다는 것을 깨달았습니다. 약 180회의 학습을 진행했으나 약 92%의 test accuracy에 도달하였습니다. 논문에서 제시한 성능인 3.58% test error에 훨씬 못미치는 성능으로, 데이터의 전처리나 weight initializaiton 등에서 차이점이 있었을 것으로 사료됩니다.
- 다른 사람들의 구현 코드를 둘러보면서, 환경 설정이나 argument에 대한 자신만의 정리된 템플릿을 갖춰가는 것이 모델의 학습이나 결과를 진행하고 정리하는 데에 있어서 중요하다는 점을 깨달았습니다.
