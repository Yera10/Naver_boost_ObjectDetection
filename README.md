# Object Detection CV-11

## 대회 개요
> 사진에서 쓰레기를 Detection 하는 모델을 만들어 잘못 분리배출되는 문제점을 해결해보고자 합니다. 문제 해결을 위한 데이터셋으로는 일반 쓰레기, 플라스틱, 종이, 유리 등 10 종류의 쓰레기가 찍힌 사진 데이터셋이 제공됩니다.
> - Input : 쓰레기 객체가 담긴 이미지와 COCO format의 bbox annotation
> - Output : 모델은 bbox 좌표, 카테고리, score 값을 return, 이를 submission 양식에 맞게 csv 파일 제출
> - 평가방법 : mAP50

## Members
| [류건](https://github.com/jerry-ryu) | [심건희](https://github.com/jane79) | [윤태준](https://github.com/ta1231) | [이강희](https://github.com/ganghe74) | [이예라](https://github.com/Yera10) |
| :-: | :-: | :-: | :-: | :-: | 
| <img src="https://avatars.githubusercontent.com/u/62556539?v=4" width="200"> | <img src="https://avatars.githubusercontent.com/u/48004826?v=4" width="200"> | <img src="https://avatars.githubusercontent.com/u/54363784?v=4"  width="200"> | <img src="https://avatars.githubusercontent.com/u/30896956?v=4" width="200"> | <img src="https://avatars.githubusercontent.com/u/57178359?v=4" width="200"> |  
|[Blog](https://kkwong-guin.tistory.com/)  |[Blog](https://velog.io/@goodheart50)|[Blog](https://velog.io/@ta1231)| [Blog](https://dddd.ac/blog) | [Blog](https://yedoong.tistory.com/) |

<div align="center">

![python](http://img.shields.io/badge/Python-000000?style=flat-square&logo=Python)
![pytorch](http://img.shields.io/badge/PyTorch-000000?style=flat-square&logo=PyTorch)
![ubuntu](http://img.shields.io/badge/Ubuntu-000000?style=flat-square&logo=Ubuntu)
![git](http://img.shields.io/badge/Git-000000?style=flat-square&logo=Git)
![github](http://img.shields.io/badge/Github-000000?style=flat-square&logo=Github)

</div align="center">

## Timeline & My Role
![timeline](image\prj_timeline.png)
> - github Issue, PR template 등록 및 사용권장
> - WandB logging 구현
> - Faster-RCNN 모델 실험&튜닝
> - Cascade-RCNN 모델 실험&튜닝
> - ATSS dyhead 모델 실험

## 최종 모델 및 결과
> ![image (6)](https://user-images.githubusercontent.com/48004826/205533073-b9e1c4ec-2fb0-4653-8097-f8a923e53719.png)
> - 1stage, 2 stage 각각 WBF 앙상블 한 뒤에, 두 결과물을 다시 앙상블
> - PL : Pseudo Labeling, 일부 모델에 한해 pseudo labeling 하여 추가 학습
> 
> ![image](https://user-images.githubusercontent.com/62556539/205196491-ecdcabd1-e4eb-4ff8-8607-61205d9b4ac6.png)


## Environments
> - Ubuntu 18.04.5 LTS
> - Intel(R) Xeon(R) Gold 5120 CPU @ 2.20GHz
> - NVIDIA Tesla V100-PCIE-32GB

## Directory Structure
> ```CMD
> level2_objectdetection_cv-level2-cv-11
> └── baseline
>     └── UniverseNet     # MMDetection 기반 패키지
>     └── detectron2
>     └── detrex          # Detectron2 기반 패키지
>     └── faster_rcnn   
>     └── mmdetection     # mmdetection 패키지
>     └── yolov7          # 자체 라이브러리
> └── notebooks           # EDA, ensemble, pseudo labeling 등
> ```

## 회고
> - Git Convention을 정하고, 이슈, PR 등을 적극적으로 활용해보았고, 혼자서는 할 수 없는 좋은 협업 경험이었다.
> - WandB를 활용해 실시간 학습 모니터링과 결과 공유에 용이했다. 
> - WandB의 자유로운 커스텀으로 다양한 metric 을 확인할 수 있었다. 
> - 힘든 일정에도 서로를 격려하고 긍정적인 팀 분위기를 유지해서 끝까지 힘내서 할 수 있었다.
> - augmentation과 데이터셋 분할 방법에 대한 고민이 부족했던 것 같아 아쉬움이 남는다. 
> - data driven 의사결정이 되지 않아 실험 방향성도 뚜렷하지 못했던 것 같다. 
> - 모델에 대한 이론적 이해가 부족한 채 실험을 진행했다. 대회가 끝난 후에 이론적인 지식을 채워나가야 겠다. 

---
- [project_report](https://excessive-help-ce8.notion.site/b41d8c9e26b64e8f9e18b529ebc1f287)