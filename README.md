## usersテーブル
|Column|Type|Options|
|------|----|-------|
|email|string||null: false|
|password|string|null: false|

|nickname|string|null: false, index: true|
## Association
- has_many :groups, through: :groups_users
- has_many :groups_users
- has many :messages

## groupsテーブル
|Column|Type|Options|
|------|----|-------|

|name|string|null: false|
## Association
- has_many :groups_users
- has_many :messages
- has many :users, through: :groups_users

## messagesテーブル
|Column|Type|Options|
|------|----|-------|

|body|text||
|image|string||
|group|references|null: false, foreign_key: true|
|user|references|null: false, foreign_key: true|

## Association
- belongs_to :group
- belongs_to :user

## groups_usersテーブル
|Column|Type|Options|
|------|----|-------|

|user|references|null: false, foreign_key: true|
|group|references|null: false, foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user