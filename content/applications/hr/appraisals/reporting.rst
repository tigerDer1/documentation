=========
Reporting
=========

In Odoo's *Appraisals* app, two metrics are tracked as appraisals are completed: an :ref:`appraisal
analysis <appraisals/analysis>`, and a :ref:`skills evolution <appraisals/skills-report>`.

.. _appraisals/analysis:

Appraisal analysis
------------------

To access the *Appraisal Analysis* report, navigate to :menuselection:`Appraisals application -->
Reporting --> Appraisal Analysis`. This displays a report of all the appraisals in the database,
highlighted in different colors to represent their status.

Appraisals in yellow are completed, appraisals in orange are in-progress (the appraisal is
confirmed, but not completed), and appraisals in gray are scheduled (according to the
:ref:`appraisals/appraisal-plan`), but have not been confirmed yet.

The report displays the whole current year, by default, grouped by department.

To change the calendar view presented, change the date settings in the top-left of the report. The
options to display are :guilabel:`Day`, :guilabel:`Week`, :guilabel:`Month`, and :guilabel:`Year`.
Use the arrows to move forward or backward in time.

At any point, click the :guilabel:`Today` button to present the calendar to include today's date in
the view.

The report can have other filters and groupings set in the :guilabel:`Search...` bar at the top.

.. image:: reporting/analysis.png
   :align: center
   :alt: A report showing all the appraisals for the Appraisal Analysis report.

.. _appraisals/skills-report:

Skills evolution
----------------

To access the *Skills Evolution* report, navigate to :menuselection:`Appraisals application -->
Reporting --> Skills Evolution`. This displays a report of all skills, grouped by employee.

All the lines of the report are collapsed, by default. To view the details of a line, click on a
line to expand the data.

Each skill has the following information listed:

- :guilabel:`Employee`: name of the employee.
- :guilabel:`Skill Type`: the category the skill falls under.
- :guilabel:`Skill`: the specific, individual skill.
- :guilabel:`Previous Skill Level`: the level the employee had previously achieved for the skill.
- :guilabel:`Previous Skill Progress`: the previous percentage of competency achieved for the skill
  (based on the :guilabel:`Skill Level`).
- :guilabel:`Current Skill Level`: the current level the employee has achieved for the skill.
- :guilabel:`Current Skill Progress`: the current percentage of competency achieved for the skill.
- :guilabel:`Justification`: any notes entered on the skill explaining the progress.

.. image:: reporting/skills-report.png
   :align: center
   :alt: A report showing all the skills grouped by employee.
