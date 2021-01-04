IGB TRACKING SCRIPTS
====================

The IGB Tracker can be used with GTM. To do this, you need to select the IGB Tracker template in the Community Template Gallery <Link toevoegen> and add it to your workspace.

Once added, you can configure the template, which has the following options:

- Trigger: Should a start or stop of an application be triggered?
- Tracking method: The tracker needs a reference to keep track of different applications at once. A unique reference should be unique per vacancy. You should not use the same unique reference for multiple vacancies. Using the tracking method you can configure how the reference can be determined.

Textual value
-------------
This can be either a hardcoded value or configured using a variable, for example a DOM-element variable which fetches the reference from the HTML of the page.

Page URL or Referrer URL
------------------------
The reference is based on the URL the user is currently on (Page URL), or the page the user was previously on (Referrer URL). In the case of Referrer URL, this must be available in the javascript property `document.referrer`. If your site does not send an HTTP_REFERER value, you cannot use this method.

Next, you need to choose a tracking source. This is either _Query string_ or _Page path_.
If your URL looks like this: http://domain.com/vacancy/apply/thankyou?vacancyID=12345 you need to choose _Query string_ and enter vacancyID in the Query parameter field.

When you have a URL like http://domain.com/vacancy/apply/12345-interesting-job-title.html you need to choose _Page path_, and enter a relevant Regular Expression. For the example URL the regular expression should be `/apply\/(\d+)-/`.

To use the IGB Tracker template correctly, you need to create at least two triggers in GTM, one which starts the tracker and one which stops the tracker when an application is finished.
