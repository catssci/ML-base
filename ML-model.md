# Machine Learning Model

## 01. Supervised vs Unsupervised

- Supervised: 정답 라벨을 포함한 데이터를 이용하여 모델을 학습하는 방법
- Unsupervised: 정답 라벨이 없는 데이터를 이용하여 모델을 학습하는 방법

## 02. Supervised Learning Model 종류

- Decision Tree
- SVM
- Knn
- Isolation forest
- Xgboosting

## 03. Decision Tree

- 학습 데이터의 특징값을 이용하여 라벨을 구분하는 트리를 만든다.

- 트리에서 자식노드 생성 시 Entropy, Information Gain을 통하여 최적의 분기 조건을 찾는다.

- Entropy : 데이터가 균일하게 분류되어 있는지에 대한 척도

  - 분기 전의 Entropy 계산 공식 (부모 노드의 Entropy)

    <img src="C:\github\TIL\images\Entropy formula.png">

  - 분기 후의 Entropy 계산 공식 (자식 노드들에서의 Entropy)

    <img src="C:\github\TIL\images\Entropy formula2.png">

  - Entropy 大 : 클래스의 분포가 균등하다.

  - Entropy 小 : 클래스의 분포가 불균등하다. (한쪽으로 기울어져 분류된 상태)

- Information Gain : 분기 이전의 Entropy와 분기 이후의 Entropy의 차이

  <img src="C:\github\TIL\images\Information Gain formula.png">

  - Information Gain 大 : 현재 선택한 분기에서 클래스의 분포가 불균형하다. 잘 분리되었다라고 판단.

- Entropy의 그래프는 다음과 같다.

  <img src="C:\github\TIL\images\Entropy graph.png">

  - 클래스의 분포가 균등하게 나와 각 클래스의 확률이 같다면 $-0.5log_20.5 -0.5log_20.5 = 1$ 로 최댓값을 계산할 수 있다.
  - 반대로 클래스의 분포가 하나의 클래스로만 분류되었다면 $-1log_21 -0log_20 = 0$, $\displaystyle\lim_{x\rightarrow0}xlogx = 0$ 로 최솟값을 계산할 수 있다.
  - Example: [Decision Tree 정리](https://github.com/catssci/TIL/blob/main/Basic%20ML%20Algorithm/Decision%20Tree.md)
  - 장점
    1. 해석하기 쉽다. 즉, 해당 클래스로 예측했을 때 트리를 따라가며 예측 과정을 해석할 수 있다.
    2. 구현과 이해하기 쉬운 모델이다.
    3. 비모수적 모델이다. 즉, 통계모델에 요구되는 가정이 없음 (정규성, 독립성, 등분산성 등..)
  - 단점
    1. 데이터의 수가 적을수록 모델이 불안정하다.
    2. Overfitting 발생 확률이 높다.

## 04. SVM

