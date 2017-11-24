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


## membersテーブル

|Column|Type|Option|
|------|----|------|
|group_id|integer|null:false, foreign_key|
|user_id|integer|null:false, foreign_key:  true|

##Asociation
- belongs_to :user
- belongs_to :group


## usersテーブル

|Column|Type|Option|
|------|----|------|
|name|stirng|null:false|
|group_id|integer|null:false, foreign_key:  true|
|member_id|integer|null:false, foreign_key: true|

### Association
- has_many :messages
- has_many :members


## groupsテーブル

|Column|Type|Options|
|------|----|-------|
|date|integer|null:false|
|user_id|integer|null:false, foreign_key: true|
|member_id|integer|null:false, foreign_key: true|

### Association
- has_many :messages
- has_many :members

