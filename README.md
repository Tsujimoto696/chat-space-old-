# Chat-Space DB設計

## Usersテーブル
|id|Column|type|Options|group_id|comments|member_id|
|--|------|----|-------|--------|--------|---------|
|integer|name|string|null: false, foreign_key: true|integer|integer|integer|

### Association
 - has_many :comments
 - has_many :members
 - has_many :groups, through: :members

                   
## Commentsテーブル
|id|Column|type|Options|CreateDate|user_id|group_id|
|--|------|----|-------|----------|-------|--------|
|integer|text|string|null: false, foreign_key: true|date|integer|integer|

### Association
 - belongs_to :user


## Groupsテーブル
|id|Column|type|Options|user_id|member_id|comments_id|
|--|------|----|-------|-------|---------|-----------|
|integer|Group_name|string|null: false, foreign_key: true|integer|integer|

### Association
 - has_many :users, through: members
 - has_many :comments
 - has_many :members


## Membersテーブル
|id|column|type|Options|user_id|comment_id|group_id|
|--|------|----|-------|-------|----------|--------|
|integer|text|string|null: false, foreign_key: true|integer|integer|integer|

### Association
 - has_many :users
 - belongs_to :group
 - has_many :comments, through: ,users

end