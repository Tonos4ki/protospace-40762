## Usersテーブル
| column             | type   | options                   |
| ------------------ | ------ | ------------------------- |
| email              | string | null: false, unique: true |
| encrypted_password | string | null: false               |
| name               | string | null: false               |
| profile            | text   | null: false               |
| occupation         | text   | null: false               |
| position           | text   | null: false               |

### Association
- hus_many:prototypes
- hus_many:comments

## Prototypesテーブル
| column      | type       | options                        |
| ----------- | ---------- | ------------------------------ |
| title       | string     | null: false                    |
| catch_copy  | text       | null: false                    |
| concept     | text       | null: false                    |
| user        | references | null: false, foreign_key: true |

### Association
- belongs_to :user
- has_many :comments

## Commentテーブル
| column    | type       | options                        |
| --------- | ---------- | ------------------------------ |
| content   | text	     | null: false                    |
| prototype | references | null: false, foreign_key: true |
| user      | string     | null: false, foreign_key: true |

### Association
- belongs_to :prototype
- belongs_to :user