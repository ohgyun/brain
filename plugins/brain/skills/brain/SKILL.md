---
name: brain
description: 세션 시작 - Role과 Project를 선택하여 컨텍스트를 로드합니다
user-invocable: true
---

# Brain 세션 시작

Role과 Project를 선택하고 컨텍스트를 로드합니다.

## 실행 절차

1. 이미 세션이 시작된 경우:
   - 현재 Role/Project 표시
   - "추가로 선택하시겠습니까?" 질문
   - "없음" 선택 시 기존 유지
2. `~/.brain/roles/`, `~/.brain/projects/` 폴더에서 목록 확인
3. 사용자에게 Role 선택 질문 (다중 선택 가능, 선택 안 함도 가능)
4. 사용자에게 Project 선택 질문 (선택 안 함도 가능)
5. 선택된 Role의 `values.md` 읽기
6. 선택된 Project의 `rules.md`, `context.md` 읽기
7. 적용된 컨텍스트 요약

## 다중 Role 적용

- 여러 Role 선택 시, values.md의 "적용 도메인" 확인
- 각 Role은 해당 도메인의 의사결정에 적용
