# draft-design 스킬 설치 안내

Claude Code에서 `/draft-design`으로 호출하는 AWS 제안·안내 스킬입니다.

## 설치

다음 위치 중 하나에 `SKILL.md`를 둡니다.

- 개인 전역: `~/.claude/skills/draft-design/SKILL.md`
- 프로젝트 한정: `<프로젝트>/.claude/skills/draft-design/SKILL.md`

## 사용

```
/draft-design <질문>
```

예: `/draft-design ALB랑 NLB 중 뭘 써야 해?`

## 검증기 경고에 대하여

이 스킬은 frontmatter에 `disable-model-invocation: true`를 사용합니다. 이는
Claude가 임의로(자율) 이 스킬을 호출하지 않고 **사용자가 `/draft-design`으로 명시 호출할 때만**
실행되게 하는, Claude Code가 읽는 정식 필드입니다.

skill-creator의 패키징 검증기(구버전)는 이 키를 아직 허용 목록에 두지 않아
`Unexpected key(s) ... disable-model-invocation` 경고를 낼 수 있습니다. 이는 **패키저 검증기의 한계**일 뿐,
Claude Code 동작에는 문제가 없습니다. 그래서 이 스킬은 검증기를 우회해 패키징했습니다.
최상위 키를 유지해야 자율 호출 차단이 실제로 적용되므로, `metadata` 안으로 옮기지 않습니다.
