# Brain - Role-based Decision Making System

Claude가 당신의 가치관과 프로젝트 규칙에 맞춰 일관된 결정을 내릴 수 있도록 돕는 의사결정 시스템입니다.

## 핵심 기능

- **Role**: 당신의 핵심 가치와 원칙을 정의 (예: Developer, Product Manager, Founder)
- **Project**: 프로젝트별 구체적인 규칙과 컨텍스트 저장
- **Log**: 의사결정 기록을 통한 패턴 발견 및 시스템 진화

## 빠른 시작

### 1. 플러그인 설치

```bash
# 마켓플레이스 추가
claude plugin marketplace add ohgyun/brain

# 플러그인 설치
claude plugin install brain
```

### 2. 첫 세션 시작

```bash
# Claude Code 실행
claude

# Brain 세션 시작
/brain
```

처음 실행 시 Role과 Project를 생성하라는 안내가 나옵니다. `/brain-new-role`, `/brain-new-project` 명령으로 생성할 수 있습니다.

모든 데이터는 `~/.brain/` 디렉토리에 마크다운 파일로 저장됩니다.

## 주요 명령어

| 명령 | 설명 |
|-----|------|
| `/brain` | 세션 시작 - Role과 Project 선택 |
| `/brain-status` | 현재 적용된 Role/Project 확인 |
| `/brain-log` | 현재 대화를 로그로 저장 |
| `/brain-update` | 로그 분석 후 rules/values 업데이트 제안 |
| `/brain-new-role` | 새 Role 생성 |
| `/brain-new-project` | 새 Project 생성 |

## 작동 방식

```
1. Role과 Project 선택
   ↓
2. values/rules가 Claude 컨텍스트에 로드
   ↓
3. Claude가 이를 기반으로 결정 내림
   ↓
4. 의미있는 결정을 로그로 기록 (/brain-log)
   ↓
5. 로그에서 패턴 발견 후 rules/values 진화 (/brain-update)
```

## 데이터 구조

모든 데이터는 `~/.brain/`에 저장됩니다:

```
~/.brain/
├── roles/              # Role 정의
│   └── {role}/
│       └── values.md   # 핵심 가치, 원칙
│
├── projects/           # Project 정의
│   └── {project}/
│       ├── rules.md    # 의사결정 규칙
│       └── context.md  # 프로젝트 배경
│
└── logs/               # 세션 로그
    └── {project}/
        └── YYYY-MM-DD_NNN.md
```

### Role vs Project

| 레이어 | 의미 | 예시 |
|--------|------|------|
| **Role** | "나는 누구인가" | Developer: "실용성 > 완벽성" |
| **Project** | "이 상황에서 어떻게 하는가" | Brain 프로젝트: "작성 부담 최소화" |

## GitHub 백업 (선택사항)

`~/.brain/` 데이터를 GitHub에 백업하고 싶다면:

```bash
# ~/.brain 디렉토리로 이동
cd ~/.brain

# Git 저장소 초기화
git init
git add .
git commit -m "Initial brain data"

# GitHub 리포지토리 생성 후 연결
git remote add origin git@github.com:yourusername/brain-data.git
git push -u origin main
```

**템플릿 리포지토리:** [brain-data](https://github.com/ohgyun/brain-data) - 참고용 예시입니다.

## 개발

### 로컬 테스트

```bash
# 플러그인 디렉토리에서 직접 실행
cd /path/to/brain
claude --plugin-dir .
```

### 검증

```bash
# 플러그인 검증
claude plugin validate plugins/brain/.claude-plugin/plugin.json

# 마켓플레이스 검증
claude plugin validate .claude-plugin/marketplace.json
```

## 라이선스

MIT
