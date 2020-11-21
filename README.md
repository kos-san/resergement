# テーブル設計

## users テーブル

| Column             | Type   | Options     |
| ------------------ | ------ | ----------- |
| email              | string | null: false |
| encrypted_password | string | null: false |
| name               | string | null: false |
| phone_num          | string | null: false |

### Association

- has_many :stores

## stores テーブル

| Column             | Type      | Options                        |
| ------------------ | --------- | ------------------------------ |
| name               | string    | null: false                    |
| open               | time      | null: false                    |
| close              | time      | null: false                    |
| last_order         | time      | null: false                    |
| address            | string    | null: false                    |
| building           | string    |                                |
| tel                | string    | null: false                    |
| capacity           | integer   | null: false                    |
| regular_holiday_id | integer   | null: false                    |
| user_id            | reference | null: false, foreign_key: true |

### Association

- belongs_to :user
- has_many :reservations

## reservations テーブル

| Column           | Type      | Options                        |
| ---------------- | --------- | ------------------------------ |
| name             | string    | null: false                    |
| phone_num        | string    | null: false                    |
| email            | string    | null: false                    |
| start_time       | time      | null: false                    |
| number_of_people | integer   | null: false                    |
| text             | text      |                                |
| store_id         | reference | null: false, foreign_key: true |

### Association

- belongs_to :store

# ER図
!(ER1.png)