## messagesテーブル

|Column|Type|Options|
|------|----|-------|
|body|text|null:false|
|image|string|null:false|
|group_id|integer|null:false, foreign_key: ture|
|user_id|integer|null:false, foreign_key: true|

### Association
- belongs_to :user
- belongs_to :group
- belongs_to :member


## membersテーブル

|Column|Type|Option|
|------|----|------|
|group_id|integer|null:false, foreign_key|
|user_id|integer|null:false, foreign_key:  true|

### Asociation
- has_one :users
- belongs_to :group
- has_many :messages


## usersテーブル

|Column|Type|Option|index|
|------|----|------|-----|
|name|stirng|null: false|unique: true|
|group_id|integer|null:false, foreign_key:  true|
|member_id|integer|null:false, foreign_key: true|

### Association
- has_many :messages
- has_one :members


## groupsテーブル

|Column|Type|Options|
|------|----|-------|
|date|integer|null:false|
|user_id|integer|null:false, foreign_key: true|
|member_id|integer|null:false, foreign_key: true|

### Association
- has_many :messages
- has_many :members

