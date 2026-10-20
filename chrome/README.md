# Chrome版 v0.4.6

Backlog to Google Calendar HelperのGoogle Chrome向けプロトタイプです。

## v0.4.6の変更点

- Googleカレンダーの説明欄が `aria-labelledby="xDescIn-label"` を使うDOMに変更されたことに対応
- ブラウザのフォーカス状態などでクリップボード書き込みに失敗しても、課題情報の保存とCalendar / Taskへの自動入力を継続するよう修正
- Backlog課題タイトル内のハイフンを区切りと誤認し、件名が途中で切れる問題を修正

## ショートカット

- Calendar: `Ctrl + Shift + L` / macOS `Command + Shift + L`
- Task: `Ctrl + Shift + K` / macOS `Command + Shift + K`

## インストール

1. このフォルダ、または `packages/backlog-to-google-calendar-helper-chrome-v0.4.6.zip` を展開したフォルダを用意する
2. `chrome://extensions/` を開く
3. デベロッパーモードをON
4. 「パッケージ化されていない拡張機能を読み込む」からフォルダを選ぶ
5. `chrome://extensions/shortcuts` でショートカットを確認する

既存バージョンから更新した場合は、拡張機能を再読み込みしたあと、開いているBacklogとGoogleカレンダーのタブも再読み込みしてください。

## トラブルシューティング

### `Extension context invalidated` と表示される / 更新後に動かない

拡張機能の更新・再読み込み前から開いていたタブに古いcontent scriptが残ると発生することがあります。

1. Backlogの課題ページを再読み込みする
2. Googleカレンダーを再読み込みする
3. 改善しない場合はGoogleカレンダーのタブを閉じて開き直す
4. 再度ショートカットを実行する

### ショートカットが効かない

`chrome://extensions/shortcuts` でCalendar / Taskのショートカットを確認してください。OSや他の拡張機能と競合する場合があります。

### Calendar / Taskへ自動入力されない

BacklogとGoogleカレンダーの両方を再読み込みしてから再度実行してください。Google CalendarのUI / DOM変更により入力欄の構造が変わった場合は、拡張側の修正が必要になることがあります。

### クリップボードへのコピーに失敗する

v0.4.6ではクリップボード書き込みの失敗をCalendar / Task連携の失敗として扱いません。課題情報を拡張ストレージへ保存できていれば、自動入力処理は継続します。

プロトタイプとしての注意事項とデータの扱いは、リポジトリ直下の `README.md` と `docs/SECURITY_AND_PRIVACY.md` を参照してください。
