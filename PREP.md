# Prep Method to solving Coding Questions

## PREP - Parameters, Return (type), Example (invocation), Pseudocode

```
Write a function that accepts a sentence that finds and returns the longest word
```

## P - Parameters

Write a function that accepts a sentence and returns the longest word.

- What parameters will our function accept?
- What type will each of our parameters have.
- What are meaningful names for our parameters?

Look for keywords like "accepts" or "takes in" in the problem description to guide you.

The statement “accepts a sentence” tells you that the function should accept a single String parameter.

You could name this parameter sentenceString to make the type crystal clear, but it's pretty obvious that just sentence implies a String, and it's more concise.

Since this is your first step, you also need to think of a meaningful name for your function itself. In your case, longestWord is both concise and descriptive. Now that you've decided this, you can write the shell for your function like this:

```js
function longestWord(sentence) {}
```

## R - Return

What type does this function return? Is it a number? A boolean? A string?

Remember: the value a function returns is not the same as what it might display in a print/log statement. Once again, you can look at the problem statement for clarification.

"Returns the longest word" tells you that you're returning a word, and you know that words are strings. Let's make this crystal clear by creating a variable to represent this return value and rigging up your function to return it. Even though you aren't returning the correct answer yet, you're set up to return the correct type. You have created a placeholder that will make the next steps easier.

```js
function longestWord(sentence) {
  var word = "placeholder";
  return word;
}
```

## E - Examples

Even for expert developers, static code is harder to understand than running code. You want to make your code runnable and “alive” as soon as possible. You can breathe life into your function with an example test invocation.

You know that if your function accepts the sentence, 'I saw a hippopotamus', it should return the string 'hippopotamus' once it's properly working. But for now, you just want to see your placeholder value from the last step to confirm your code is runnable and setup correctly.

```JS
function longestWord(sentence){
  var word = 'placeholder';
  return word;
}

console.log(longestWord('I saw a hippopotamus'));
```

## P - Pseudocode

While it's tempting to just dive in and start coding now, it would be too easy to get caught up in a detail that could distract you from the bigger picture. You need to devise a strategy first, and pseudocoding is just the tactic for this.

```JS
function longestWord(sentence){
  // Use a variable to keep track of the longest word so far.
  var word = 'placeholder'

  // Convert the sentence into an array of words, so we can easily
  // iterate over each word.

  // Loop through each of the words.

  // If the length of the current word is greater than the longest
  // so far, update our variable tracking the longest word.

  // After we've looked at every word, return the tracking variable.
  return word
}

// This should log "hippopotamus" once our function is working
// correctly. Currently, it logs "placeholder"
console.log(longestWord('I saw a hippopotamus'))
```

## You've finished PREP. Now you can code!

The four steps in PREP helped you clearly frame the problem and think about how to solve it. In truth, accurate framing is half the battle. At this point, your goal is to just write code that will make your examples and tests pass. You'll do this by encoding each of your pseudocode steps.

You know you've got a working solution when you can run your code and see the correct output.

```JS
function longestWord(sentence){
  // Use a variable to keep track of the longest word so far.
  var longestWordSoFar = ''

  // Convert the sentence into an array of words, so we can easily
  // iterate over each word.
  var wordArray = sentence.split(' ')
  var currentWord

  // Loop through each of the words.
  for (var i = 0; i < wordArray.length; i++){
    currentWord = wordArray[i]
    // If the length of the current word is greater than the longest
    // so far, update our variable tracking the longest word.
    if (currentWord.length > longestWordSoFar.length){
      longestWordSoFar = currentWord
    }
  }

  // after we've looked at every word, return the tracking variable
  return longestWordSoFar;
}

// This should log "hippopotamus" once our function is working
// correctly.
console.log(longestWord('I saw a hippopotamus'))
```
