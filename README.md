진행 기간 : 2017.09 ~ 2018.05



개발 목표

- 현재 비상구를 나타내는 비상구표지판은 화재 시에 연기로 인해 비상구의 표지판이 잘 보이지 않아 비상구 유도의 기능을 다 하지 못함. 그래서 비상구를 최단경로로 위험요소를 피하여 유도 할 수 있는 기기를 만들어 보려함
아키텍쳐 설계
[사진1]
1. 불꽃 감지 센서들을 아두이노 WIDO를 이용하여 제어합니다.
2. 불꽃 감지 센서의 센서값을 기기에 전송합니다.
3. 기기에 사용할 아두이노 WIDO에 수신용 UWB센서를 달고, 송신용 UWB센서 3개를 건물에 적절한 곳에 위치시킵니다.
4. 불꽃 감지 센서의 센서값과 UWB센서의 센서값을 받은 기기는 서버에 정보를 전송합니다.
5. 서버는 기기에서 정보를 받아 이동경로를 탐색한 후, 기기에 정보를 전송합니다.
[사진2]
송신 UWB센서의 구조입니다.
UWB센서인 dwm1000을 adapter board와 결합하여 아두이노 Nano보드로 제어하도록 하였습니다.



주요 내용

- 실내에서 기기의 위치를 정확히 파악하기 위해 실내 측위에 가장 적합하다고 생각되는 UWB센서를 사용하였고, 현재 위치에서 가야할 방향을 정확히 알려주거나, 벽과 구조물을 고려해서 정확한 길을 알려주기 위해 서버에 실내 구조를 이미지로 맵핑하고, 상대적인 좌표를 이용합니다. 기기가 탐색한 방향과 다른 방향으로 가려하면 기기에 메시지를 출력해주어 사용자에게 경고를 줍니다.
- 또한, 안전한 길로 안내하기 위해 실내 곳곳에 불꽃감지센서를 이용하여 화재를 감지하고, 화재 발생 시, 서버에 알려주어 서버에서 기기에 알림을 줄 수 있도록 하였고, 이동경로를 탐색할 때, 화재가 난 위치는 배제하여 탐색할 수 있도록 합니다.
- 그리고 사용자의 위치를 빠르게 파악하여 신속하게 길을 안내하기 위하여 서버를 이용하였습니다. 서버를 이용하면 기기를 이용하는 것보다 위치를 파악하는 수식계산에 유리할 것이기 때문입니다.
- 마지막으로 이동방향을 알기 쉽게 알려주기 위하여 기기의 LCD화면에 방향을 출력해주는 방법을 사용하였습니다.
본인이 기여한 점



사용한 Skill



어려웠던 점

- 건물에 철근콘크리트로 만들어진 벽이 다수 있다면 uwb센서에 오차가 발생가능 
기존의 안전장치(소화기,비상구 유도등 등)외에 추가적인 기기 설치비용 발생
화재 시 네트워크가 지원이 안 되는 상태면 서버와 통신 불가능



결과