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

<img src="https://github.com/user-attachments/assets/23a4f0ba-010c-427c-9c1a-24722d19099d">

<img src="https://github.com/user-attachments/assets/e40aa8e6-4777-4a8c-833d-5c3129083258">

<img src="https://github.com/user-attachments/assets/e8b0dd8c-bd46-4276-a6f5-6a79d0e9ae50">

<h4>JPA, React를 이용한 게시글 작성</h4>

<p>게시글 작성코드입니다. 파일을 올릴 수 있도록 기능 추가했으며 파일이 올라가기 위해서 클라이언트 측에서는 폼데이터로 처리했습니다. 비동기처리를 하지 않았기 때문에, 게시글 작성 후 새로고침될 수 있도록 기능을 만들어 넣어줬으며 이미지를 올리지 않았을때 글 작성이 되지 않는 문제가 있어서, 아래 사진의 빨간 박스처럼 조건문을 걸어 boardFile을 따로 처리하였습니다. 
보시는 것처럼 board데이터를 가져와 게시글이 조회될 수 있도록 만들었고, 위 사진의 빨간 박스는 useParam으로 가져온 브라우저의 mbti와, 데이터베이스에 입력된 mbtiType이 같은 경우에만 게시글이 표시되도록 필터처리하였습니다.
</p>


  <h2>4.게시글 페이지</h2>
  
<img src="https://github.com/user-attachments/assets/0bff3b8b-a6fa-46ef-8c9c-5c2a10698ce3">

<img src="https://github.com/user-attachments/assets/62617908-34bb-4757-a12d-7cdd148c3cea">

<img src="https://github.com/user-attachments/assets/a966e30c-2aa2-4af8-a4c7-c7a92d819fdc">

<img src="https://github.com/user-attachments/assets/608e99f0-f4a0-4a60-8b8d-ac9fc35ab2ad">

<h4>queryDSL, JPA, React를 이용한 댓글, 답글 작성</h4>

<p>댓글 관련 코드입니다. 이 부분은 답글 기능을 넣기 위한 편의성으로 queryDSL을 사용했으며 댓글 추가, 댓글 조회 기능을 넣어두었습니다. 컨트롤러 측에서는 반복문을 이용해서, 댓글에 댓글이 담겨서 답글로 표시될 수 있도록 했습니다. DTO의 경우에는 답글이 리스트로 나올 수 있도록 하기위해 사용하게되었습니다. 
클라이언트 측에선 reactQuery로 데이터를 가져와 1초마다 자동으로 새로고침이 되도록 설계했습니다. 이후, useMutation을 이용해 댓글이 서버에 전송될 수 있도록 하였으며, 브라우저 경로에 게시글 클릭 시 게시글의 넘버가 보이도록 만들어놨는데, 이것또한 모든 댓글이 한 게시글에 모두 보이는 문제가 있어, mbtiType과 비슷한 구성으로, useParam으로 따온 no와, 데이터베이스의 no가 같은경우에만 댓글이 표시되도록 했습니다.
답글의 경우 댓글과 비슷하지만, 댓글과 비슷하지만, 답글의 경우 누구에게 답글달았는지 표시될 수 있도록 span태그로 한 줄 더 추가하였으며,  commentWriter와 같이 게시글 작성했을때, 댓글 작성했을때, 답글 작성했을때 작성자를 입력하지 않는경우, useParam으로 게시판의 MBTI를 따와 익명의 ISTP, ENFP처럼 게시판의 MBTI가 표시될 수 있도록 했습니다. 
</p>


  <h2>5.핫한 게시글</h2>
  

<img src="https://github.com/user-attachments/assets/746f8a8c-75ed-4a1e-9f39-584e4147817e">

<img src="https://github.com/user-attachments/assets/bc63615a-bffe-485b-aa6a-d25cd6c9f449">

<img src="https://github.com/user-attachments/assets/ae168f29-ca5c-4c70-bed4-b7717d77bcdd">

<img src="https://github.com/user-attachments/assets/9e4b4370-fb8d-48b9-8720-30aa0058a3a1">

<h4>Redux, ReactCookie, JPA, React를 이용한 핫게시글</h4>

<p>핫게시글입니다. 리액트쿠키라는 라이브러리를 사용해서, 클라이언트 측에서 쿠키에 담고, 삭제할 수 있게했습니다. 첫번째사진은 리액트 쿠키 셋팅인데, 핵심은 핫게시글이 시간이 지났을때 자연스럽게 사라지게 하고싶었기에, maxAge로 시간초를 설정해서 쿠키에 수명을 넣어뒀습니다. 현재설정은 일주일로 되어있는데, 만약 사용자가 많다면 10분으로 설정하는 등, 유동적인 설정이 가능합니다. 
 두번째 사진은 아까 보여드린 게시글 클릭시 발동되는 기능인데, 게시글의 조회수가 9가 되는 순간 쿠키가 현재시간, 모든 경로에서 셋팅될수있도록 조건문을 걸었습니다.
 첫번째 사진은 맵처리인데, 이것또한 ISTP의 핫게시글이 다른 게시판에 보이는 문제가 발생해 mbtiType과 mbti가 같은경우여야했고, 조회수가 10이상일때 쿠키가 담기도록 했습니다. 이후, 네번째사진처럼 필터처리를 넣어 원하는 정보가 나올수 있게 처리했습니다.
셋팅되는 타이밍은 조회수가 9와 같을때인데, 쿠키가 담기는 타이밍은 조회수가 10이상으로 상이하게 설정한 이유는, 조회수가 9와 같을때는 쿠키가 삭제된 이후에 조회수가 늘어나 쿠키가 다시 담기는걸 방지하는 역할을하고, 조회수가 10이상일때는 조회수가 11,12일때 담겼던 쿠키가 빠지는 걸 방지하기 위해 설정하게 되었습니다.
</p>


<h1>마치며..</h1>

<p>팀프로젝트와 다르게 개인 프로젝트를 진행하니, 처음부터 혼자 설계와 구현을 하는 것이 쉽지 않았습니다. 필요한 설계를 모두 마쳐놓았다고 생각했음에도, 뒤늦게 빠진 기능을 추가로 넣어야하는 일이 발생하는 등 일이 발생해 협업의 중요성을 깨달아 좋은 경험이기도 했습니다.
또, React의 사용 이유를 경험했습니다. Redux나 ReactCookie와 같은 라이브러리는 재미있는 경험이였고, 나눠놓은 컴퍼논트가 유용하게 쓰일 때 성취감이 들었습니다.
</p>
