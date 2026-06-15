# SpaceCraft Korean Patch Translation QA - 2026-06-15

## Fixed In This Pass

- Runtime placeholders such as `::name::`, `::count::`, `::item::`, `::price::`, and `::target::` are now protected during translation.
- Existing bad cache output such as `::이름::`, `::개수::`, `::항목::`, and `::가격::` is restored from the source placeholder when building the patch.
- `verify_patch_pak` now fails if the generated XML contains non-ASCII runtime placeholders.
- Current generated XML has `bad_runtime_placeholders = 0`.

## Remaining High-Priority Translation QA

These were found by parallel read-only QA agents and should be handled through manual overrides or a glossary pass.

### Terminology

| Source / Pattern | Current Problem | Recommended Korean |
|---|---|---|
| `ALT` / altitude UI | `대체` | `고도` or keep `ALT` if the UI is narrow |
| `License` | `라이센스` / `라이선스` mixed | `라이선스` |
| `Permit` | `허가`, `허가증`, `기업 허가` mixed | `허가` |
| `Unlock` | literal `잠금 해제` in many UI strings | `해금`, or `구매` when it costs currency |
| `Ship` | `선박`, `함선`, `우주선`, `배` mixed | `함선` for player ships |
| `Base` | `기본`, `기반`, `베이스` in facility context | `기지` |
| `Contract` | mixed with `요청` | `계약` |
| `Corpo Request` / `Commission` | `시체 요청`, `수수료`, `커미션` | `기업 의뢰` |
| `Corpo` | `Corpo`, `corpo`, `코포`, `비즈니스`, `시체` | `기업` or one chosen proper noun |

### Quest / Tutorial Examples

| Current Text | Recommended Text |
|---|---|
| `::permit::permission을 잠금 해제` | `[key.MenuKnowledges]를 눌러 <t>지식</t> 메뉴를 열고 ::permit:: 허가를 잠금 해제하세요.` |
| `채광::resource::획득::count::::item::.` | `::resource::를 채굴해 ::count::개의 ::item::을 획득하세요.` |
| `구매::count2::::item2::.` | `::count2::개의 ::item2::을 구매하세요.` |
| `잠금 해제::permit::허가.` | `::permit:: 허가를 잠금 해제하세요.` |
| `::target::우주정거장에 도킹되었습니다.` | `::target:: 정거장에 도킹하세요.` |
| `생산::item::` | `기지에 [B_Chemical]을 배치하고 ::item::을 생산하세요.` |
| `만나기::target::의::npc::` | `::target::에서 ::npc::를 만나세요.` |
| `::resource::를 찾았습니다.` | `::target-raw::에서 ::resource::를 찾으세요.` |
| `접근 방식::resource::잔해` | `::resource:: 잔해에 접근하세요.` |
| `In::target::수집::resource::광업국` | `::target:: 광업국에서 ::resource:: 위치 정보를 얻으세요.` |

## Suggested Next QA Rules

- Fail generated XML on `???` except known intentional debug strings.
- Fail generated XML on any CJK in Korean output.
- Compare source and translated inline tag signatures.
- Compare source and translated runtime placeholder multisets.
- Fail caches that contain leaked `ZXTOKEN0000Z` markers.
