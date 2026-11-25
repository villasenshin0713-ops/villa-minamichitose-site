# Villa南千歳 公式サイト

静的サイト（HTML1ファイル＋画像）。**このリポジトリが正本**。
`00_素材ライブラリ/Villa南千歳_ホームページ/` は移行前のコピーなので編集しないこと。

## 構成
- `public/index.html` — 日本語ページ
- `public/en/index.html` — 英語ページ（2026-11-25追加）
- `public/assets/site.css` — 共通CSS（2ページで共有）
- `public/sitemap.xml` / `public/llms.txt` — 検索エンジン・AI向け
- `docs/SEO_AIO_MEO_運用メモ.md` — 対応内容とGoogleビジネスプロフィール等のチェックリスト
- `public/images/` — 写真・ロゴ・間取り図
- `public/robots.txt`
- `wrangler.jsonc` — Cloudflare Workers（静的アセット配信）の設定

## 公開先
**https://villa-minamichitose.com** （2026-10-02公開）
Cloudflare Workers & Pages プロジェクト `villa-minamichitose-site`。ドメインはCloudflare Registrarで取得。
GitHubの `main` にpushすると、Cloudflare側が `npx wrangler deploy` を実行して自動公開する。

## 更新のしかた
1. Claude Codeをこのフォルダで開き、「〇〇を直して」と頼む
2. 直った内容を確認する（ローカル確認は `cd public && python3 -m http.server 8000` → http://127.0.0.1:8000 ）
3. commit＆pushすると、数十秒〜1分で本番に反映される

## 素材の出どころ
- 2026-11-25: 観光写真5枚（images/nagano1〜5.jpg）を Wikimedia Commons の自由利用写真に差し替え（方針: 人が写っていない写真のみ）。**ページ内のクレジット表記は削除しないこと**（CC BY / BY-SA の利用条件）
  - nagano1 善光寺: Christophe95, CC BY-SA 4.0 — https://commons.wikimedia.org/wiki/File:Main_Hall_of_Zenk%C5%8D-ji_3.jpg（人が写らないようトリミング）
  - nagano2 戸隠: lumoplank, CC0 — https://commons.wikimedia.org/wiki/File:Togakushi_-_Togakushi17.jpg（参道の人が写らないようトリミング）
  - nagano3 野尻湖: RESPITE, パブリックドメイン — https://commons.wikimedia.org/wiki/File:Lake_Nojiri.JPG
  - nagano4 長野駅善光寺口: MaedaAkihiko, CC BY-SA 4.0 — https://commons.wikimedia.org/wiki/File:JRE_Nagano-STA_Zenkoji_Under-the-eaves.jpg（通行人2名をレタッチで消去）
  - nagano5 長野駅前: くろふね, CC BY-SA 4.0 — https://commons.wikimedia.org/wiki/File:長野駅前の風景.jpg（通行人1名をレタッチで消去）
- 2026-11-25更新: `villa_minamichitose.pdf`（新冊子）— アクセスマップ・目印・コインパーキング・ローカルガイド・ベッド構成
- デザイン・ロゴ・コピー・間取り図・観光写真: `2611_villa南千歳_冊子.pdf`
- 館内写真・施設情報・ハウスルール・紹介文: Booking.com掲載ページ（2026-10-02取得）
  https://www.booking.com/hotel/jp/villanan-qian-sui.ja.html

## 掲載情報（確定）
〒380-0822 長野県長野市鶴賀南千歳町977-2 ／ JR長野駅善光寺口から徒歩約7分 ／ 95㎡・2フロア・寝室3室 ／
最大9名・寝室3室（ベッド構成は要確認）／ IN 15:00-22:00・OUT ~10:00 ／
営業許可番号 長野市指令08保食第2ー30号 ／ 運営 株式会社コントラディスト

## 予約・問い合わせ導線
- 公式予約ページ（Chillnn）: https://www.chillnn.com/1a0c30f006511b ← ヘッダー/ヒーロー/予約ボックスのCTAはすべてここ
- Booking.com: 予約ボックスの副ボタン＋クチコミスコアの出典
- TEL 050-8896-2394 ／ villasenshin0713@gmail.com

## 未確定・要確認
- **ベッド構成**: 新冊子は「1F シングルベッド1台の寝室」、旧記載/Booking.comは「ダブル4台＋ソファベッド1台」。サイトは冊子に合わせた（詳細は docs/ のメモ）
- **チェックイン/アウトの表記ゆれ**: 公式予約ページは IN 15:00-22:00・OUT ~10:00、Booking.comは IN 15:00-23:00・OUT 8:00-10:00。サイトは公式予約ページに合わせた。OTA側を直すか要判断
- 寝室数: Booking.comは部屋タイプ「3ベッドルーム」・説明文「ベッドルーム2室」で食い違い。冊子の間取り図に合わせて3室で記載
- 「ホットタブ」表記が実態と合うか
- クチコミ本文は未掲載（スコアのみ）
