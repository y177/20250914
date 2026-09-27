# Supabase 작업 폴더

- 이 폴더는 yunclinic 조직의 Supabase 프로젝트(서울 리전)에 연결되어 있다.
- 테이블 변경은 대시보드에서 직접 하지 말고, `supabase migration new`로 SQL 파일을 만든 뒤 `supabase db push`로 반영한다.
- `db push` 전에는 무엇이 바뀌는지 먼저 설명하고 확인을 받는다.
- 새 테이블에는 항상 RLS를 켠다.
- 토큰, 비밀번호, API 키는 파일에 적지 않는다.
