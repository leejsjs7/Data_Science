# 다중 븐류 모델의 평가




 ㅁ     강아지 고양이 거북 이 - 예측값
 강아지 4      6      3 
 
 고양이 1     2       0

 거북이 1      2      6

 -실제값


### Macro vs Micro

마이크로 관점 (좀 더 자세하게 보는거임)
고양이 굉장히 많음, 당연히 고양이 판단이 중요함 // 거북이와, 강아지에 대해서 영향이 적어짐

 ㅁ     강아지 고양이 거북 이 - 예측값
 강아지 4      6      3 
 
 고양이 1     10002       0

 거북이 1      2      6

 -실제값


매크로 관점 (크게봄 거시적으로 봐서)

고양이를 중요하게 볼꺼냐, 아니면 고양이 거북이 다 똑같이 볼꺼암

어떤게 좋고, 어떤게 나쁘다고 할 수 없음 다만 각자 특징이 있고 상황에 맞게 잘 쓸수 있어야 함

MNIST - 주립대에서 공개한 손글씨 데이터임, 일일이 레이블링 한 거다 

픽셀 하나하나가 수치를 갖고있음, 그 하나하나의 기반으로 예측을 하는거임

## 제품의 불량 판별
### 주조 불량 판별

인공지능은 사진이 아니라, 숫자, 표를 주로 활용함
1. 차량의 크기
2. 배기량 

하지만 데이터가 숫자가 아니라 사진일때는?? 이럴때 인공지능은 어떻게 처리할까
이미지 데이터를 표의 형태로 잘 정리

수치형 데이터로 잘 정리

빨강색 부분을 확대, 확대를 하면 할 수록 격자 형태가 나옴 각각 네모난 칸 안에
의도적으로 격자와 격자 사이의 간격을 희미하게 처리함, 경계가 이미지를 희미하게 처리하면 이미지를 확대하게 되면, 격자들을 픽셀이라고함, 하나의 픽셀은 하나의 숫자를 가짐


사진을 흑백화 하면, 색깔이라는 차원이 없어지고, 얼마나 밝냐 어둡냐로 포현됨 증 피처개수를 줄임 -> 이미지의 크기가 줄어듬'


`
'''
Let f be an image
SIZE = 256
image = Image.open(f).resize((SIZE,SIZE)).convert('L') # 이미지가 크니까 손실을 각오하고 줄임, L은 흑백으로 변환

if f is "oKay" 

# 이미지를 숫자형으로 변환
data = asarray(image) // image to an array
flat = data.flatten

이미지 데이터를 어떻게 컴퓨터가 이해할 수 있는 형태로 바꿀까

임베딩s
 - 데이터를 백터화 함, 이미지 데이터를 백터화 함
 - 이미지가 아니라, 텍스트, 비디오, 문서도 백터화 할 수 있음 
 - 인공지능에서 임베딩은 매우 중요해, 컴퓨터가 알아 먹어야 하니까, 
    이미지를  백터로 바꾸는 한 가지 방법, 


 랜덤으로 백터로 보는게 아니라, 의미가 비슷한 놈들끼리는 가깝게 보내는 거지 
Cat -----------> (c1,c2,c3) 
Father --------> (f1,f2,f3)
Dog -----------> (d1,d2,d3)
Family---------> (f1,f2,f3,......)


그러니까 Dog랑 켓은 가깝게, 페밀리랑, 파더랑은 가깝게 보내자 이거지

word to vector 
Vqueen = Vking - v=Vman - Vwoman / 그럴듯하지 

딥러닝과 임베딩의 관계

뉴럴 네트워크를 만드는걸 딥러닝이라고 하는데...

이미지를 맨왼쪽에 넣음 -> 임베딩 -> 백터
ex) Inception v3 model 

아키텍쳐 (구저)


추출되는 정보의 해석을 사람이 하기에는 어려움이 있음
Inseption v3, 알렉스랩 등 이미지 차원을 적절하게 축소하고, 이를 기반으로 logistic Regretion을 적절하게 사용하자 

이미지에서, 머신러닝을 돌렸더니 logstic이 아니라 Nerual Network를 구축했다
이러면 convolution network , CNN과 유사하게 만든 거임 

픽셀로 했을떄 와 이미지에서 적절한 데이터를 추출했을때 차이가 있다잉