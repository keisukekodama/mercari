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
|rate|string|null: false|
|profile|text|

### Association
- has_many :paies
- has_many :productes
- has_many :reviews
- belongs_to :adress

## adressesテーブル
|Column|Type|Options|
|------|----|-------|
|family_name|string|null: false|
|family_name_kana|string|null: false|
|name_first|string|null: false|
|name_first_kana|string|null: false|
|postal_code|integer|null: false|
|prefecture|string|null: false|
|city_name|string|null: false|
|bilding|string|null: true|
|tel_phone|integer|null: false|
|tel_home|integer|null: ture|
|user_id|refernces|null: false, foreign_key: true|

### Association
- belongs_to user

## productsテーブル
|Column|Type|Options|
|------|----|-------|
|name|string|null: false|
|description|string|null: false|
|category|string|null: false|
|product_status|string|null: false|
|price|integer|null: false|
|delivery_fee|string||null: false|
|delivery_from|string||null: false|
|delivery_day|string||null: false|
|comment|text|
|status|value|enum|
|like_count|integer|defult:0|
|user_id|refernces|null: false, foreign_key: true|
|review_id|refernces|null: , foreign_key: true|

### Association
- belongs_to :user
- belongs_to :review
- has_many :images
- has_many :likes

## paiesテーブル
|Column|Type|Options|
|------|----|-------|
|cardnumber|integer|null: false|
|expiration_date|date|null: false|
|code|integer|null: false|
|user_id|refernces|null: false, foreign_key: true|

### Association
- belongs_to :user

## imagesテーブル
|Column|Type|Options|
|------|----|-------|
|image_name|string|null: false|
|product_id|refernces|null: false, foreign_key: true|


### Association
- belongs_to :product

## likesテーブル
|Column|Type|Options|
|------|----|-------|
|user_id|refernces|null: false, foreign_key: true|
|product_id|refernces|null: false, foreign_key: true|


### Association
- belongs_to :product

## reviewテーブル
|Column|Type|Options|
|------|----|-------|
|review|string|null: false|
|comment|text|
|customer_id|references|null: false, foreign_key: true|
|product_id|references|null: false, foreign_key: true|


### Association
- belongs_to :user
- belongs_to :product

