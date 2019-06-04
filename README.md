### PROBLEM STATEMENT
After losing the World Series on their home field twice in the last two seasons
and failing to secure one of the marquee free agents in the off-season,
the Los Angeles Dodgers need to identify three possible ways to keep fan
engagement high in the 2019 season.

I collected a large sample of Reddit posts from both the r/Dodgers and
r/baseball subreddits, conducted EDA and natural language processing on them,
and fit multiple classification models on them to determine what inferences
can be made that might help the Dodgers organization better connect with its
fanbase.


### EXECUTIVE SUMMARY
I have a strong Random Forest classifier that can predict with greater than 80%
accuracy whether a block of text was posted to the r/Dodgers subreddit or the
r/baseball subreddit. Based on exploratory analysis of tens of thousands of
posts, I believe the Dodgers should focus on engaging fans via short-form
social media platforms to celebrate the legacy of the organization while also
promoting current fan-favorite players like Justin Turner.


### TECHNICAL RESOURCES
Please note that in the provided Jupyter notebooks, code blocks that perform
external write commands and model fitting are mostly commented out to protect
against accidental overwrites.


### PRIMARY CONCLUSIONS AND RECOMMENDATIONS
My analysis began with 20,000 posts collected from the r/Dodgers subreddit and
20,000 posts collected from the r/baseball subreddit. Slightly more than
half of the posts collected from the r/Dodgers subreddit had no text within
the body of the post. Roughly two-thirds of the r/baseball posts had textless
bodies, suggesting that Dodger fans do not have as great a need for multimedia
engagement in their online communication as general baseball fans do. Just over
two-thirds of the r/Dodgers posts with text were under 280 characters in length,
suggesting that Twitter's character limitations are not prohibitive for fan
outreach. Short-form social medial platforms including Twitter and Instagram
should be a primary means of engaging Dodger fans.

Next, I ran the text data through a 500-feature CountVectorizer and fit a
multinomial Naive Bayes classification model on the features. Unfortunately,
this model only achieved an accuracy score of just shy of 70%. That being said,
the model did have a precision score of roughly 80%, meaning that the vast
majority of posts it predicted to be Dodger posts were correct. The words that
the model found to be most predictive in classifying a post as coming from
r/Dodgers did present insights worth exploring. The words "hall" and "fame"
were both top indicators of a post being from the Dodgers subreddit. This
suggests that Dodger fans have a stronger interest in the National Baseball
Hall of Fame and the history of the game than baseball fans at large. For this
reason, I suggest focusing marketing materials on the legacy of the Dodgers
franchise and how the team and its most famous players fit into the broader
history of Major League Baseball. Furthermore, the Dodgers organization should
consider creating its own team hall of fame, similar to what the St. Louis
Cardinals have created, to invite its fans to celebrate the team's history.

Finally, I applied a TF-IDF vectorizer to the text data and used GridSearchCV
and RandomizedSearchCV to fit a Random Forest decision tree classifier on the
features. At over 80% accuracy, this model performed substantially better than
the Naive Bayes model and provided additional insights into the most predictive
words within the collected text. The names of three current Dodger players
(Clayon Kershaw, Justin Turner, and Walker Buehler) featured prominently.
The frequent mentions of Kershaw and Buehler could be attributed to the
injuries both players faced during the most recent spring training. But Justin
Turner's prevalence is most likely the result of his consistently impressive
play throughout the Dodgers' ill-fated 2018 postseason. He caught the attention
of the fanbase and as the bright spot in those dim memories, he should be a
primary focus when engaging fans with marketing materials and promotions in
the early days of the 2019 season.


### ADDITIONAL CONSIDERATIONS
Moving forward, I believe the best-performing Random Forest model from this
analysis is a strong classifier and is worth further investment through
additional tuning. Furthermore, as its accuracy improves it should continue
to be used to monitor new trends and fan response to individual players as
the regular season progresses.

Additionally, because the contributors to the Dodgers subreddit are a
self-selecting sample of fans, the Dodgers organization should seek
validation of the findings within this report through independent fan surveys.
This sample bias is potentially most problematic with regards to Dodger fans
who either do not speak English or for whom English is a secondary language.
Additional research focused on other languages, particularly Spanish, would be
invaluable.