---
name: brain-new-role
description: 새로운 Role을 생성합니다
user-invocable: true
---

# Brain 새 Role 생성

새로운 Role을 생성합니다.

## 실행 절차

1. 새 Role 이름 질문
2. 적용 도메인 질문 (예: "코드, 아키텍처, 기술 의사결정")
3. 핵심 가치 질문 (비워두기 가능)
4. `~/.brain/roles/{role_name}/values.md` 생성
5. 생성된 파일 확인

## 파일 생성 규칙

- 최소 구성만 생성 (제목 + 적용 도메인)
- 플레이스홀더, 가이드 텍스트 제거
- 사용자 입력 내용만 반영
- 비워두기 선택 시 해당 섹션 제외
- 나중에 `templates/role/values.md` 참고하여 확장

## 인자 사용

`/brain-new-role {role_name}` 형태로 이름 직접 지정 가능.
