---
layout: post
title:      "Building a Sinatra Web App (Getting Started)"
date:       2020-07-13 14:57:37 +0000
permalink:  building_a_sinatra_web_app_getting_started
---


To begin, let's understand what Sinatra is exactly. Sinatra is a Ruby framework that provides a simpler experience (IMO) to building web applications. Some people say Sinatra/ActiveRecord is magic. It certainly can feel that way. 

# File Structure
Let's begin building our application by setting up the structure for your models, controllers, and views. *Big Help* Install the [Corneal gem](https://github.com/thebrianemory/corneal) (amazing gem built by former Flatiron student, Brian Emory) to help get you started on the structure of your files. Once, you've installed corneal, take a look through the file structure to refamiliarize yourself. You will notice your app folder that will be home to your MVC - Model, View, Controller. Inside of your app folder, you will have subfolders to correspond with your MVC. The subfolders will contain a model file to hold your object models, controller files to build your routes, and a views folder which holds your html files. You will also see or should create a 'db' folder with a 'migrate' subfolder to create and store your database migrations.
![](https://screencast-o-matic.com/watch/cYiI2F58Qh)
# M-V-C (Models)
My Sinatra web app model consists of two folders - users.rb and meals.rb. The relationship between these models is a user ``has_many`` meals and a meal ``belongs_to`` a user. Make certain your classes inherit ActiveRecord macros by placing the inheritence code beside your class title.
Example: ``class Meal < ActiveRecord::Base`` . ActiveRecord consists of macros that allow our objects to be created with minimal effort. By doing this, I didn't need to create my own setter/getter methods, etc like we normally do in Ruby. 
Once you have your object relationships built, make your way over to the db/migrate folder to create your migrations table. Here, you will want your user to have a username, email, and password for signing up and login functionality. These will become your params used in your controller and views. 

![](https://screencast-o-matic.com/watch/cYiI2Z586D)
![](https://screencast-o-matic.com/watch/cYiI2O586w)

In these two files you'll notice two things: the use of ``password_digest`` and ``user_id``. 
Encryption of a password will be important here, as your user's password should be protected. By installing using the bcrypt gem and ActiveRecord's ``has_secure_password`` macro, you will allow your user's information to be protected.
Next, by placing user_id into our meals table, this enures that each is linked to the correct user. Eventually, you'll have many users and the database will need to know which meal goes to its corresponding user. Run rake db:migrate to create your migrations.

# M-V-C (Controller)
If you have already installed and are using the corneal gem file structure, you will see your applicaton controller. In that controller is your starter get route (/). You'll want to run that to test and see if your application is running correctly before adding any new code. Your get route should be responsible for showing the user the index page of your app/site. Once you've confirmed that your get route and app is running correctly, you can continue building your controller routes. For this project, it's best to have different controllers for different functionality. Any user functionality should be placed inside of a User controller -- that is your signup, login, and logout routes. For Dine Well, I also created a Meals controller, responsible for holding the routes that allows a user to create a meal, show all meals, edit, and delete a meal. We do this by using CRUD- create, read, update, delete  and RESTful routes.

![](https://screencast-o-matic.com/watch/cYiI2H582c)
![](https://screencast-o-matic.com/watch/cYiI2O586w)
![](https://screencast-o-matic.com/watch/cYiI2J582X)

# M-V-C(Views)
Although this is the second word in the acronym, I decided to hit on this last. The views are responsible for holding all of your HTML, the actual pages that the user sees.Some of your routes will be redirected to these html or .erb files when a user logs in or clicks a submit button in your forms. 


