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
|name|text|null: false|
|password|text|null: false|
|mail-address|text|null: fa;se, unique: true|

### Association
- has_many :groups, through: :users_groups
- has_many :comments

## groupsテーブル

|Column|Type|Option|
|------|----|------|
|id|integer|null: false|
|name|text|null: false|

### Association
- has_many :users, through: :users_groups
- has_many :comments

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
|user_id|integer|null: false|
|group_id|integer|null: false|


### Association
- belongs_to :user
- belongs_to :group