# 청크 인덱스

승인된 청크의 기본본과 바리에이션을 찾는 인덱스다. `ID` 링크는 패키지 JSON을 열고, `구성` 열은 그 파일 안의 구성 키를 표시한다. `base`는 기본본이며 `v01`부터는 바리에이션이다.

내용 분류는 장면 전체 구성의 SFW/NSFW를 나타낸다. 역할 열에는 대상 종류와 역할 이름을 표시한다. 분류·역할·판정 기준은 [청크 작성 규약](FORMAT.md)을 따른다.

## 장면 전체 청크

신규 청크는 스타일·캐릭터를 제외한 나머지 전체를 `library/chunks/ckNNN.json`에 저장한다.

| ID | 구성 | 이름 | 내용 분류 | 역할 |
|---|---|---|---|---|
| [ck001](ck001.json) | base | 햇빛 아래 격투 자세 | SFW | BASE: 밝은 장면 공통 · CHARACTER: 격투 자세의 인물 |
| [ck002](ck002.json) | base | 흰 배경을 향한 액스 킥 | SFW | BASE: 흰 배경의 역동적 장면 · CHARACTER: 액스 킥을 하는 인물 |
| [ck003](ck003.json) | base | 괴물 의자에 구속된 인물 | NSFW | BASE: 어두운 괴물 의자 장면 · CHARACTER: 구속된 인물 · CHARACTER: 괴물 의자의 행동 |
| [ck003](ck003.json) | v01 | 괴물 의자에 구속된 인물 — 아래 시점·다리 벌림 | NSFW | BASE: 어두운 괴물 의자 장면 · CHARACTER: 구속된 인물 · CHARACTER: 괴물 의자의 행동 |
| [ck004](ck004.json) | base | 흐린 배경의 양손 브이 포즈 | NSFW | BASE: 흐린 배경의 인물 장면 · CHARACTER: 양손 브이 포즈의 인물 |
| [ck005](ck005.json) | base | 촉수에 구속된 인물 | NSFW | BASE: 어두운 촉수 장면 · CHARACTER: 촉수에 구속된 인물 |
| [ck006](ck006.json) | base | 촉수에 습격당하는 인물 | NSFW | BASE: 촉수 장면 · CHARACTER: 습격당하는 인물 · CHARACTER: 촉수 |
| [ck006](ck006.json) | v01 | 촉수에 습격당하는 인물 — 오염 표현 | NSFW | BASE: 촉수 장면 · CHARACTER: 습격당하는 인물 — 오염 표현 · CHARACTER: 촉수 |
| [ck006](ck006.json) | v02 | 촉수에 구속되어 고통받는 인물 | NSFW | BASE: 촉수 성행위 장면 · CHARACTER: 구속되어 고통받는 인물 · CHARACTER: 삽입하는 촉수 |
| [ck006](ck006.json) | v03 | 거리에서 촉수에 매달린 인물 | NSFW | BASE: 거리의 측면 촉수 장면 · CHARACTER: 촉수에 매달린 인물 · CHARACTER: 삽입하는 촉수 |
| [ck006](ck006.json) | v04 | 촉수에 매달린 구강 삽입 장면 | NSFW | BASE: 삼사분면 머리 중심 촉수 장면 · CHARACTER: 촉수에 매달린 인물 · CHARACTER: 구강·성기 삽입 촉수 |
| [ck006](ck006.json) | v05 | 촉수에 매달린 삽입 단면도 | NSFW | BASE: 삼사분면 머리 중심 삽입 단면도 · CHARACTER: 촉수에 매달린 인물 · CHARACTER: 구강·성기 삽입 촉수 |
| [ck007](ck007.json) | base | 성행위 후 의식을 잃은 인물 | NSFW | BASE: 상부 삼사분면 NSFW 장면 · CHARACTER: 성행위 후 의식을 잃은 인물 |
| [ck008](ck008.json) | base | 와인병을 이용한 알코올 관장 | NSFW | BASE: NSFW 단일 인물 장면 · CHARACTER: 알코올 관장을 당하는 인물 |
| [ck009](ck009.json) | base | 호텔 방에서 성폭행을 촬영하는 장면 | NSFW | BASE: 호텔 방 성폭행 촬영 장면 · CHARACTER: 성폭행을 당하는 인물 · CHARACTER: 성폭행을 하는 인물 |
| [ck009](ck009.json) | v01 | 호텔 방에서 성폭행을 촬영하는 장면 — 위 시점·등 젖힘 | NSFW | BASE: 호텔 방 성폭행 촬영 장면 — 위 시점 · CHARACTER: 성폭행을 당하는 인물 — 등 젖힘 · CHARACTER: 성폭행을 하는 인물 |
| [ck010](ck010.json) | base | 몸을 숙여 브이 포즈를 하는 인물 | SFW | BASE: 텍스트 없는 단일 인물 장면 · CHARACTER: 몸을 숙여 브이 포즈를 하는 인물 |
| [ck011](ck011.json) | base | 텍스트 없는 단일 인물 포스터 | SFW | BASE: 텍스트 없는 단일 인물 포스터 |
| [ck012](ck012.json) | base | 호텔 방 강간 장면 | NSFW | BASE: 호텔 방 NSFW 장면 · CHARACTER: 강간당하는 인물 · CHARACTER: 강간하는 인물 |
| [ck013](ck013.json) | base | 흰 배경의 무희 의상 인물 | NSFW | BASE: 흰 배경의 텍스트 없는 장면 · CHARACTER: 무희 의상의 역동적인 인물 |
| [ck013](ck013.json) | v01 | 흰 배경의 무희 의상 인물 — 추가 노출 | NSFW | BASE: 흰 배경의 텍스트 없는 장면 · CHARACTER: 노출이 강화된 무희 의상의 역동적인 인물 |
| [ck013](ck013.json) | v02 | 흰 배경의 무희 의상 인물 — 안쪽 형태 | NSFW | BASE: 흰 배경의 텍스트 없는 장면 · CHARACTER: 안쪽 형태가 추가된 무희 의상의 역동적인 인물 |
| [ck014](ck014.json) | base | 바닥에서 돌핀 쇼츠를 내리며 뒤돌아보는 자세 | SFW | BASE: 단일 인물 실내 장면 · CHARACTER: 쇼츠를 허벅지까지 내리고 뒤돌아보는 인물 |
| [ck015](ck015.json) | base | 흰 배경에서 열린 셔츠를 잡고 양팔을 벌린 정면 샷 | SFW | BASE: 텍스트 없는 단일 인물 장면 · CHARACTER: 열린 셔츠를 잡고 양팔을 벌린 인물 |
| [ck016](ck016.json) | base | 선드레스 인물과 페이딩 다중 뷰 | NSFW | BASE: 페이딩 다중 뷰와 텍스트 없는 장면 · CHARACTER: 흰 배경에 선 선드레스 인물 · CHARACTER: 위쪽 오른쪽 클로즈업 인물 · CHARACTER: 위쪽 왼쪽 신체 클로즈업 · CHARACTER: 아래쪽 오른쪽 인물 · CHARACTER: 아래쪽 왼쪽 인물 |
| [ck017](ck017.json) | base | 어두운 골목 벽에 기대 담배를 든 측면 장면 | SFW | BASE: 텍스트 없는 단일 인물 장면 · CHARACTER: 골목 벽에 기대 담배를 든 인물 |
| [ck018](ck018.json) | base | 술집 테이블에 나란히 앉은 두 인물 | NSFW | BASE: 장면 공통 · CHARACTER: 히로이 키쿠리 · CHARACTER: 동행 인물 |
| [ck018](ck018.json) | v01 | 술집 테이블에 나란히 앉은 두 인물 — 술잔을 든 옆모습 | NSFW | BASE: 장면 공통 · CHARACTER: 히로이 키쿠리 · CHARACTER: 동행 인물 |
| [ck018](ck018.json) | v02 | 술집 테이블에 나란히 앉은 두 인물 — 바 카운터와 반쯤 감은 눈 | NSFW | BASE: 장면 공통 · CHARACTER: 히로이 키쿠리 · CHARACTER: 동행 인물 |
| [ck019](ck019.json) | base | 밤거리에서 서로 기대어 손을 흔드는 두 인물 | NSFW | BASE: 장면 공통 · CHARACTER: 히로이 키쿠리 · CHARACTER: 동행 인물 |
| [ck020](ck020.json) | base | 호텔방 침대의 두 인물 — 가로 구도 | NSFW | BASE: 장면 공통 · CHARACTER: 히로이 키쿠리 · CHARACTER: 동행 인물 |
| [ck020](ck020.json) | v01 | 호텔방 침대의 두 인물 — 상체 노출이 늘어난 가로 구도 | NSFW | BASE: 장면 공통 · CHARACTER: 히로이 키쿠리 · CHARACTER: 동행 인물 |
| [ck021](ck021.json) | base | 호텔방 침대 — 등을 대고 누운 인물 | NSFW | BASE: 장면 공통 · CHARACTER: 히로이 키쿠리 · CHARACTER: 동행 인물 |
| [ck021](ck021.json) | v01 | 호텔방 침대 — 등을 젖히고 다리로 감싼 자세 | NSFW | BASE: 장면 공통 · CHARACTER: 히로이 키쿠리 · CHARACTER: 동행 인물 |
| [ck022](ck022.json) | base | 호텔방 침대 — 엎드린 인물과 뒤쪽 동행인 | NSFW | BASE: 장면 공통 · CHARACTER: 히로이 키쿠리 · CHARACTER: 동행 인물 |
| [ck023](ck023.json) | base | 검열 억제 단일 인물 장면 | SFW | BASE: 장면 |
