======
Alerts
======

In the *Referrals* application, it is possible to post a message, also referred to as an *alert*, at
the top of the dashboard to share important information with users. These alerts appear as a thin
semi-transparent banner, with the word :guilabel:`New!` appearing on the far left. The text for the
alert is in the center of the banner, and on the far right side is an :guilabel:`X`.

Alerts appear on the main dashboard for the specified time configured on the individual alert. If a
user does not wish to see a specific alert again, click the :guilabel:`X` in the far right side of
the alert. This removes the alert from the dashboard and will not appear again, even when opening
the *Referrals* application for the first time in a new session.

.. image:: alerts/alerts.png
   :align: center
   :alt: Two alert banners appear above the user's photo.

Create an alert
===============

Only users with :guilabel:`Administrator` rights for the *Recruitment* application can create
alerts. To add a new alert, navigate to the :menuselection:`Referrals application --> Configuration
--> Alerts`.

Click :guilabel:`Create` and a blank alert form loads. Enter the following information on the form:

- :guilabel:`Date From`: the date the alert starts. On this date, the alert will be visible on the
  dashboard.
- :guilabel:`Date To`: the date the alert ends. After this date, the alert will be hidden from view.
- :guilabel:`Company`: the current company populates this field by default. To modify the company
  the alert should be displayed for, select the company from the drop-down menu. If this field
  remains blank, the alert is visible to everyone with access to the *Referrals* application. If a
  company is specified, only user's within that company (who also have access to the *Referrals*
  application) will see the alert. This field only appears when in a multi-company database.
- :guilabel:`Alert`: enter the text for the alert. This message appears inside the alert banner on
  the main dashboard.
- :guilabel:`On Click`: there are three options for the alert. Click the radio button next to the
  desired selection. The options are:

  - :guilabel:`Not Clickable`: the alert only displays text, there is no link to click.
  - :guilabel:`Go to All Jobs`: the alert contains a link that when clicked, navigates to the
    website with all the currently posted job positions.
  - :guilabel:`Specify URL`: the alert contains a link to a specific URL, that when clicked,
    navigates to that URL. When selected, a :guilabel:`URL` field appears below the :guilabel:`On
    Click` section. Enter the URL in the field.

.. image:: alerts/alert-form.png
   :align: center
   :alt: An alert form completely filled in with all selections entered.
