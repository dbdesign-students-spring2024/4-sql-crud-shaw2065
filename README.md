# SQL CRUD
## Part 1: Restaurant finder
### Create the database table 
- Design a database table named `restaurants`
```sql
SELECT * FROM restaurants
WHERE strftime('%H:%M', 'now', 'localtime') >= open_hour
AND strftime('%H:%M', 'now', 'localtime') <= close_hour;
```
- Import the data into `restaurants`
```sql
SELECT * FROM restaurants
WHERE strftime('%H:%M', 'now', 'localtime') >= open_hour
AND strftime('%H:%M', 'now', 'localtime') <= close_hour;
```
- Design a database table named `reviews`
```sql
SELECT * FROM restaurants
WHERE strftime('%H:%M', 'now', 'localtime') >= open_hour
AND strftime('%H:%M', 'now', 'localtime') <= close_hour;
```
- Import the data into `reviews`
```sql
SELECT * FROM restaurants
WHERE strftime('%H:%M', 'now', 'localtime') >= open_hour
AND strftime('%H:%M', 'now', 'localtime') <= close_hour;
```

### Queries
1. Find all cheap restaurants in a particular neighborhood (using Koreatown as an example).
```sql
SELECT * FROM restaurants
WHERE strftime('%H:%M', 'now', 'localtime') >= open_hour
AND strftime('%H:%M', 'now', 'localtime') <= close_hour;
```
2. Find all restaurants in a particular genre (using Indian as an example) with 3 stars or more, ordered by the number of stars in descending order.
```sql
SELECT * FROM restaurants
WHERE strftime('%H:%M', 'now', 'localtime') >= open_hour
AND strftime('%H:%M', 'now', 'localtime') <= close_hour;
```
3. Find all restaurants that are open now.
```sql
SELECT * FROM restaurants
WHERE strftime('%H:%M', 'now', 'localtime') >= open_hour
AND strftime('%H:%M', 'now', 'localtime') <= close_hour;
```
4. Leave a review for a restaurant.
```sql
SELECT * FROM restaurants
WHERE strftime('%H:%M', 'now', 'localtime') >= open_hour
AND strftime('%H:%M', 'now', 'localtime') <= close_hour;
```
5. Delete all restaurants that are not good for kids.
```sql
SELECT * FROM restaurants
WHERE strftime('%H:%M', 'now', 'localtime') >= open_hour
AND strftime('%H:%M', 'now', 'localtime') <= close_hour;
```
6. Find the number of restaurants in each NYC neighborhood.
```sql
SELECT * FROM restaurants
WHERE strftime('%H:%M', 'now', 'localtime') >= open_hour
AND strftime('%H:%M', 'now', 'localtime') <= close_hour;
```

## Part 2: Social media app
### Create the database table
- Design a database table named `users`
```sql
SELECT * FROM restaurants
WHERE strftime('%H:%M', 'now', 'localtime') >= open_hour
AND strftime('%H:%M', 'now', 'localtime') <= close_hour;
```
- Import the data into `users`
```sql
SELECT * FROM restaurants
WHERE strftime('%H:%M', 'now', 'localtime') >= open_hour
AND strftime('%H:%M', 'now', 'localtime') <= close_hour;
```
- Design a database table named `posts`
```sql
SELECT * FROM restaurants
WHERE strftime('%H:%M', 'now', 'localtime') >= open_hour
AND strftime('%H:%M', 'now', 'localtime') <= close_hour;
```
- Import the data into `posts`
```sql
SELECT * FROM restaurants
WHERE strftime('%H:%M', 'now', 'localtime') >= open_hour
AND strftime('%H:%M', 'now', 'localtime') <= close_hour;
```

### Queries
1. Register a new User.
```sql
SELECT * FROM restaurants
WHERE strftime('%H:%M', 'now', 'localtime') >= open_hour
AND strftime('%H:%M', 'now', 'localtime') <= close_hour;
```
2. Create a new Message sent by a particular User to a particular User (pick any two Users for example).
```sql
SELECT * FROM restaurants
WHERE strftime('%H:%M', 'now', 'localtime') >= open_hour
AND strftime('%H:%M', 'now', 'localtime') <= close_hour;
```
3. Create a new Story by a particular User (pick any User for example).
```sql
SELECT * FROM restaurants
WHERE strftime('%H:%M', 'now', 'localtime') >= open_hour
AND strftime('%H:%M', 'now', 'localtime') <= close_hour;
```
4. Show the 10 most recent visible Messages and Stories, in order of recency.
```sql
SELECT * FROM restaurants
WHERE strftime('%H:%M', 'now', 'localtime') >= open_hour
AND strftime('%H:%M', 'now', 'localtime') <= close_hour;
```
5. Show the 10 most recent visible Messages sent by a particular User to a particular User (pick any two Users for example), in order of recency.
```sql
SELECT * FROM restaurants
WHERE strftime('%H:%M', 'now', 'localtime') >= open_hour
AND strftime('%H:%M', 'now', 'localtime') <= close_hour;
```
6. Make all Stories that are more than 24 hours old invisible.
```sql
SELECT * FROM restaurants
WHERE strftime('%H:%M', 'now', 'localtime') >= open_hour
AND strftime('%H:%M', 'now', 'localtime') <= close_hour;
```
7. Show all invisible Messages and Stories, in order of recency.
```sql
SELECT * FROM restaurants
WHERE strftime('%H:%M', 'now', 'localtime') >= open_hour
AND strftime('%H:%M', 'now', 'localtime') <= close_hour;
```
8. Show the number of posts by each User.
```sql
SELECT * FROM restaurants
WHERE strftime('%H:%M', 'now', 'localtime') >= open_hour
AND strftime('%H:%M', 'now', 'localtime') <= close_hour;
```
9. Show the post text and email address of all posts and the User who made them within the last 24 hours.
```sql
SELECT * FROM restaurants
WHERE strftime('%H:%M', 'now', 'localtime') >= open_hour
AND strftime('%H:%M', 'now', 'localtime') <= close_hour;
```
10. Show the email addresses of all Users who have not posted anything yet.
```sql
SELECT * FROM restaurants
WHERE strftime('%H:%M', 'now', 'localtime') >= open_hour
AND strftime('%H:%M', 'now', 'localtime') <= close_hour;
```

### Links to each of the practice CSV data files
- test
- test
- test