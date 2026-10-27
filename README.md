# 이든·북브런치 팝업 초대장

2026년 11월 9일 이든카페·북브런치 카페 팝업 초대장 사이트입니다.

- `index.html` — 초대장 (초대 · 활동 소개 · 오시는 길 · 수요조사 · 교환권)
- `admin.html` — 운영진용 교환권 확인 페이지 (PIN 필요)
- `assets/` — 쿠폰·장소 사진

## 데이터 흐름

- 수요조사 응답은 Supabase `popup_rsvp` 테이블에 저장됩니다. 페이지는 `popup_submit_rsvp` 함수로만 저장할 수 있고, 표를 직접 읽을 수는 없습니다.
- 운영진 페이지는 PIN으로 `popup_admin_list` / `popup_admin_set_redeemed` 함수를 호출합니다.
- 구글 시트는 Edge Function `popup-rsvp-csv`가 내보내는 CSV를 `IMPORTDATA`로 불러옵니다.

## 배포

GitHub Pages (Settings → Pages → Branch: `main`, 폴더: `/ (root)`).
