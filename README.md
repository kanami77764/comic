<p align="center"><img src="https://res.cloudinary.com/dtfbvvkyp/image/upload/v1566331377/laravel-logolockup-cmyk-red.svg" width="400"></p>

<p align="center">
<a href="https://travis-ci.org/laravel/framework"><img src="https://travis-ci.org/laravel/framework.svg" alt="Build Status"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://poser.pugx.org/laravel/framework/d/total.svg" alt="Total Downloads"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://poser.pugx.org/laravel/framework/v/stable.svg" alt="Latest Stable Version"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://poser.pugx.org/laravel/framework/license.svg" alt="License"></a>
</p>
![管理アプリ](https://user-images.githubusercontent.com/64050565/83852558-f18c1a80-a74e-11ea-9235-3bd3e745f74b.png)

![ruby](https://img.shields.io/badge/-ruby-red)
![ruby on rails](https://img.shields.io/badge/-ruby%20on%20rails-orange)
![jQuery](https://img.shields.io/badge/-jquery-green)
![heroku](https://img.shields.io/badge/-heroku-blueviolet)
![MySQL](https://img.shields.io/badge/-MySQL-ff69b4)


# README

## コミック管理アプリ
自身の大好きなコミックを管理できるアプリです。
<br>購入前の新刊コミック管理に！
<br>読みたいコミックのメモ欄に！
<br>使い方は、人によって多種多様です。

## 💬 アプリ説明
コミック大好き！にお届けするアプリです。
使い方
<br>もちろん、気になるコミックの名前をストックするメモに使う

## 🎨 DEMO
![memoapp説明用１](https://user-images.githubusercontent.com/64050565/83348378-ee67e780-a366-11ea-8933-6b60b35f84cc.png)

## 💬 開発意図
【対象者】
<br>読んでいるコミックの種類が多すぎて、新刊発売を忘れる時がしばしば。
<br>そんな時は、こちらのアプリをコミックメモとして活用しましょう。
<br>【使用例】
<br>①新刊発売の日にちを忘れてしまう
<br>（書店に寄っても、マイナーなタイトルは店先に置かれていないこともある）
<br>②友達におすすめされたコミック名のメモに使える（最近は長いタイトルが多い）
<br>③コミック→アニメ化情報もメモできる
<br>
<br>このメモを見るだけで、少しでもワクワクできれば幸いです！


## 📦 実装機能
### "コミック管理アプリ"の機能
<br>＊メモ投稿機能
<br>＊メモを削除できる機能
<br>＊メモはデータベースに管理、閲覧できる機能
<br>＊ログイン機能実装
<br>
<br>
## 📦 工夫した点
<br>＊メモ一覧の見た目
<br>　⇨bootstrapを使用し、一目でわかるようなシンプルな実装を心がけました。
<br>＊メモ削除の機能
<br>　⇨ユーザーとして、購入、またはメモの役割を完了したコミックは削除できる方が使いやすいと考えました。
<br>＊ログイン機能実装
<br>　⇨Laravelを初めて使用するため、他の言語との違いを学習するために、実装しました。
<br>

## 📦 今後の実装したい機能
<br>＊発売日など、日付を追加できる機能
<br>＊メモの編集機能
<br>＊コミックと連動して、アニメ化の期限も管理できる機能
<br>

## 💬 使っている言語、フレームワーク
＊PHP 7.3.19
<br>＊Laravel Installer 3.1.0


## 💬 インストール方法
```
$ git clone https://github.com/kanami77764/memos_app.git
$ cd bookapp2
$ brew install composer
$ composer insall
$ cp .env.example .env
$ cd php artisan key:generate
$ touch database/database.sqlite

 .envファイル設定
~略~
DB_CONNECTION=sqlite
# DB_HOST=127.0.0.1
# DB_PORT=3306
# DB_DATABASE=laravel
# DB_USERNAME=root
# DB_PASSWORD=
~略~

$ php artisan migrate
$ php artisan serve
```

## 👀 作成者
kanami66674

## 💬 データベース
### book table
| Columm | Type | Option |
|:------:|:----:|:------:|
|book|string|null: false|
|user_id|integer|null: false, foreign_key: true|

#### Association
- belongs_to :user


### User table
| Column | Type | Option |
|:------:|:----:|:------:|
|name|string|null:false|
|email|string|null: false ,add_index  unique: ture|
|password|string|null: false|

#### Association
- has_many :books
