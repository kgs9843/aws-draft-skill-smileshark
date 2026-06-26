# aws-draft-skill-smileshark

SmileShark용 Claude Code 스킬 모음입니다.

---

## 스킬 목록

| 스킬 | 호출 명령 | 설명 |
|------|-----------|------|
| [draft-design](./aws-draft-design/) | `/draft-design` | AWS 인프라 설계 선택지 비교 및 일반 안내 |

---

## draft-design

AWS 인프라 관련 질문에 대해 공식 문서를 근거로 여러 설계 선택지를 비교하거나, 설정 절차·기능 사용법을 안내하는 스킬입니다.

**두 가지 모드**로 동작합니다.

- **모드 1 — 설계 비교**: 비용 최적화·성능·운영 단순성·역발상·극단 최적화 등 5개 슬롯의 선택지를 비교표와 함께 제시하고, Claude의 선택을 참고용으로 덧붙입니다.
- **모드 2 — 일반 안내**: 크레딧 신청, 서비스 설정 절차, 기능 사용법 등을 AWS 콘솔 기준으로 안내합니다.

결과는 작업 디렉토리에 `.md` 파일로 저장됩니다.

### 설치

```bash
# 개인 전역 설치 (모든 프로젝트에서 사용)
cp aws-draft-design/SKILL.md ~/.claude/skills/draft-design/SKILL.md

# 또는 프로젝트 한정 설치
cp aws-draft-design/SKILL.md <프로젝트>/.claude/skills/draft-design/SKILL.md
```

### 사용

```
/draft-design <질문>
```

**예시**

```
/draft-design ALB랑 NLB 중 뭘 써야 해?
/draft-design VPC peering vs Transit Gateway 선택지 비교해줘
/draft-design RDS 멀티AZ 구성 옵션 비교해줘
/draft-design AWS 크레딧 신청 방법 알려줘
```

---

## 참고

- 근거 우선순위: AWS 공식 문서 → SmileShark 기술 가이드 → AWS 공식 블로그 → 대기업 테크 블로그
- 모든 URL은 `web_fetch`로 실존 여부를 확인한 뒤 보고서에 포함합니다.
- SmileShark 기술 가이드: https://smilesharkhelp.zendesk.com/hc/ko/sections/5433312593935
