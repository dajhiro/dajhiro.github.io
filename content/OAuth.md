Google OAuth 설정과 Next.js-NestJS 구조에 대해 설명드리겠습니다.

  Google OAuth Console 설정

  Google Cloud Console에서 OAuth 2.0 클라이언트 ID 설정 시:

  1. 승인된 JavaScript 원본 (Authorized JavaScript origins):
  http://localhost:3000
  http://localhost:4000

  2. 승인된 리디렉션 URI (Authorized redirect URIs):
  http://localhost:4000/auth/google/callback

  Next.js와 NestJS 구조

  프론트엔드와 백엔드는 별도의 서버로 실행됩니다:

  Frontend (Next.js)     Backend (NestJS)
  localhost:3000    →    localhost:4000

  포함시키는 게 아니라 분리된 구조입니다.

  인증 플로우

  1. 사용자가 Next.js에서 "Google 로그인" 버튼 클릭
     ↓
  2. window.location.href = 'http://localhost:4000/auth/google'
     (백엔드로 리다이렉트)
     ↓
  3. Google 로그인 페이지로 이동
     ↓
  4. 로그인 성공 → http://localhost:4000/auth/google/callback
     (백엔드에서 세션 생성)
     ↓
  5. http://localhost:3000/auth/success로 리다이렉트
     (프론트엔드로 돌아옴)
     ↓
  6. Next.js에서 fetch('http://localhost:4000/auth/status', { credentials: 'include' })
     (세션 쿠키로 인증 상태 확인)

  Next.js 예시 코드

  프론트엔드에서 구현할 코드 예시를 보여드릴까요?

  // 로그인 버튼
  <button onClick={() => {
    window.location.href = 'http://localhost:4000/auth/google';
  }}>
    Google 로그인
  </button>

  // 인증 상태 확인
  const res = await fetch('http://localhost:4000/auth/status', {
    credentials: 'include' // 쿠키 포함 중요!
  });