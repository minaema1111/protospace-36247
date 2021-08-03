# テーブル設計

## users テーブル

| column    | Type   | Options    |
| ----------|--------|------------|
| email     | string | null: false|
| password  | string | null: false|
| name      | string | null: false|
| profile   | text   | null: false|
| occupation| text   | null: false|
| position  | text   | null: false|

### Association

- has_many :prototypes
- has_many :comments

## comments テーブル

| column   | Type      | Option     |
| ---------|-----------|------------|
| text     | text      | null: false|
| user     | references|            |
| prototype| references|            |

### Association

- belongs_to :user
- belongs_to :prototype

## prototypes テーブル

| column    | Type      | Option     |
|-----------|-----------|------------|
| title     | string    | null: false|
| catch_copy| text      | null: false|
| concept   | text      | null: false|
| user      | references|            |

### Association

- has_many :comments
- belongs_to :users