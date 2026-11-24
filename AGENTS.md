# 프로젝트 목표

NovelAI 이미지 생성에 사용한 프롬프트와 설정을 보존한다. 승인된 샘플에서 사용자가 지정한 스타일·캐릭터·장면 구성을 다음 이미지 생성에 재사용할 수 있게 저장한다.

## Markdown 명세서의 구조

`파일#절`은 해당 절과 하위 절을 가리킨다. 본문과 **세부 규칙**을 함께 적용한다.

- **본문**에는 사용자가 검토할 작업 절차(담당자, 할 일, 순서, 판단 기준)와 형식(구조, 핵심 기준)을 적는다.
- **세부 규칙**에는 조건·명령·필드명·금지 사항·예외를 적는다. 단계별 규칙은 `2:`처럼 본문 번호에 맞춰 표기한다.

각 규칙은 담당 문서에 한 번 쓰고, 다른 문서에서는 해당 절을 링크한다.

## 모든 작업에 적용하는 원칙

- 교정·승인·패키징·이미지 생성은 사용자가 요청한 단계만 진행한다.
- RAW 원문과 이미지 원본 파일, 패키지의 승인된 태그 구성을 보존한다.

## 금지 사항

- 작업 중 예외를 발견해도 Markdown 명세서의 규칙을 임의로 수정하지 않는다. 규칙을 바꿀 필요가 있으면 먼저 사용자와 협의하고, 합의한 내용만 반영한다.

## 색인

[작업별 읽기 안내](READING_GUIDE.md)에서 요청에 해당하는 문서와 절을 읽는다.

### 폴더별 자료

| 폴더 | 들어 있는 내용 | 먼저 열 문서 |
|---|---|---|
| `library/samples/` | 샘플별 RAW·REG·REFINE 기록과 결과 이미지 | [샘플 목록](library/samples/INDEX.MD) · [인덱스 규약](formats/storage.md#샘플-인덱스) |
| `library/styles/` | 승인된 표현 방식을 담은 스타일 패키지 | [스타일 목록](library/styles/INDEX.MD) · [작성 규약](library/styles/FORMAT.md) |
| `library/characters/` | 인물의 정체성·외형·의상을 담은 캐릭터 패키지 | [캐릭터 목록](library/characters/INDEX.MD) · [작성 규약](library/characters/FORMAT.md) |
| `library/chunks/` | 스타일·캐릭터를 제외한 장면 구성을 담은 청크 패키지 | [청크 목록](library/chunks/INDEX.MD) · [작성 규약](library/chunks/FORMAT.md) |
| `workflows/` | 샘플 처리·패키지 등록·이미지 생성 절차 | [REG](workflows/reg.md) · [REFINE·승인](workflows/refine.md) · [지정한 패키지 등록](workflows/package_registration.md) · [패키지 이미지](workflows/package_images.md) · [API 생성](workflows/api_generation.md) |
| `formats/` | 프롬프트 표기, 파일 배치, JSON 구조와 예시 | [프롬프트 규칙](formats/prompt_rules.md) · [저장 규약](formats/storage.md) · [JSON 예시](formats/storage_examples.md) |
| `danbooru-tags/` | REFINE에서 태그를 추가하거나 대체할 때 쓰는 태그 사전 | [태그 검색](danbooru-tags/README.md#태그-검색) |
| `scripts/` | 메타데이터 추출, 패키지 검증, HTML 갱신 등의 실행 도구 | [실행 안내](scripts/README.md) · [구현 범위](formats/storage.md#적용-상태) |
| `runs/` | API 실행별 생성 이미지 원본과 처리 상태 | [생성 작업본](workflows/api_generation.md#생성-작업본) |
| `viewer/` | HTML 라이브러리와 프롬프트 구성기의 화면 소스 | [뷰어 안내](viewer/README.md) · [표시 그룹](viewer/README.md#묶음-목록과-구성-선택) |

[용어 정리](GLOSSARY.md) · [HTML 라이브러리 열기](library.html) · [HTML 갱신](update_html.cmd)
