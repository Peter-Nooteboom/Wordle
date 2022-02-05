# Wordle Solutions Analysis
---

![Wordle Solutions Analysis](https://imgur.com/5gtzHgN.jpg)

In this project I analyzed the Wordle solutions dictionary, and provided 8 insights and visualizations to help others win the game in fewer moves.

## What is Wordle?

**Game Premise:** If you spent any time on the internet in early 2021, you have probably heard of Wordle. Wordle is a word game with one puzzle per day. Each puzzle shares a single 5-letter solution for every player. A player is given 6 chances to guess the solution word. Each guess is accompanied with feedback to direct the player closer to the correct answer. If a correct letter is guessed in the correct position, the letter turns green. If a correct letter is guessed, but it is in an incorrect position, the letter turns yellow. The goal is to find the solution word in as few guesses as possible. Here is an example of what a few of the puzzles look like:

![Wordle Puzzle Examples](https://imgur.com/KmzZoVz.jpg)

## Project Summary

**Problem:** Given the viral trajectory the game has taken, players are looking to up their game. With only 6 chances to win, it can be difficult to make the best possible guesses without cheating. What strategies can people use to help them choose ideal words, and win the game more quickly?

**Goal:** Wordle was programmed in a way where there is a set solutions dictionary of 2315 words. Each day one of these words is the correct solution. For a player, looking at these answers would clearly be considered cheating. My goal is to provide insights about this list using data analysis. From this, people will be able to make more informed guesses without directly cheating.


## Data

Wordle has a built in dictionary of predetermined solutions. The 2315 words in this dictionary were scraped from the Wordle site. A copy of this list can also be found on [Kaggle](https://www.kaggle.com/bcruise/wordle-valid-words).


## 1. Letter Frequency

One of the first strategies that someone might consider is guessing a word that includes the most common letters in English. Doing so gives you the best chance of getting a correct letter. The key to not wasting Wordle guesses is using common letters. However, letter commonness in the actual Wordle solution dictionary is slightly different than regular English.

As can be seen below, in the set of Wordle solutions, vowels are very common. In fact, all of them are in the top 50% of letters, even when including Y. In terms of consonants, R, T, L, S, N are the most common, and Z, X, Q, &, J are very rare. In general, guessing words that contain letters towards the left of the plot will give you a better chance of getting correct letters. Additionally, if you are basing your guesses purely on letter frequency, a great starting word would be ROATE.

![Wordle Letter Frequency](https://imgur.com/batM1hK.jpg)

## 2. Vowel Frequency

Given that most English words have a vowel in them, it may not be all that surprising that they are so common in Wordle. However, less obvious is the number of vowels that most words in Wordle actually have. The below plot shows how many vowels appear in each word. The plot contains the counts for both when you include or exclude Y as a vowel. In this instance Y was only added to the count when it classified linguistically as vowel.

Whether you count Y as a vowel or not, most words in the Wordle solutions dictionary have two vowels, followed by one vowel as the second most frequent, and three vowels in third place. Only a handful of solution words contain four or zero vowels, and none have five vowels. With that in mind, once you have revealed one or two vowels, you will probably want to focus on guessing consonants for most of your other letters.


![Wordle Vowel Frequency](https://imgur.com/fyEaFIj.jpg)

## 3. Top Letters in Each Position

Now that we have some understanding of what letters and vowels are most frequent, a next step would be to consider the placement of these letters. The following plot shows the top five most frequent letters in each of the five positions.

As mentioned previously, vowels are very common. However, that dominance primarily takes place in positions two and three. Additionally, E remains common in positions four and five. Y is also common, but only in the fifth spot. The first position is highly dominated by consonants, with S being by far the most frequent. This shows that even with a single set of five letters, the arrangement of those letters matters. For example, earlier I identified ROATE as a good first guess given the overall frequency of its letters. However, those same letters could also form ORATE. That said, this would be a marginally worse word given that O is more common in the second position over R.

![Wordle Positional Frequency](https://imgur.com/OnzOj0c.jpg)

## 4. Most Common Letter Positions

Taking the investigation of letter frequency one step further, we can also look at the most frequent position of each letter individually. Let's say Q was identified as a yellow letter. What position could it be moved to that would give it the best chance of being correct? The below plot shows the relative frequencies of each letter in each of the five possible positions. When Q appears in a word, it is by far most commonly in position one, and never in four or five.

Every letter has a position where it is most frequent. Additionally, almost every letter has at least some chance of appearing in any of the positions. For example, R appears fairly evenly across the board. However, for some, the distribution is more skewed. For letters like Y, it is best off placed at the end of the word when used. Additionally, S does not occur very frequently in position 5. In fact, a deeper look at the data reveals that there are no plural S's in the solutions dictionary.

![Wordle Common Letter Positions](https://imgur.com/MrUctn7.jpg)

## 5. Commonly Repeated Letters

One additional challenge that Wordle poses is the possibility of double letters appearing in a word. Even if a letter has been identified as yellow or green, that doesn't mean that a second instance of that letter isn't present in the solution. The below plot shows the letters that are most likely to be repeated. In this instance every additional appearance of a letter in a single word was counted as a repeat. For example, TEPEE would have 2 additional appearances of E, and therefore 2 repeats total.

Vowels are commonly repeated, with E standing out above the rest. The most commonly repeated consonants are L, R, T, and S. In an instance where a repeated letter seems probable, these are the most likely suspects.

![Wordle Repeated Letters](https://imgur.com/44yzeKq.jpg)

## 6. Average Unique Letter Count

It is helpful to know which letters are most likely to be repeated, but how often should such an occurrence be expected? This plot shows the percentage of words that have various numbers of unique characters. For example, a word with five unique letters would have no repeats.

About 75% of solution words have five unique letters (no repeats). About 30% have four unique letters (1 repeat), and only a handful had two or three unique characters. Therefore, about one third of the puzzles, can expect to have at least one repeat.

Once a couple of letters are correctly guessed, it may be difficult to know what other letters to test next. The following plot shows the frequency of each letter given a particular "correct" letter (along the top. For example, if a Green Q has identified, U's are extremely common as an additional letter in that word.

![Wordle Unique Letters](https://imgur.com/qYGgBhV.jpg)

## 7. Related Letters

Once a couple of letters are correctly guessed, it may be difficult to know what other letters to test next. The following plot shows the frequency of each letter given a particular "correct" letter (along the top. For example, if a Green Q has identified, U's are extremely common as an additional letter in that word.

![Wordle Related Letters](https://imgur.com/OgWSB28.jpg)

## 8. Parts of Speech
Beyond the letter arrangement of each guess, the meaning and part of speech of the words can also be considered. The following plot shows the percentage of words that can be classified as nouns, verbs, adjectives, and adverbs. Keep in mind that a single word can be classified as multiple parts of speech.

A little over 75% of the words in the Wordle solutions list can be classified as nouns. Slightly over 45% can be classified as adjectives. About 25% of them can be classified as adjectives, and under 10% as adverbs. Given this, guessing nouns and verbs is the most likely strategy to lead to a correct answer.

![Wordle Parts of Speech](https://imgur.com/sEvOuMf.jpg)

## Conclusion

The present analyses revealed several relevant insights that can be leveraged to improve your chances of success when playing Wordle. You can focus on letter and vowel frequency, the position of those letters, repeated/unique letters, related letters, and even parts of speech. These techniques will enable your to compete and beat your friends at Wordle while also maintaining the pride of not cheating your way to victory.

---

If you enjoyed this project, please consider following me on [Twitter](https://twitter.com/Peter_Nooteboom) and [Linkedin](https://www.linkedin.com/in/peter-nooteboom/).

