# Full Stack Review - basic social media site
what does this do? 
who is this for?

## MVP - minimum viable product 
<ul>
    <li> login functionality </li>
    <li> post posts </li>
    <li> delete/edit posts </li>
    <li> control the view based on authorization (protected routes) </li>
</ul>

**icebox**
work on once you complete basic assignmetn
<ul>
    <li> delete account </li>
    <li> play music </li>
    <li> customize background </li>
    <li> datamine customers </li>
    <li> fav five friends </li>
</ul>

### Database
User table schema
```SQL
CREATE TABLE users (
    user_id SERIAL PRIMARY KEY,
    email VARCHAR(100),
    password TEXT
)
```

Post table schema
```SQL
CREATE TABLE posts (
    post_id SERIAL PRIMARY KEY,
    user_id INT REFERENCES users(user_id),
    content VARCHAR(250),
    created_at DATE
)
```

### Server
**dependencies**: 
<ul>
    <li> express </li>
    <li> dotenv </li>
    <li> massive </li>
    <li> express-session </li>
    <li> bcrypt </li>
</ul>

**endpoints**:
auth:
    - app.post('/auth/login') - log a user in
    - app.post('/auth/register') - register a user
    - app.delete('/auth/logout') - log user out
    - app.get('/auth/user') - request user session 
    axios call to our server -> who is in user session? then we send user session back 

post: 
    - app.get('/api/posts')
    - app.post('/api/post')
    - app.put('/api/posts/:post_id)
    - app.delete('/api/posts/:post_id)

### Client
**dependencies**: 
<ul>
    <li> axios </li>
    <li> react-router-dom </li>
    <li> redux </li>
    <li> react-redux </li>
    <li> redux-promise-middleware </li>
</ul>