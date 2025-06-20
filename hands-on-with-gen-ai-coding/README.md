<h1>
  <span class="headline">Intro to AI Asssited Coding</span>
  <span class="subhead">Hands-on with GenAI coding tools</span>
</h1>

**Learning objective:** By the end of this lesson, students will be able to use GenAI tools to co-write or refactor code in response to specific prompts, with attention to clarity, completeness, and correctness.

## Making your coding environment GenAI-ready

You already know your way around Python in a Jupyter notebook or other coding workspace. Today, you’ll add a new “digital teammate”: an AI assistant (for example, ChatGPT or Claude). This will let you blend your skills with the AI’s ability to generate and explain code.

Let’s set up:

* **Jupyter notebook (.ipynb file) or your favorite Python IDE**
  This is where you’ll run, edit, and check code—just as you’re used to.
* **GenAI coding tool in your browser**
  Open ChatGPT or Claude in a browser window or tab. You’ll use this chat-based tool to prompt the AI and review its replies.

> 🏆 Keeping the chat window and your coding workspace side by side helps you work seamlessly with AI while verifying code before you run it.

---

## Tag-teaming with AI

Think of this workflow as collaborating with a colleague who’s **quick at writing snippets, but sometimes misses your intent.**&#x20;

You explain what you need in the chat, receive their code suggestion, and then bring it into your notebook for real-world testing.

> 💡 Like reviewing a teammate’s draft, your job is to make sure everything works and is fit for your project rather than just to accept what’s handed to you.

---

## Crafting clear prompts for AI-assisted coding

Writing concise, specific prompts gets you better results from the AI. Here are adaptable templates:

* **Generate a new function**

  > Write a Python function called `calculate_total_price` that takes a list of item prices and returns their sum, rounded to two decimal places.

* **Refactor your existing code**

  > Here’s a function for standardizing names. Can you refactor it for readability and performance?
  >
  > ```python
  > def standardize_names(names):
  >     for i in range(len(names)):
  >         names[i] = names[i].strip().lower()
  >     return names
  > ```

* **Debug or explain code**

  > I’m getting an error when trying to merge two DataFrames. What’s wrong?
  >
  > ```python
  > merged = df1.append(df2)
  > ```

> ⚠ Even small clarifications like **providing example input data or specifying the libraries** to use make a big difference in the code you receive.

---

## Best practices for prompting AI assistants

* **Describe expected behaviors clearly.**
  Specify what the function should achieve, including input and output data types.

* **Break down complex objectives.**
  For a multi-step task, ask for each part separately, testing as you go.

* **Request comments in the code.**
  Ask the AI to include explanations to improve code readability.

* **State any requirements.**
  If you need solutions using particular packages or styles, name them in your prompt.

> 📚 A *prompt* is the instruction or request you give to an AI assistant to obtain a desired result.

---

## Real-world example: Summarizing DataFrames

Suppose you want a function that:

* Lists, for each column, the total count of non-missing values, the mean (for numeric columns), and the total number of missing values.

Prompt:

> Write a Python function called `column_summary` that accepts a pandas DataFrame and returns a new DataFrame with each column’s count, mean, and number of missing values.

AI output:

```python
import pandas as pd

def column_summary(df):
    summary = pd.DataFrame({
        'count': df.count(),
        'mean': df.mean(numeric_only=True),
        'missing': df.isnull().sum()
    })
    return summary
```

You test with data:

```python
data = {
    'temperature': [22, 25, None, 28],
    'humidity': [60, 65, 63, None],
    'location': ['North', 'East', 'West', None]
}

df = pd.DataFrame(data)
print(column_summary(df))
```

To include only numeric columns, you revise your prompt:

> Only include numeric columns in the summary output.

> 🧠 Prompt refinement is core to leveraging AI well: give feedback, clarify details, and iterate based on results.

---

## Activity: Refactor ➡️ verify ➡️ enhance

1. **Start with this code:**

```python
def extract_emails(df):
    emails = []
    for email in df['email']:
        if '@' in email:
            emails.append(email)
    return emails
```

2. **Prompt your AI assistant to improve it.**

> Can you refactor this function to efficiently extract all valid email addresses from the 'email' column of a pandas DataFrame? Ignore invalid or missing entries.

3. **Test the result using this DataFrame:**

```python
data = {
    'email': [
        'aiko.sato@example.com',
        None,
        'invalid_email',
        'karim.rahman@domain.org'
    ]
}

df = pd.DataFrame(data)
print(extract_emails(df))
```

4. **Evaluate the AI’s suggestions.**

5. **Ask for improvements if needed.**

> Can the function use a regular expression to check if the string is a valid email format and handle missing columns?

6. **Summarize the differences.**

* What improved?
* What did you change or decline?

---

## Knowledge check and discussion

* How will you decide when to trust the AI’s code suggestions?
* What steps will you take to verify clarity and correctness?
* How does this process compare to working with a human teammate?
