<h1>Personal Project : MBTIS</h1>
<h2>본인의 성향과 맞는 사람들끼리 소통하는 커뮤니티 MBTIS</h2>

<h1>주제 선정 배경</h1>
<ul>
  <li>사용자의 성향과 맞는 게시판 사용 가능</li>
  <li>사용자들의 간편한 접근과 사용</li>
  <li>핫한 게시글과 검색을 이용한 원하는 게시글 조회</li>
  <li>원하는 사람과 소통을 위한 댓글과 답글</li>
</ul>


<h1>전체 기술 스택</h1>
<p>React, JPA, MySQL, queryDSL, JPQL</p>

<h1>DB 모델링</h1>
<img src="https://github.com/user-attachments/assets/3e0fad2d-de10-4ac9-93f8-68ea67dd7527">

<h1>코드 리뷰</h1>
  <h2>1.index 페이지</h2>

  <p>접속 시 가장 먼저 보이는 사이트 소개 페이지입니다. 로그인 창이 모달로 구현되어있으며 회원가입, 개발자 탭 클릭 시 
      해당하는 페이지로 이동합니다. 
  </p>


<img src="https://github.com/user-attachments/assets/b40d2069-096b-4d68-9ce2-28d171629bf7">
  

<img src="https://github.com/user-attachments/assets/2a6a1263-c07c-4a2f-b9b0-2ab8474cff22">

<h4>React를 이용한 페이지 이동</h4>

<p> MBTI는 총 4개가 합쳐져 하나의 MBTI가 되는것에서 아이디어를 얻어 총 4개의 셀렉트 박스에 각기 id와, value를 부여한 후 4개의 id와 value를 하나로 합쳐 경로가 되도록 만들었습니다. 해당 mbtiResult는 이후, 데이터베이스에서 mbtiType이 되고, 게시판을 나누는 데 사용됩니다. 다만 ISP, 혹은 IST등 4개를 온전히 선택하지않고 게시판에 들어가는 것을 방지하기 위해, 조건문을 걸어 mbtiResult의 length가 4인 경우에만 접속되도록 했으며, 4가 아닌 경우 접속되지않습니다.
</p>

  <h2>2.게시판 페이지</h2>


<img src="https://github.com/user-attachments/assets/ef7ecec9-568c-4535-8f8d-ffb3f12694ba">

<img src="https://github.com/user-attachments/assets/965f3354-e71c-4c88-861a-5ce7e17320dd">

<img src="https://github.com/user-attachments/assets/9d8378cd-078e-47da-a116-89e7b2047f23">

<h4>JPA, JQPL, React를 이용한 게시판 페이지</h4>

<p>게시판 화면입니다. 화면 상 ISTP 홈이라고 되어있는데, ISTP 게시판에서 작성한 글은 이곳에서만 보이게 할 필요가 있었습니다. 그래서 사용하게된게 JPQL문법이고, mbtiType을 따로 select할수 있도록 코드를 짰으며, 추가로 조회수를 업데이트하는 기능도 JPQL로 짜게되었습니다.
클라이언트 측에서는 map을 이용하여 게시글이 표시되도록 하였으며, 이곳에서도 조건문을 걸어 board.mbtiType이 mbti와 같은 경우에만 표시되도록 하였습니다. 특이사항으로는 온클릭을 보시면 쿠키클릭이라는 함수를 넣어놨는데, 이것또한 이후에 게시글을 눌렀을때, 쿠키가 담기는 기능을 합니다.
체크된 코드의 경우 페이징의 역할을 하며, 검색기능과 함께 비슷한 구성으로 되어있지만, 특이사항으로 Sort로 조회되는 글 순서를 원하는 대로 설정하였고, mbti 정보를 함께 보내 게시판 별로 페이징 처리가 다르게 될 수 있게 하였습니다.
</p>



  <h2>3.게시글 작성</h2>

  <h2>4.게시글 페이지</h2>

  <h2>5.핫한 게시글</h2>
  
