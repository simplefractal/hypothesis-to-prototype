# Hypothesis to Prototype 101

## Objectives
- Learn and apply framework for going from hypothesis to prototype
- Get familiar with common tools and technologies for hypothesis-driven product development
- Get introduced to recommender systems
- Walk through a worked example from hypothesis to prototype, analysis, and conclusion

## Agenda
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


## Ideation Process
1. How do you come up with an idea?
    - Observations
    - Trends, what is up/down
    - Discover problems (must train/emphathize/comunicate), e.g. CI SAAS
    - Combine things, e.g. phone + camera, restaurant + courier, pets + social networks
    - New technologies, e.g. email recruiting, computers, internet, AppStore, voice control
    - New consumer tastes, e.g. photos to share vs. document

2. How do you go past the idea stage?
    - Convince people with resources, using data and numbers
    - Go bulls-eye for efficiency
    - Use the scientific method:
        1. Make observations
        2. Formulate a hypothesis
        3. Design an experiment to test the hypothesis
        4. State the indicators to evaluate if the experiment has succeeded
        5. Conduct the experiment
        6. Evaluate the results of the experiment
        7. Accept or reject the hypothesis
        8. If necessary, make and test a new hypothesis

3. How are things different now compared to a decado ago and why?
    - Luxury of quick iteration, and easy data capture
    - Easy to split test in online world
    - Objective can be learning instead of immediate profit
        - Uninformed optimism cycle

## Hypotheses
1. What is a hypothesis?
    - Falsifiable, repeatable statement that you believe to be true and if proven to be true would have a meaningful impact.

2. How do you distinguish a good hypothesis from a bad one?
    - Falsifiable? e.g. god exists
    - Testable? e.g. TSA scan is harmful for pregnant women
    - Measurable? e.g. user thinks of green polar bears when eating kale
    - Specific? e.g. gamification is good
    - non-tautological? e.g. a better UI will result in less user confusion
    - Meaningful? e.g. rats are stronger than pigeons in NYC
    - Cheap? e.g. exiting the stratosphere in a space vessel will reduce racist tendencies
    - Fast? e.g. only eating fast-food vs. only eating salads for a decade has no effect on health indicators
    - Rooted? e.g. sloths can be trained to perform complex tasks

3. Exercise: Formulate your project hypothesis
4. Critique each other's hypotheses and see if you can improve them
5. How do we accept/reject a hypothesis?
    - Based on significant data
        - T test
        - P value
    - Test group, control group

## Data Collection
1. Why is it important to determine what data to collect?
    - We don't want to backward induct or overinterpret randomness.
        - e.g. Chinese story of the farmer and the rabbit who hit a tree
        - confusing correlation with causation, e.g. Romanian police and crime

2. What are some general metrics we could collect to accept/reject a hypothesis?
    - Conversion rate, good for funnels
    - Clicks, Page loads, Minutes watched, Bounce rate
    - Videos watched in full, canceled videos (browsing vs. consuming)
    - MAU, MUV, Revenue, Signups, Subscribers
    - Qualitative data: user surveys, recordings of user sessions
        - Good for detecting e.g. frustration clicks and other anomalies
    - Shares

    - Which metric to judge?
        - Primary metric
        - Company-wide metric
        - Basket of metrics (each with their own criteria)

3. What are the ideal characteristics of the data we collect?
    - High volume (faster significance testing)
    - Quantitative in nature
    - Quick to collect (common user metric)
    - Highly correlated with hypothesized feature
    - Isolated/controlled (increase in metric is indeed due to feature) 

4. What is A/B testing and how does it work?
    - Splitting user group randomly based on e.g. modulo user id
    - Defining a control group along with one or several test groups

5. Example: What metric should I measure for testing an alternative user signup flow?
    - \# unique landing page visitors (not just conversion rate, b/c base might increase due to SEO)
    - \# unique signups
    - Cohort testing of base metric
        - Revenue
        - Clicks
        - Monthly active users (MAU)

5. Exercises: What metric(s) would you measure for testing the success of the following hypotheses?
    a. Voice control for sports stats will increase engagement on our sports websites by at least 20%
        - \# times voice control was used and by whom
        - \# clicks
        - \# MAU

    b. New pricing model for all-inclusive access will increase cross-platform engagement
        - \# clicks
        - \# MAU
        - revenue

    c. Sports betting feature will increase revenue from sports channels by at least 10%
        - sports revenue
        - overall revenue

    d. Crowdsourced voting for trending content will increase user engagement
        - \# unique voters
        - \# votes
        - \# clicks on featured content
        - Bounce rate on featured content

    e. Gamification of our content channels will increase user engagement
        - scores by user (nice metric for later)
        - avg. days of inactivity (daily rewards or push notifications to re-engage would decrease this)
        - monthly unique visitors
        - clicks
        - revenue

    f. Promotional text messages will increase user acquisition for our other channels by 10% or more
        - \# texts sent
        - \# unsubscriptions
        - \# signups in each channel
        - source of signup in each channel

### Combined Template
1. Formula: [Feature] will result in [outcome], as indicated by [measured metric]
    - WHAT, WHY, HOW

2. Exercise: Revise your project hypothesis to adhere to this format.
    - Reshare and critique

## Prototype
1. What does the ideal experiment look like?
    - Simple, fast, and cheap to build
    - Collects the data we need
    - Can be rolled out to a subsection of user base
    - Easily switched on/off

2. Example: Crowdsourced voting for trending content will increase user engagement, which we’ll know when the top 10 list of content receives a net score of +1000 in a day, and overall viewers of our promoted content will increase by 10%.
    - Control: Sees existing list of content.
    - Test group: Sees list of trending content as well as UI to upvote or down vote content.
    - Metrics to track:
        - \# up votes by article/video
        - \# down votes by article/video
        - \# unique viewers by article video

3. What is the concept of a test group vs. control group?
    - Test group is a random unbiased sample of the user base selected to receive experimental feature
    - Control group is the rest of the user base that just sees the application as it was before
    - Purpose is to isolate differences in measurements and attribute them to the experimental feature

4. How do you handle multiple experiments running?
    - Continually split on modulo 2, 4, 8, 16, 32, etc.
    - Use a third-party service like MixPanel or Optimizely

5. Exercise: Determine the following for each hypothesis below:
    - Test group UX
    - Control group UX
    - How to split test and control groups
    - How to track each metric

        1. Making it harder to close out signup modal will increase user acquisition, as indicated by daily signups increasing 10%.
        2. Moderating comments on articles will increase user engagement
        3. Promotional text messages will increase user acquisition for our other channels by 10% or more

## Decisions
1. Be aware of your assumptions and experimental flaws
    - When do you stop running the experiment? Calculate required sample size.
    - Was there a selection bias in your user survey?
    - Could anomalies have occurred due to someone leaving their computer and viewing back-to-back videos for 55 hours straight?
    - Could success in the key metric have negative externalities?

2. Who is the decision-maker?

3. How do you convince the decision-maker?
    - Compelling story-telling
    - ROI
    - Cost/Benefit analysis
    - Mitigate risks

4. What forms could the decision take?
    - Roll out to entire user base
    - Incorporate key learnings and iterate on experiment
    - Discontinue the feature

5. How do you measure the results of a decision?
    - Tracking company-wide metrics over the long term

## Summary
1. In the modern world we should take advantage of the ability to be scientific and efficient in testing out our business hypotheses.
2. It's important to formulate a good hypothesis along with the metrics to measure and required [sample size](https://www.optimizely.com/sample-size-calculator/) for significance.
3. We can leverage modern technologies and tools to construct an experiment quickly and cheaply compared to the past.
4. It's important to recognize the limitations of the experiment to make a trustworthy, yet compelling pitch to resourceholders and decision-makers.
5. It's ok if the hypothesis is rejected - the important thing is that it was a worthwhile shot and extracted key learnings from it.
