[[Next.js 빠른 시작]]
[[튜토리얼/Next.js 튜토리얼]]
### 질의응답
- [?] 파일 위치는 알아서 찾는겨?
- [>] `tsconfig.json` 파일 설정을 통해 해결
    - `"paths"`
    - `"baseUrl"`

tsconfig.json
```json
{
  "compilerOptions": {
    "baseUrl": "src/"
  }
}
```

- [i] public 폴더 구성: 이미지, 폰트 파일 등: 알아서 참조된다
- [?] 아직 tsconfig이 앱 전체 구성을 설정하는지는 모르겠다

