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

## userテーブル

|Column|Type|Options|
|------|----|-------|
|nickname|integer|null: false|
|image|string|
|text|string|

### Association
- has_many :comment
- has_many :item



## itemテーブル

|Column|Type|Options|
|------|----|-------|
|name|integer|null: false|
|image|string|null: false|
|text|string|null: false|
|user_id|references|null: false|
|category_id|references|null: false|


### Association
- belongs_to :user
- has_many :comment
- has_one :category

## commentsテーブル

|Column|Type|Options|
|------|----|-------|
|user_id|references|null: false|
|item_id|references|null: false|
|text|string|null: false|

### Association
- belongs_to :item
- belongs_to :user

## categoryテーブル

|Column|Type|Options|
|------|----|-------|
|tops|string|
|bottoms|string|
|accessory|string|
|other|string|

### Association
- belongs_to :item