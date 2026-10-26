# Isaac and Lylah

## Labeled Passages
### From the Beloit Student Handbook, Alcohol Section
#### Alcohol with Others
Using alcoholic beverages as the primary focus of any activity, including participating in
drinking games. Kegs are not permitted. Pressuring others to drink, as in exerting direct or nonverbal pressure to consume alcohol
or additional alcohol, or alcohol along with other drugs. Providing alcohol to minors, especially if those minors are not college students at Beloit.
#### Drinks with Alcohol
Drinking hard liquor directly from the bottle (non-single serving size), or multiple shots. Mixing alcohol with energy drinks is prohibited.
#### Behavior
Displaying violent, inappropriate or other kinds of offensive behavior (including but not
limited to, groping, harassing, and physical injury). Intoxication does not absolve the
drinker of responsibility for their actions.
#### Judicial Processes
The normal judicial processes, described later in this Student Handbook, will be used to respond
to violations of the alcohol policy. Whether through Restorative Justice or the traditional
processes, the full range of sanctions (and more than one at a time) are possible, including a
discussion with parents (for which there is an exemption to the law that limits communication
with parents - FERPA).
#### Alcohol in Academic Buildings
Alcoholic beverages may not be served or consumed in academic areas unless prior approval is
received from the Department/Division Chair or Provost.
#### Parties and Social Gatherings
For any social gathering, there must be at least one unintoxicated person responsible 
for the gathering, the facility and the guests. In a student room, this is normally the resident of the room. 
In a planned party, it is often the person planning who is responsible for the event.

 ## Three Questions a Student Would Ask

 - Is pressuring others to drink prohibited?
 - Can I drink liquor from the bottle?
 - Does intoxication absolve the drinker of responsibility for their actions? 

## Fourth Question
Can I get drunk with my roommate?

# D1
## Key word Scores
 Is pressuring others to drink prohibited?
   expected passage: Alcohol with Others
   shares 2 word(s): drink, pressuring
   
 Can I drink liquor from the bottle?
   expected passage: Drinks with Alcohol
   shares 2 word(s): bottle, liquor
   
 Does intoxication absolve the drinker of responsibility for their actions?
   expected passage: Behavior
   shares 6 word(s): absolve, actions, does, drinker, intoxication, responsibility
   
 Can I get drunk with my roommate?
   expected passage: Parties and Social Gatherings
   shares NO words.
# D4 D5
Since the question has no keywords shared with any of the passages it should have a score of 0 for any similarity. Running the model gives this exact result
## embedding results
```
Is pressuring others to drink prohibited?
0.1490  Alcohol with Others  <- you expected this
0.1353  Drinks with Alcohol
0.0000  Behavior

Can I drink liquor from the bottle?
0.2706  Drinks with Alcohol  <- you expected this
0.0646  Alcohol with Others
0.0000  Behavior

Does intoxication absolve the drinker of responsibility for their actions?
0.5270  Behavior  <- you expected this
0.0000  Alcohol with Others
0.0000  Drinks with Alcohol

Can I get drunk with my roommate?
0.0000  Alcohol with Others
0.0000  Drinks with Alcohol
0.0000  Behavior
gap between 1st and 2nd: 0.0000
VERDICT: every score is zero. This question shares no words with anything in the corpus, so the ranking is arbitrary - whichever passage happens to be listed first wins. Ignore the winner.
```

## Your fourth question shared no words with the passage that answers it. What did the keyword method do, and what does that tell you about what it can and cannot measure?
Since the keyword search was zero across all passages all passages had the same similarity of 0. The model had no way of knowing mathematically which passage was related and so it could not answer the question. This means that when we use passages like these, we have to structure questions in a way that matches the syntax structure of the sentences in the handbook.


## Look at the gap between the top two passages in the embedding run. If that gap is small, what does it imply about building a system on top of this? Would you trust the top result on its own?
If a gap is small between two passages it means that the question shares a lot of keywords with both passages. If the question has more keywords shared with an irrelevant passage than the one with the answer, the model will give a useless answer by prioritizing the irrelevant passage, meaning that the top result can be completely wrong.

## Your Project 2 system retrieves passages and then answers from them. What happens to the answer when retrieval picks the wrong passage? How would you find out that this had happened?
As discussed in the previous question, the model can give a wrong or useless answer when choosing the wrong passage. This can be helped by testing the model with
questions we already know the answer to, if the model gives a wrong answer we can edit the model to be more accurate. A way to prevent the model from giving useless information could be to make it give multiple answers from multiple passages, this is computationally expensive and can overwhelm the user with text.


