# 헬트래커
- 지금까지 한 운동을 기록하고 간편하게 모아볼 수 있는 간단한 운동 기록 사이트입니다. 로그인을 지원하여 사용자 별로 운동 기록이 분리됩니다.
- 백엔드
	- Express를 사용하여 REST API를 구현하였습니다. 라우팅을 처리하고, 유저가 구분되는 API 호출에 대해서는 requireAuth 미들웨어를 사용하여 올바른 jwt 토큰인지, 로그인이 되어 있는지 판별합니다.
	- MongoDB의 document에 대해 특정한 형식으로 트랜잭션이 이루어지는 것을 보장하기 위해 Mongoose의 schema를 작성하였습니다. 이를 통해 올바르지 않은 값, 불완전한 document의 삽입을 방지합니다.
	- controller에서 유저/운동 내역 관련 CRUD 작업을 처리하고 REST API request에 대한 JSON 응답을 생성합니다.
- 프론트엔드
	- React를 사용하여 구현하였습니다. 라우팅은 React Router를 통해 처리했습니다.
	- React의 Context API를 사용하여 일일이 prop을 통해서 하위 component에 값을 넘겨 주지 않고도 상태를 업데이트할 수 있도록 하였습니다.

# LMS
- Express를 사용하여 학습 관리 시스템(Learning Management System)을 제작하였습니다. 교수는 수업을 개설하고 각 수업마다 게시물을 올릴 수 있습니다. 학생은 계정을 생성하고 로그인하여 원하는 수업을 신청하고 신청한 수업의 게시물의 확인할 수 있습니다.
- Pug template engine을 사용하여 server-side에서 렌더링을 진행합니다.
- express-session을 통해 로그인 세션을 관리하고, MariaDB를 DB로 사용합니다. SQL문을 통해 트랜잭션을 수행합니다.