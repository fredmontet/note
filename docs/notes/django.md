Django Cheatsheet
=================

## Useful Documentation

- Topics : https://docs.djangoproject.com/en/2.0/topics/
- Search the Django documentation : https://docs.djangoproject.com/en/2.0/search/
- Index : https://docs.djangoproject.com/en/2.0/genindex/
- How-to : https://docs.djangoproject.com/en/2.0/howto/

## Using the Console

Change directory to go at the root of the project, where manage.py is and type the following command

    python3 manage.py shell

## Templating

They go in the following folder

    <project_name>/<app_name>/template/<app_name>/...

## Static files

They go in the following folder

    <project_name>/<app_name>/static/<app_name>/...

## Unit Test

Don't worry if tests:
- becomes messy
- are redundant

Rules are:
- A separate TestClass for each model or view
- A separate test method for each set of conditions you want to test
- A test method name that describe its function

### Creating Tests

To create a test, you must subclass the TestCase class and start its method witht the `test` prefix. e.g.

    class QuestionModelTests(TestCase):

        def test_was_published_recently_with_future_question(self):
        """
         was_published_recently() returns False for questions whose pub_date
         is in the future.
         """
        time = timezone.now() + datetime.timedelta(days=30)
        future_question = Question(pub_date=time)
        self.assertIs(future_question.was_published_recently(), False)

### Running Tests

To test the complete django application, launch the following command

    python3 manage.py test

If you want to test only one module

    python3 manage.py test <module_name>

### Testing the views

Django provides a test client for the views, it can be imported this way

    from django.test import Client

and used like

    client = Client()
    response = client.get('/')
    response.status_code  # will return 404 for instance

Also, to make some in browser testing, Django has a `LiveServerTestCase` to ease the integration of tools such as Selenium.

