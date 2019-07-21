# Chat-Space DB設計

## Usersテーブル
|id|Column|type|Options|group_id|
|--|------|----|-------|--------|
|integer|name|string|null: false, foreign_key: true|integer|integer|

### Association
 - has_many :comments
 - has_many :groups, through: :members
 - has_many :members

                   
## commentsテーブル
|Column|type|Options|CreateDate|user_id|group_id|
|------|----|-------|----|-------|--------|
|text|string|null: false, foreign_key: true|integer|integer|

### Association
 - belongs_to :user
 - belongs_to :group
 - has_many :members, throught: :groups


## groupsテーブル
|id|Column|type|Options|user_id|member_id|
|--|------|----|-------|-------|---------|
|integer|text|string|null: false, foreign_key: true|integer|integer|

### Association
 - has_many :users, through: members
 - has_many :comments
 - has_many :members


## membersテーブル
|Id|column|type|Options|user_id|group_id|
|--|------|----|-------|-------|--------|
|integer|text|string|null: false, foreign_key: true|||

### Association
 - belongs_to :user
 - belongs_to :group

end