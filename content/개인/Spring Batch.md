[Spring Batch란 무엇인가 - Claude](https://claude.ai/chat/a8e96e86-a79b-4f29-83f6-7e7a4fdf80c4)
batch processing을 위함

대량의 데이터를 일정한 주기나 트리거에 따라 자동으로 처리
- **Job**: 전체 배치 작업 단위 (예: "매일 자정 매출 집계")
	- **Step**: Job을 구성하는 개별 처리 단계. 하나의 Job은 여러 Step으로 구성 가능

Chunk 기반 처리: ItemReader ⇒ ItemProcessor ⇒ ItemWriter
- **ItemReader**: 데이터를 읽음 (DB, 파일, API 등)
- **ItemProcessor**: 읽은 데이터를 가공/변환 (선택사항)
- **ItemWriter**: 처리된 데이터를 저장/출력

일정 개수(chunk) 단위로 묶어서 처리

### 그래서 왜 쓰는가
대량의 데이터를 다룰 때, 일반적인 서비스 로직으로 처리하면 다음의 까다로운:
- 메모리 문제
- 트랜젝션 관리
- 실패 복구

Spring Batch는 다음의 표준화된 방식으로:
- 재시작(Restart): 실패한 지점부터 다시 시작 가능
- 재시도(Retry) / 스킵(Skip): 특정 에러는 재시도하거나 건너뛰기 처리
- 메타데이터 관리: Job 실행 이력, 상태, 파라미터를 DB에 자동 저장 (JobRepository)
- 트랜잭션 관리: chunk 단위 커밋/롤백 자동 처리
- 병렬/분산 처리: 멀티스레드, 파티셔닝, 원격 청킹 지원

### 대표적인 사용 사례
- 대량 데이터 마이그레이션 (DB → DB, 파일 → DB)
- 정기 집계/통계 작업 (일별/월별 매출 집계 등)
- 외부 API와 대량 데이터 동기화
- 대용량 CSV/Excel 파일 import/export
- 정산, 청구 같은 금융 배치 작업

---
### NestJS 대응
















