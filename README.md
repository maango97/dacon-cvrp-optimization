# 🎅선물 배송 경로 최적화 경진대회: 산타와 루돌프의 워라벨 사수작전

<img src = "https://github.com/maango97/dacon-cvrp-optimization/blob/main/%ED%91%9C%EC%A7%80.png" width="600" height="320"/>

- 주제 : LKH-3와 4-OPT를 활용한 배송 경로 최적화
- 기간 : 2024.12 - 2025.01 (5인)
- 성과 : Private 9th(상위 4%)
- [데이터 출처(DACON)](https://dacon.io/competitions/official/236437/data)
- [DACON 게시판 코드공유](https://dacon.io/competitions/official/236437/codeshare/12186?page=1&dtype=recent)
- [대회 제출 PPT](https://github.com/maango97/dacon-cvrp-optimization/blob/main/DACON_%EC%A0%9C%EC%B6%9CPPT.pdf)


## 📋개요

- 목표 : 총 이동 거리를 최소화할 수 있는 최적 경로를 설계하는 알고리즘을 개발
  
- 제약 조건
  
  - 한 번에 최대 25개의 선물만 운반 가능(선물이 부족할 경우, 다시 출발점으로 돌아가 선물을 채워야 함)
  
  - 마을에 방문했을 때, 모든 어린이들에게 배송해야함(선물을 받지 못해 우는 아이가 발생하므로 !)
  
  - 한 마을에는 한 번씩만 들러야함
  
- 사용 알고리즘   

  - **LKH-3 알고리즘** : LKH-3 알고리즘은 기존 LKH 알고리즘을 확장한 버전으로, 약 40가지의 다양한 TSP 변형 문제를 해결가능
 
  - **4-opt 알고리즘** : 경로 최적화(Traveling Salesman Problem, TSP)에서 사용되는 휴리스틱 기법으로, 경로를 개선하기 위해 4개의 에지(edge)를 동시에 제거하고 새로운 방식으로 연결하여 총 경로 거리를 줄이는 알고리즘
  
- 최적화 순서

  - LKH-3 기반 초기 경로 도출 -> 4-OPT 기반 경로 최적화 -> 최종 최적화 경로 출력 
  
- 최종 거리 : 2173.58914km (1위와 1.3km 차이)
<img src="https://github.com/maango97/dacon-cvrp-optimization/blob/main/%EC%B5%9C%EC%A2%85%EA%B2%BD%EB%A1%9C_%EC%8B%9C%EA%B0%81%ED%99%94.png" width="600" height="600"/>


## 🧐고민의 흔적들

- 한정된 시간 안에서 다양한 메타 휴리스틱 알고리즘 중 어떤 알고리즘을 선택할지 고민
 
  - 5명이 문제에 적합한 알고리즘을 분담하여 시도 -> 제일 **비용이 적게 든(거리가 짧은) LKH-3 알고리즘**을 선택 -> 그 후 **개선을 위해 4-opt를 추가 적용**
    
  - 그 외 시도했던 알고리즘 : **Or-tools, 유전 알고리즘, SA(담금질), Tabu, NN, Greedy, Clarke-Wright Savings** 등


## ⚙환경

- Anaconda - Jupyter Notebook
