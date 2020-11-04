# テーブル設計

## users テーブル

| column　    | Type  | Options      |
| -----------|--------|-------------|
| email      | string | null: false |
| password   | string | null: false |
| name       | string | null: false |
| profile    | text   | null: false |
| occupation | text   | null: false |
| position   | text   | null: false |

### Association

- has_many :prototypes
- has_many :comments

## prototypes テーブル

| column　    | Type               | Options    |
| -----------|--------------------|-------------|
| title      | string             | null: false |
| catch_copy | text               | null: false |
| concept    | text               | null: false |
| image      | ActiveStorageで実装 |             |
| user       | reference          |             |　　　

### Association

- has_many :comments
- belongs_to :users

## comments テーブル

| column　   | Type     | Options    |
| ----------|-----------|-------------|
| text      | text      | null: false |
| user      | reference |             |
| prototype | reference |             |　　　

### Association

- belongs_to :prototype
- belongs_to :users
