# git

git のあれこれ

## 直前のコミットを取り消す

```bash
git reset --soft HEAD^
```

ステージングされた状態に戻る

### 参考 URL

https://qiita.com/shuntaro_tamura/items/06281261d893acf049ed

---

## GitHub のリポジトリ名を変更

1. GitHub 側のリポジトリ名を変更
2. リモート側のリポジトリ名を変更
   1. 変更後の GitHub の SSH の URL を確認
   2. `.git/config`の`url`を上記で確認した URL に修正
3. リモートのディレクトリ名を修正

### 参考 URL

https://www.fuwamaki.com/article/78
