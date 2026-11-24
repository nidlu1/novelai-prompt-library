# 용어 정리서

사용자의 표현을 현재 작업과 문서에 연결하는 용어 정리서다.

요청문의 영문 대소문자·띄어쓰기 차이는 구분하지 않는다. 세부 절차와 규칙은 연결된 정본을 따른다.

## 태그와 저장 단위

| 사용자 표현 | 뜻·연결 |
|---|---|
| 추상화태그, 추상 의도 | 장면의 상위 개념·의도. [태그 역할](workflows/refine.md#용어) |
| 핵심태그, 핵심개념태그, 코어 | 세부 표현을 묶는 대표 개념. [태그 역할](workflows/refine.md#용어) |
| 디테일태그, 세부태그, 상세태그, 구체화태그 | 개념의 구체적인 모습·조건. [태그 역할](workflows/refine.md#용어) |
| 프롬, 프롬프트, Positive | 생성할 내용을 지정하는 Prompt 문자열 |
| UC, 네거티브 | 억제할 내용을 지정하는 문자열 |
| base 프롬·base UC, 캐릭터 프롬·캐릭터 UC | BASE·Character의 입력 칸. [입력 슬롯](formats/prompt_rules.md#입력-슬롯과-재사용-묶음) |
| 인원 앵커, 카운팅 | 인원·개체 수 태그. [입력 슬롯](formats/prompt_rules.md#입력-슬롯과-재사용-묶음) |
| 스타일, 그림체 | 표현 방식의 묶음. [스타일 FORMAT](library/styles/FORMAT.md) |
| 캐릭터, 캐릭터.json | 인물의 정체성·외형·함께 유지할 의상 묶음. [캐릭터 FORMAT](library/characters/FORMAT.md) |
| 청크, chunk | 스타일·캐릭터를 제외한 전체 Prompt·UC를 하나로 저장·재사용하는 장면 묶음. [청크 FORMAT](library/chunks/FORMAT.md) |
| 기타, 이외 | 기존 실행에서 스타일·캐릭터·부분 청크에 포함하지 않았던 표현. 신규 작업에서는 모두 장면 청크에 포함. [묶음 구성](workflows/refine.md#묶음-구성과-교정) |
| 샘플, sample, 사례 | RAW·REG·선택적 REFINE과 결과·최종 승인 기록을 모은 사례. [저장 규약](formats/storage.md) |
| 표시 그룹, 샘플 모음, HTML 묶음 | 같은 종류의 관련 항목을 카드 하나에 모으는 조회 단위. 실행·승인·패키지의 정체성은 개별 항목에 유지. [표시 그룹](viewer/README.md#묶음-목록과-구성-선택) |
| 스타일·캐릭터·청크 패키지 | 기본 ID별 JSON에 기본본과 바리에이션의 승인 묶음을 저장한 자료. [패키지 형식](formats/storage.md#재사용-패키지-json) |
| 최종 승인 이미지 | 샘플의 `approval.json`이 선택한 REG 또는 REFINE 이미지. [최종 승인](formats/storage.md#최종-승인-기록) |
| 대표 이미지, 서브 이미지 | 패키지의 특정 구성에 직접 소속되고 사용자가 채팅으로 선택한 이미지. [자체 이미지](formats/storage.md#패키지-자체-이미지) |
| 패키지 이미지 생성 정보 | 대표·서브 이미지에 딸린 실제 전체 입력문·설정과 사용 패키지 연결. |
| 패키지 출처, sources | 패키지 태그의 근거인 승인된 REG 또는 REFINE과 해당 단계 이미지. |

## 작업 표현

| 사용자 표현 | 해석·작업 |
|---|---|
| 1단계 작업, raw 이미지 분석, reg 분석, reg화, 정규화 | RAW → REG. [reg.md](workflows/reg.md) |
| REG 이미지 전달, RAW와 REG 비교 피드백, REG 이미지 생성 검증 | 생성된 REG의 실제 실행값과 RAW 대비 중요한 차이 확인. [REG 결과 확인](workflows/reg.md#결과-확인) |
| 2단계 작업, refine 작업, 리파인, 정제 | 확인된 충돌 또는 중요한 특징의 미구현을 해결하는 선택적 최소 교정. 문제가 없으면 REG에서 승인. [REFINE](workflows/refine.md) |
| REFINE 세트, 리파인 세트, REFINE 세트 출력 | 교정 실행의 스타일·캐릭터·장면 청크와 조립한 최종 입력본. [출력](workflows/refine.md#refine-세트-출력) |
| 변주용, 변주 확인, 핵심 개념 보강 | 사용자가 별도로 지정하는 표현 변경·탐색. [교정 범위](workflows/refine.md#방향-선택) |
| 디테일용, RAW 구현, RAW 재현 | 유지할 중요한 특징의 미구현 여부와 요청 범위를 확인해 필요한 부분만 교정. [교정 범위](workflows/refine.md#방향-선택) |
| REFINE 이미지 전달, 작업본 피드백 | 실제 실행과 묶음별 결과 확인·재정제. [피드백과 승인](workflows/refine.md#피드백과-승인) |
| REFINE 재정제 | 이미지 피드백을 바탕으로 현재 REFINE의 Prompt·UC 또는 묶음 구성을 수정. [피드백과 승인](workflows/refine.md#피드백과-승인) |
| REG 승인, REFINE 확정, 샘플 승인 | 해당 실행과 기준 이미지를 기록하고 샘플 작업을 마친다. [샘플 최종 승인](workflows/refine.md#샘플-최종-승인) |
| 샘플에서 스타일·캐릭터·청크 저장, 패키지 등록 | 사용자가 지정한 샘플에서 선택한 묶음을 등록한다. [패키지 등록](workflows/package_registration.md) |
| 그림 피드백 | 현재 단계의 이미지·태그 보완 요청 |
| `runs` 초기화, API 생성 작업본 초기화 | `runs/novelai/`에서 지정한 실행 폴더를 비운다. 삭제 범위에는 실행 기록(`manifest.json`)과 해당 실행에서 받은 이미지 원본이 포함된다. [생성 작업본](workflows/api_generation.md#생성-작업본) |
| 플로우 피드백, 워크플로우 변경, 명세 수정 | 작업 절차·문서·처리 코드의 개선 요청 |
| 스타일·캐릭터·청크 대표 이미지 만들기, 대표 이미지 프롬프트, 서브 이미지 프롬프트 | 기존 패키지 구성으로 전체 생성 프롬프트를 제출. [패키지 이미지](workflows/package_images.md) |
| 이걸 대표로, 대표 지정·교체, 서브 추가·해제 | 명시한 소유 패키지 구성의 이미지 표시를 지정·변경. [결과 선택](workflows/package_images.md#결과-확인과-명시적-선택) |

## 문서·자료 별칭

| 사용자 표현 | 현재 위치 |
|---|---|
| agent.md, 에이전트 지침 | [AGENTS.md](AGENTS.md) |
| 포맷/프롬프트, 프롬프트.md, 프롬프트 룰, prompt_rules | [formats/prompt_rules.md](formats/prompt_rules.md) |
| 포맷/스토리지, 스토리지.md, storage | [formats/storage.md](formats/storage.md) |
| 샘플 index, 샘플 인덱스 | [library/samples/INDEX.MD](library/samples/INDEX.MD) |
| 단부루 태그, reclassified, danbooru-tags-classified, 태그 라이브러리 | [태그 검색과 사전 선택](danbooru-tags/README.md#태그-검색) |

## 문맥이 필요한 표현

- 구조화·스트럭처·STRUCTURED가 원문 정규화·분류·정렬을 뜻하면 REG로 해석한다.
- core·detail을 REFINE 방향으로 말하면 각각 변주·RAW 재현 문맥으로 해석한다. 태그 역할을 가리키는 경우에는 [태그와 저장 단위](#태그와-저장-단위)를 따른다.
- 의도·정체성은 문맥에 따라 장면 의도나 인물 식별을 뜻한다.
- 저장·패키지처럼 대상이 여러 개인 표현은 현재 요청으로 범위를 정한다. 해석에 따라 작업이 달라지고 문맥으로 구분되지 않을 때만 확인한다.
