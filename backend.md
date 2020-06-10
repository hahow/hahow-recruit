# Hahow Backend Engineer 徵才小專案

這是一個小型的徵才專案，會需要你使用 Node.js，來寫簡單的 API server，而實作這個 API server 所需要使用到的資料，則會在我們預先寫好的 API 中提供


## 細部需求

- 必須使用 Node.js 來實作這個 API server
- 完成後的 API 需要有相對應的測試
- 你的 code 裡面必須包含你所寫的註解（英文尤佳）
- 實作的過程必須使用 git 來做版本控管
- 可以使用第三方的 library
- 提供一份 README 文件說明
  - 我們該如何跑起這個 server
  - 專案的架構，API server 的架構邏輯
  - 你對於所有使用到的第三方 library 的理解，以及他們的功能簡介
  - 你在程式碼中寫註解的原則，遇到什麼狀況會寫註解
  - 在這份專案中你遇到的困難、問題，以及解決的方法

## 加分建議

- 各個 route 對於接收資料的各種邊際情況的處理
- 程式的可讀性與可維護性
- 任何你想得到會讓我們覺得很酷的東西

## 最後

當你完成的時候，請將你的 GitHub repo 連結(或 GitLab 等可以讓我們看到 repo 的地方) e-mail 給我們。

同時我們也認為在程式開發的過程中溝通是很重要的，所以如果過程中你有任何問題，不論是看不懂我們所寫的文件，或是對於我們提供的 API 有疑問，都歡迎直接 email 和我們討論

## API Server 需求

### List Heroes [GET] `/heroes`

**Request**

```bash
curl -H "Accept: application/json" -H "Content-Type: application/json" -X GET https://yourapiserver/heroes
```

**Response 200**

```jsonc
{
  "heroes": [
    {
      "id": "1",
      "name": "Daredevil",
      "image": "http://i.annihil.us/u/prod/marvel/i/mg/6/90/537ba6d49472b/standard_xlarge.jpg"
    },
    {
      "id": "2",
      "name": "Thor",
      "image": "http://x.annihil.us/u/prod/marvel/i/mg/5/a0/537bc7036ab02/standard_xlarge.jpg"
    },
    // ...
  ]
}
```

### Single Hero [GET] `/heroes/:heroId`

**Request**

```bash
curl -H "Accept: application/json" -H "Content-Type: application/json" -X GET https://yourapiserver/heroes/1
```

**Response 200**

```jsonc
{
  "id": "1",
  "name": "Daredevil",
  "image": "http://i.annihil.us/u/prod/marvel/i/mg/6/90/537ba6d49472b/standard_xlarge.jpg"
}
```

### Authenticated List Heroes [GET] `/heroes`

**Request**

```bash
curl -H "Accept: application/json" -H "Content-Type: application/json" -H "Name: hahow" -H "Password: rocks" -X GET https://yourapiserver/heroes
```

**Response 200**

```jsonc
{
  "heroes": [
    {
      "id": "1",
      "name": "Daredevil",
      "image": "http://i.annihil.us/u/prod/marvel/i/mg/6/90/537ba6d49472b/standard_xlarge.jpg",
      "profile": {
        "str": 2,
        "int": 7,
        "agi": 9,
        "luk": 7
      },
    },
    {
      "id": "2",
      "name": "Thor",
      "image": "http://x.annihil.us/u/prod/marvel/i/mg/5/a0/537bc7036ab02/standard_xlarge.jpg"
      "profile": {
        "str": 8,
        "int": 2,
        "agi": 5,
        "luk": 9
      },
    },
    // ...
  ]
}

```

### Authenticated Single Heroes [GET] `/heroes/:heroId`

**Request**

```bash
curl -H "Accept: application/json" -H "Content-Type: application/json" -H "Name: hahow" -H "Password: rocks" -X GET https://yourapiserver/heroes/1
```

**Response 200**

```jsonc
{
  "id": "1",
  "name": "Daredevil",
  "image": "http://i.annihil.us/u/prod/marvel/i/mg/6/90/537ba6d49472b/standard_xlarge.jpg",
  "profile": {
    "str": 2,
    "int": 7,
    "agi": 9,
    "luk": 7
  }
}
```

## 我們所提供的資料及 API

### List Heroes [GET] `https://hahow-recruit.herokuapp.com/heroes`

**Request**

```bash
curl -H "Accept: application/json" -H "Content-Type: application/json" -X GET https://hahow-recruit.herokuapp.com/heroes
```

**Response 200**

```jsonc
[
  {
    "id": "1",
    "name": "Daredevil",
    "image": "http://i.annihil.us/u/prod/marvel/i/mg/6/90/537ba6d49472b/standard_xlarge.jpg"
  },
  {
    "id": "2",
    "name": "Thor",
    "image": "http://x.annihil.us/u/prod/marvel/i/mg/5/a0/537bc7036ab02/standard_xlarge.jpg"
  },
  // ...
]
```

### Single Hero [GET] `https://hahow-recruit.herokuapp.com/heroes/:heroId`

**Request**

```bash
curl -H "Accept: application/json" -H "Content-Type: application/json" -X GET https://hahow-recruit.herokuapp.com/heroes/1
```

**Response 200**

```json
{
  "id": "1",
  "name": "Daredevil",
  "image": "http://i.annihil.us/u/prod/marvel/i/mg/6/90/537ba6d49472b/standard_xlarge.jpg"
}
```

### Profile of Hero [GET] `https://hahow-recruit.herokuapp.com/heroes/:heroId/profile`

**Request**

```bash
curl -H "Accept: application/json" -H "Content-Type: application/json" -X GET https://hahow-recruit.herokuapp.com/heroes/1/profile
```

**Response 200**

```json
{
  "str": 2,
  "int": 7,
  "agi": 9,
  "luk": 7
}
```

### Authenticate [POST] `https://hahow-recruit.herokuapp.com/auth`

**Request**

```bash
curl -X POST -H "Content-Type: application/json" -d '{
  "name": "hahow",
  "password": "rocks"
}' "https://hahow-recruit.herokuapp.com/auth"
```

**Response 200**

---

**Request**

```bash
curl -X POST -H "Content-Type: application/json" -d '{
  "name": "hahow",
  "password": "rockssss"
}' "https://hahow-recruit.herokuapp.com/auth"
```

**Response 401**

---

**Request**

```bash
curl -X POST -H "Content-Type: application/json" -d '{
  "show": "me the secret"
}' "https://hahow-recruit.herokuapp.com/auth"
```

**Response 400**
