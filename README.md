# Overview of Tools and Technologies
## The Stack
What is a "stack"?

1. UI
2. Server
3. Database

## UI
### HTML
```html
<html>
    <body>
        <h1>This is an example header!</h1>
        <p class="tagline">The Verizon workshop is the place to be. We're going to learn so much.</p>
        <img class="big-logo" src="https://verizon.com/logo.png"/>
    </body>
</html>
```

#### Questions
1. What does the HTML do?
2. What is it responsible for?

### CSS
```css
.tagline {
    font-size: 24px;
    color: red;
}

.big-logo {
    height: 190px;
    width: 250px;
    margin-top: 30px;
}
```

#### Questions
1. What does the CSS do?
2. What is it responsible for?


### Javascript
```javascript
$(".big-logo").on("click", function() { alert("Thanks for clicking!")});
```

#### Questions
0. What does Javascript do?
1. What is it responsible for?

### Javascript Frameworks
What is the point of Javascript frameworks?

- [ReactJS](https://facebook.github.io/react/)
- [AngularJS](https://angularjs.org/)
- [EmberJS](https://www.emberjs.com/)

### Summary
HTML, CSS and JS are the main technologies used in web UIs.

#### Questions
1. What is the job of the UI?

## Server
```python

@app.route('/recommendations')
def get_recommendations():
    recommendations = fetch_recommendations_from_db()
    template = 'recommendation-feed.html'
    return render_template(template, recommendations=recommendations)

```

### Questions
1. What is happening in the code snippet above?
2. What's the job of the server?
3. What is a server?

### Languages & Frameworks
What is a back-end framework?

- Python (Flask, Django)
- Ruby (Sinatra, Ruby on Rails)
- Java

## (SQL) Databases
### Questions
1. What is data?
2. What is a database?
3. What gets stored in a database?
4. Is a spreadsheet a database?

## SQL
### Users
id | username | email               | date_signed_up
--- | --- | --- | ---
1  | james.c  | james.c@verizon.com | 2017-07-11 11:01:25
2  | stacy    | stacy@verizon.com   | 2017-07-11 13:01:25
3  | raul.r   | raul.r@verizon.com  | 2017-07-12 15:35:44
```

### Events
id | user_id | action    | date_logged
--- | --- | --- | ---
...| ... |... |...
7  | 3       | login         | 2017-07-12 08:08:08
8  | 3       | add_to_cart   | 2017-07-12 08:28:11
9  | 3       | clear_cart    | 2017-07-12 08:29:35
10 | 1       | reset_password| 2017-07-13 14:12:12
11 | 2       | login         | 2017-07-14 11:12:12

### Questions
0. What do the above tables correspond to?
1. What are the fields and what is the data type of each field?
2. How are these tables related?
3. What types of questions would you ask this database?

### Discuss Together
0. What is SQL?
1. Why SQL?
2. Are there alternatives to SQL?

## Hosting
- [Heroku](https://heroku.com)
- [Amazon Web Services](https://aws.amazon.com)

What are the pros & cons of each?

## Analytics
- [Google Analytics](https://analytics.google.com)
- [Mixpanel](https://mixpanel.com/)
- [Segment](https://segment.com)
- [Fullstory](https://fullstory.com)

## Development & Workflow Tools
- [GitHub](https://github.com)
- [Asana](https//asana.com)
- [Slack](https://slack.com)
- [Codeship](https://codeship.com/)
- [Sublime](https://www.sublimetext.com/)
- [Postico](https://eggerapps.at/postico/)

## Testing
### Questions
0. How do you know your app works the way you want it to?
1. How do you know your new feature doesn't break old functionality?

### Automation
- Unit
- Functional
- Integration
- End-to-End (E2E)

### Examples
#### End-to-End Test
[Here](https://drive.google.com/file/d/0Byveb6yWfKu2MDAzM0RaQ2hyY0U/view) is an example of an E2E test

### Unit Test
```python
def cool_add(a, b, c):
    return a + b + c

def test_cool_add():
    assert cool_add(1, 2, 3) == 6
    assert cool_add(-5, -10, 88) = 73
```

### Functional Test
```python
def test_sign_up():
    # 1. Create test data
    create_user(email='tester@verizon.com', password='oldpass')

    # 2. Make the request to the server
    make_request(
        '/change-password',
        email='tester@verizon.com',
        new_password='newpass'
    )
    # 3. Fetch the user from the database
    user = get_user_from_database(email='tester@verizon.com')

    # 4. Check that the password got updated correctly
    assert user.password_matches("newpass")
```