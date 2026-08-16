# EventSystem 리소스팩

Minecraft **26.2** / Paper 서버용 이벤트 토큰 텍스처 팩입니다.
(pack format **88**)

## 다운로드

**[Releases](../../releases/latest) 에서 `EventSystemPack.zip` 을 받으세요.**

서버 관리자는 아래 주소를 그대로 `resource-pack` URL 로 쓰면 됩니다:

```
https://github.com/bouz3337-cell/eventsystem-resourcepack/releases/download/v1.0/EventSystemPack.zip
```

## 서버 적용

EventSystem 플러그인의 `plugins/EventSystem/config.yml`:

```yaml
resource-pack:
  enabled: true
  url: "https://github.com/bouz3337-cell/eventsystem-resourcepack/releases/download/v1.0/EventSystemPack.zip"
  sha1: "<릴리스에 적힌 SHA-1>"
  required: true
```

`required: true` 면 리소스팩을 거부한 플레이어는 서버에 들어올 수 없습니다.

## 내용

```
pack.mcmeta
assets/eventsystem/
  items/<id>.json          아이템 모델 정의 (1.21.4+ 신형식)
  models/item/<id>.json    2D 스프라이트 모델
  textures/item/<id>.png   텍스처
```

| 토큰 ID | 텍스처 |
|---|---|
| `event_token` | 이벤트 토큰 |
| `gold_coin` | 금화 |
| `raffle_ticket` | 추첨권 |

## 텍스처 교체

1. `assets/eventsystem/textures/item/` 의 PNG 를 덮어쓰기 (배경 투명, 정사각형 + 2의 거듭제곱)
2. 이 폴더를 zip 으로 압축 — **`pack.mcmeta` 가 zip 최상위**에 와야 합니다
3. 새 릴리스로 올리고, **SHA-1 을 반드시 갱신** — 안 바꾸면 클라이언트가 옛 팩을 캐시에서 계속 씁니다

```powershell
(Get-FileHash EventSystemPack.zip -Algorithm SHA1).Hash.ToLower()
```
