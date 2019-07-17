# Chat-Space DB設計

## Usersテーブル
|Column|type|Options|
|------|----|-------|
|name|string|null: false, foreign_key: true|

### Association
 - has_many :comments
 - belongs_to :group

                   
## commentsテーブル
|Column|type|Options|
|------|----|-------|
|text|string|null: false, foreign_key: true|

### Association
 - belongs_to :user
 - belongs_to :group


## groupsテーブル
|Column|type|Options|
|------|----|-------|
|text|string|null: false, foreign_key: true|

### Association
 - has_many :users, through: members
 - has_many :comments

## membersテーブル
|id|Options|
|--|-------|
|integer|null: false, foreign_key: true|
|integer|null: false, foreign_key: true|

### Association
 - belongs_to :user
 - belongs_to :group

end