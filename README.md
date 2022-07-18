# README

# usersテーブル
| Column               | Type    | Options                   |
| -------------------- | ------- | ------------------------- |
| nickname             | string  | null: false               |
| email                | string  | null: false, unique: true |
| encrypted_password   | string  | null: false               |
| skintype_id          | integer | null: false               |


### Association
- has_many :todolists
- has_many :logolists

# todolistsテーブル
| Column               | Type       | Options                           |
| -------------------- | ---------- | --------------------------------- |
| todolist             | string     | null: false                       |
| troubletype_id       | integer    | null: false                       |
| goal                 | text       | null: false                       |
| user                 | references | null: false, foreign_key: true    |

### Association
- has_many :logolists
- belongs_to :user

# logolistsテーブル
| Column               | Type       | Options                           |
| -------------------- | ---------- | --------------------------------- |
| comment              | string     | null: false                       |
| todolist             | references | null: false, foreign_key: true    |
| user                 | references | null: false, foreign_key: true    |

### Association
- belongs_to :todolist
- belongs_to :user