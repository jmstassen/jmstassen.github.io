---
layout: post
title:      "Forward Position task manager (Sinatra project)"
date:       2021-01-31 21:22:08 +0000
permalink:  forward_position_task_manager_sinatra_project
---


Learning Sinatra is when things really start to come together - being able to see what you're making in a browser makes all the difference. I can't count the number of times I've typed "shotgun" - or "tux", or "binding.pry". Learning to get what you want out of params, learning to keep what you want using sessions, thinking through database tables and model relationships, migrating and rolling back (and rolling back and rolling back) the database - it really makes clear how messages are sent between objects, and how the real world and anything you can think of is a collection of objects that sometimes have associations or interact with each other.

Our assignment was to create a content management system, basically having at least one one-to-many relationship, and with controls over viewing the resources of other people. For my project, I wanted to take it a step further for a very specific use case: I decided to create a task management app that would be suitable for keeping track of your own tasks (and preventing others from seeing, editing, or deleting them) but I also wanted to give the ability for someone to assign access to an assistant, who them *would* be able to view your tasks.

What I ended up with was built on these models:
1. Users - a user has the typical email, name, and password attributes, but also has an assistant_email attribute. I used Bcrypt for password authentication and handling and built out a simple process to change your password if needed.
2. Tasks - this is the most complicated model and really is the star of the show. There is a task name, a description, options for due date or do date (the date you plan to do the task), as well as category (the type of task) and size (which could also be seen as complexity). As a business analyst in an agile scrum framework I got used to using the fibonacci sequence to refer to size/complexity - in that case it was for software development user stories, but the values of 1, 2, 3, 5, 8, and 13 work just as well for your own task management and they really help to identify the tasks that will take time to either complete, develop more, or break down in smaller tasks (the 8's and 13's) and those that can quickly be accomplished, even if there is only a little bit of time.
3. Notes - Every task can have multiple notes (a one to many relationship). This called for some complex forms when editing a task that would allow existing notes to be edited or deleted and new notes to be created all with one submission. The most useful view, technically an index of your tasks, is the Task List view, which shows the details of active tasks and allows marking a task done, updating the do date, or adding a note.
4. References - References belong to a user and are displayed separately from tasks. I imagined these would be useful for information that a user wants to keep at their fingertips - lists of commonly used data or things that are often looked up.

With all of these basics in place, I also created Assistant Mode for users whose email addresses are listed as assistant_email for another user. The assistants can edit tasks, notes, and references (or delete them) and can exit assistant mode to go back to their own resources. The way I see this working is that an assistant prepares the task list for the person they support, and then using the task list as a guide, both of them can talk about the tasks and fill out the update forms (new note, mark done, or change do date) and then submit the changes for all the tasks using the Update All button. I also thought it would be helpful to have a list of completed tasks - so instead of being deleted, a task that is completed is shown in a separate list, and could, if warranted, be changed back to active status and show up in the Task List again.

One of the challenges of the project was making sure to commit changes often enough. Many times when developing a solution, one solution would lead directly to another issue or error, and it's easy to just keep playing whack-a-mole until you realize you don't know what you've done since your last commit.

Here's a super quick demo of the app: [coming soon]
