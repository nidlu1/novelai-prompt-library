# 단부루 태그 자료

REFINE에서 추가·대체할 태그를 찾거나 캐릭터·작품·작가의 등록명을 확인할 때 사용하는 태그 사전이다.

## 태그 검색

| 찾는 태그 | 2026년 11월 검색용 전체 사전 |
|---|---|
| 일반 태그 | [general](2026-11-10/reclassified/danbooru-tags-general-prompt-rules-kr-2026-11-10.csv) |
| 캐릭터 | [characters](2026-11-10/reclassified/danbooru-tags-characters-kr-2026-11-10.csv) |
| 작품·시리즈 | [copyrights](2026-11-10/reclassified/danbooru-tags-copyrights-kr-2026-11-10.csv) |
| 작가 | [artists](2026-11-10/reclassified/danbooru-tags-artists-kr-2026-11-10.csv) |

종류에 맞는 사전에서 등록명(`tag`), 한글 라벨(`label_ko`), 검색어(`keywords_ko`)로 찾고, 설명(`description_ko`)에서 뜻을 확인한다.

**세부 규칙**

- 일반 태그는 `major_category`와 `subcategory`로 범위를 좁힐 수 있다. 두 열은 [프롬프트 규칙](../formats/prompt_rules.md#대분류와-소분류)의 분류를 따른다.
- `source_related_tags`는 추가로 조회할 후보로만 사용한다. 단부루 카테고리 코드, 원본 분류 경로와 열 정의는 [사전 설명](2026-11-10/reclassified/SOURCE.txt)을 따른다.
- 네 CSV는 헤더가 있는 UTF-8 BOM 파일이다. 따옴표 안의 쉼표와 줄바꿈을 처리하는 CSV 파서로 읽는다.
- 검색은 읽기 전용이다. CSV를 수정하거나 `tools/`의 생성·재분류·검증 스크립트를 실행하지 않는다.
