# API

API 全般に関して記載

## API 設計思想

### LSUDs

- Large Set of Unknown Developers
- 大多数向けの未知の外部開発者に向けた API

### SSKDs

- Small Set of Known Developers
- 利用者が自分が知っている開発者向けの API

### 参考

- [WebAPI を作る前に考えること - LSUDs と SSKDs、オーケストレーション層](https://qiita.com/peka2/items/273be01065a921833878)

## HATEOAS

- Hypermedia As The Engine Of Application State
- API の返すデータの中にリンクを含める設計

### 例

```json
{
  "friends": [
    {
      "name": "Jack",
      "link": {
        "uri": "http://api.example.com/v1/users/2",
        "rel": "user/detail"
      }
    },
    {
      "name": "EVA",
      "link": {
        "uri": "http://api.example.com/v1/users/3",
        "rel": "user/detail"
      }
    }
  ]
}
```
