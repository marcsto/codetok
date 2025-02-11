# CodeTok
Improve your coding skills with bite-sized tutorials in a vertical scrolling interface.

# Live Demo
Visit https://marc.ai/codetok/

# Key Features
* Learn through small examples that fit on a single page.
* Scroll to the next item by swiping upwards in a TikTok-style interface.
* To learn more about a topic, click on its title which will launch an LLM that will teach you more and where you can ask questions.
* Has tutorials for over 15 languages and frameworks.
* Has tutorials for beginners and advanced programmers who want to learn more.
* Also has a few language crossover tutorials (e.g. Learn Kotlin if you already know Java, Learn Swift if you know Objective-C
* Has more advanced concepts like large language models, and neural network tips and tricks.

# How to add a new language
* Option 1: Request one in the issues tab or email me at marcsto@gmail.com
* Option 2: Use an LLM to create a new language file (see below). Add it to the data directory (you can see other examples there). Update index.html to point to it.

# Using an LLM to generate a tutorial for a new langauge
Give an LLM one of the following prompts (I used ChatGPT o3-mini-high. I recommend using whatever is the best model at the time of writing even if it's slow).
(See prompts.txt for more examples)

Example prompt:
I've been programming in Python for several years. Teach me advanced concepts that will make me a better programmer as well as best practices. Split this into small examples that can be consumed on a single page on a phone. I'm building a database of these, so please provide 50 examples. Provide the output in markdown so I can store it in a database and render it later on my website in a way that will preserve the formatting (bold text, coding blocks etc.). Users won't be able to run the code, so provide comments when appropriate. Keep the comments short. Don't add print statements if comments already explain outputs.

Here's an example format:
{
examples: [
{
        "name": "Functions and Arrow Functions",
        "example": "Functions perform tasks; arrow functions offer a shorter syntax.\n\n```js\n// Traditional function\nfunction greet(user) {\n  return \"Hello, \" + user;\n}\n\n// Arrow function\nconst add = (a, b) => a + b;\n```"
      },
{
"name": "Name for example 2",
"example": "Example using markdown for both code and explanation",
},
]
}

-----------
Once it has generated 50, ask it to "Generate 50 more". Note: Doing it this way gave better results than asking for 100 directly as it made the examples too small when asking for the 100 at a time.

Note the example shown in the prompt is important: In this case I asked it for a python program but gave it a javascript example so it would have enough context to generate the right style of examples but it recognized that the javascript example wasn't the right thing so it didn't just re-use it.

You can also experiemnt with this by asking it to generate 5 examples. Then you fine tune the formatting of it and ask it again, showing it the new, better formatted example so it follows that style going forward while also not having the example interfere with the curriculum it wants to write.
