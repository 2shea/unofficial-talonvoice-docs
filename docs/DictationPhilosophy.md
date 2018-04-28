# Dictation Philosophy

This page tries to give a historical context and reasoning for Talon's way of working, which differs from other speech-to-text systems.

When dictating complex things to a computer, there are two types of tasks to accomplish.

1. **Data Entry**: entering data, such as words, phrases, and numbers.
2. **Commands**: executing commands, triggering shortcuts, and inserting symbols.


## Data Entry First Philosophy

Historically, speech-to-text systems have emphasized Data Entry. Most words and phrases are entered by inserting exactly what was heard by the dictation engine. For symbols, occasionally, special phrases or words might have been used, but much of the formatting and command operation was done by changing modes within the dictation engine: one mode for entering data, another for editing, etc.

As interest in speech-to-text systems for use with programming grew, some of the first attempts took the same basic approach. By default, spoken words and phrases were assumed to be Data Entry tasks. Speaking a word or phrase would cause that word or phrase to be entered literally. For Commands, developers developed large sets of uncommon and made-up words to represent all sorts of operations and symbol insertions. Effectively, they created a new language on top of English that could be interspersed with it as needed to provide the right meaning or action.

* When speaking a phrase like `🔊 my variable`, the program would output "my variable".
* If one used a trigger word before a phrase, such as `🔊 snake my variable`, the output would be "my_variable", because `🔊 snake` was a trigger word used to mean 'join the next phrase with underscores.'
* A user might say `🔊 crunder` to mean 'enter an underscore (_).'


## Command First Philosophy

An alternative philosophy is merely the opposite. Everything said is assumed to be intended as a Command task, if recognized as such. To do Data Entry, one has to use a Command for input.

* When speaking a phrase like `🔊 my variable`, nothing will happen, because it would not match with any existing Commands.
* To match a literal entry command, one would say `🔊 phrase my variable` or `🔊 say my variable` to output "my variable".
* If one used a trigger word before a phrase, such as `🔊 snake my variable`, the output would be "my_variable", because `🔊 snake` was a trigger word used to mean 'join the next phrase with underscores.' This is the same as with the first philosophy.
* A user might say `🔊 underscore` to mean 'enter an underscore (_).'

> **Notice:** The `snake` trigger word can be used in both systems in exactly the same way.


## Pros & Cons

Both approaches have their pros and cons.

### Data Entry First Philosophy

* Pros
  - No trigger words needed to enter words and phrases.
  - For sentences with minimal markup, the amount of stopping/context switching can be minor.
  - That feeling of accomplishment after learning a new language.
* Cons
  - All detected speech is interpreted as input or commands, intentional or not, requiring the microphone to be disabled when input is not desired.
  - In practice, the range of available uncommon or made up words is limited by the sounds a human mouth can make reasonably and how similar they sound to real words or words for Data Entry.
  - Using uncommon words for Commands only works well so long as those words remain uncommon in a particular instance of Data Entry.
  - To prevent ambiguity, sometimes phrases must be used with a trigger word anyway.
  - In practice, made up words are harder to accurately detect.
  - You basically have to learn a new language.

### Command First Philosophy

* Pros
  - With only a few exceptions, all words are available for all commands; be they real, uncommon, or made up.
  - Fewer trigger word collisions.
  - Much more efficient and quicker recognition.
  - More accurate recognition.
  - Command trigger words can be as verbose or as svelte as desired, but they can more easily be paired with their underlying concept (`🔊 underscore` means "_").
  - Less to learn, as an operation's Command is usually triggered by a word or phrase describing that Command.
  - With some trigger word exceptions, one can speak normally with others, or be in an environment with others talking, without all that speech being interpreted as input.
* Cons
  - Trigger words must be used to input anything.
  - Initially, most speakers think in terms of the phrase they want to input with special words for Commands and symbols. This system requires the user to reverse that natural tendency.
  - Emphasis on learnability of Commands can potentially slow down input for an advanced user. This would require shifting to a more svelte alternative language for common Commands.


## Talon's Philosophy

Talon's philosophy, unlike previous speech-to-text systems, chooses the Command First philosophy. It values the greater speed, efficiency, recognition, and flexibility of a Command-based input system over its inconvience while dictating normal phrases. Talon's design implies a belief that the time necessary to retrain a user's thought process to inject an input trigger word into his sentences will be a much quicker and easier task than effectively learning a new language that the other philosophy requires.

Hopefully this answers the questions about why Talon's Command structure is designed the way it is.