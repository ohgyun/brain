# Brain System

이 리포지토리는 Role 기반 의사결정 시스템입니다.

## 세션 시작

새 세션을 시작할 때 `/brain`을 실행하여 Role과 Project를 선택하세요.

## 사용 가능한 명령

| 명령 | 설명 |
|-----|------|
| `/brain` | 세션 시작 - Role과 Project 선택 (추가 선택도 가능) |
| `/brain-status` | 현재 적용된 Role/Project 확인 |
| `/brain-log` | 대화 요약을 로그로 저장 |
| `/brain-update` | 로그 분석하여 rules/values 업데이트 |
| `/brain-new-role` | 새 Role 생성 |
| `/brain-new-project` | 새 Project 생성 |

## 구조

- `roles/`: Role 정의 (values.md)
- `projects/`: Project 정의 (rules.md, context.md)
- `logs/`: 세션 로그 ({project}/YYYY-MM-DD_NNN.md)

## Git

- 커밋 메시지는 한글로 작성