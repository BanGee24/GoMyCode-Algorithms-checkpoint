An algorithm pseudocode that reads a sentence and determines it's length, numbers of vowels.
Initialize a counter variable for the length of the sentence, set to 0.
Initialize a counter variable for the number of words, set to 1 (assuming there is at least one word).
Initialize a counter variable for the number of vowels, set to 0.
Read in the sentence as a string.
Loop through each character in the string:
     a. Increment the length counter.
     b. If the character is a space, increment the word counter.
     c. If the character is a vowel (a, e, i, o, or u), increment the vowel counter.
     d. If the character is a period, exit the loop.
Print the length of the sentence, number of words, and number of vowels.


This is the JavaScript code for it:
const readline = require('readline').createInterface({
  input: process.stdin,
  output: process.stdout
});

readline.question('Enter a sentence: ', sentence => {
  let length = 0;
  let words = 1;
  let vowels = 0;

  for (let i = 0; i < sentence.length; i++) {
    const char = sentence.charAt(i);
    length++;
    if (char === ' ') {
      words++;
    } else if (/[aeiou]/i.test(char)) {
      vowels++;
    } else if (char === '.') {
      break;
    }
  }

  console.log(`Length: ${length}`);
  console.log(`Words: ${words}`);
  console.log(`Vowels: ${vowels}`);

  readline.close();
});
