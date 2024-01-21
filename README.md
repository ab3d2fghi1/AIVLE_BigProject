# [KT AIVLE School AI 4기 Big Project]

<img src="https://github.com/ab3d2fghi1/AIVLE_BigProject/assets/104991721/69fbfdb4-14d4-40d4-8317-c852b1956961" width="50%" height="50%"></img>

</br>

### 선정 배경
#### 1. 산업 재해로 인한 사망자의 절반 이상이 건설 업계, 50인 미만 사업장 사고 발생률 多
>
> <img src="https://github.com/ab3d2fghi1/AIVLE_BigProject/assets/104991721/befc4e17-2ae2-4951-8e1d-c18f4d5c8871" width="30%" height="20%"></img>

#### 2. 사고의 원인은 외부적 요인보다 작업자의 실수에서 비롯됨
>
> <img src="https://github.com/ab3d2fghi1/AIVLE_BigProject/assets/104991721/0df14f5f-9da7-41eb-a7fc-e746dff3172d" width="40%" height="30%"></img>

#### 3. 작업 일지를 매번 수기로 작성해야하는 번거로움
>
> <img src="https://github.com/ab3d2fghi1/AIVLE_BigProject/assets/104991721/08333546-060a-47dd-a4ed-e953ac47d328" width="40%" height="30%"></img>

</br>

### 서비스 소개
> *중소규모 건설 현장을 위한 AI 기반 안전 관리 서비스*
> 1. AI 모델을 이용한 인지하지 못한 위험 요소 감지
> 2. 번거로운 문서 작업 보조
> 3. 관리자와 근로자 간 원활하게 소통할 수 있는 환경 제공

</br>

### AI 구현 내용
#### 1. 데이터 수집
> <img src="https://github.com/ab3d2fghi1/AIVLE_BigProject/assets/104991721/742e3510-b04a-477f-a0c1-70bbb2a5cec6" width="40%" height="30%"></img>
>
> https://aihub.or.kr/aihubdata/data/view.do?currMenu=115&topMenu=100&aihubDataSe=realm&dataSetSn=71407
> 
> AI hub에서 제공되는 건설 현장 위험 상태 판단 데이터를 활용

#### 2. 모델링 계획
> <img src="https://github.com/ab3d2fghi1/AIVLE_BigProject/assets/104991721/6a94bb88-f07c-4646-86f7-b93af61e025b" width="30%" height="20%"></img>
>
> YOLOv5 classification 모델을 활용한 분류 모델링 시행
>
> 1. [정상/비정상] 이진 분류
> 
> 2. [추락/낙하/협착/화재/전도] 5대 사고 부류
>
> <img src="https://github.com/ab3d2fghi1/AIVLE_BigProject/assets/104991721/b335a1ce-5606-4602-8292-05a70d535796" width="40%" height="30%"></img>
>
> 정상/비정상 판별 후 비정상 판별 시 5대 사고 분류 예측

</br>

### 추후 보완 사항
#### 1. 과적합
> 모델링 파일 onnx 로드 후 실제 데이터를 이용하여 예측 시 과적합 발생
>
> YOLOv5 predict 이용 시에는 정확한 예측 결과, onnx 로드 시 성능 문제 발생
>
> => 문제 해결을 통한 보다 더 정확한 실제 데이터 예측 결과 도출
#### 2. 이진 분류 성능 보완
> <img src="https://github.com/ab3d2fghi1/AIVLE_BigProject/assets/104991721/1df338f5-35d8-4060-834d-2173e326e4b5" width="40%" height="30%"></img>
>
> pretrained 모델 가중치를 이용한 학습 시 정상 데이터 성능 저하 발생
>
> => 데이터 추가 학습을 통한 클래스별 성능 개선
#### 3. 학습 데이터
> 시간 관계 상 validation data 사용 (약20GB)
>
> => 제공 데이터(약200GB)를 모두 활용한 학습을 통한 성능 향상 기대
