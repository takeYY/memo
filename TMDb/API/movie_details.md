# Movies

{docsify-updated}

https://developers.themoviedb.org/3/movies/get-movie-details

## Response

### スキーマ

| 項目                  | 型                  | 必須     | 制限                                                                                   | 説明 |
| --------------------- | ------------------- | -------- | -------------------------------------------------------------------------------------- | ---- |
| adult                 | `boolean`           | optional |                                                                                        |      |
| backdrop_path         | `string` or `null`  | optional |                                                                                        |      |
| belongs_to_collection | `null` or `object`  | optional |                                                                                        |      |
| budget                | `integer`           | optional |                                                                                        |      |
| genres                | `array[object]`     | optional |                                                                                        |      |
| ├ id                  | `integer`           | optional |                                                                                        |      |
| └ name                | `string`            | optional |                                                                                        |      |
| homepage              | `string` or `null`  | optional |                                                                                        |      |
| id                    | `integer`           | optional |                                                                                        |      |
| imdb_id               | `string` or `null`  | optional | minLength: 9<br>maxLength: 9<br>pattern: ^tt[0-9]{7}                                   |      |
| original_language     | `string`            | optional |                                                                                        |      |
| original_title        | `string`            | optional |                                                                                        |      |
| overview              | `string` or `null`  | optional |                                                                                        |      |
| popularity            | `number`            | optional |                                                                                        |      |
| poster_path           | `string` or `null`  | optional |                                                                                        |      |
| production_companies  | `array[object]`     | optional |                                                                                        |      |
| ├ name                | `string`            | optional |                                                                                        |      |
| ├ id                  | `integer`           | optional |                                                                                        |      |
| ├ logo_path           | `string` or `null`  | optional |                                                                                        |      |
| └ origin_country      | `string`            | optional |                                                                                        |      |
| production_countries  | `array[object]`     | optional |                                                                                        |      |
| ├ iso_3166_1          | `string`            | optional |                                                                                        |      |
| └ name                | `string`            | optional |                                                                                        |      |
| release_date          | `string`            | optional | format: date                                                                           |      |
| revenue               | `integer`           | optional |                                                                                        |      |
| runtime               | `integer` or `null` | optional |                                                                                        |      |
| spoken_languages      | `array[object]`     | optional |                                                                                        |      |
| ├ iso_639_1           | `string`            | optional |                                                                                        |      |
| └ name                | `string`            | optional |                                                                                        |      |
| status                | `string`            | optional | Allowed Values: [Rumored, Planned, In Production, Post Production, Released, Canceled] |      |
| tagline               | `string` or `null`  | optional |                                                                                        |      |
| title                 | `string`            | optional |                                                                                        |      |
| video                 | `boolean`           | optional |                                                                                        |      |
| vote_average          | `number`            | optional |                                                                                        |      |
| vote_count            | `integer`           | optional |                                                                                        |      |

### 例

```json
{
  "adult": false,
  "backdrop_path": "/1Jpkm9qZcsT0mSyVXgs4VlGjPNI.jpg",
  "belongs_to_collection": null,
  "budget": 70000000,
  "genres": [
    {
      "id": 18,
      "name": "ドラマ"
    },
    {
      "id": 28,
      "name": "アクション"
    },
    {
      "id": 53,
      "name": "スリラー"
    },
    {
      "id": 10752,
      "name": "戦争"
    }
  ],
  "homepage": "",
  "id": 16869,
  "imdb_id": "tt0361748",
  "original_language": "en",
  "original_title": "Inglourious Basterds",
  "overview": "1941年、ナチス占領下のフランスの田舎町で、家族を虐殺されたユダヤ人のショシャナはランダ大佐の追跡を逃れる。一方、“イングロリアス・バスターズ”と呼ばれるレイン中尉率いる連合軍の極秘部隊は、次々とナチス兵を血祭りにあげていた。やがて彼らはパリでの作戦を実行に移す。",
  "popularity": 61.331,
  "poster_path": "/l8s62Qkdc9OkGpKjUIuAoRqrssm.jpg",
  "production_companies": [
    {
      "id": 33,
      "logo_path": "/8lvHyhjr8oUKOOy2dKXoALWKdp0.png",
      "name": "Universal Pictures",
      "origin_country": "US"
    },
    {
      "id": 59,
      "logo_path": "/yH7OMeSxhfP0AVM6iT0rsF3F4ZC.png",
      "name": "A Band Apart",
      "origin_country": "US"
    },
    {
      "id": 308,
      "logo_path": "/e8F3mQM7DkJ5SfYYDp8FYzPBOGX.png",
      "name": "The Weinstein Company",
      "origin_country": "US"
    },
    {
      "id": 682,
      "logo_path": null,
      "name": "Peninsula Films",
      "origin_country": "FR"
    },
    {
      "id": 6817,
      "logo_path": null,
      "name": "Zehnte Babelsberg Film",
      "origin_country": "DE"
    },
    {
      "id": 6818,
      "logo_path": null,
      "name": "Visiona Romantica",
      "origin_country": "US"
    }
  ],
  "production_countries": [
    {
      "iso_3166_1": "FR",
      "name": "France"
    },
    {
      "iso_3166_1": "DE",
      "name": "Germany"
    },
    {
      "iso_3166_1": "US",
      "name": "United States of America"
    }
  ],
  "release_date": "2009-08-19",
  "revenue": 321457747,
  "runtime": 152,
  "spoken_languages": [
    {
      "english_name": "German",
      "iso_639_1": "de",
      "name": "Deutsch"
    },
    {
      "english_name": "English",
      "iso_639_1": "en",
      "name": "English"
    },
    {
      "english_name": "French",
      "iso_639_1": "fr",
      "name": "Français"
    },
    {
      "english_name": "Italian",
      "iso_639_1": "it",
      "name": "Italiano"
    }
  ],
  "status": "Released",
  "tagline": "悪名こそ、彼らの名誉(グロリアス)。",
  "title": "イングロリアス・バスターズ",
  "video": false,
  "vote_average": 8.211,
  "vote_count": 19529
}
```
