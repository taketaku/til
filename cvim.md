
- [origin](https://github.com/1995eaton/chromium-vim)
- [参考](https://qiita.com/quiwamu/items/f7acdbf0ef4bf374c2b7)
- [コンフリクト注意 - googleショートカット](https://support.google.com/chrome/answer/157179?hl=ja)
# cvim操作


## 移動系
|コマンド|説明|
|---|---|
|j,k|↑, ↓|
|w,s|↑, ↓|
|h,l|←, →|
|H,L|進む, 戻る|
|J,K|タブ ←, →|
|gT,gt|タブ ←, →|
|gg,G|ページ 最上部, 最下部|

## 閉じる
|コマンド|説明|
|---|---|
|x|タブを閉じる|

## 検索系
|title|コマンド|移動コマンド|移動コマンド説明|
|---|---|---|---|
|ページ内検索|/(対象文字列)|n, N|次, 前|

## cvimrc

```
set noautofocus # 自動的にインプットフィールドにフォーカスが合うのを中止
map u lastClosedTab # 最後に閉じたタブを開く（undoの感覚）
iunmap <C-k> # カーソルより後ろを消す

```