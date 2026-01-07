구현 내용:
  1. .env.example:18-31

  환경 변수 추가:
  - NODE_ENV - 환경 구분 (development/production)
  - FRONTEND_URL - 프론트엔드 URL (리다이렉트용)
  - CORS_ORIGINS - 허용할 도메인 리스트 (쉼표로 구분)

  2. src/main.ts:12-73

  CORS 설정:
  - 환경 변수에서 허용할 origin 리스트 읽기
  - 동적 origin 검증 (화이트리스트 방식)
  - credentials, methods, headers 설정
  - 차단된 요청은 콘솔에 경고 출력

  Session Cookie 설정:
  - secure: 프로덕션에서만 HTTPS 강제
  - sameSite: 프로덕션에서 'none' (크로스 도메인)
  - proxy: Railway/Cloudflare 프록시 신뢰

  시작 로그:
  - 환경, 포트, CORS origins, 쿠키 설정 출력

  ---
  환경별 설정 가이드:

  로컬 개발 (.env)

  NODE_ENV=development
  FRONTEND_URL=http://localhost:3000
  CORS_ORIGINS=http://localhost:3000,http://localhost:5173
  GOOGLE_CALLBACK_URL=http://localhost:4000/auth/google/callback

  Railway 프로덕션 (환경 변수)

  NODE_ENV=production
  FRONTEND_URL=https://textube.io
  CORS_ORIGINS=https://textube.io,https://www.textube.io
  GOOGLE_CALLBACK_URL=https://api.textube.io/auth/google/callback
  SESSION_SECRET=<강력한-랜덤-문자열>

  ---
  주의사항:

  1. Cloudflare 설정

  - api.textube.io → Railway CNAME 설정 완료 확인
  - SSL/TLS 모드: Full (strict) 권장

  2. Google OAuth

  - Google Console에서 승인된 리디렉션 URI 추가:
    - https://api.textube.io/auth/google/callback
    - http://localhost:4000/auth/google/callback (개발용)

  3. 프론트엔드 설정

  - API 요청 시 credentials: 'include' 필수:
  fetch('https://api.textube.io/posts', {
    credentials: 'include'
  })

  4. 테스트

  로컬에서 서버 시작 시 다음과 같이 출력됩니다:
  🚀 Application is running in DEVELOPMENT mode
  📡 Server listening on port 4000
  🌐 CORS enabled for origins: http://localhost:3000, http://localhost:5173
  🍪 Cookies: secure=false, sameSite=lax

  환경 분리 완료!