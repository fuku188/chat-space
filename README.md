## usersテーブル

|Column|Type|Option|
|------|----|------|-----|
|name|stirng|null: false,unique: true|
|mail|string|null: false,unique: true|

### Association
- has_many :groups, through: members
- has_many :memssages
- has_many :members


## groupsテーブル

|Column|Type|Options|
|------|----|-------|
|name|integer|null:false,unique: true|

### Association
- has_many :users, through: :members
- has_many :messages
- has_many :messages


## messagesテーブル

|Column|Type|Options|
|------|----|-------|
|body|text|
|image|string|
|group_id|integer|null:false, foreign_key: ture|
|user_id|integer|null:false, foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user


## membersテーブル(中間テーブル)

|Column|Type|Option|
|------|----|------|
|group_id|integer|null:false, foreign_key|
|user_id|integer|null:false, foreign_key:  true|

### Asociation
- belongs_to :group
- belongs_to :user
