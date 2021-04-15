# Hahow Quality Engineer 徵才小專案

這是一個小型的徵才專案，會需要你使用熟悉的框架與語言來實作 API & UI 的驗證

## 細部需求

### API

[API Spec]

- URL: https://swapi.dev/
- swapi has rate limiting to prevent malicious abuse. Rate limiting is done via IP address and is currently limited to 10,000 API request per day. be no reason for hitting the rate limit.
- No performance testing with swapi.

[Goal]

- Please design an automation script to check:
  - How many different species appears in film-6 (Revenge of the Sith) ? 有多少不同種族的人出現在第六部？
  - Please list all the film names and sort the name by episode_id. 請依據電影集數去排序電影名字？
  - Please find out all vehicles which max_atmosphering_speed is over 1000. 請幫我挑出電影裡所有的車輛，馬力超過１０００的。

## 加分建議

- 程式的可讀性與可維護性
- 任何你覺得很酷的事情
- 利用 GraphQL 實作相同題目
  - URL: https://graphql.org/swapi-graphql

### UI

- URL: https://github.com/hahow/hahow-recruit

[Goal]

- Please design an automation script to check:
  - How many contributors in this project? and please find out their name
  - Please Go into the frontend.md and check the "Wireframe" images is exist or not
  - Who is the lastest commit person?
