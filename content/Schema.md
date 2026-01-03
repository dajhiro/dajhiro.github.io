User
- id
- email
- googleId 
- createdAt


설명
- id: 내부용 id
- email: 로그인용 email
- googleId: 고유 id
- updatedAt: 이거 왜 필요함? 폐기
- createdAt: 이건 진짜 혹시 모르니까 그냥 두자
- username: 일단 프로토타입에는 빼버리자

---
Post
- id
- title
- content

- source
    - authorName
    - authorImage
    - authorUrl

- sharedBy User @relation("SharedBy", )

- createdAt
- updatedAt

---
Author
- id
- channelId
- name
- profileImage String
- channelUrl

