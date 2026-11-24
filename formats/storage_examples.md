# 샘플과 패키지 JSON 예시

[저장 규약](storage.md)의 구조를 보여준다. RAW·REG·REFINE은 노르마 할로웰의 양손 브이 사례를 바탕으로 작가 태그와 UC를 줄인 설명용 예시다. 세 실행의 `image` 값에는 경로 형식만 표시했다. 실제 샘플에는 원본 프롬프트·UC와 해당 이미지의 상대 경로를 기록한다.

## RAW 예시

RAW 결과에는 양손 브이가 보였지만 캐릭터 Prompt에는 `cute pose`만 포즈로 적혀 있다. 남겨 둔 태그는 RAW의 표기와 순서를 따른다.

```json
{
  "images": [
    {
      "image": "images/raw.<ext>",
      "base": {
        "prompt": "1girl, solo, 0.55::artist:imamura_ryou::, 1.4::artist:poruserin ::, year 2025, year 2026, \n\ndepth of field, blurry background, \n\nhigh complexity, -0.3::ultra complexity::, 1.2::masterpiece, very aesthetic, highres, best quality, amazing quality, incredibly absurdres, novel illustration::, photorealistic, very aesthetic, masterpiece, animated, explicit, 0.5::blender (medium), realistic::, ",
        "uc": "text, bad anatomy, lowres"
      },
      "width": 832,
      "height": 1216,
      "model": "NovelAI Diffusion V5",
      "seed": 3716581855,
      "steps": 28,
      "sampler": "k_euler_ancestral",
      "noise_schedule": "karras",
      "scale": 5.5,
      "cfg_rescale": 0.0,
      "characters": [
        {
          "prompt": "norma hollowell, tsurime, 장난스러운 표정, cute pose, cowboy shot, dynamic angle,",
          "uc": ""
        }
      ]
    }
  ]
}
```

## REG 예시

같은 시드와 설정을 사용한다. RAW 태그의 표기와 순서를 정리하고, 인물의 정체성과 장면 속 포즈를 각각 캐릭터 묶음과 장면 청크에 담았다.

```json
{
  "schema_version": 3,
  "bundles": [
    {
      "kind": "style",
      "name": "poruserin + imamura ryou",
      "slot": "BASE",
      "prompt": "0.55::artist:imamura ryou ::,\n1.4::artist:poruserin ::,\nphotorealistic, animated, 0.5::blender (medium), realistic ::,\nhigh complexity, -0.3::ultra complexity ::, 1.2::masterpiece, very aesthetic, highres, best quality, amazing quality, incredibly absurdres, novel illustration ::, very aesthetic, masterpiece,\nyear 2025, year 2026,",
      "uc": "lowres,"
    },
    {
      "kind": "character",
      "name": "노르마 할로웰",
      "slot": "CHARACTER_1",
      "prompt": "norma hollowell,\ntsurime,",
      "uc": ""
    },
    {
      "kind": "chunk",
      "name": "노르마 할로웰의 귀여운 포즈",
      "roles": {
        "scene": {
          "name": "흐린 배경의 인물 장면",
          "slot": "BASE",
          "prefix_prompt": "1girl, solo, explicit,",
          "prompt": "depth of field, blurry background,",
          "uc": "bad anatomy,\ntext,"
        },
        "subject": {
          "name": "귀여운 포즈의 인물",
          "slot": "CHARACTER_1",
          "prompt": "cute pose,\n\n장난스러운 표정,\n\ncowboy shot, dynamic angle,",
          "uc": ""
        }
      }
    }
  ],
  "width": 832,
  "height": 1216,
  "model": "NovelAI Diffusion V5",
  "seed": 3716581855,
  "steps": 28,
  "sampler": "k_euler_ancestral",
  "noise_schedule": "karras",
  "scale": 5.5,
  "cfg_rescale": 0.0,
  "images": [
    {
      "image": "images/reg.<ext>",
      "width": 832,
      "height": 1216,
      "model": "NovelAI Diffusion V5",
      "seed": 3716581855,
      "steps": 28,
      "sampler": "k_euler_ancestral",
      "noise_schedule": "karras",
      "scale": 5.5,
      "cfg_rescale": 0.0
    }
  ]
}
```
BASE Prompt는 장면 청크의 `prefix_prompt` → 스타일 Prompt → 장면 청크의 `scene.prompt` 순서로 조립한다. `images`에는 REG 결과의 경로와 생성 설정을 기록한다.

### 교정 없이 REG 승인

`approval.json`에서 최종 단계와 정확한 이미지 경로를 선택한다. `reg.json`의 `images[]`에 이 이미지가 연결되고 실행값이 일치해야 한다.

```json
{
  "schema_version": 1,
  "final_stage": "reg",
  "final_image": "images/reg.png",
  "approved_images": {
    "reg": [
      "images/reg.png"
    ]
  }
}
```
## REFINE 예시

REG 결과에서 빠진 양손 브이를 표현하기 위해 장면 청크의 인물 역할에 `double v`를 추가했다. 표정은 `playful expression`으로 바꾸고, BASE의 `explicit` 가중치는 1.1로 조정했다.

```json
{
  "schema_version": 3,
  "bundles": [
    {
      "kind": "style",
      "name": "poruserin + imamura ryou",
      "slot": "BASE",
      "prompt": "0.55::artist:imamura ryou ::,\n1.4::artist:poruserin ::,\nphotorealistic, animated, 0.5::blender (medium), realistic ::,\nhigh complexity, -0.3::ultra complexity ::, 1.2::masterpiece, very aesthetic, highres, best quality, amazing quality, incredibly absurdres, novel illustration ::, very aesthetic, masterpiece,\nyear 2025, year 2026,",
      "uc": "lowres,"
    },
    {
      "kind": "character",
      "name": "노르마 할로웰",
      "slot": "CHARACTER_1",
      "prompt": "norma hollowell,\ntsurime,",
      "uc": ""
    },
    {
      "kind": "chunk",
      "name": "흐린 배경의 양손 브이 포즈",
      "roles": {
        "scene": {
          "name": "흐린 배경의 인물 장면",
          "slot": "BASE",
          "prefix_prompt": "1girl, solo, 1.1::explicit::,",
          "prompt": "depth of field, blurry background,",
          "uc": "bad anatomy,\ntext,"
        },
        "subject": {
          "name": "양손 브이 포즈의 인물",
          "slot": "CHARACTER_1",
          "prompt": "double v, cute pose,\n\nplayful expression,\n\ncowboy shot, dynamic angle,",
          "uc": ""
        }
      }
    }
  ],
  "width": 832,
  "height": 1216,
  "model": "NovelAI Diffusion V5",
  "seed": 3716581855,
  "steps": 28,
  "sampler": "k_euler_ancestral",
  "noise_schedule": "karras",
  "scale": 5.5,
  "cfg_rescale": 0.0,
  "images": [
    {
      "image": "images/refine.<ext>",
      "width": 832,
      "height": 1216,
      "model": "NovelAI Diffusion V5",
      "seed": 3716581855,
      "steps": 28,
      "sampler": "k_euler_ancestral",
      "noise_schedule": "karras",
      "scale": 5.5,
      "cfg_rescale": 0.0,
      "features": "양손 브이 사인, 이를 드러낸 미소, 정면 상반신 구도."
    }
  ]
}
```
아래 `approval.json`은 REG와 REFINE을 모두 승인한 경우의 별도 예시다.

```json
{
  "schema_version": 1,
  "final_stage": "refine",
  "final_image": "images/refine.png",
  "approved_images": {
    "reg": [
      "images/reg.png"
    ],
    "refine": [
      "images/refine.png"
    ]
  }
}
```
## 패키지 예시

스타일·캐릭터는 스키마 3을 유지하며 출처에 승인된 REG 또는 REFINE을 연결한다. 출처의 실행 묶음도 실제 패키지 경로·구성 키를 참조해야 검증이 통과한다.

```json
{
  "schema_version": 3,
  "id": "st001",
  "kind": "style",
  "variants": {
    "base": {
      "name": "수채화",
      "slot": "BASE",
      "prompt": "watercolor,",
      "uc": "lowres,",
      "sources": [
        {
          "sample": "../samples/s0001/reg.json",
          "image": "../samples/s0001/images/reg.png"
        }
      ],
      "gallery": {
        "images": [],
        "sub_images": []
      }
    }
  }
}
```
### 장면 전체 청크 예시

`library/chunks/ck050.json`. BASE와 캐릭터 한 명을 함께 포함할 수 있다. `category`·`subcategory`는 사용하지 않는다. `ck050`은 가상 번호이며 실제 저장에서는 미사용 번호를 확인한다.

```json
{
  "schema_version": 4,
  "id": "ck050",
  "kind": "chunk",
  "variants": {
    "base": {
      "name": "창가에서 바라보기",
      "content_rating": "sfw",
      "roles": {
        "scene": {
          "name": "장면 공통",
          "prefix_prompt": "1girl,",
          "prompt": "indoors, window,",
          "uc": "text,",
          "target": "BASE"
        },
        "subject": {
          "name": "서 있는 인물",
          "prompt": "standing, looking at viewer,",
          "uc": "",
          "target": "CHARACTER"
        }
      },
      "sources": [
        {
          "sample": "../samples/s0001/reg.json",
          "image": "../samples/s0001/images/reg.png"
        }
      ],
      "gallery": {
        "images": [],
        "sub_images": []
      }
    }
  }
}
```
출처의 승인된 실행 묶음에는 `{"path": "../../chunks/ck050.json", "variant": "base"}` 참조를 둔다. 출처 이미지와 실제 승인 기록도 모두 일치해야 한다.

## 복수 역할 연결 예시

REG·REFINE에서 장면 공통(`scene`), 주는 인물(`giver`), 받는 인물(`receiver`) 역할을 입력 슬롯에 연결한 예시다. 모든 역할의 전체 문자열은 한 청크에 함께 저장한다.

```json
{
  "scene": "BASE",
  "giver": "CHARACTER_2",
  "receiver": "CHARACTER_1"
}
```
## 패키지 자체 이미지 예시

장면 청크 `ck050/base`의 대표 이미지 예시다. 이미지 경로는 `library/chunks/ck050/base/images/p001.png`이며, `gallery`에 실제 `execution`, 사용한 `components`, `user_selection`을 기록한다. 실제 등록에는 전체 실행문·설정과 원본 파일을 함께 확인한다.

```json
{
  "images": [
    {
      "id": "p001",
      "image": "ck050/base/images/p001.png",
      "execution": {
        "base": {
          "prompt": "1girl,\n\nwatercolor,\n\nindoors, window,",
          "uc": "lowres,\n\ntext,"
        },
        "characters": [
          {
            "prompt": "girl, black hair,\n\nstanding, looking at viewer,",
            "uc": ""
          }
        ],
        "width": 832,
        "height": 1216,
        "seed": 42,
        "steps": 20
      },
      "components": [
        {
          "kind": "style",
          "path": "../styles/st001.json",
          "variant": "base",
          "slot": "BASE"
        },
        {
          "kind": "character",
          "path": "../characters/ch001.json",
          "variant": "base",
          "slot": "CHARACTER_1"
        },
        {
          "kind": "chunk",
          "path": "ck050.json",
          "variant": "base",
          "roles": {
            "scene": "BASE",
            "subject": "CHARACTER_1"
          }
        }
      ],
      "user_selection": "사용자가 해당 구성을 대표로 지정한 실제 요청을 기록"
    }
  ],
  "representative": "p001",
  "sub_images": []
}
```
### 복수 역할의 구성 연결

```json
{
  "kind": "chunk",
  "path": "ck051.json",
  "variant": "base",
  "roles": {
    "scene": "BASE",
    "giver": "CHARACTER_2",
    "receiver": "CHARACTER_1"
  }
}
```
