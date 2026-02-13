# 📚 Elicit Research Agent — OpenClaw Skill

논문 기반 답변을 자동으로 가져오는 OpenClaw 서브에이전트.

[Elicit.com](https://elicit.com)의 1.38억 학술 논문 데이터베이스를 활용하여, 사용자의 질문에 대한 과학적 근거 기반 답변을 제공합니다.

## 작동 방식

```
"커피가 수면에 미치는 영향이 뭐야?"
    ↓ 질문 최적화 (한→영, 학술 용어 변환)
"Effects of caffeine consumption on sleep quality and duration"
    ↓ Elicit.com 브라우저 자동화
    ↓ 검색 결과 스크래핑
📄 논문 5편 요약 + 핵심 발견 + 원본 링크
```

## 설치

1. 이 레포를 클론:
```bash
git clone https://github.com/VoidLight00/elicit-research-agent.git
```

2. 스킬 폴더를 OpenClaw workspace에 복사:
```bash
cp -r elicit-research-agent/skills/elicit-research ~/.openclaw/workspace/skills/
```

3. Elicit.com에 가입 후, OpenClaw 브라우저에서 로그인:
```
에이전트에게: "OpenClaw 브라우저로 elicit.com 열어서 로그인해줘"
```

4. 사용:
```
"논문 검색해줘: 간헐적 단식이 체중 감량에 효과적인가?"
```

## 요구사항

- OpenClaw (브라우저 자동화 지원)
- Elicit.com 계정 (무료 가능)
- OpenClaw 브라우저에서 Elicit 로그인 상태 유지

## 기능

- 한국어/영어 질문 지원
- 질문 자동 최적화 (학술 검색에 적합하게)
- 논문 제목, 저자, 연도, 핵심 발견 추출
- 원본 Elicit 링크 제공

## License

MIT

---
*Built with OpenClaw*
