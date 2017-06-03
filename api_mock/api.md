# Data Structure

## Event
  + event (object) - event
      + date: `2017-02-15` (string) - 日付
      + note: `社内研修` (string) - 備考
      + holiday: true (boolean) - 祝日有無 0: false, 1: true

# Group イベント関連API

## 一覧 [/events{?started_at,ended_at}]

### イベント一覧取得 [GET]

* 登録済みのイベント一覧を取得する

+ Parameters
    + started_at: `2017-02-01` (string, required) - 開始日
    + ended_at: `2017-02-28` (string, required) - 終了日

+ Response 200 (application/json; charset=utf-8)

    + Attribute
        + events (array) - イベント一覧
            + (object)
                + start_date: `2017-02-15` (string) - 日付
                + end_date: `2017-02-15` (string) - 日付
                + summary: `社内研修` (string) - 備考
                + national_holiday: true (boolean) - 祝日有無

# Group 認証関連API

## トークン [/user/token]

### 発行 [POST]

* 認証を実施し成功した場合はトークンを発行する

+ Request (application/json)

    + Attribute
        + email: `xxxxxxxxxx` (string, required) - メールアドレス
        + password: `xxxxxxxxxx` (string, required) - パスワード

+ Response 201 (application/json; charset=utf-8)

    + Attribute
        + access_token: `xxxxxxxxxx` (string) - アクセストークン

## パスワード [/user/password]

### 変更 [PUT]

* パスワードを変更する

+ Request (application/json)

    + Attribute
        + old_password: `xxxxxxxxxx` (string, required) - 現在パスワード
        + new_password: `xxxxxxxxxx` (string, required) - 新パスワード

+ Response 200 (application/json; charset=utf-8)
