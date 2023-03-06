# git tag

## コメント付きタグ作成

`{:TAG}`: v1.2 など

```bash
git tag -a {:TAG} -m '{:COMMENT}'
```

### 例

```bash
git tag -a v1.3 -m "2020.12.25リリース"
```

## リモートに反映

```bash
git push origin {:TAG}
```

## 参考

- [git tag の使い方まとめ](https://qiita.com/growsic/items/ed67e03fda5ab7ef9d08)
