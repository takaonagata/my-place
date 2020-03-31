# README
![image](https://user-images.githubusercontent.com/60649410/77246829-4e0e8c00-6c6e-11ea-9071-6251e6ebf152.png)
# MY-PLACE

ユーザー同士での投稿アプリ

## 概要

- 登録されたユーザーにしか投稿を見られず、不特定多数の人に投稿を見られたく無い人向けのアプリです</br>
- 登録を行えば、投稿する事ができユーザーの一覧も見る事ができます</br>
- 初めて利用される方に向け、トップページには概要を見るためのリンクをつけています  
https://i.gyazo.com/178eeb18c0a5a131ca83acf91cd30ee5.mp4</br>
- 他のユーザーが誰の投稿をお気に入りしているのかを見ることも可能です</br>


***デモ***
- 新規投稿</br>
https://i.gyazo.com/a3be3ba891dd23f9a0709e5b29f50f5e.mp4

- お気に入り機能</br>
https://i.gyazo.com/8f7e44879ee2f24bae6c91f25573eb11.mp4

## 機能

- ログイン/ログアウト機能</br>
- 投稿機能（投稿の編集、削除）</br>
- お気に入り機能</br>
- 登録しているユーザーの一覧表示</br>
- 投稿一覧表示</br>

## 製作意図
投稿アプリがたくさんある中で私は不特定多数の人に投稿をみられるのではなく、登録を行なった物にしか投稿を閲覧できないようなアプリを作ってみたいと考え製作しました。</br>
投稿を行なって行くうちに他のユーザの投稿が良いな、と思った時のためにもお気に入り機能をつけています。</br>
投稿と、ユーザーは一覧として見ることができ、お気に入りした投稿についてはマイページより見ることができます。

## 使用言語
- フロント</br>
HTML</br>
CSS
  
- バックエンド</br>
Ruby（ver 2.5.1）</br>
Ruby on Rails(ver 5.0.7.2)</br>

## DB
- My SQL(Ver 14.14)</br>



## 使い方
- テスト用アカウント
ユーザー名：test</br>
メールアドレス：a</br>
パスワード：a

- 投稿機能は以下の手順で確認できます
1. トップページからテスト用アカウントでログインを行なってください
2. 新規投稿の画面より投稿を行うことができます
3. 投稿一覧、ユーザー一覧の画面でそれぞれ一覧を見ることが可能です

- 確認後、ログアウト処理をお願いします




## インストール

```
$ git clone https://github.com/takaonagata/my-place.git
$ cd my-place
$ bundle install
$ rails db:create
$ rails db:migrate
```


## デプロイ

URL http://18.180.177.238/

## その他



## 作者

[@cJvgXe2xaz7jJAd](https://twitter.com/cJvgXe2xaz7jJAd)
<br>
<br>
<br>
# MY-PLACE DB設計
## usersテーブル
|Column|Type|Options|
|------|----|-------|
|name|string|null: false|
|email|string|null: false|
|image_name|string||
|password|string|null: false|
### Association
- has_many :posts
- has_many :likes

## postsテーブル
|Column|Type|Options|
|------|----|-------|
|content|text|null: false|
|user_id|integer|null: false, foreign_key: true|
### Association
- belongs_to :user
- has_many :likes

## likesテーブル
|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|post_id|integer|null: false, foreign_key: true|
### Association
- belongs_to :post
- belongs_to :user
