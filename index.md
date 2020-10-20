---
layout: workshop
venue: "Netherlands eScience Center"
address: "https://us02web.zoom.us/j/82865220880"
country: "NL"
language: "EN"
latitude: "52"
longitude: "4"
humandate: "Oct 28, Nov 4, Nov 11, 2020"
humantime: "9:15 - 16:00 CET"
startdate: 2020-10-28
enddate: 2020-11-11
instructor: ["Peter Kalverla", "Jaro Camphuijsen", "Johan Hidding"]
helper: ["Sarah Alidoost", "Stef Smeets", "Niels Drost", "Bouwe Andela", "Faruk Diblen", "Ou Ku"]
email: ["p.kalverla@esciencecenter.nl","f.alidoost@esciencecenter.nl"]
collaborative_notes: https://nlesc.sharepoint.com/:f:/s/team-beta/EgtUYOWdlfFNsmgpJxAKqiwBmBLuoqw0wc3_69SLq0gtpQ
---

<h2 id="general">General Information</h2>

Many researchers, institutes, governments and other funding bodies nowadays
subscribe to a vision on open science. The general premise is that scholarly
research can be more effective and transparent if everyone shares their data,
methods, codes, tools, analyses and results in a structured way, so that they
will be reusable and/or reproducible with minimal human effort.

This workshop aims to provide an overview of, and facilitate discussion on,
relevant developments in this landscape of open science, specifically focusing
on the field of climate sciences. In three sessions, we will cover an
interpretation of the FAIR data principles in the context of climate sciences,
the basic principles for sharing software in a FAIR manner, and the use of
ESMValTool to streamline and homogeneize scientific workflows.

**Who**: This workshop is organized by the Netherlands eScience Center for
project partners in the EUCP (European Climate Prediction) Horizon 2020 project.

{% assign begin_address = page.address | slice: 0, 4 | downcase  %}
{% if page.address == "online" %}
{% assign online = "true_private" %}
{% elsif begin_address contains "http" %}
{% assign online = "true_public" %}
{% else %}
{% assign online = "false" %}
{% endif %}
{% if page.latitude and page.longitude and online == "false" %}
<p id="where">
  <strong>Where:</strong>
  {{page.address}}.
  Get directions with
  <a href="//www.openstreetmap.org/?mlat={{page.latitude}}&mlon={{page.longitude}}&zoom=16">OpenStreetMap</a>
  or
  <a href="//maps.google.com/maps?q={{page.latitude}},{{page.longitude}}">Google Maps</a>.
</p>
{% elsif online == "true_public" %}
<p id="where">
  <strong>Where:</strong>
  online at <a href="{{page.address}}">{{page.address}}</a>.
  You will need a passcode to enter to zoom meeting, which will be send to you by email.
</p>
{% elsif online == "true_private" %}
<p id="where">
  <strong>Where:</strong> This training will take place online.
  The instructors will provide you with the information you will need to connect to this meeting.
</p>
{% endif %}

{% comment %}
DATE

This block displays the date and links to Google Calendar.
{% endcomment %}
{% if page.humandate %}
<p id="when">
  <strong>When:</strong>
  {{page.humandate}}.
  {% include workshop_calendar.html %}
</p>
{% endif %}

{% comment %}
SPECIAL REQUIREMENTS

Modify the block below if there are any special requirements.
{% endcomment %}
<p id="requirements">
  <strong>Requirements:</strong> Please refer to the <a href="#setup">setup instructions below</a> about videoconferencing, github account, and the required setup for ESMValTool.
</p>

{% comment %}
CONTACT EMAIL ADDRESS

Display the contact email address set in the configuration file.
{% endcomment %}
<p id="contact">
  <strong>Contact:</strong>
  Please email
  {% if page.email %}
  {% for email in page.email %}
  {% if forloop.last and page.email.size > 1 %}
  or
  {% else %}
  {% unless forloop.first %}
  ,
  {% endunless %}
  {% endif %}
  <a href='mailto:{{email}}'>{{email}}</a>
  {% endfor %}
  {% else %}
  to-be-announced
  {% endif %}
  for more information.
</p>

<hr/>

{% comment%}
CODE OF CONDUCT
{% endcomment %}
<h2 id="code-of-conduct">Code of Conduct</h2>

<p>
Participants are expected to follow those guidelines:
  <ul>
    <li>Use welcoming and inclusive language</li>
    <li>Be respectful of different viewpoints and experiences</li>
    <li>Gracefully accept constructive criticism</li>
    <li>Focus on what is best for the community</li>
    <li>Show courtesy and respect towards other community members</li>
  </ul>
</p>

{% comment %}
Collaborative Notes

If you want to use an Etherpad, go to

https://pad.carpentries.org/YYYY-MM-DD-site

where 'YYYY-MM-DD-site' is the identifier for your workshop,
e.g., '2015-06-10-esu'.

Note we also have a CodiMD (the open-source version of HackMD)
available at https://codimd.carpentries.org
{% endcomment %}
{% if page.collaborative_notes %}
<h2 id="collaborative_notes">Collaborative Notes</h2>

<p>
We will use this <a href="{{ page.collaborative_notes }}">collaborative drive</a> with one document for each workshop day for taking notes and sharing URLs and bits of code. During the workshop you may make your own document in this drive to work on the exercises and/or your own use cases. Before the workshop, you will receive an invitation via email that will give you access to this folder.
</p>
<hr/>
{% endif %}


{% comment %}
SURVEYS - DO NOT EDIT SURVEY LINKS
{% endcomment %}
<h2 id="surveys">Surveys</h2>
In order to improve our teaching material, we ask you to complete a short survey after each lesson.
Here are the links for each of the surveys:

- [FAIR (Climate) data survey](https://www.surveymonkey.com/r/BGFQB55)
- [FAIR software survey](https://www.surveymonkey.com/r/PNTZPYJ)
- [ESMValTool survey](https://www.surveymonkey.com/r/P3DWCFF)

<hr/>


{% comment %}
SCHEDULE

Show the workshop's schedule.  Edit the items and times in the table
to match your plans.  You may also want to change 'Day 1' and 'Day
2' to be actual dates or days of the week.
{% endcomment %}
<h2 id="schedule">Schedule</h2>
<p>This is a preliminary schedule. Small changes might still be made by the instructors.</p>

<div class="row">
    <div class="col-md-4">
      <h3>FAIR (Climate) data (Oct 28)</h3>
      <table class="table table-striped"><tbody>
        <tr> <td>09:15</td>  <td>Connect and get ready</td> </tr>
        <tr style="font-weight:bold"> <td>09:30</td>  <td>Welcome and general information</td> </tr>
        <tr> <td>09:45</td>  <td>Introduction</td> </tr>
        <tr> <td>10:00</td>  <td>Data documentation and metadata</td> </tr>
        <tr style="font-weight:bold"> <td>10:45</td>  <td>Coffee break</td> </tr>
        <tr> <td>11:00</td>  <td>File formats and data access</td> </tr>
        <tr style="font-weight:bold"> <td>11:45</td>  <td>Coffee break</td> </tr>
        <tr> <td>12:00</td>  <td>Persistent identifiers and data licences</td> </tr>
        <tr style="font-weight:bold"> <td>13:00</td>  <td>Lunch break</td> </tr>
        <tr> <td>14:15</td>  <td>Group discussions and work together on own use cases in breakout rooms</td> </tr>
        <tr> <td>15:45</td>  <td>Wrap-up (plenary)</td> </tr>
        <tr style="font-weight:bold"> <td>16:00</td>  <td>End</td> </tr>
        <tr> <td> </td>  <td> Please take a minute to complete the <a href="https://www.surveymonkey.com/r/BGFQB55">survey</a></td> </tr>
      </tbody></table>
    </div>
    <div class="col-md-4">
      <h3>FAIR software (Nov 4)</h3>
      <table class="table table-striped"><tbody>
        <tr> <td>09:15</td>  <td>Connect and get ready</td> </tr>
        <tr style="font-weight:bold"> <td>09:30</td>  <td>Welcome and general information</td> </tr>
        <tr> <td>09:45</td>  <td>Introduction to 5 FAIR software recommendations</td> </tr>
        <tr> <td>10:00</td>  <td>Use a publicly accessible repository with version control</td> </tr>
        <tr style="font-weight:bold"> <td>10:40</td>  <td>Coffee break</td> </tr>
        <tr> <td>10:55</td>  <td>Add a license</td> </tr>
        <tr> <td>11:25</td>  <td>Register your code in a community registry</td> </tr>
        <tr style="font-weight:bold"> <td>11:55</td>  <td>Coffee break</td> </tr>
        <tr> <td>12:10</td>  <td>Enable citation of the software</td> </tr>
        <tr> <td>12:40</td>  <td>Use a software quality checklist</td> </tr>
        <tr style="font-weight:bold"> <td>13:10</td>  <td>Lunch break</td> </tr>
        <tr> <td>14:00</td>  <td>Group discussions and working together on own use cases in breakout rooms</td> </tr>
        <tr> <td>15:45</td>  <td>Wrap up (plenary)</td> </tr>
        <tr style="font-weight:bold"> <td>16:00</td>  <td>End</td> </tr>
        <tr> <td> </td>  <td> Please take a minute to complete the <a href="https://www.surveymonkey.com/r/PNTZPYJ">survey</a></td> </tr>
      </tbody></table>
    </div>
    <div class="col-md-4">
      <h3>ESMValTool (Nov 11)</h3>
      <table class="table table-striped"><tbody>
        <tr> <td>09:15</td>  <td>Connect and get ready</td> </tr>
        <tr style="font-weight:bold"> <td>09:30</td>  <td>Welcome and general information</td> </tr>
        <tr> <td>09:45</td>  <td>Introduction, installation and configuration</td> </tr>
        <tr  style="font-weight:bold"> <td>10:30</td>  <td>Coffee break</td> </tr>
        <tr> <td>10:45</td>  <td>Running a recipe</td> </tr>
        <tr  style="font-weight:bold"> <td>11:30</td>  <td>Coffee break</td> </tr>
        <tr> <td>11:45</td>  <td>Making your own recipe</td> </tr>
        <tr  style="font-weight:bold"> <td>13:00</td>  <td>Lunch break</td> </tr>
        <tr> <td>14:00</td>  <td>Group discussions and work together on own use cases in breakout rooms</td> </tr>
        <tr> <td>15:45</td>  <td>Wrap-up (plenary)</td> </tr>
        <tr  style="font-weight:bold"> <td>16:00</td>  <td>End</td> </tr>
        <tr> <td> </td>  <td> Please take a minute to complete the <a href="https://www.surveymonkey.com/r/P3DWCFF">survey</a></td> </tr>
      </tbody></table>
    </div>
  </div>

<hr/>

{% comment %}
SETUP

Delete irrelevant sections from the setup instructions.  Each
section is inside a 'div' without any classes to make the beginning
and end easier to find.

This is the other place where people frequently make mistakes, so
please preview your site before committing, and make sure to run
'tools/check' as well.
{% endcomment %}

<h2 id="setup">Preparation before the workshop</h2>

<div id="usecase">
  <h3>Think about use cases</h3>
  <p>
  To get the most out of this workshop, please think beforehand about which datasets, software tools, data analysis notebooks, etc. you would like to make (more) FAIR. There will be exercises for which you can use your own use case, and in the afternoons there is time to discuss and work on your own use cases as well.
  </p>

<p>
  To participate in this
  {% if site.carpentry == "swc" %}
  Software Carpentry
  {% elsif site.carpentry == "dc" %}
  Data Carpentry
  {% elsif site.carpentry == "lc" %}
  Library Carpentry
  {% endif %}
  workshop,
  you will need access to the software described below.
  In addition, you will need an up-to-date web browser.
</p>
<p>
  We maintain a list of common issues that occur during installation as a reference for instructors
  that may be useful on the
  <a href = "{{site.swc_github}}/workshop-template/wiki/Configuration-Problems-and-Solutions">Configuration Problems and Solutions wiki page</a>.
</p>

{% comment %}
For online workshops, the section below provides:
- installation instructions for the Zoom client
- recommendations for setting up Learners' workspace so they can follow along
  the instructions and the videoconferencing

If you do not use Zoom for your online workshop, edit the file
`_includes/install_instructions/videoconferencing.html`
to include the relevant installation instrucctions.
{% endcomment %}
{% if online != "false" %}
{% include install_instructions/videoconferencing.html %}
{% endif %}

{% comment %}
These are the installation instructions for the tools used
during the workshop.
{% endcomment %}

{% if site.carpentry == "swc" %}
{% include swc/setup.html %}
{% elsif site.carpentry == "dc" %}
{% include dc/setup.html %}
{% elsif site.carpentry == "lc" %}
{% include lc/setup.html %}
{% endif %}

<div id="github">
  <h3>GitHub</h3>
  <p>
  On the second workshop day we will be working with git and GitHub. You will
  need a GitHub account and some basic knowledge about GitHub and version
  control. If you have never used it before, please have a look at GitHub's
  <a href="https://guides.github.com/activities/hello-world/">Hello World tutorial</a> before the workshop.
  </p>

<div id="esmvaltool">
  <h3>ESMValTool setup instructions</h3>
  <p>
  For the ESMValTool workshop it is highly recommended to use a Linux machine on
  which you have admin priviliges. Mac or Windows should also work, but for
  Windows you will need the Windows Subsystem for Linux (WSL). Please refer to
  Microsofts <a
  href="https://docs.microsoft.com/en-us/windows/wsl/install-win10">installation
  instructions</a>.
  </p>
  <p>
  Please make sure to download the two datasets that we'll be using before the
  workshop day (<a
  href="http://esgf3.dkrz.de/thredds/fileServer/cmip6/CMIP/BCC/BCC-ESM1/historical/r1i1p1f1/Amon/tas/gn/v20181214/tas_Amon_BCC-ESM1_historical_r1i1p1f1_gn_185001-201412.nc">dataset1</a>,
  <a
  href="http://esgf2.dkrz.de/thredds/fileServer/lta_dataroot/cmip5/output1/CCCma/CanESM2/historical/mon/atmos/Amon/r1i1p1/v20120718/tas/tas_Amon_CanESM2_historical_r1i1p1_185001-200512.nc">dataset2</a>)
  and store them in a folder called "/esmvaltool_tutorial/data/".
  </p>
