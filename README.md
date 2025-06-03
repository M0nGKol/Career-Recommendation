# My Career Prediction Model 🚀

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Python 3.x](https://img.shields.io/badge/python-3.x-blue.svg)](https://www.python.org/downloads/)

This project is my final work, where I've built a machine learning model to help predict potential IT career paths based on a person's skills.

## Why This Matters (Societal & Industrial Impact)

I truly believe this project can make a big difference for both individuals and businesses. From a personal side, imagine being a student or someone looking for a new job. It's often really tough figuring out what career path truly fits best. My model can give people clear, data-backed ideas about careers that match their skills. This means they can make smarter choices, feel less stressed about their future, and hopefully find jobs where their talents can really shine.

For businesses, especially HR teams, this model can be super helpful for finding the right talent. It can assist them in quickly identifying candidates whose skills are a perfect match for specific roles. It can also help companies understand what skills their team might be missing, which is great for planning future growth.

## The Problem I'm Trying to Solve

Alright, so picture this: You're an IT student in college, right? You're learning a ton of cool skills – maybe coding in Python, understanding databases, or diving into AI. But when it comes to actually picking a specific career path after graduation, the job market can feel like this huge, confusing maze. You might have awesome skills, but figuring out where exactly they fit in, whether it's software development, data science, cybersecurity, or something else entirely, can be a real head-scratcher.

On the flip side, companies are out there desperately looking for IT talent, but it's tough for them to easily spot students with *just* the right mix of skills for their specific roles. It takes a lot of time and sometimes they don't find the perfect match.

So, I built this project to create a clear way to help IT students like you predict which careers are a great match for the skills you're gaining, and help companies easily find the skilled IT people they need.

## My Big Questions (Research Questions)

* **What kind of job can someone expect** if they have a certain mix of technical and soft skills?
* **Why is predicting careers from skills even important?** For me, it's about helping people find their way and helping businesses find talent faster. It makes the whole job-matching process more efficient.
* **How did I actually make this prediction happen?** I used machine learning models to connect all those different skills to different job types.

## What I've Achieved (My Contributions)

With this project, I've put together a machine learning system that helps predict careers. Here are some of the cool things I've contributed:

* I cleaned and prepared a dataset of skills and associated careers, making it ready for machine learning tasks.
* I built and tested two different classification models (Naive Bayes and Logistic Regression) for predicting careers.
* I can even show you how to type in a bunch of skills, and the model will tell you what career might be a good fit.
* I also dug into the data to see which careers were most common and what skills popped up most often.

## My Data

* **Where did I get the data?** It's a "Secondary Dataset," meaning I didn't collect it myself, but found it already available.
* **What's in it?** The dataset is called `Career Dataset.xlsx`. It's pretty simple, with just two columns:
    * `Career`: This is the job title I'm trying to predict.
    * `Skill`: This column lists different skills for each career, separated by commas.

* **A quick look at the numbers:**
    * It has 4076 rows (think of them as examples) and 2 columns.
    * The column names are exactly `Career` and `Skill`.
    * Good news: There are no missing values!
    * I found 6 different career categories in total.
    * Some of the careers I saw were: "Software Development and Engineering", "Development", "Data Science", "Artificial Intelligence", "Security", and "User Experience (UX) and User Interface (UI) Design".
* From what I saw, "Development" was a very common career, and "Web Development" was a super frequent skill listed.

## How I Built It (My Methodology)

I followed a few main steps to get this model working:

1.  **Loading the Data:** First, I just loaded my `Career Dataset.xlsx` file into a Pandas DataFrame in Python.
2.  **Checking Out the Data:** I took a good look at the data to understand its format, make sure nothing was missing, and see how careers and skills were spread out.
3.  **Turning Text into Numbers (Text Vectorization):** The `Skill` column has text like "Web Development, Mobile App Development." To make my machine learning models understand this, I used something called `CountVectorizer`. It basically looks at all the skills, breaks them down (using `, ` to separate them), and then counts how many times each skill appears for each career. This turns all that text into a big table of numbers.
4.  **Encoding the Careers:** The `Career` column also has text names. Machine learning models prefer numbers, so I used `LabelEncoder` to turn each career name into a unique number.
5.  **Splitting the Data:** I then split my data into two parts: a "training set" (80% of the data) for the model to learn from, and a "testing set" (20% of the data) to see how well it performs on new, unseen data. I set `random_state` to 42 so that my split is always the same if I run the code again.

## Choosing My Machine Learning Models

I picked two different machine learning models for this job:

1.  **Multinomial Naive Bayes (`MultinomialNB`):**
    * **Why I chose it:** This model is really good for text-based problems where you're counting words or features, which is exactly what my `CountVectorizer` does. It's relatively simple and fast, and it often does a surprisingly good job with text classification.

2.  **Logistic Regression (`LogisticRegression`):**
    * **Why I chose it:** Logistic Regression is a solid, reliable choice for classification. Even though "regression" is in its name, it's used for predicting categories. It's pretty easy to understand how it makes decisions, and it generally works well when you have a clear relationship between your skills and the careers.

## How I Checked My Work (Evaluation Technique)

To see how well my models were doing, I looked at a few key things:

* **Accuracy Score:** This is the most straightforward one – it tells me the percentage of times my model got the career prediction right.
* **Classification Report:** This gives me a more detailed breakdown. It shows me "precision" (how many of its positive predictions were actually correct), "recall" (how many of the actual positive cases it caught), and "F1-score" (a balance between precision and recall) for each individual career type. This is important because sometimes a model might be good at predicting some careers but not others.

## My Results (Accuracy)

Here's how accurate my models were when I tested them:

* **Naive Bayes Model:** It hit an accuracy of **90.07%**. Not bad!
* **Logistic Regression Model:** This one did a little better, reaching **92.40%** accuracy.

So, based on these numbers, the Logistic Regression model performed slightly better on my dataset.

## The "Knob" I Adjusted (Hyperparameter)

For my Logistic Regression model, there was one specific "knob" I explicitly adjusted, called `max_iter`:

* **`LogisticRegression(max_iter=1000)`:** This just tells the model how many times it should try to "learn" and refine its predictions. I set it to 1000 iterations to make sure it had enough chances to find the best possible fit for the data. I didn't do any fancy automatic tuning for this, but making sure it had enough iterations was important.

## Installation

To get this project up and running on your local machine, follow these steps:

1.  **Clone the repository:**
    ```bash
    git clone [https://github.com/M0nGKol/Career-Recommendation.git](https://github.com/M0nGKol/Career-Recommendation.git)
    cd Career-Recommendation
    ```
2.  **Make sure you have the dataset:**
    Place the `Career Dataset.xlsx` file inside a `data/` folder within the cloned repository. So, the path should look like `Career-Recommendation/data/Career Dataset.xlsx`.
3.  **Create a virtual environment (recommended):**
    ```bash
    python -m venv venv
    source venv/bin/activate # On Windows: `venv\Scripts\activate`
    ```
4.  **Install dependencies:**
    ```bash
    pip install pandas numpy matplotlib seaborn scikit-learn openpyxl
    ```
    *(Alternatively, you can create a `requirements.txt` file with these libraries listed and run `pip install -r requirements.txt`)*

## Usage

You can run the Jupyter Notebook (`CareerPredicts.ipynb`) to see the full analysis and prediction process. If you want to make a quick prediction, you can extract the relevant code from the notebook into a Python script and run it.

Here's a simple example of how to use the trained model for prediction (assuming the model is trained as in the notebook):
