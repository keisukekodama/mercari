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
|Column|Type|Options|
|------|----|-------|
|nickname|string|null: false,index: true|
|email|string|null: false, unique: true|
|password|string|null: false|
|profile|text|

### Association
- has_many :paies
- has_many :productes
- has_many :evaluations
- belongs_to :adress

## adressesテーブル
|Column|Type|Options|
|------|----|-------|
|name_last|string|null: false|
|name_last_kana|string|null: false|
|name_first|string|null: false|
|name_first_kana|string|null: false|
|postal_code|string|null: false|
|ken_name|string|null: false|
|city_name|string|null: false|
|bilding|string|null: true|
|tel_phone|string|null: false|
|tel_home|string|null: ture|

### Association
- belongs_to user

## productsテーブル
|Column|Type|Options|
|------|----|-------|
|name|references|null: false, foreign_key: true|
|description|references|null: false, foreign_key: true|
|category|string|null: false|
|status|text|null: false|
|prise|string|null: false|
|sold|tstring|null: false|
|transaction|text|null: false|
|user|string|null: false, foreign_key: true|
|evaluation|string|null: , foreign_key: true|

### Association
- belongs_to :user
- belongs_to :evaluation
- has_many :images

## paiesテーブル
|Column|Type|Options|
|------|----|-------|
|cardnumber|references|null: false|
|month|references|null: false|
|day|string|null: false|
|code|text|null: false|
|banck|string|null: false|
|tatemono|text|null: false|
|cardnumber|string|null: false|

### Association
- belongs_to :user

## imagesテーブル
|Column|Type|Options|
|------|----|-------|
|name|references|null: false, foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user

## evaluationsテーブル
|Column|Type|Options|
|------|----|-------|
|rate|references|null: false|
|review|references|null: false|
|product|text|null: false, foreign_key: true|
|user|string|null: false, foreign_key: true|

### Association
- belongs_to :user
- belongs_to :evaluation
