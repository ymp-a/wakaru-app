# テーブル設計

## users テーブル

| Column   | Type   | Options     |
| -------- | ------ | ----------- |
| nickname | string | null: false |
| email    | string | null: false |
| password | string | null: false |

### Association

- has_many :questions
- has_many :answers

## questions テーブル

| Column  | Type       | Options                        |
| ------- | ---------- | ------------------------------ |
| title   | string     |                                |
| content | text       |                                |
| old     | integer    |                                |
| job     | integer    |                                |
| statu   | integer    |                                |
| tokumei | integer    |                                |
| user    | references | null: false, foreign_key: true |

### Association

- belongs_to :user
- has_many :answers

## answers テーブル

| Column   | Type       | Options                        |
| -------- | ---------- | ------------------------------ |
| comment  | text       | null: false                    |
| question | references | null: false, foreign_key: true |
| user     | references | null: false, foreign_key: true |



### Association

- belongs_to :answer
- has_many :users


