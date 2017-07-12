# Hypothesis to Prototype 101
- Learn and apply framework for going from hypothesis to prototype
- Get familiar with common tools and technologies for hypothesis-driven product development
- Get introduced to recommender systems
- Walk through a worked example from hypothesis to prototype, analysis, and conclusion


# Agenda
1. [15] Intro to Hypothesis-Driven Product Development
2. [30] Form a Hypothesis
3. [30] Determine What Data to Collect
4. [60] Construct the Experiment
5. [45] Lunch
6. [45] Overview of Tools and Technologies
7. [120] Complete the scaffolded movie recommender app
8. [10] Break
9. [60] Analyze Results with Pandas
10. [30] Discuss, Conclude, and Decide
11. [15] Q & A


# Ideation Process
1. How do you come up with an idea?
2. How do you go past the idea stage?
3. How are things different now compared to a decado ago and why?


# Hypotheses
1. What is a hypothesis?
2. How do you distinguish a good hypothesis from a bad one?
3. Exercise: Formulate your project hypothesis
4. Critique each other's hypotheses and see if you can improve them
5. How do we accept/reject a hypothesis?


# Data Collection
1. Why is it important to determine what data to collect?
2. What are some general metrics we could collect to accept/reject a hypothesis?
3. What are the ideal characteristics of the data we collect?
4. What is A/B testing and how does it work?
5. Exercises: What metric(s) would you measure for testing the success of the following hypotheses?
    1. Voice control for sports stats will increase engagement on our sports websites by at least 20%
    2. New pricing model for all-inclusive access will increase cross-platform engagement
    3. Sports betting feature will increase revenue from sports channels by at least 10%
    4. Crowdsourced voting for trending content will increase user engagement
    5. Gamification of our content channels will increase user engagement
    6. Promotional text messages will increase user acquisition for our other channels by 10% or more


### Combined Template
1. Formula: [Feature] will result in [outcome], as indicated by [measured metric]
2. Exercise: Revise your project hypothesis to adhere to this format.


# Prototype
1. What does the ideal experiment look like?
2. What is the concept of a test group vs. control group?
3. How do you handle multiple experiments running?
4. Exercise: Determine the following for each hypothesis below:
    - Test group UX
    - Control group UX
    - How to split test and control groups
    - How to track the below metrics:
        1. Making it harder to close out signup modal will increase user acquisition, as indicated by daily signups increasing 10%.
        2. Moderating comments on articles will increase user engagement
        3. Promotional text messages will increase user acquisition for our other channels by 10% or more

# Overview of Tools and Technologies
## The Stack
What is a "stack"?

1. UI
2. Server
3. Database

## UI (10)
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

## Server (5)
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
### Questions (Optional)
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

### Questions (5)
0. What do the above tables correspond to?
1. What are the fields and what is the data type of each field?
2. How are these tables related?
3. What types of questions would you ask this database?

### Discuss Together (Optional)
0. What is SQL?
1. Why SQL?
2. Are there alternatives to SQL?

## Hosting, Analytics, and Tools (5)
### Hosting
- [Heroku](https://heroku.com)
- [Amazon Web Services](https://aws.amazon.com)

### Analytics
- [Google Analytics](https://analytics.google.com)
- [Mixpanel](https://mixpanel.com/)
- [Segment](https://segment.com)
- [Fullstory](https://fullstory.com)

### Development & Workflow Tools
- [GitHub](https://github.com)
- [Asana](https//asana.com)
- [Slack](https://slack.com)
- [Codeship](https://codeship.com/)
- [Sublime](https://www.sublimetext.com/)
- [Postico](https://eggerapps.at/postico/)

## Testing (20)
### Questions (5)
0. How do you know your app works the way you want it to?
1. How do you know your new feature doesn't break old functionality?

### Automation (5)
- Unit
- Functional
- Integration
- End-to-End (E2E)

### Examples (10)
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

## Prediction, Clustering & Recommendation (55-90)
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

### Unsupervised Learning - Clustering (20)
#### Questions (15)
1. Suppose you have 100 users and you know for each user what their age, location, favorite genres, and other useful intelligence. How would you organize them into 10 subgroups? Why would you even do this?
2. Suppose you have a lot of historical data on John, who belongs to Subgroup 1, in terms of what movies he's watched. How could this be useful?
3. Could this process of grouping apply to movies as well? If so, how and why?

#### Definitions (5)
- clustering
- collaborative filtering

## Let's Live-Code an Example (45)
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

# Analyzing Our Results Using Pandas (25)
## Significance Testing (10)
Here we'll walk through the intuition and explanation of significance testing.

##  Example (15)
We'll follow this process:

0. Read in the data
1. Compute aggregate metrics
2. Do some significance testing

# Decisions
1. At the end of hypothesis-driven development, how do you make a business decision?
2. Who is the decision-maker?
3. How do you convince the decision-maker?
4. What forms could the decision take?
5. How do you measure the results of a decision?


# Summary
1. In the modern world we should take advantage of the ability to be scientific and efficient in testing out our business hypotheses.
2. It's important to formulate a good hypothesis along with the metrics to measure and required [sample size](https://www.optimizely.com/sample-size-calculator/) for significance.
3. We can leverage modern technologies and tools to construct an experiment quickly and cheaply compared to the past.
4. It's important to recognize the limitations of the experiment to make a trustworthy, yet compelling pitch to resourceholders and decision-makers.
5. It's ok if the hypothesis is rejected - the important thing is that it was a worthwhile shot and extracted key learnings from it.
