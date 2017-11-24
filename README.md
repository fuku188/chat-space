## messagesテーブル

|Column|Type|Options|
|------|----|-------|
|body|text|null:false|
|image|string|null:false|
|group_id|references:group|null:false, foreign_key: ture|
|user_id|references:user|null:false, foreign_key: true|

### Association
- belongs_to :user
- belongs_to :group


## membersテーブル(中間テーブル)

|Column|Type|Option|
|------|----|------|
|group_id|references:group|null:false, foreign_key|
|user_id|references:user|null:false, foreign_key:  true|

### Asociation
- has_one :user
- belongs_to :group


## usersテーブル

|Column|Type|Option|index|
|------|----|------|-----|
|name|stirng|null: false|unique: true|

### Association
- has_many :messages
- has_one :member


## groupsテーブル

|Column|Type|Options|
|------|----|-------|
|date|integer|null:false|

### Association
- has_many :messages
- has_many :members

