# README

## usersテーブル
|Column|Type|Options|
|------|----|-------|
|email|string|null: false|
|name|string|null: false|add_indexTo
### Association
- has_many :groups
- has_many :messeages
- has_many :group_users

## groupテーブル
|Column|Type|Options|
|------|----|-------|
|image|text||
|text|text||
|integer|null: false, foreign_key: true|
|group_name|integer|null: false, foreign_key: true|
### Association
- has_many :users, throgh: groups_users
- has_many :messages
- has_many :group_users

## messagesテーブル
|Column|Type|Options|
|------|----|-------|
|text|text|image|null: false|
|group_id|integer|null: false, foreign_key: true|
|tweet_id|integer|null: false, foreign_key: true|
### Association
- belongs_to :group
- belongs_to :user

## groups_usersテーブル
|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|
### Association
- belongs_to :group
- belongs_to :user