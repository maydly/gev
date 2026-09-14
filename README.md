# 신의눈 (God's Eye View) — maydly 웹 배포본

폰에서도 보려고 정적으로 빌드한 것입니다. `배포_웹용_만들기.command` 로 다시 만듭니다.

- **원작**: [bilawalsidhu/gods-eye-view](https://github.com/bilawalsidhu/gods-eye-view) (MIT License)
- **추가 레이어** (maydly)
  - 📍 내 장소 — 네이버 저장폴더 + 구글맵 리스트
  - 🎞 촬영지 10,525곳
    - 한국 8,614 — 한국문화정보원 미디어콘텐츠 영상 촬영지 데이터(공공데이터포털, 이용허락범위 제한 없음)
    - 일본 2,383 — 일본어 위키백과 (CC BY-SA 4.0)

## 웹에서 되는 것 / 안 되는 것

정적 배포본에는 프록시 서버가 없다. 그래서 키가 필요 없고 CORS가 열린 소스는
브라우저가 원본을 직접 부르도록 `index.html`에 fetch 전환을 심는다(배포 스크립트가 자동으로 한다).

**된다**: 3D 지구본 · 촬영지 · 내 장소 · **장소 검색(OSM Nominatim으로 갈아끼움)** ·
**인공위성(Celestrak)** · **로켓발사(Launch Library)** · 지진(USGS) · 해저케이블

**안 된다**: 비행기·군용기 — 공개 API(adsb.lol / adsb.fi / airplanes.live / OpenSky)가 전부
CORS를 막아 브라우저에서 직접 부를 수 없다. 선박(AIS)·실시간 교통(TomTom)·산불(FIRMS)·CCTV는
열쇠 또는 서버가 필요하다. 이 기능들을 웹에서도 쓰려면 서버리스 프록시(예: Cloudflare Workers)가 필요한데,
**명진이 "비행기는 맥에서만 본다"로 정했다(260912)** — 새 계정을 만들지 않기로 한 판단이다.

맥에서 `npm run dev` 로 켜면 전부 된다.
