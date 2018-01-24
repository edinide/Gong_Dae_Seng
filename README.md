https://goo.gl/Ep8yF9 (기획)
https://goo.gl/PgT8kv (일지)
 
 <h3>"유니티 C#으로 만드는 공대생 액션 게임”</h3>
 <strong>- 졸업해주세요 공대생이여! -</strong>
 <h1>개발 내용</h1>

『3D필드 위에서 공대생이 학점을 채워나가며 게임 클리어하기』

[게임 시작 화면 -> 설명 대화창 화면 -> 1~4번째 스테이지들]로 이루어져 있다.


▶게임 시작 화면
MenuCtrl.cs로 제어, 각 버튼을 눌렀을 때 해당 함수를 호출하게 했다.

▶설명 대화창 화면
캐릭터 3D특성을 살려 대화의 문장 번호를 받아 애니메이터 컨트롤러에서 상황에 따른 메카님 애니메이션을 이용해 구현, iTween 플러그인 대신 TextBoxMgr.cs와 PlayerDialogCtrl.cs로 제어하였다.

▶스테이지들
총 4가지(1~4학년) 스테이지가 있다. 오브젝트들은 대부분 겹치며 다음과 같다 :
(카메라, ‘공대생(캐릭터)’ 외에 ‘포털’, ‘학점(코인)’, ‘과제 폭탄’ 그리고 ‘F학점몬(적)’ 등)

<li>폭탄->범위 안에 들어가면 카운트다운, 시간 지나도 그곳에 있으면 멘탈게이지 하락.</li>
<li>학점->어두운 스테이지에서 쉽게(?) 찾을 수 있도록 point light기능을 통해 빛 발산.</li>
<li>적->적이 돌아다닐 수 있는 범위 설정, 이동로직은 AI와 Nav Mesh Agent컴포넌트를 통해 구현하였는데, 15f만큼의 구 형태에서 랜덤으로 위치를 받고 이동하게 한다. 차일드화된 Eye컴포넌트는 기다린 직육면체 형태로 마치 시야처럼 만들었고 그 범위 안으로 공대생이 들어가면 그를 향해 속도를 높이고 달려가게 하였다 (creepy) </li>
