# Database Drill One To Many Schema 
 
##Learning Competencies 

##Summary 

 A database with a single table is not that useful &mdash; a database of any complexity will have more than one kind of "thing" it wants to keep track of.
A classroom database, for example, could have separate tables for students, teachers, classes, sections, homework assignments, grades, etc.

These tables are all related to each other through one of three types of **relations**.  One-to-many relations are the easiest to understand.

An Amazon user has many orders, but an order belongs to exactly one user.  A movie theater has multiple screens, but each screen belongs to only that movie theater.  A street has many houses on it, but a house belongs to only one street.

We design this by having a **foreign key** on the "many" table which stores the **primary key** of the "one" table.  Remember that a table's primary key uniquely identifies a row.  The <code>users</code> and <code>orders</code> table would be designed this way:

<pre>
+------------+        +-------------+
| users      |        | orders      |
+------------+        +-------------+
| id         |&lt;---\   | id          |
| first_name |     \--| user_id     |
| last_name  |        | total       |
| email      |        | address     |
| created_at |        | created_at  |
| updated_at |        | updated_at  |
+------------+        +-------------+
</pre>

The **convention** is that the **foreign key** (<code>user_id</code>, here) contains the singular version of the foreign table.  Because <tt>user_id</tt> contains an integer that corresponds to a one and only one row in the <code>users</code> table, we see that every order only has one users.  However, there could be two rows in the <code>orders</code> table with the same values in the <code>user_id</code> field.

One user has many orders, but an order has exactly one user.

<!--
**Resource:** Here's a [video](http://shereef.wistia.com/medias/fd684c61cb) of Jesse going over Schema Design on July 3, 2012.  Contact staff if you haven't received the login and password in your email.  **Spoiler Alert:** this will show you the schemas for some of the challenges!
-->

## Objectives

### Design the schema

Link the <code>users</code> and <code>orders</code> tables together by clicking 'connect foreign key', pointing the <code>user_id</code> field in the <code>orders</code> table to the <code>id</code> field in the <code>users</code> table.

Use [SQL Designer](/sql.html) to create your schema.  When you are done, save the XML of your schema and copy it into the gist. Then, take a screenshot of your final schema design, and upload it using a free image-upload service like [Min.us](http://minus.com).  Paste the URL of the screenshot into your gist (before your XML code). 

##Releases
###Release 0 

##Optimize Your Learning 

##Resources