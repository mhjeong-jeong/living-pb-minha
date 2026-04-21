# 리빙 PB 대시보드

오늘의집 리빙 PB 상품들의 성과·유입·SRP 분석 대시보드.

**🔗 Live**: 레포 설정 후 `Settings > Pages` 활성화하면 `https://<username>.github.io/<repo>/` 로 접근 가능

## 구성

- `index.html` — 대시보드 허브 (랜딩 페이지)
- `towel-pb.html` — 호텔수건 PB 대시보드 (자사 3920046 vs 경쟁사 2종)

## 업데이트 주기

매일 오전 9시, Cowork 스케줄 태스크가 Athena에서 최신 데이터를 쿼리하여 HTML을 갱신하고 자동 `git push`. GitHub Pages는 push 후 1~2분 내 반영.

## 데이터 원천

- `ba_preserved.commerce_daily_user_count_v3` — 노출·PDP·구매 UV/count
- `ba_preserved.commerce_gross_profit_orders` — GMV·판매수량
- `ba_preserved.ds_com_productions_imp_click_d` — 유입 경로(page_id)
- `ba_preserved.commerce_product_search_tb` — SRP 노출 순위
- `ba_preserved.comm_product_info_latest` — 상품 메타

## 지표 산식

- `CTR = pdpview_count / impression_count`
- `CVR(UV) = purchase_user_join / pdpview_user_join`
- 회원 기준 UV, 당일취소 제외

## 라이선스

Internal only · 오늘의집(버킷플레이스)
