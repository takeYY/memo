# フォーマッターの設定

## VSCode

### settings.json にコピペするだけ

https://deecode.net/?p=2047

```jsonc
{
  // 保存時のフォーマットを有効にする
  "": {
    "editor.tabSize": 4,
    "editor.formatOnSave": true,
    // importの自動整形
    "editor.codeActionsOnSave": {
      "source.organizeImports": true
    }
  },
  // 保存時のフォーマットにblackを使用するようにする
  "python.formatting.provider": "black",
  // オプションを指定,不要なら空にする
  // オプションで設定ファイル指定可能
  "python.formatting.blackArgs": ["--config=pyproject.toml"],

  // 型チェックはPylanceかmypyどちらか一方で良い
  // mypyの設定
  "python.linting.mypyEnabled": true,
  // オプションを指定,不要なら空にする
  // config fileの指定はできなそう
  "python.linting.mypyArgs": [],
  // pylanceの型チェック設定
  "python.analysis.typeCheckingMode": "basic",

  // flake8の有効化、設定
  "python.linting.flake8Enabled": true,
  // オプションを指定,不要なら空にする
  // config fileの指定はできなそう
  "python.linting.flake8Args": [
    "--ignore=E203,E266,W503,",
    "--max-line-length=88",
    "--max-complexity=10"
  ],

  // (これはどっちでもいい)docstringをgoogleフォーマットにする
  // https://sphinxcontrib-napoleon.readthedocs.io/en/latest/example_google.html
  "autoDocstring.docstringFormat": "google"
}
```
