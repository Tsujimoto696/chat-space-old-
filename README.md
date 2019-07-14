# Chat-Space DB設計

## Usersテーブル
|id|Name|E-mail|Options|coments_id|member_id|group_id|
|--|----|------|-------|----------|---------|--------|
|integer|string|string|null: false, foreign_key: true|
|integer|string|string|null: false, foreign_key: true|
|integer|string|string|null: false, foreign_key: true|


### Association
- belongs_to :coments
- belongs_to :group
- belongs_to :member


## commentsテーブル
|id|Column|Options|user_id|member_id|group_id|
|--|------|-------|-------|---------|--------|
|integer|text|null: false, foreign_key: true|
|integer|text|null: false, foreign_key: true|
|integer|text|null: false, foreign_key: true|

### Association
- belongs_to :user


## groupsテーブル
|id|Options|user_id|comemnts_id|member_id|
|--|-------|-------|-----------|---------|
|integer|null: false, foreign_key: true|
|integer|text|null: false, foreign_key: true|

### Association
- belongs_to :member
- belongs_to :user


## memberテーブル
|id|Options|comments-id|user_id|group_id|
|--|-------|-----------|-------|--------|
|integer|text|null: false, foreign_key: true|
|integer|text|null: false, foreign_key: true|

### Association
- belongs_to :user
- belongs_to :group
