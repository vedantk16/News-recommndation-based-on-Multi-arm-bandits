# News-recommndation-based-on-Multi-arm-bandits

# Abstract

Personalized web services strive to adapt their services (advertisements, news articles, etc.) to
individual users by making use of both content and user information. News recommendation is a
field different from traditional recommendation fields. News articles are created and deleted
continuously with a very short life cycle. Users’ preference is also hard to model since they can
easily be attracted by things happening around them. One of the major challenges is
recommendations for new users, also known as the cold-start problem. Now, there are some
studies which propose a bandit approach to this problem, but they fall short on the
recommendations to users with a lot of behavioral history.
This study proposes a hybrid algorithm which adapts as the user interacts with the environment.
Along with this, we also propose a framework for unregistered users for which we have no
information about.

# Introduction

The user base can be divided into two different categories the unregistered and registered
users. For the unregistered users, no prior knowledge about the user is observed and in the
case of registered users, some level of demographic, geographic or behavioral information is
available to us.
The unregistered users have temporary click information for a particular session. Hence, the
expected reward can only be predicted by features based on articles including URL categories,
editor categories, and topic. Now if the article considered is new and thus has no user
interactions, it becomes very hard for the MAB to find the expected reward. On the other hand
for articles with large user interactions are easy to model the expected payoffs.
In the case of registered users, we face a different challenge of a cold start. We do not have any
behavioral information for new users and thus are hard to model.
We solve the challenges by introducing a hybrid model for both cases:
1. Registered user: We have two algorithms contextual bandit for all users and linear bandit
for each user. For a new user, contextual bandit algorithm will be used and as the
behavior information increases, we shift to linear bandit for each user.
2. Unregistered user: Similar to above we have contextual bandit for all articles and linear
bandit for new articles. Linear bandit will use features based on the topic of article and
URL, editor categories to predict expected reward and as the user interactions for article
increases, we can use MAB using the click rate of the article.
