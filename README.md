# テーブル設計

## users テーブル

| Column             | Type   | Options                         |
| ------------------ | ------ | ------------------------------- |
| name               | string | null: false                     |
| email              | string | null: false, uniqueness: true   |
| encrypted_password | string | null: false                     |

### Association

- has_many :knowledge

## knowledges テーブル

| Column               | Type       | Options                        |
| -------------------- | ---------- | ------------------------------ |
| company_id           | integer    |                                |
| category_id          | integer    | null: false                    |
| subcategory_id       | integer    | null: false                    |
| subsubcategory_id    | integer    | null: false                    |
| case                 | text       | null: false                    |
| isolation            | text       | null: false                    |
| solution             | text       | null: false                    |
| addition             | text       | null: false                    |
| user                 | references | null: false, foreign_key: true |

### Association

- belongs_to :user