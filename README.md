# Chat-Space DB設計

## Usersテーブル
|id|Name|E-mail|Options|Coments_id|Member_id|Group_id|
|--|----|------|-------|----------|---------|--------|
|integer|string|string|null: false, foreign_key: true|
|integer|string|string|null: false, foreign_key: true|
|integer|string|string|null: false, foreign_key: true|


### Association
class Users  << ApplicationRecord
  has_many    : coments  : group
  has_many    : member
end

                   
## commentsテーブル
|id|Column|Options|User_id|Member_id|Group_id|
|--|------|-------|-------|---------|--------|
|integer|text|null: false, foreign_key: true|
|integer|text|null: false, foreign_key: true|
|integer|text|null: false, foreign_key: true|

### Association
class Users  << ApplicationRecord
  belongs_to :user
end


## groupsテーブル
|id|Options|User_id|Comemnts_id|Member_id|
|--|-------|-------|-----------|---------|
|integer|null: false, foreign_key: true|
|integer|text|null: false, foreign_key: true|

### Association
class groups  << ApplicationRecord 
  belongs_to :member
  belongs_to :users
end

## memberテーブル
|id|Options|Comments-id|User_id|Group_id|
|--|-------|-----------|-------|--------|
|integer|null: false, foreign_key: true|
|integer|null: false, foreign_key: true|

### Association
class member  << ApplicationRecord
  belongs_to :user
  belongs_to :group
  belongs_to  :comments
end
