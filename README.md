# Chatspace DB設計

## usersテーブル
|Column|Type|Options|
|------|----|-------|
|nickname|string|null: false|
|email|string|null: false|
|password|string|null: false|

### association
- has_many :tweets
- has_many :groups
- has_many  :groups,  through:  :groups_users

 ## tweetsテーブル
|Column|Type|Options|
|------|----|-------|
|text|text||
|user_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :user
- belongs_to :group

## groupsテーブル
|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|

### Association
- has_many :users
- has_many  :users,  through:  :groups_users

## groups_usersテーブル

|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user

