## MVP

<ul>
<li>Login Functionality</li>
<li>Post Comment</li>
<li>Delete/ Edit Posts</li>
<li>Control View based on authorization</li>
</ul>

### icebox

    - delete account
    - play music
    - customize background
    - datamine customers
    - fave five list

### Database

    User
    ```SQL
    create table users (
        user_id serial primary key,
        email varchar(100),
        password text
    );
    ```

    Post
    ```SQL
    create table posts (
        post_id serial primary key,
        user_id int references users(user_id),
        content varchar(250),
        created_at date
    );
    ```

### Server

#### Dependencies

    - axios, massive, express, express-session, dotenv, bcrypt

#### Endpoints

    - auth:
        + app.post('/auth/login')
        + app.post('/auth/register')
        + app.delete('/auth/logout')
        + app.get('/auth/user')


    - post:
        + app.get('/api/posts')
        + app.post('/api/post')
        + app.put('/api/posts/:post_id')
        + app.delete('/api/posts/:post_id')

### Client

#### Dependencies

    - axios, redux, react-router-dom, react-redux, redux-promise-middleware

### Routes

    - landing (/)
    - register (/register)
    - dashboard (/dashboard)
    - profile (/profile)

### File Structure

    - src/
        + App.js
        + App.css
        + index.js
        + redux/
            - store
            - reducer
        + components/
            - Landing.js
            - Register.js / .css
            - Dashboard.js / .css
            - Profile.js / .css
            - PostContainer.js / .css
            - Post.js / .css
            - Edit.js / .css
            - Header.js / .css
            - AuthHead.js / .css
