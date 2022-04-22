## REST API Document

---
### USER

<details>
  <summary>
    <code>POST</code> 
    <code><b>/users</b></code> 
    <code>(강사회원 생성)</code>
  </summary>

##### Header

> | name   | Description      | Required |
> |--------|------------------|-----------|
> | `Authorization` |   사용자 인증 수단, 액세스 토큰 값     | O |
##### Parameters

> | name   |  type      | Description      | Required |
> |--------|------------|----------------|---|
> | `name` |  String  | 이름     | O |
> | `email` |  String  | 이메일     | O |
> | `address` |  String  | 주소     |  |
> | `phone` |  String  | 전화번호     |  |

##### Responses

> | name   |  type      | Description      | Required |
> |--------|------------|----------------|---|
> | `userId` |  Integer  | 강사회원 ID     | O |

</details>



<details>
  <summary>
    <code>POST</code> 
    <code><b>/users/join</b></code>
    <code>(학생회원 가입)</code>
  </summary>

##### Parameters

> | name   |  type      | Description      | Required |
> |--------|------------|----------------|---|
> | `name` |  String  | 이름     | O |
> | `email` |  String  | 이메일     | O |
> | `address` |  String  | 주소     |  |
> | `phone` |  String  | 전화번호     |  |

##### Responses

> | name   |  type      | Description      | Required |
> |--------|------------|----------------|---|
> | `userId` |  Integer  | 학생회원 ID     | O |


</details>


<details>
  <summary>
    <code>POST</code> 
    <code><b>/users/login</b></code> 
    <code>(회원 로그인)</code>
  </summary>

##### Parameters

> | name   |  type      | Description      | Required |
> |--------|------------|----------------|---|
> | `email` |  String  | 이메일     | O |
> | `password` |  String  | 비밀번호     | O |

##### Responses

> | name   |  type      | Description      | Required |
> |--------|------------|----------------|---|
> | `token_type` |  string  | 토큰 타입     | O |
> | `access_token` |  string  | 사용자 액세스 토큰 값     | O |
> | `expires_in` |  Integer  | 토큰 만료 시간     | O |

</details>


---

### Lecture

<details>
  <summary>
    <code>GET</code> 
    <code><b>/lectures</b></code> 
    <code>(강의 리스트 조회)</code>
  </summary>

  ##### Header

  > | name   | Description      | Required |
  > |--------|------------------|-----------|
  > | `Authorization` |   사용자 인증 수단, 액세스 토큰 값     | O |
  ##### Responses

  > | name   |  type      | Description      | Required |
  > |--------|------------|----------------|---|
  > | `elements` |  Integer[]  | 강의ID 목록     | O |

</details>

<details>
  <summary>
    <code>GET</code> 
    <code><b>/lectures/{lectureId}</b></code> 
    <code>(강의 열람)</code>
  </summary>

##### Header

> | name   | Description      | Required |
> |--------|------------------|-----------|
> | `Authorization` |   사용자 인증 수단, 액세스 토큰 값     | O |
##### Parameters

> | name   |  type      | Description      | Required |
> |--------|------------|----------------|---|
> | `lectureId` |  Integer  | 강의 ID     | O |

##### Responses

> | name   |  type      | Description      | Required |
> |--------|------------|----------------|---|
> | `title` |  String  | 강의명     | O |
> | `location` |  String  | 강의 장소     | O |

</details>

<details>
  <summary>
    <code>GET</code> 
    <code><b>/lectures/{lectureId}/contents</b></code> 
    <code>(콘텐츠 리스트 조회)</code>
  </summary>

##### Header

> | name   | Description      | Required |
> |--------|------------------|-----------|
> | `Authorization` |   사용자 인증 수단, 액세스 토큰 값     | O |
##### Responses

> | name   |  type      | Description      | Required |
> |--------|------------|----------------|---|
> | `elements` |  Integer[]  | 콘텐츠 ID 목록     | O |

</details>



<details>
  <summary>
    <code>GET</code> 
    <code><b>/lectures/{lectureId}/contents/{contentId}</b></code> 
    <code>(콘텐츠 열람)</code>
  </summary>

##### Header

> | name   | Description      | Required |
> |--------|------------------|-----------|
> | `Authorization` |   사용자 인증 수단, 액세스 토큰 값     | O |
##### Responses

> | name   |  type      | Description      | Required |
> |--------|------------|----------------|---|
> | `content` |  String  | 콘텐츠     | O |
> | `examYn` |  String  | 시험유무     |  |

</details>

<details>
  <summary>
    <code>GET</code> 
    <code><b>/lectures/{lectureId}/score</b></code> 
    <code>(성적 조회)</code>
  </summary>

##### Header

> | name   | Description      | Required |
> |--------|------------------|-----------|
> | `Authorization` |   사용자 인증 수단, 액세스 토큰 값     | O |
##### Responses

> | name   |  type      | Description      | Required |
> |--------|------------|----------------|---|
> | `score` |  String  | 성적     | O |
> | `comment` |  String  | 코멘트     |  |

</details>


<details>
  <summary>
    <code>GET</code> 
    <code><b>/lectures/{lectureId}/rating</b></code> 
    <code>(별점 리스트 조회)</code>
  </summary>

##### Header

> | name   | Description      | Required |
> |--------|------------------|-----------|
> | `Authorization` |   사용자 인증 수단, 액세스 토큰 값     | O |
##### Responses

> | name   |  type      | Description      | Required |
> |--------|------------|----------------|---|
> | `elements` |  Integer[]  | 별점 ID 목록    | O |
> | `average_rating` |  String  | 별점 평균     |  |

</details>


<details>
  <summary>
    <code>GET</code> 
    <code><b>/lectures/{lectureId}/rating/{ratingId}</b></code> 
    <code>(별점 조회)</code>
  </summary>

##### Header

> | name   | Description      | Required |
> |--------|------------------|-----------|
> | `Authorization` |   사용자 인증 수단, 액세스 토큰 값     | O |
##### Responses

> | name   |  type      | Description      | Required |
> |--------|------------|----------------|---|
> | `rating` |  Float  | 별점     | O |
> | `comment` |  String  | 코멘트     |  |

</details>

<br>
<details>
  <summary>
    <code>POST</code> 
    <code><b>/lectures</b></code> 
    <code>(강의 개설)</code>
  </summary>

##### Header

> | name   | Description      | Required |
> |--------|------------------|-----------|
> | `Authorization` |   사용자 인증 수단, 액세스 토큰 값     | O |
##### Parameters

> | name   |  type      | Description      | Required |
> |--------|------------|----------------|---|
> | `title` |  String  | 강의명     | O |
> | `location` |  String  | 장소     |  |

##### Responses

> | name   |  type      | Description      | Required |
> |--------|------------|----------------|---|
> | `lectureId` |  Integer  | 강의 ID     | O |

</details>


<details>
  <summary>
    <code>POST</code> 
    <code><b>/lectures/{lectureId}/enrolment</b></code> 
    <code>(수강 신청)</code>
  </summary>

##### Header

> | name   | Description      | Required |
> |--------|------------------|-----------|
> | `Authorization` |   사용자 인증 수단, 액세스 토큰 값     | O |
##### Parameters

> | name   |  type      | Description      | Required |
> |--------|------------|----------------|---|
> | `userId` |  Integer  | 회원 ID     | O |

##### Responses

> | name   |  type      | Description      | Required |
> |--------|------------|----------------|---|
> | `enrolmentId` |  Integer  | 수강신청 ID     | O |

</details>

<details>
  <summary>
    <code>POST</code> 
    <code><b>/lectures/{lectureId}/matching</b></code> 
    <code>(강사 매칭)</code>
  </summary>

##### Header

> | name   | Description      | Required |
> |--------|------------------|-----------|
> | `Authorization` |   사용자 인증 수단, 액세스 토큰 값     | O |
##### Parameters

> | name   |  type      | Description      | Required |
> |--------|------------|----------------|---|
> | `lectureId` |  Integer  | 강의 ID     | O |
> | `userId` |  Integer  | 강사 회원 ID     | O |

##### Responses

> | name   |  type      | Description      | Required |
> |--------|------------|----------------|---|
> | `matchingId` |  Integer  | 매칭 ID     | O |

</details>

<details>
  <summary>
    <code>POST</code> 
    <code><b>/lectures/{lectureId}/contents</b></code> 
    <code>(컨텐츠 등록)</code>
  </summary>

##### Header

> | name   | Description      | Required |
> |--------|------------------|-----------|
> | `Authorization` |   사용자 인증 수단, 액세스 토큰 값     | O |
##### Parameters

> | name   |  type      | Description      | Required |
> |--------|------------|----------------|---|
> | `content` |  String  | 컨텐츠     | O |
> | `examYn` |  String  | 시험유무     |  |

##### Responses

> | name   |  type      | Description      | Required |
> |--------|------------|----------------|---|
> | `contentId` |  Integer  | 콘텐츠 ID     | O |

</details>

<details>
  <summary>
    <code>POST</code> 
    <code><b>/lectures/{lectureId}/score/{userId}</b></code> 
    <code>(성적 입력)</code>
  </summary>

##### Header

> | name   | Description      | Required |
> |--------|------------------|-----------|
> | `Authorization` |   사용자 인증 수단, 액세스 토큰 값     | O |
##### Parameters

> | name   |  type      | Description      | Required |
> |--------|------------|----------------|---|
> | `score` |  String  | 성적     | O |
> | `comment` |  String  | 코멘트     |  |

##### Responses

> | name   |  type      | Description      | Required |
> |--------|------------|----------------|---|
> | `scoreId` |  Integer  | 성적 ID     | O |

</details>

<details>
  <summary>
    <code>POST</code> 
    <code><b>/lectures/{lectureId}/rating</b></code> 
    <code>(별점 입력)</code>
  </summary>

##### Header

> | name   | Description      | Required |
> |--------|------------------|-----------|
> | `Authorization` |   사용자 인증 수단, 액세스 토큰 값     | O |
##### Parameters

> | name   |  type      | Description      | Required |
> |--------|------------|----------------|---|
> | `rating` |  Float  | 별점     | O |
> | `comment` |  String  | 코멘트     |  |

##### Responses

> | name   |  type      | Description      | Required |
> |--------|------------|----------------|---|
> | `ratingId` |  Integer  | 별점 ID     | O |

</details>

<br>

<details>
  <summary>
    <code>PATCH</code> 
    <code><b>/lectures/{lectureId}</b></code> 
    <code>(강의 노출 상태 변경)</code>
  </summary>

##### Header

> | name   | Description      | Required |
> |--------|------------------|-----------|
> | `Authorization` |   사용자 인증 수단, 액세스 토큰 값     | O |
##### Parameters

> | name   |  type      | Description      | Required |
> |--------|------------|----------------|---|
> | `lectureId` |  Integer  | 강의 ID     | O |

##### Responses

> | name   |  type      | Description      | Required |
> |--------|------------|----------------|---|
> | `exposedYn` |  String  | 강의 노출 유무  | O |

</details>


---

### Community




<details>
  <summary>
    <code>GET</code> 
    <code><b>/articles</b></code> 
    <code>(게시글 리스트 조회)</code>
  </summary>

##### Header

> | name   | Description      | Required |
> |--------|------------------|-----------|
> | `Authorization` |   사용자 인증 수단, 액세스 토큰 값     | O |
##### Responses

> | name   |  type      | Description      | Required |
> |--------|------------|----------------|---|
> | `elements` |  Integer[]  | 게시글 ID 목록     | O |

</details>


<details>
  <summary>
    <code>GET</code> 
    <code><b>/articles/{articleId}/comments</b></code> 
    <code>(댓글 리스트 조회)</code>
  </summary>

##### Header

> | name   | Description      | Required |
> |--------|------------------|-----------|
> | `Authorization` |   사용자 인증 수단, 액세스 토큰 값     | O |
##### Responses

> | name   |  type      | Description      | Required |
> |--------|------------|----------------|---|
> | `elements` |  Integer[]  | 댓글 ID 목록     | O |

</details>

<details>
  <summary>
    <code>GET</code> 
    <code><b>/articles/{articleId}/comments/{commentId}</b></code> 
    <code>(댓글 조회)</code>
  </summary>

##### Header

> | name   | Description      | Required |
> |--------|------------------|-----------|
> | `Authorization` |   사용자 인증 수단, 액세스 토큰 값     | O |
##### Responses

> | name   |  type      | Description      | Required |
> |--------|------------|----------------|---|
> | `content` |  String  | 댓글 내용     | O |
> | `blockYn` |  String  | 블록 유무    | O |

</details>


<details>
  <summary>
    <code>GET</code> 
    <code><b>/articles/{articleId}</b></code> 
    <code>(게시글 조회)</code>
  </summary>

##### Header

> | name   | Description      | Required |
> |--------|------------------|-----------|
> | `Authorization` |   사용자 인증 수단, 액세스 토큰 값     | O |
##### Responses

> | name   |  type      | Description      | Required |
> |--------|------------|----------------|---|
> | `title` |  String  | 게시글 제목     | O |
> | `content` |  String  | 게시글 내용     | O |
> | `blockYn` |  String  | 블록 유무    | O |

</details>

<br>

<details>
  <summary>
    <code>POST</code> 
    <code><b>/articles</b></code> 
    <code>(게시글 작성)</code>
  </summary>

##### Header

> | name   | Description      | Required |
> |--------|------------------|-----------|
> | `Authorization` |   사용자 인증 수단, 액세스 토큰 값     | O |
##### Parameters

> | name   |  type      | Description      | Required |
> |--------|------------|----------------|---|
> | `title` |  String  | 게시글 제목     | O |
> | `content` |  String  | 게시글 내용     | O |

##### Responses

> | name   |  type      | Description      | Required |
> |--------|------------|----------------|---|
> | `articleId` |  Integer  | 게시글 ID     | O |

</details>


<details>
  <summary>
    <code>POST</code> 
    <code><b>/articles/{articleId}</b></code> 
    <code>(댓글 작성)</code>
  </summary>

##### Header

> | name   | Description      | Required |
> |--------|------------------|-----------|
> | `Authorization` |   사용자 인증 수단, 액세스 토큰 값     | O |
##### Parameters

> | name   |  type      | Description      | Required |
> |--------|------------|----------------|---|
> | `content` |  String  | 댓글 내용     | O |

##### Responses

> | name   |  type      | Description      | Required |
> |--------|------------|----------------|---|
> | `commentId` |  Integer  | 게시글 ID     | O |

</details>


<br>


<details>
  <summary>
    <code>PATCH</code> 
    <code><b>/articles/{articleId}</b></code> 
    <code>(게시글 숨김 처리)</code>
  </summary>

##### Header

> | name   | Description      | Required |
> |--------|------------------|-----------|
> | `Authorization` |   사용자 인증 수단, 액세스 토큰 값     | O |
##### Parameters

> | name   |  type      | Description      | Required |
> |--------|------------|----------------|---|
> | `comment` |  String  | 블록 사유     |  |

##### Responses

> | name   |  type      | Description      | Required |
> |--------|------------|----------------|---|
> | `articleId` |  Integer  | 게시글 ID     | O |

</details>


<details>
  <summary>
    <code>PATCH</code> 
    <code><b>/articles/{articleId}/{commentId}</b></code> 
    <code>(댓글 숨김 처리)</code>
  </summary>

##### Header

> | name   | Description      | Required |
> |--------|------------------|-----------|
> | `Authorization` |   사용자 인증 수단, 액세스 토큰 값     | O |
##### Parameters

> | name   |  type      | Description      | Required |
> |--------|------------|----------------|---|
> | `comment` |  String  | 블록 사유     |  |

##### Responses

> | name   |  type      | Description      | Required |
> |--------|------------|----------------|---|
> | `commentId` |  Integer  | 게시글 ID     | O |

</details>
