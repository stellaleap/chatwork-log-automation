# Chatworkログ自動化 ― 稼働ランブック（Claude Code用）

- リポジトリ：**stellaleap/chatwork-log-automation**（GAS）
- 保全区分：🟡 **資産保全（停止）**。**必要時に改修して再稼働**。SlackFetcher の Chatwork版。
- scriptId：`1hLxBiIvUUZXKdP0NUzlUeBHdMJ0pK-3ZB3gYr4aybToA-UXwy5uRCKTu`

## 何をするシステムか
指定 Chatwork ルームのメッセージを Google スプレッドシート/ドキュメントへ自動アーカイブ（資産化）。複数ルームを `TARGET_ROOMS_CONFIG` で設定。

## エントリ / トリガー
- メイン：`fetchAndStockChatwork`（取得＆保存）。UI：`runFromSidebar`／`onOpen`。
- 定期実行が必要なら時間主導トリガーで `fetchAndStockChatwork` を設定（現在は停止）。

## Secrets（スクリプトプロパティ）
`CHATWORK_API_TOKEN`／`LOG_SHEET_ID`（保存先）／`TARGET_ROOMS_CONFIG`（対象ルーム設定）

## 再稼働（必要時）
1. `gh repo clone stellaleap/chatwork-log-automation` → clasp設定。
2. `CHATWORK_API_TOKEN`・`LOG_SHEET_ID`・`TARGET_ROOMS_CONFIG` を設定。
3. `fetchAndStockChatwork` を手動実行して確認 → 必要なら時間主導トリガーを作成。
