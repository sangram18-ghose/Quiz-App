Django quiz app
===============
[![Build Status](https://travis-ci.org/tomwalker/django_quiz.svg?branch=master)](https://travis-ci.org/tomwalker/django_quiz)

This is a configurable quiz app for Django.

I use it to run a few medical revision websites. Here is an [example website](http://www.revisemrcp.com/)

My websites have used twitter bootstrap for the front end and I have tried to strip out anything from
the template files that are dependant on bootstrap.

![Questions](http://i.imgur.com/VRYx3OV.png "Question picture hosted by Imgur")


Current features
----------------
Features of each quiz:
* Question order randomisation
* Storing of quiz results under each user
* Previous quiz scores can be viewed on category page
* Correct answers can be shown after each question or all at once at the end
* Logged in users can return to an incomplete quiz to finish it and non-logged in users can complete a quiz if their session persists
* The quiz can be limited to one attempt per user
* Questions can be given a category and subcategory
* Success rate for each category can be monitored on a progress page
* Explanation for each question result can be given
* Pass marks can be set
* Multiple choice question type
* True/False question type
* Essay question type
* Display an image alongside the question
* Custom message displayed for those that pass or fail a quiz
* Custom permission (view_sittings) added, allowing users with that permission to view quiz results from users
* A marking page which lists completed quizzes, can be filtered by quiz or user, and is used to mark essay questions
* After selecting a larger pool of questions, a quiz can be set to show a random subset rather than all within the pool
* Start and end times for sitting exams are recorded
* i18n support
* Russian and Italian language translation




![Result page](http://i.imgur.com/UJtRZxo.png "Result picture hosted by Imgur")

Requirements
------------
django-model-utils

Pillow

Tests are included and pass for Django versions 1.5, 1.6, 1.7 and 1.8, running with Python 2.7, 3.3 and 3.4

Installation
------------
Clone the repo with `git clone https://github.com/tomwalker/django_quiz.git`.

Run `pip install -r requirements.txt`.
Run `python setup.py install`

Add `'quiz', 'multichoice', 'true_false', 'essay'` to your `INSTALLED_APPS` setting.

    INSTALLED_APPS = (
        ...
        'quiz',
        'multichoice',
        'true_false',
	'essay',
        ...
    )

Add the following to your projects `urls.py` file, substituting `q` for whatever you want the quiz base url to be.

    urlpatterns = patterns('',
        ...
        url(r'^q/', include('quiz.urls')),
    	...
    )
