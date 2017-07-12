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

# Movie Recommender
## App Objective
We want to build a recommendation back-end that takes your taste profile and generates movies you might like, based on some measure of similarity to the ones in your taste profile.

We'll then run an experiment where we surface the "recommended" movies for a random subset of the users (Experimental Group) and for the users we would show the most popular movies, regardless of taste profile - this will be the Control Group.

## Third-Party API Integration (35)

### Questions (10)
0. What is [TheMovieDB API](https://www.themoviedb.org/documentation/api)?
1. What are the different endpoints?
2. Find examples of how to query the API
3. How can we use this API in our application?

### Live Code Together (5)
Let's fetch a list of the most popular movies overall.

**Note**: Here is my API key: `34a332fb7669cdf88e89f1fefdbb2c3e`

### Exercise Set 1 (10)
0. What are the genres available for Movies? What is the id of Horror?
1. What are the most popular sci-fi movies?

### Exercise Set 2 (10)
2. What are the most popular sci-fi movies released in 2011?
3. What are the movies that match the search term "Lord"?

## Prediction, Clustering & Recommendation
### Questions (15)
1. What is a prediction?
2. What do you base it on?
3. How do you know it's good?
4. What are some examples of predictions you make or technology that you use makes?

### Supervised Learning
#### Definitions (10)
- target
- feature
- training set
- validation set
- model

#### Questions (10)
Suppose we only have the following data set.

release_year | genre | imdb_score | fb_fan_count | watched
--- | --- | --- | --- | ---
2011 | Sci-Fi | 6.5 | 750000 | 1
1977 | Romance | 8.8 | 1500 | 0
1977 | Sci-Fi  | 7.5 | 8688 | 1
... | ... | ... | ... |...

0. What should be the target?
1. What are the features?
2. What data should we train it on?
3. What data should we test it against?

### A Simple Model (10, Optional)
We'll explore k Nearest Neighbors to illustrate how a machine learning model works.

### Neural Networks & Feedback (Optional, 25)
#### Questions (15)
0. What is feedback?
1. How do you think it relates to recommendations?
2. What types of feedback could you collect from the user that should factor into future recommendations?

#### Perceptron Neural Network (10)
Let's walk through how a perceptron works, at a high-level.

### Unsupervised Learning - Clustering (2)
#### Questions (15)
1. Suppose you have 100 users and you know for each user what their age, location, favorite genres, and other useful intelligence. How would you organize them into 10 subgroups? Why would you even do this?
2. Suppose you have a lot of historical data on John, who belongs to Subgroup 1, in terms of what movies he's watched. How could this be useful?
3. Could this process of grouping apply to movies as well? If so, how and why?

#### Definitions (5)
- clustering
- collaborative filtering

## Let's Live-Code an Example (30)
### The Data
https://s3.amazonaws.com/simple-fractal-workshops/movie_history_for_user.csv

### Together (10)
0. What is [`pandas`](http://pandas.pydata.org/pandas-docs/stable/)?
1. Let's read in the data.

### Questions (5)
0. What is the data? What are the fields?
1. What should we consider the target? How about the features?
2. Any questions about this data?

### Logistic Regression (10)
A brief walk-through of logistic regression and how it works.

### Together (20)
0. What is [`scikit-learn`](http://scikit-learn.org/stable/)?
1. Let's separate into feature and target.
2. Let's split into training and validation set.
3. Let's train the model, using logistic regression.
4. Let's predict a few entries from the validation set and check.
5. Let's check the overall accuracy.
