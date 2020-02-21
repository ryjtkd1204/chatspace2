# README

## usersテーブル
|Column|Type|Options|
|------|----|-------|
|email|string|null: false|
|name|string|null: false,add_indexTo|
### Association
- has_many :groups, throgh: groups_users
- has_many :messeages
- has_many :group_users

## groupテーブル
|Column|Type|Options|
|------|----|-------|
|name|
- |group_name|integer|null: false, foreign_key: true| 
### Association
- has_many :users, throgh: groups_users
- has_many :messages
- has_many :group_users

## messagesテーブル
|Column|Type|Options|
|------|----|-------|
|text|text|image|null: false|
|image|
|group_id|reference|null: false, foreign_key: true|
|user_id|reference|null: false, foreign_key: true|
### Association
- belongs_to :group
- belongs_to :user

## groups_usersテーブル
|Column|Type|Options|
|------|----|-------|
|user_id|reference|null: false, foreign_key: true|
|group_id|reference|null: false, foreign_key: true|
### Association
- belongs_to :group
- belongs_to :user