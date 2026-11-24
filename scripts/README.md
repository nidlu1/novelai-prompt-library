# 스크립트 실행

모든 명령은 프로젝트 루트에서 Python 3.10 이상으로 실행한다. 도구별 지원 범위는 [적용 상태](../formats/storage.md#적용-상태), 접수·저장 규칙은 [RAW → REG](../workflows/reg.md)가 정본이다.

## 실행 환경 준비

PNG 추출은 표준 라이브러리만 사용한다. WebP 추출에는 `requirements.txt`에 지정된 Pillow가 필요하다.

```text
python -m pip install -r scripts/requirements.txt
```

**세부 규칙**

- 해당 의존성이 현재 환경에 없을 때만 설치한다.

## 문서 절 읽기

파일 경로와 절의 앵커를 지정한다.

```text
python -X utf8 -B scripts/read_sections.py "formats/storage.md#적용-상태"
```

## 패키지 조회·검증과 HTML 갱신

### 패키지 조회와 검증

`list`는 구성 목록, `show`는 지정한 구성 전체를 출력한다. `validate`는 검사만 하며 파일을 수정하지 않는다.

```text
python -X utf8 -B scripts/packages.py list library/styles/st013.json
python -X utf8 -B scripts/packages.py show library/styles/st013.json --variant base
python -X utf8 -B scripts/packages.py validate
```

검사 범위는 [패키지 조회와 검증](../formats/storage.md#패키지-조회와-검증)·[자체 이미지 검증](../formats/storage.md#패키지-자체-이미지-검증)을 따른다.

### 장면 전체 청크와 최종 승인

신규 REG·REFINE은 실행 스키마 3, 장면 청크는 패키지 스키마 4를 사용한다. `assemble_refine.py`는 장면 청크 하나와 선두·본문을 조립하고, `classify_raw.py --reg`도 묶음형 REG를 지원한다. 기존 자료는 그대로 읽는다.

`sample_approval.py`는 샘플의 `approval.json`을 읽어 [최종 승인 기록](../formats/storage.md#최종-승인-기록)을 해석한다.

### 스타일 랜덤 프롬프트 출력

`style_randomizer.py`는 [스타일 공통 랜덤 생성](../workflows/package_images.md#스타일-공통-랜덤-생성)의 템플릿에 저장된 스타일만 교체한다. 출력은 전체 BASE Prompt·UC다. `--all`은 모든 스타일을 일괄 출력한다.

```text
python -X utf8 -B scripts/style_randomizer.py library/styles/st013.json --variant base
python -X utf8 -B scripts/style_randomizer.py --all
```

**세부 규칙**

- 이 도구는 출력만 한다. 파일 저장·직접 추첨·이미지 생성·등록은 하지 않는다.
- 랜덤 이미지 검증은 원본 입력 템플릿과 `actual_prompts`의 실제 선택 결과를 모두 확인한다.

### HTML 갱신

```text
./update_html.cmd --no-pause
```

HTML만 직접 생성하려면 `python -X utf8 -B scripts/build_viewer.py`를 실행한다. 생성기는 원본을 읽어 `library.html`을 교체하며, 실패하면 기존 HTML을 보존한다.

갱신 방법과 구성기·브라우저 검사는 [HTML 안내](../viewer/README.md)를 따른다.

## 자동 검사

```text
python -X utf8 -B -m unittest discover -s scripts -p "test_*.py"
```

자동 검사는 임시 폴더의 합성 메타데이터를 사용한다.
