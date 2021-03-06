# README

This README would normally document whatever steps are necessary to get the
application up and running.

Things you may want to cover:

* Ruby version

* System dependencies

* Configuration

* Database creation

* Database initialization

* How to run the test suite

* Services (job queues, cache servers, search engines, etc.)

* Deployment instructions

* ...

## usersテーブル

|Column|Type|Option|
|------|----|------|
|id|integer|null: false|
|name|string|null: false|
|password|text|null: false|
|mail-address|text|null: fa;se, unique: true|

### Association
- has_many :groups, through: :users_groups
- has_many :comments
- has_many :users_groups

## groupsテーブル

|Column|Type|Option|
|------|----|------|
|id|integer|null: false|
|name|string|null: false|

### Association
- has_many :users, through: :users_groups
- has_many :comments
- has_many :users_groups

## users_groupsテーブル

|Column|Type|Option|
|------|----|------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :user
- belongs_to :group


## commentsテーブル

|Column|Type|Option|
|------|----|------|
|id|integer|null: false|
|body|text|--------|
|image|string|-----|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|


### Association
- belongs_to :user
- belongs_to :group