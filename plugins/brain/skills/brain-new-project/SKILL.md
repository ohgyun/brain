---
name: brain-new-project
description: 새로운 Project를 생성합니다
user-invocable: true
---

# Brain 새 Project 생성

새로운 Project를 생성합니다.

## 실행 절차

1. 새 Project 이름 질문
2. 프로젝트 개요 질문 (비워두기 가능)
3. 주요 규칙 질문 (비워두기 가능)
4. 새 Project 폴더 생성:
   - `~/.brain/projects/{project_name}/rules.md`
   - `~/.brain/projects/{project_name}/context.md`
5. 생성된 파일 확인

## 파일 생성 규칙

- 최소 구성만 생성 (제목만)
- 플레이스홀더, 가이드 텍스트 제거
- 사용자 입력 내용만 반영
- 비워두기 선택 시 해당 섹션 제외
- 나중에 `templates/project/` 참고하여 확장

## 인자 사용

`/brain-new-project {project_name}` 형태로 이름 직접 지정 가능.
