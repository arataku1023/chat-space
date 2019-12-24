# README

## usersテーブル

|Column|Type|Options|
|------|----|-------|
|email|string|null: false|
|password|string|null: false|
|name|string|null: false|

### Association
has_many :messages
has_many :groups, through: :users_groups

## groupsテーブル
|Column|Type|Options|
|------|----|-------|
|title|text|null: false|
|user_id|references|null: false, foreign_key: true|

### Association
has_many :messages
has_many :users, through: :users_groups


## groups_usersテーブル

|Column|Type|Options|
|------|----|-------|
|user_id|references|null: false, foreign_key: true|
|group_id|references|null: false, foreign_key: true|

### Association
belongs_to :group
belongs_to :user

## messsges テーブル

|Column|Type|Options|
|------|----|-------|
|text|text|
|image|string|
|user_id|references|null: false, foreign_key: true|
|group_id|references|null: false, foreign_key: true|

### Association
belongs_to user
belongs_to group

