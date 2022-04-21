## REST API 설계

---

- /user
    - (post) 강사회원 생성

- /user/join
    - (post) 학생회원 가입

- /user/login
    - (post) 회원 로그인

---

- /lecture
    - (get) 강의 리스트 조회

- /lecture/{lecture_id}
    - (get) 열람
    - (patch) 강의 노출 상태 전환

- /lecture/{lecture_id}/enrolment
    - (post) 수강신청

- /lecture/{lecture_id}/matching
    - (patch) 강사 매칭

- /lecture/{lecture_id}/content
    - (post) 컨텐츠 업로드
    - (get) 컨텐츠 조회

- /lecture/{lecture_id}/score
    - (Post) 성적 입력
    - (Get) 성적 조회

- /lecture/{lecture_id}/rating
    - (post) 별점 입력
    - (get) 별점 조회

---

- /article
    - (get) 게시글 리스트 조회

- /article/{article_id}
    - (post) 게시글 작성
    - (get) 게시글 조회
    - (patch) 숨김 처리

- /comment/{article_id}
    - (get) 댓글 리스트 조회

- /comment/{article_id}/{comment_id}
    - (post) 댓글 작성
    - (get) 댓글 조회
    - (patch) 숨김 처리
