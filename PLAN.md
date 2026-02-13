# Elicit Research Agent — 논문 기반 답변 서브에이전트

## 개요
사용자의 질문을 받아 Elicit.com에서 논문 기반 답변을 가져오는 OpenClaw 서브에이전트.

## 작동 흐름

```
사용자 질문
    ↓
[1단계] 질문 분석 & 확장
    - 사용자의 한국어/영어 질문을 학술 검색에 최적화
    - 키워드 추출, 동의어 확장, 영어 변환
    - 예: "커피가 건강에 좋아?" → "Effects of coffee consumption on health outcomes systematic review"
    ↓
[2단계] Elicit 브라우저 자동화
    - OpenClaw 브라우저(profile=openclaw)로 elicit.com 접속
    - 검색창에 최적화된 질문 입력
    - 결과 페이지 대기 & 스크래핑
    ↓
[3단계] 결과 정리 & 출력
    - 논문 제목, 저자, 연도, 핵심 발견 추출
    - 사용자에게 구조화된 답변 전달
    - 원본 Elicit 링크 포함
```

## 구현 방식

### Option A: 브라우저 자동화 (Primary)
- OpenClaw `browser` 도구로 Elicit 웹 UI 직접 조작
- 장점: API 키 불필요, 무료 티어 활용 가능
- 단점: UI 변경 시 깨질 수 있음, 속도 느림

### Option B: Elicit API (Backup)
- Elicit이 API 제공 시 직접 호출
- 현재 공개 API 확인 필요

## 기술 스택

| 구성요소 | 기술 |
|---------|------|
| 에이전트 프레임워크 | OpenClaw `sessions_spawn` |
| 브라우저 자동화 | OpenClaw `browser` tool (profile=openclaw) |
| 질문 최적화 | LLM 프롬프트 (에이전트 자체) |
| 배포 형태 | OpenClaw Skill 패키지 |

## 스킬 구조

```
skills/elicit-research/
├── SKILL.md              # 스킬 사용 가이드 (다른 사용자도 바로 적용 가능)
├── SUBAGENT_TEMPLATE.md  # 서브에이전트 프롬프트 템플릿
└── README.md             # 설치 & 사용법 (GitHub 공개용)
```

## 구현 단계

### Phase 1: 기본 동작 (MVP)
- [ ] Elicit 회원가입/로그인 자동화 (또는 수동 로그인 유지)
- [ ] 검색 페이지 접근 & 질문 입력 자동화
- [ ] 검색 결과 스크래핑
- [ ] 결과 포맷팅 & 출력
- **체크포인트: `v0.1-mvp`**

### Phase 2: 질문 최적화
- [ ] 한국어 → 영어 학술 질문 변환
- [ ] 질문 구체화/확장 로직
- [ ] 다중 검색어 시도 (결과 부족 시)
- **체크포인트: `v0.2-query-optimization`**

### Phase 3: 스킬 패키지화
- [ ] SKILL.md 작성 (OpenClaw 스킬 표준)
- [ ] SUBAGENT_TEMPLATE.md 작성
- [ ] README.md (설치/사용법)
- [ ] 다른 사용자 테스트 가이드
- **체크포인트: `v0.3-skill-package`**

### Phase 4: 고도화
- [ ] Elicit Report 기능 활용 (심층 분석)
- [ ] 결과 캐싱 (같은 질문 재검색 방지)
- [ ] Obsidian 저장 연동
- **체크포인트: `v1.0-stable`**

## 사전 요구사항

1. **Elicit 계정** — 무료 계정으로 기본 검색 가능 (월 10회 무료 리포트)
2. **OpenClaw** — 브라우저 자동화 지원 버전
3. **Elicit 로그인 상태** — OpenClaw 브라우저에서 미리 로그인 필요

## 다른 사용자 적용 방법

1. GitHub에서 스킬 폴더 다운로드
2. `~/.openclaw/workspace/skills/elicit-research/` 에 배치
3. Elicit.com 계정 생성 & OpenClaw 브라우저에서 로그인
4. 에이전트에게 "논문 검색해줘: [질문]" 으로 사용

## 주의사항
- Elicit 무료 티어: 기본 검색 무제한, 리포트 월 10회
- 브라우저 자동화는 Elicit ToS 확인 필요
- UI 변경 시 스크래핑 코드 업데이트 필요

---
*Kraken.Ver — 2026-02-13*
