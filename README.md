# Chat-Space DB設計

## Usersテーブル
|id|Name|E-mail|Options|coments_id|member_id|group_id|
|--|----|------|-------|----------|---------|--------|
|integer|string|string|null: false, foreign_key: true|integer|integer|integer|


### Association
- has_many :comments
- has_many :members
- has_many :groups, through: :members


## Commentsテーブル
|id|Column|type|Options|user_id|CreateDate|member_id|group_id|
|--|------|----|-------|-------|----------|---------|--------|
|integer|text|null: false, foreign_key: true|integer|integer|

### Association
- belongs_to :user
- belongs_to :group
- belongs_to :member

## Groupsテーブル
|id|Column|type|Options|user_id|member_id|comemnts_id|
|--|------|----|-------|-------|---------|-----------|
|integer|Group_name|string|null: false, foreign_key: true|integer|integer|integer|

### Association
- has_many :users, through: members
- has_many :comments
- has_many :members



## memberテーブル
|id|Options|comments-id|user_id|comments_id|group_id|
|--|-------|-----------|-------|-----------|--------|
|integer|text|null: false, foreign_key: true|integer|integer|integer|

### Association
- has_many :users
- belongs_to :group
- has_many :comments, through: ,users

end
