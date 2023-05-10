# git branch

## default のブランチ名を変えた時の対応

```bash
git branch -m main develop
git fetch origin
git branch -u origin/develop develop
git remote set-head origin -a
```
