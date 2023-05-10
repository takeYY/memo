# git branch

## default のブランチ名を変えた時の対応

```bash
git branch -m main develop
git fetch origin
git branch -u origin/develop develop
git remote set-head origin -a
```

## 【Git】リモートに存在しないローカルブランチを一括削除する方法

- https://e-penguiner.com/remove-local-branches-not-on-remote/
- 試したことはない
  ```bash
  git fetch -p && git branch -vv | grep ': gone]' | awk '{print $1}' | xargs git branch -D
  ```
