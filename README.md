## usersテーブル
|Column|Type|Options|
|------|----|-------|
|email|string||null: false|
|password|string|null: false|
|nickname|string|null: false, index: true|
## Association
- has_many :groups
- has_many :messages

## groupsテーブル
|Column|Type|Options|
|------|----|-------|
|name|string|null: false|
## Association
- has_many :groups_users
- has_many :messages

## messagesテーブル
|Column|Type|Options|
|------|----|-------|
|body|text||
|image|string||
|group_id|references|null: false, foreign_key: true|
|user|references|null: false, foreign_key: true|
## Association
- belongs_to :groups
- belongs_to :users

## groups_usersテーブル
|Column|Type|Options|
|------|----|-------|
|user|references|null: false, foreign_key: true|
|group_id|references|null: false, foreign_key: true|
### Association
- belongs_to :groups
- belongs_to :users