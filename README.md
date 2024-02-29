# SQL CRUD
## Part 1: Restaurant finder
### Create the database table 
- Design a database table named `restaurants`
```sql
CREATE TABLE restaurants (
    id INTEGER PRIMARY KEY,
    name TEXT,
    category TEXT,
    pricetier TEXT,
    neighborhood TEXT,
    openinghour TEXT,
    closinghour TEXT,
    averagerating REAL,
    goodforkids TEXT
    );
```
- Import the data into `restaurants`
```sql
.mode csv
.import data/restaurant.csv restaurants --skip 1
```
- Design a database table named `reviews`
```sql
CREATE TABLE reviews (
    reviewid INTEGER PRIMARY KEY,
    restid TEXT,
    user TEXT,
    rating REAL,
    comment TEXT,
    created DATETIME DEFAULT CURRENT_TIMESTAMP,
    FOREIGN KEY (restid) REFERENCES restaurants(id)
    );
```

### Queries
1. Find all cheap restaurants in a particular neighborhood (using `Tudor City` as an example).
```sql
select * from restaurants where pricetier="cheap" and neighborhood="Tudor City";
```
2. Find all restaurants in a particular genre (using `Indian` as an example) with 3 stars or more, ordered by the number of stars in descending order.
```sql
select * from restaurants where category="Indian" and averagerating>=3 order by averagerating DESC;
```
3. Find all restaurants that are open now.
```sql
select * from restaurants where strftime('%H:%M', 'now', 'localtime')>=openinghour and strftime('%H:%M', 'now', 'localtime')<=closinghour;
```
4. Leave a review for a restaurant.
```sql
insert into reviews (restid,user,rating,comment) values (448,"randompeople",3,"Mediocre");
```
5. Delete all restaurants that are not good for kids.
```sql
delete from restaurants where goodforkids="false";
```
6. Find the number of restaurants in each NYC neighborhood.
```sql
select count(id), neighborhood from restaurants group by neighborhood;
```

## Part 2: Social media app
### Create the database table
- Design a database table named `users`
```sql
CREATE TABLE users (
    id INTEGER PRIMARY KEY,
    email TEXT,
    password TEXT,
    handle TEXT
    );
```
- Import the data into `users`
```sql
.mode csv
.import data/users.csv users --skip 1
```
- Design a database table named `posts`
```sql
CREATE TABLE posts (
    id INTEGER PRIMARY KEY,
    user INTEGER,
    type TEXT,
    content TEXT,
    recipient INTEGER,
    visibility TEXT,
    created DATETIME,
    FOREIGN KEY (user) REFERENCES users(id),
    FOREIGN KEY (recipient) REFERENCES users(id)
    );
```
- Import the data into `posts`
```sql
.mode csv
.import data/posts.csv posts --skip 1
```

### Queries
1. Register a new User.
```sql
insert into users (email,password,handle) values ("random@gmail.com","pw123456","randompeople");
```
2. Create a new Message sent by a particular User to a particular User (using  `user 177` as the sender and `user 897` as the recipient).
```sql
insert into posts (user,type,content,recipient,visibility, created) values (177,"message","hello friend",897,"true",datetime('now'));
```
3. Create a new Story by a particular User (using  `user 64` as the sender).
```sql
insert into posts (user,type,content,recipient,visibility, created) values (64,"story","today i had a croissant",390,"true",datetime('now'));
```
4. Show the 10 most recent visible Messages and Stories, in order of recency.
```sql
select * from posts where visibility="true" order by created desc limit 10;
```
5. Show the 10 most recent visible Messages sent by a particular User to a particular User (using  `user 77` as the sender and `user 577` as the recipient), in order of recency.
```sql
select * from posts where visibility="true" and type="message" and user=77 and recipient=577 order by created desc limit 10;
```
6. Make all Stories that are more than 24 hours old invisible.
```sql
update posts set visibility="false" where type="story" and (julianday('now')-julianday(created))*24>24;
```
7. Show all invisible Messages and Stories, in order of recency.
```sql
select * from posts where visibility="false" order by created desc;
```
8. Show the number of posts by each User.
```sql
select user,count(id) from posts group by user;
```
9. Show the post text and email address of all posts and the User who made them within the last 24 hours.
```sql
select posts.content,users.email from posts inner join users on posts.user=users.id where (julianday('now')-julianday(created))*24<24;
```
10. Show the email addresses of all Users who have not posted anything yet.
```sql
select email from users where id not in (select user from posts);
```

## Links to each of the practice CSV data files
- [Practice data for one thousand restaurants](https://github.com/dbdesign-students-spring2024/4-sql-crud-shaw2065/blob/main/data/restaurant.csv)
- [Practice data for one thousand Users](https://github.com/dbdesign-students-spring2024/4-sql-crud-shaw2065/blob/main/data/users.csv)
- [Practice data for one thousand Messages, and one thousand Stories](https://github.com/dbdesign-students-spring2024/4-sql-crud-shaw2065/blob/main/data/posts.csv)