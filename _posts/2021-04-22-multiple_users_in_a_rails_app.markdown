---
layout: post
title:      "How to Have Multiple Users in a Rails App"
date:       2021-04-22 21:21:21 -0500
permalink:  multiple_users_in_a_rails_app
---

Sometimes in an application, you will have multiple users, if not most times. What do I mean? For example, your application may consist of a User, Courses, and Assignments. Your users may be teachers, students, and admin. So, how do you set up multiple users under your User model?


# The Enum Role Method

Enum is a Ruby class that allow us to use integers to represent our various users (user roles). 

