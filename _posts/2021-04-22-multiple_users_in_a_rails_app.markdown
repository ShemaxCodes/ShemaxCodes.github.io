---
layout: post
title:      "How to Have Multiple Users in a Rails App"
date:       2021-04-22 21:21:21 -0500
permalink:  multiple_users_in_a_rails_app
---

Sometimes in an application, you will have multiple users, if not most times. What do I mean? For example, your application may consist of a User, Courses, and Assignments. Your users may be teachers, students, and admin. So, how do you set up multiple users under your User model?


# The Enum Role Method

One way to achieve this is by assigning a role to your users and using Ruby's enum class. Enum is a Ruby class that allow us to use integers to represent our various users (user roles). 
In my project, I have users with three different roles: student, teacher, and administrator. These users have different restrictions as far as what they can and can't access within the app.

# The Process
We can begin by setting up the role attribute for the User model by setting up the migration.
```rails g migration AddRoleToUsers role:integer```

By default, the database will store these integers beginning with the digit 0. Normally, when counting, we begin with the number 1. So, before you run ```rails db:migrate```, add this small change to the column with the table's migration file.

```
class AddRoleToUsers < ActiveRecord::Migration[6.1]
  def change
    add_column :users, :role, :integer, default: 1
  end
end
```

