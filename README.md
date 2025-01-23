# CS_5262_ML

Repository for the ML course in Vandy, CS 5262.

# Machine Learning Model to Predict the Effectiveness of Bank Telemarketing Calls

## Background
This is a ML projet using the dataset available at this link: https://archive.ics.uci.edu/dataset/222/bank+marketing

This is a dataset provided by UCI about marketing calls conducted by a bank in Portugual. Using its telemarketing team and often calling the same customers more than once, the bank aimed to get its audience to subscribe a term deposit.

This is more of a business research. The idea of this model is to measure the success of the marketing calls and ideally predict whether the
callee will actually place a deposit in the bank. The company would like to ideally use every bit of money spent on
telemarketing to cause a successive outcome (a deposit from the audience). Because there are different types of demographics and other characteristics of the people that the company reaches out to, and there are different aspects of the call itself (duration, what time the call was conducted, etc.), many variables go into this model. The idea is we want to guide the telemarketers to follow the infromation from this model and ensure that each time an individual is called, they are called in the "correct way" such that they do make a deposit.


## Confusion Matrix and Business Evaluation
Here are the interpretations of the false positive and false negative cases:
False Positive Case:
Scenario: The model predicts a client will subscribe (yes), but in reality, the client does not.
What Does It Mean:
Marketing resources are wasted on clients who were predicted to subscribe but did not.

False Negative Case:
Scenario: The model predicts a client will not subscribe (no), but the client actually subscribes.
Implications:
Missed opportunities for subscription.
The campaign might lose potential revenue since interested clients are not targeted effectively.

As for the confusion matrix, these are some rough estimates that we will use:
There is data on 45211 calls. Lets say each call is an average of 5 minutes.
From this [website](https://rep.ai/blog/cold-calling-statistics#:~:text=It%20takes%20about%20six%20calls,can%20close%20on%20about%2030%25.) we learned that the average sales company turns 20-30% of their calls into leads. So let's assume that 30% is a true positive, and lets make it symmetrical so that 30% is false negative. False negatives are less common since there is no outreach so it's rarer for people to come make a deposit, so lets make that 10% and make the false positive case 30%. Below is a table to better show this:
|                    | Actual Positive     | Actual Negative    |
| ------------------ | ------------------- | ------------------ |
| Predicted Postive  | True Positive 30%   | False Positive 30% |
| Predicted Negative | False Negative 10 % | True Negative 30%  |

Cost Breakdown:
The cost for a false positive is the time of the telemarketer it took (if we say $36 an hour that is $3 for one 5 minute call).
The cost for a false negative is that if the company had targeted that customer with calls they would have deposited more (so let's say the bank loses an average of $50 revenue for each of the times there is a false negative).

Calculation:
We have a total of 45211 calls in the dataset.
That means we have 4521 false negative calls and 13563 false positive calls.
With the assoicated costs, that means that the company lost 4521 * 50 = $226,050 because of the false negatives.
And that means the company lost 13563 * 3 = $40,689 because of false positives.
That brings the total of $266,739 that the company lost due to inefficient allocation of sales resoruces.

Ideally we can save the company all of this money. Along with that, in general sales calls have a very low rate of success and can be really annoying to some people who get those calls so strategizing such a task and targeting audiences at times that are more likely to get an adequate and successful response can be a tremendous source of success for the company. It will also allow it to use that extra money for further services and expansion, and provide increased value to the shareholders.
