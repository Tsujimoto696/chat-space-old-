# Chat-Space DB設計

## Usersテーブル
|id|Name|E-mail|Options|Coments_id|Member_id|Group_id|
|--|----|------|-------|----------|---------|--------|
|integer|string|string|null: false, foreign_key: true|
|integer|string|string|null: false, foreign_key: true|
|integer|string|string|null: false, foreign_key: true|


### Association
- belongs_to :coments
- belongs_to :group
- belongs_to :member


## commentsテーブル
|id|Column|Options|User_id|Member_id|Group_id|
|--|------|-------|-------|---------|--------|
|integer|text|null: false, foreign_key: true|
|integer|text|null: false, foreign_key: true|
|integer|text|null: false, foreign_key: true|

### Association
- belongs_to :user


## groupsテーブル
|id|Options|User_id|Comemnts_id|Member_id|
|--|-------|-------|-----------|---------|
|integer|null: false, foreign_key: true|
|integer|text|null: false, foreign_key: true|

### Association
- belongs_to :member
- belongs_to :user


## memberテーブル
|id|Options|Comments-id|User_id|Group_id|
|--|-------|-----------|-------|--------|
|integer|text|null: false, foreign_key: true|
|integer|text|null: false, foreign_key: true|

### Association
- belongs_to :user
- belongs_to :group
