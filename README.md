# PetGame(펫 키우기 게임)
이 게임은 Java를 기반으로 나의 작은 친구, 디지털 펫을 내 손으로 직접 만들어보는 프로젝트입니다.

### 프로젝트 제작자 
- **오인준** | **@01nJun**

## 프로젝트 계획 의도
- 이 프로젝트는  나의 작은 친구, 디지털 펫을 내 손으로 직접 만들어보는 프로젝트입니다. 햄스터의 귀여운 몸매와 오리의 뒤뚱거리는 걸음걸이를 보며 키우고 싶었던 두 동물, 오리와 햄스터를 직접 돌볼 수 있는 디지털 펫 게임을 만드는 것을 목표로 했습니다.

## 구현한 핵심 기능
- try-catch문으로 exception 처리

- extends(상속)와 interface 구현 <br>
  상속을 사용한 이유로는 Pet이라는 '설계도'를 만들고 모든 펫들이 물려받으면 Pet에다가 공통 기능들을 만들어 놓으면 <br>
   자동으로 물려받기 때문에 코드의 양을 줄이려고 사용했다

## 개발기간
25.10.31(금)~25.11.03(월)

##  개발 일지

이 프로젝트의 상세한 개발 과정은 아래 링크에서 확인하실 수 있습니다.

- **[Pet Game 개발 일지 보러가기](./PetGame.md)**

 ### 개발 환경
- 언어      

    <img src="https://img.shields.io/badge/Java-ED8B00?style=for-the-badge&logo=java&logoColor=white"/>

- 개발도구

    <img src="https://img.shields.io/badge/Java%20Swing-5382a1?style=for-the-badge&logo=java&logoColor=white"/>

- IDE

    <img src="https://img.shields.io/badge/Eclipse%20IDE-2C2255?style=for-the-badge&logo=eclipse%20ide&logoColor=white"/>

- OS

    <img src="https://img.shields.io/badge/Windows-0078D6?style=for-the-badge&logo=windows&logoColor=white"/>

# 실행구조

## 프로젝트 구조
```
PetGame/
└── src/
    ├── mygame.pet/
    │   ├── Pet.java
    │   ├── Duckling.java
    │   ├── BabyHamster.java
    │   ├── Duck.java
    │   ├── Hamster.java
    │   ├── Evolvable.java
    │   ├── PetIsAsleepException.java
    │   ├── PetIsFullException.java
    │   ├── Game.java
    │   └── GameGUI.java
    │
    └── images/
        ├── Duckling.png
        ├── babyham.jpg
        ├── Duck.jpg
        └── ham.jpg

 ```



## Class Diagram


<img width="1014" height="792" alt="Image" src="https://github.com/user-attachments/assets/5079d547-2826-4661-8e54-7505a409884d" />



### 실행화면
- 처음 실행되는 화면(gif)

![Image](https://github.com/user-attachments/assets/213f4f40-6950-46a4-8230-38258ee1e4bc) <br>




- 처음 켰을 때 아기오리와 아기햄스터 중 선택

![펫 선택 화면](https://github.com/user-attachments/assets/c5b4dc11-481b-4ec0-ab23-2cebc450016f) <br>

- 펫 선택 후 펫 이름 정해주기

![이름 입력 화면](https://github.com/user-attachments/assets/575b4b88-2213-4381-8f07-95a6e36b1632) <br>




## 게임 시스템 주요 기능 구조

이 프로젝트의 핵심이 되는 펫의 행동과 그에 따른 능력치 변화 구조를 정리했습니다. 

<br>

### 기본 기능
<img width="579" height="485" alt="Image" src="https://github.com/user-attachments/assets/5c80650e-161d-42ad-811c-5735383b74e8" />


### 밥주기
| 내용 | 행복도 | 배고픔 | 경험치 | 피로도 |
| :--- | :---: | :---: | :---: | :---: |
| 밥주기 | ▲ +5 | ▼ -10 | ▲ +5 | ▲ +4 |

<br>

### 놀아주기
| 내용 | 행복도 | 배고픔 | 경험치 | 피로도 |
| :--- | :---: | :---: | :---: | :---: |
| 놀아주기 | ▲ +5 | ▲ +5 | ▲ +10 | ▲ +10 |

### 놀아주기 특별 선물 효과 
| 내용 | 발생 조건 | 행복도 | 배고픔 | 경험치 | 피로도 |
| :--- | :--- | :---: | :---: | :---: | :---: |
| 특별한 놀아주기 | 행복도 90 이상 & 20% 확률 | ▲ +10 | ▼ -10 | ▲ +20 | ▼ -30 |

<br>

### 산책 이벤트
| 내용 | 행복도 | 배고픔 | 경험치 | 피로도 |
| :--- | :---: | :---: | :---: | :---: |
| 친구 만나기 | ▲ +15 | ▲ +5 | ▲ +10 | ▲ +10 |
| 간식 줍기 | ▲ +5 | ▼ -10 | ▲ +5 | ▲ +5 |
| 소나기 만나기 | ▼ -10 | ▲ +5 | - | ▲ +10 |
| 평범한 산책 | ▲ +5 | ▲ +5 | - | ▲ +5 |

<br>

### 펫이 자는 중에 다른 행동을 시도했을 때
| 시도한 행동 | 결과 | 행복도 | 배고픔 | 경험치 | 피로도 |
| :--- | :--- | :---: | :---: | :---: | :---: |
| 밥주기/놀아주기/산책하기 | 행동 실패 & 알림창 표시 | ▲ +1 | ▲ +2 | - | ▼ -20 |

<br>


- 펫이 5레벨이 됐을 때 <br>
![진화 화면](https://github.com/user-attachments/assets/ea827f3d-31e8-4859-8496-615abfc9fd3b) <br>

- 펫의 피로도가 100이 되었을 때
 <img width="578" height="481" alt="Image" src="https://github.com/user-attachments/assets/048b7e4d-6f0a-4ea5-a722-bd491be1277a" />

- 펫의 배고픔이 100이 되었을 때
 <img width="586" height="490" alt="Image" src="https://github.com/user-attachments/assets/ea2220e3-459d-4131-9adf-f8db3d69cb02" />


## 좋았던 점과 아쉬웠던 점

#### 좋았던 점
- 내가 좋았던 점은 내가 키우고 싶었던 친구들이라 프로젝트를 만들면서 직접 밥을 주고 놀아주고 산책도 가고 한다고 생각해보면서 만드니까 재밌었다.
- 아무래도 펫 키우기 게임이다 보니까 평범하게 만드는거 보다는 여기에 이런 기능을 넣어보면 재밌지 않을까 ? 하면서 기능에 대해서 재미있는 고민을 했던 것 같다.

#### 아쉬웠던 점
- 내가 아쉬웠던 건 진화가 5렙진화까지밖에 없다. 아기오리 -> 오리 이렇게 진화를 하게 해놨는데 그 다음 진화가 마땅히 생각도 안나고 사진으로 쓸 것도 없어보여서 하지 못했는데 진화 종류가 다양했다면 재밌었을 것 같다.
- 뭔가 만들고 해보면서 게임의 요소가 부족하다고 생각했다 펫의 진화도 부족했고 게임의 컨텐츠 ? 재미 ?가 없다고 생각이 되어서 생각 해낸 게 "추억 앨범"이라는 수집 요소인데 이건 향후 계획에 넣었다.
<br>

## 향후 계획
  콜렉션 프레임워크를 사용해 게임 내 "추억 앨범" 이라는 기능을 넣을 것입니다. <br> 
  "추억 앨범"이란 펫을 놀아주거나 산책을 했을 때에 가끔씩 펫이 특별한 무언가를 가져옵니다.
  - ex) 황금 해바라기씨 / 반짝이는 조약돌
   

  그리고 펫이 특정 레벨을 달성하였을 때에 그 펫에 해당하는 물건을 얻게됩니다.
  - ex) 햄스터의 털뭉치 / 오리의 깃털
  <br>
  이렇게 얻게 된 특별한 물건들을 "추억 앨범"에 넣게 됩니다.   
