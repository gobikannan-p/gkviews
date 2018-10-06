Title: How to change username in WordPress
Published: 05/23/2017
Category: General
Tags: Wordpress
---

There are three ways to change username in WordPress.

First one is using Add New User in WordPress:-


* Login to your WordPress dashboard.
* Click on Add New User in User section and provide user details. Maksure that the role should be Administrator then click on Add User.
* Log out current user session and Login again using new user credentialOnce you logged in successfully, Go to User section.
* Select the admin user and then click delete button.
* It asks about existing posts. Select Attribute all posts and links toption and select your current username in the drop down and then clicConfirm delete.   

Now the admin user is deleted from your user section and the existing posts are changed to your current user detail.

Second way is using phpMyAdmin:-

You need credential for your database to do these steps.

Backup your database before doing the following steps for safe.


* Login in to phpMyAdmin to access your database.
* Under the Structure section you will find out WP_users table. (theprefix of the table WP_ may vary in your table structure, based on yourtable prefix configuration )
* Click the Browse icon next to that table it will list out the recordsin the table(the users for your site). Here you can find the user name.
* Click on Edit icon (Like pencil icon) in the corresponding row.
* Change the value of user_login field to your new login username andclick Go button to save the current changes.
    
Now you can login using the new username which you updated in the user table

The third way is using WordPress plugin:-

The following plugin will help you to change user’s login username.

[Username Changer](https://wordpress.org/plugins/username-changer/){target="_blank"}

[User ID Changer](https://wordpress.org/plugins/user-id-changer/){target="_blank"}

You need to follow the instructions with in the plugin to change user name.

You may use any one the way to change the default username. But my preference goes to the first way. Because it is secured one and it is provided by WordPress itself.

