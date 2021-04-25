---
layout: post
title:      "How to Have Multiple Users in a Rails App"
date:       2021-04-18 21:21:21 -0500
permalink:  multiple_users_in_a_rails_app
---

Sometimes in an application, you will have multiple users, if not most times. What do I mean? For example, your application may consist of a User, Courses, and Assignments. Your users may be teachers, students, and admin. So, how do you set up multiple users under your User model?


# The Enum Role Method

One way to achieve this is by assigning a role to your users and using Ruby's enum class. Enum is a Ruby class that allow us to use integers to represent our various users (user roles). 
In my project, I have users with three different roles: student, teacher, and administrator. These users have different restrictions as far as what they can and can't access within the app.

# The Process

We can begin by setting up the role attribute for the User model by setting up the migration.
```rails g migration AddRoleToUsers role:integer```

By default, the database will store these integers beginning with the digit 0. Normally, when counting, we begin with the number 1. So, before you run ```rails db:migrate```, add this small change to the column within the table's migration file.

```
class AddRoleToUsers < ActiveRecord::Migration[6.1]
  def change
    add_column :users, :role, :integer, default: 1
  end
end
```
This will assign the first user within the role array with the integer of one instead of zero. 

# Setting up Roles in the User Model

In your User model, place the following code within the class, above any methods.
```
enum role: {student: 1, teacher: 2, admin: 3}
```
You can rename these roles to fit the titles of your application's users.
[:student, :teacher, :admin] are the names we’re using to reference the user role. Since this is an array, and the index starts at 0, standard role would have been stored as 0 in the database. However, because we added the small change to our role column in the database, we can refer to our roles starting with the number 1. 