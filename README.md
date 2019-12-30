# Chatify Laravel Package
It is a Laravel package to add a complete real-time chat system to your application with one command line.

# Requirements
- PHP >=5.3.2.
- Laravel >=5.4
- Pusher Api Account.

# Features
 - Users / groups(soon) chat system.
 - Real-time contacts list updates.
 - Favorites contacts list (Like stories style) and add to favorite button.
 - Saved Messages to save your messages online like Telegram messenger app.
 - Search functionality.
 - Contact item's last message indicator (e.g. You: ....).
 - Real-time user's active status.
 - Real-time typing indicator.
 - Real-time seen messages indicator.
 - Upload attachments (Photo/File).
 - User settings and chat customization : user's profile photo, dark mode and chat color.
   with simple and wonderful UI design.

# Demo
Soon

# Installation
Video Tutorial [SOON]
##### Steps :
#### 1. Install the package in your Laravel app
```sh
$ composer require munafio/chatify
```

#### 2. Pusher Api Settings
This package using Pusher Api, so you need to :
- Create account and modify `.env` file of your Laravel app with your api credentials.
- This package used a Pusher client events, and client events must be enabled for the application. You can do this in the `Settings` tab for your app within the Channels dashboard.
[Read more about Pusher 'Triggering client events'](https://pusher.com/docs/channels/using_channels/events#triggering-client-events)
<img src="https://1.bp.blogspot.com/-1N10R4h8tO0/XgoBH7Xw55I/AAAAAAAAA6Y/KBRG-W-PqSQfhq1rKAsv-B61VfiQvwgTgCLcBGAsYHQ/s1600/Screenshot%2Bfrom%2B2019-12-30%2B16-47-05.png" style="width:100%;"/>

#### 3. Publishing Assets
Packages' assets to be published :<br/>
The Important assets:
- config
- assets
- migrations

 and the optional assets :
- controllers
- views

to pusblish the assets, do the following command line with changing the tag value .. that means after `--tag=` write `chatify-` + asset name as mentioned above.<br/>
Example :
```sh
$ php artisan vendor:publish --tag=chatify-config
```
* NOTE: Publishing assets means (e.g. config) that creating a copy of the package's config file into the `config` folder of your Laravel applications and like so with the other asstes (Package's Views, controllers, migrations ...). 

#### 4. Migrations
Migrate the new `migrations` that added by the previous step 
```sh
$ php artisan migrate
```
#### 5. Storage Symlink
Create a shourtcut or a symlink to the `storage` folder into the `public` folder
```sh
$ php artisan storage:link
```
##### That's it .. Enjoy :)

<br/>

# Configurations
You can find and modify the default configurations of the package at `config/chatify.php` file that you published in the step 2 of the installation steps .. and all configurations is documented well to be understood by other developers.
* All package’s files is documented to understand the whole code.

#### Messenger Name
This value is the name of the app which is used in the views or elsewhere in the app.
```sh
...
'name' => env('CHATIFY_NAME', 'Chatify Messenger'),
...
```

#### Messenger Path in Your App
This value is the path of the package or in other meaning, it is the prefix of all the registered routes in this package.
##### e.g (yourapp.domain/chatify)
```sh
...
'path' => env('CHATIFY_PATH', 'chatify'),
...
```


#### Package's web routes middleware
This value is the middleware of all routes registered in this package which is by default : `auth`.
```sh
...
'middleware' => env('CHATIFY_MIDDLEWARE', 'auth'),
...
```


#### Pusher API credentials
you don't need to modify the credentials of Pusher from here, because you already added your credentials in the `.env` file of your Laravel app.

#### User Avatar
This is the user's avatar setting that includes :
```sh
...
'user_avatar' => [
        'folder' => 'users-avatar',
        ...
    ],
...
```
which is the default folder name to upload and get user's avatar from.

```sh
...
'user_avatar' => [
        ...
        'default' => 'avatar.png',
    ],
...
```
which is the default avatar file name for users stored in database .. and when you publishing `assets`, a copy of the avatar photo will be copied into your storage path.

#### Attachments By Default
This array contains the important default values that used in this package :
```sh
...
'attachments' => [
        'folder' => 'attachments',
        ...
    ],
...
```
This is the default folder name for `attachments` in the storage which is all the attachments will be stored in .. and also going to be used in attachments urls in the views.

```sh
...
'attachments' => [
        ...
        'route' => 'attachments.download',
    ],
...
```
It is the route name of the `download attachments` method.

## Author 
[Munaf A. Mahdi](https://www.munafio.com/p/contact-me.html)

## License
[MIT](https://choosealicense.com/licenses/mit/)

