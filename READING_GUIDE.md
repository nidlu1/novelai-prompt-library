# 작업별 읽기 안내

요청한 작업에 나열된 문서와 절을 읽는다. 묶음은 그 안의 모든 절을 포함한다. [공통 추가 조건](#공통-추가-조건)에 해당하면 그 문서도 읽는다.

## 샘플 작업

### RAW → REG

- [REG 범위](workflows/reg.md#목적과-범위), [중요 포인트](workflows/reg.md#raw-접수-시-중요-포인트), [RAW 저장·추출·분류](workflows/reg.md#raw-저장과-추출), [REG 작성·저장·전달](workflows/reg.md#reg-작성저장전달)
- [프롬프트 규칙](formats/prompt_rules.md), [RAW 구조](formats/storage.md#raw-json), [REG 구조](formats/storage.md#reg-json)
- [실행 확인](#실행-확인), [저장](#저장)

REG 결과 이미지를 받으면 [REG 결과 확인](#reg-결과-확인)을 읽는다.

### REG 결과 확인

- [중요 포인트](workflows/reg.md#raw-접수-시-중요-포인트), [결과 확인 절차](workflows/reg.md#결과-확인)
- [RAW 구조](formats/storage.md#raw-json), [REG 구조](formats/storage.md#reg-json), [REG 결과 이미지 연결](formats/storage.md#결과-이미지-연결)
- [실행 확인](#실행-확인), [저장](#저장)

| 추가 작업 | 읽을 곳 |
|---|---|
| 실행문·슬롯 차이 확인 또는 REG 수정 | [REG 범위](workflows/reg.md#목적과-범위), [REG 작성·저장·전달](workflows/reg.md#reg-작성저장전달), [프롬프트 규칙](formats/prompt_rules.md) |
| 확인된 문제를 REFINE에서 교정 | [REG → REFINE](#reg--refine) |

### REG → REFINE

- [입력 비교](workflows/refine.md#입력과-비교), [최초 제안과 생성](workflows/refine.md#최초-제안과-생성)
- [REG 결과 확인 절차](workflows/reg.md#결과-확인), [REG 결과 이미지 연결](formats/storage.md#결과-이미지-연결)
- [실행 확인](#실행-확인), [저장](#저장), [REFINE 구성](#refine-구성), [REFINE 출력](#refine-출력)

REG 자체의 오류를 고칠 때는 [REG 결과 확인](#reg-결과-확인)의 수정 경로를 읽는다.

### REFINE 세트 출력

- [REFINE 출력](#refine-출력)

실행문이나 묶음을 변경할 때는 [REFINE 결과 피드백·재정제](#refine-결과-피드백재정제)를 읽는다.

### REFINE 결과 피드백·재정제

- [피드백과 승인](workflows/refine.md#피드백과-승인), [REFINE 결과 이미지 연결](formats/storage.md#refine-결과-이미지-연결)
- [실행 확인](#실행-확인), [REFINE 출력](#refine-출력)

| 추가 작업 | 읽을 곳 |
|---|---|
| 태그나 묶음 수정 | [REFINE 구성](#refine-구성) |
| 결과 이미지 연결 또는 수정본 저장 | [저장](#저장) |
| 샘플 승인 요청 | [REG·REFINE 샘플 승인](#regrefine-샘플-승인) |

### REG·REFINE 샘플 승인

- REG는 [REG 결과 확인](workflows/reg.md#결과-확인)과 [REG 구조](formats/storage.md#reg-json), REFINE은 [피드백과 승인](workflows/refine.md#피드백과-승인)과 [REFINE 결과 이미지 연결](formats/storage.md#refine-결과-이미지-연결)을 읽는다.
- [샘플 최종 승인](workflows/refine.md#샘플-최종-승인), [최종 승인 기록](formats/storage.md#최종-승인-기록), [실행 확인](#실행-확인), [저장](#저장)

묶음을 보완하거나 다시 구성할 때는 [REFINE 결과 피드백·재정제](#refine-결과-피드백재정제)를 읽는다.

### 승인 후 시드 변주 기록

- [시드 변주 절차](workflows/refine.md#승인-후-시드-변주), [묶음별 저장과 조립](workflows/refine.md#묶음별-저장과-조립)
- [묶음 구조](formats/storage.md#refine-json), [결과 이미지의 특징 기록](formats/storage.md#refine-결과-이미지-연결)
- [실행 확인](#실행-확인), [저장](#저장)

| 조건 | 읽을 곳 |
|---|---|
| REG 승인본의 결과 연결 | [REG 결과 이미지 연결](formats/storage.md#결과-이미지-연결) |
| 승인된 실행의 교정 요청 | [REFINE 구성](#refine-구성) |
| 교정본의 승인 요청 | [REG·REFINE 샘플 승인](#regrefine-샘플-승인) |

## 패키지 등록 작업

- [지정한 샘플에서 패키지 등록](workflows/package_registration.md), [패키지 구성 조회](#패키지-구성-조회)
- [최종 승인 기록](formats/storage.md#최종-승인-기록), [재사용 패키지 구조](formats/storage.md#재사용-패키지-json), [보존 기준](formats/prompt_rules.md#보존-기준), [저장](#저장)

## 패키지 이미지 작업

### 패키지 대표·서브 이미지 프롬프트 요청

- [목적과 범위](workflows/package_images.md#목적과-범위), [요청과 구성 확인](workflows/package_images.md#요청과-구성-확인), [생성 구성](workflows/package_images.md#생성-구성), [프롬프트 제출과 생성](workflows/package_images.md#프롬프트-제출과-생성)
- [패키지 자체 이미지](formats/storage.md#패키지-자체-이미지), [실행 확인](#실행-확인), [패키지 구성 조회](#패키지-구성-조회)

패키지 태그 변경을 요청받으면 [묶음 구성과 교정](workflows/refine.md#묶음-구성과-교정)과 [재정제 경로](#refine-결과-피드백재정제)를 읽는다.

### 패키지 대표 지정·교체·서브 추가·해제

- [결과 확인과 명시적 선택](workflows/package_images.md#결과-확인과-명시적-선택), [교체와 해제](workflows/package_images.md#교체와-해제)
- [패키지 자체 이미지](formats/storage.md#패키지-자체-이미지), [실행 확인](#실행-확인), [HTML 표시](viewer/README.md#패키지-이미지-표시)
- [이미지를 등록할 패키지의 규약](AGENTS.md#폴더별-자료)과 해당 패키지의 실제 구성

## 뷰어 작업

### HTML 구성기 개선·검토

- [뷰어 안내와 구성기 명세](viewer/README.md), [청크 규약](library/chunks/FORMAT.md), [프롬프트 규칙](formats/prompt_rules.md)
- [최종 승인 기록](formats/storage.md#최종-승인-기록), [REG 구조](formats/storage.md#reg-json), [REFINE 구조](formats/storage.md#refine-json), [재사용 패키지 구조](formats/storage.md#재사용-패키지-json)

| 추가 작업 | 읽을 곳 |
|---|---|
| 샘플 분류 확인 | [RAW 분류](workflows/reg.md#raw-분류), [저장 위치](formats/storage.md#저장-위치) |
| 샘플 재정제 | [REFINE 결과 피드백·재정제](#refine-결과-피드백재정제) |
| 승인 결과 저장 | [REG·REFINE 샘플 승인](#regrefine-샘플-승인) |

## 공통 추가 조건

| 조건 | 읽을 곳 |
|---|---|
| 용어의 뜻이 불명확할 때 | [용어 정리서](GLOSSARY.md) |
| 도구를 사용하거나 장면 전체 청크·최종 승인 구조를 다룰 때 | [적용 상태](formats/storage.md#적용-상태) |
| API로 이미지 생성을 요청받았을 때 | [선택적 API 생성](workflows/api_generation.md) |
| 패키지 묶음을 구성·비교·저장·재사용할 때 | [패키지 구성 조회](#패키지-구성-조회) |
| 메타데이터 추출 방법이나 지원 형식을 확인할 때 | [RAW 저장과 추출](workflows/reg.md#raw-저장과-추출) |
| 저장 규약을 읽고도 JSON 필드나 중첩 구조가 불명확할 때 | [JSON 예시](formats/storage_examples.md)의 해당 절 |

## 읽기 묶음

### 실행 확인

- [실행값과 원본 메타데이터](formats/storage.md#실행값과-원본-메타데이터), [자동 프리셋과 실제 실행문](formats/storage.md#자동-프리셋과-실제-실행문), [실행문 대조](formats/storage.md#실행문-대조)

### 저장

- [저장 위치](formats/storage.md#저장-위치), [샘플 인덱스](formats/storage.md#샘플-인덱스), [저장 시 확인](formats/storage.md#저장-시-확인)

### REFINE 구성

- [중요 포인트](workflows/reg.md#raw-접수-시-중요-포인트), [태그 역할](workflows/refine.md#용어), [교정 방향](workflows/refine.md#방향-선택)
- [묶음 구성과 교정](workflows/refine.md#묶음-구성과-교정), [프롬프트 규칙](formats/prompt_rules.md)

태그를 추가하거나 대체할 때는 [태그 검색](danbooru-tags/README.md#태그-검색)을 읽는다.

### REFINE 출력

- [묶음별 저장과 조립](workflows/refine.md#묶음별-저장과-조립), [REFINE 세트 출력](workflows/refine.md#refine-세트-출력), [REFINE 구조](formats/storage.md#refine-json)
- [실행값과 원본 메타데이터](formats/storage.md#실행값과-원본-메타데이터), [자동 프리셋](formats/storage.md#자동-프리셋과-실제-실행문), [정렬 표기](formats/prompt_rules.md#정렬-표기)

### 패키지 구성 조회

대상 패키지의 [규약과 목록](AGENTS.md#폴더별-자료)을 읽고, 목록에 연결된 JSON에서 해당 구성을 확인한다. 조회·검증 방법은 [패키지 조회와 검증](formats/storage.md#패키지-조회와-검증)을 따른다.
