# busan_schedule

釜山旅行のスケジュール表（1ファイル完結の静的HTML）。台湾版 `taiwan_schedule.html` と同じ構造で作成しています。

## ファイル構成

- `busan_schedule.html` … 本体。行程データ・地図・予算集計まですべてこの1ファイルに入っています
- `images/` … 各スポットの画像置き場（未配置の画像は自動でプレースホルダー表示になります）

## 編集方法

`busan_schedule.html` 内 `<script>` の以下を書き換えます。

- `TRIP_YEAR` … 旅行年（「現在のスケジュールへジャンプ」の判定に使用）
- `days` … 日程とスポットの本体データ
  - `time` / `name` / `type`（`spot` | `hotel` | `transport`）/ `desc` / `img` / `map` が必須項目
  - `mapUrl` を指定するとGoogle Mapの共有リンクをそのまま使えます
  - `budget` は表示用テキスト、`budgetMin` / `budgetMax` は下部の予算集計用（上限なしは `budgetMax: null`）
- `spotCoordinates` … 地図ピンの座標。未登録のスポットは OpenStreetMap のジオコーディングで自動補完します
- `cityCenters` / `detectCity` … 都市ごとの地図の初期表示とスポットの都市振り分け

画像は `images/` に置き、`days` の `img` にパスを書きます。ファイルが無い場合はプレースホルダー画像にフォールバックします。

## 公開（GitHub Pages）

リポジトリの Settings → Pages で Source を `main` ブランチのルートに設定すると、
`https://kurotonkotu.github.io/busan_schedule/busan_schedule.html` で閲覧できます。
