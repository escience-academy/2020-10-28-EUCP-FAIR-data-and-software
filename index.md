---
layout: workshop
venue: "Netherlands eScience Center"
address: "https://fixme.join.link"  # TODO: add zoomlink here
country: "NL"
language: "EN"
latitude: "52"
longitude: "4"
humandate: "Oct 28, Nov 4, Nov 11, 2020"
humantime: "9:30 - 16:00 CET"
startdate: 2020-10-28
enddate: 2020-11-11
instructor: ["Peter Kalverla", "Jaro Camphuijsen", "Johan Hidding"]
helper: ["Sarah Alidoost", "Stef Smeets", "Niels Drost", "Bouwe Andela", "Faruk Diblen"]
email: ["p.kalverla@esciencecenter.nl","f.alidoost@esciencecenter.nl"]
collaborative_notes: FIXME
eventbrite:
---


{% comment %}
Check DC curriculum
{% endcomment %}

{% if site.carpentry == "dc" %}
{% unless site.curriculum == "dc-ecology" or site.curriculum == "dc-genomics" or site.curriculum == "dc-socsci" or site.curriculum == "dc-geospatial" %}
<div class="alert alert-warning">
It looks like you are setting up a website for a Data Carpentry curriculum but you haven't specified the curriculum type in the <code>_config.yml</code> file (current value in <code>_config.yml</code>: "<strong>{{ site.curriculum }}</strong>", possible values: <code>dc-ecology</code>, <code>dc-genomics</code>, <code>dc-socsci</code>, or <code>dc-geospatial</code>). After editing this file, you need to run <code>make serve</code> again to see the changes reflected.
</div>
{% endunless %}
{% endif %}

{% comment %}
Check SWC curriculum
{% endcomment %}

{% if site.carpentry == "swc" %}
{% unless site.curriculum == "swc-inflammation" or site.curriculum == "swc-gapminder" %}
<div class="alert alert-warning">
It looks like you are setting up a website for a Software Carpentry curriculum but you haven't specified the curriculum type in the <code>_config.yml</code> file (current value in <code>_config.yml</code>: "<strong>{{ site.curriculum }}</strong>", possible values: <code>swc-inflammation</code>, or <code>swc-gapminder</code>). After editing this file, you need to run <code>make serve</code> again to see the changes reflected.
</div>
{% endunless %}
{% endif %}

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
  If you need a password or other information to access the training,
  the instructor will pass it on to you before the workshop.
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
  <strong>Requirements:</strong> Participants must bring a laptop with a
  Mac, Linux, or Windows operating system (not a tablet, Chromebook, etc.) that they have administrative privileges on. They should have a few specific software packages installed (listed <a href="#setup">below</a>).
</p>

{% comment %}
ACCESSIBILITY

Modify the block below if there are any barriers to accessibility or
special instructions.
{% endcomment %}
<p id="accessibility">
  <strong>Accessibility:</strong>
{% if online == "false" %}
  We are committed to making this workshop
  accessible to everybody. The workshop organizers have checked that:
</p>
<ul>
  <li>The room is wheelchair / scooter accessible.</li>
  <li>Accessible restrooms are available.</li>
</ul>
<p>
  Materials will be provided in advance of the workshop and
  large-print handouts are available if needed by notifying the
  organizers in advance.  If we can help making learning easier for
  you (e.g. sign-language interpreters, lactation facilities) please
  get in touch (using contact details below) and we will
  attempt to provide them.
{% else %}
  We are dedicated to providing a positive and accessible learning environment for all. Please
  notify the instructors in advance of the workshop if you require any accommodations or if there is
  anything we can do to make this workshop more accessible to you.
</p>
{% endif %}

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
We will use this <a href="{{ page.collaborative_notes }}">collaborative drive</a> with one document for each workshop day for chatting, taking notes, and sharing URLs and bits of code. During the workshop you may make your own document in this drive to work on the exercises and/or your own use cases.
</p>
<hr/>
{% endif %}


{% comment %}
SURVEYS - DO NOT EDIT SURVEY LINKS
{% endcomment %}
<h2 id="surveys">Survey</h2>
<p>Please provide feedback by completing <a href="{{ site.post_survey }}{{ site.github.project_title }}">this survey</a> after the workshop.</p>

<hr/>


{% comment %}
SCHEDULE

Show the workshop's schedule.  Edit the items and times in the table
to match your plans.  You may also want to change 'Day 1' and 'Day
2' to be actual dates or days of the week.
{% endcomment %}
<h2 id="schedule">Schedule</h2>

<div class="row">
    <div class="col-md-4">
      <h3>FAIR (Climate) data (Oct 28)</h3>
      <table class="table table-striped"><tbody>
        <tr> <td>09:00</td>  <td>Connect and get ready</td> </tr>
        <tr> <td>09:30</td>  <td>Welcome and general information</td> </tr>
        <tr> <td>09:45</td>  <td>Introduction</td> </tr>
        <tr> <td>10:00</td>  <td>Data documentation</td> </tr>
        <tr> <td>10:15</td>  <td>Metadata</td> </tr>
        <tr> <td>10:30</td>  <td>Coffee break</td> </tr>
        <tr> <td>10:45</td>  <td>File formats</td> </tr>
        <tr> <td>11:00</td>  <td>Data access</td> </tr>
        <tr> <td>11:15</td>  <td>Persistent identifiers</td> </tr>
        <tr> <td>11:30</td>  <td>Data Licenses</td> </tr>
        <tr> <td>11:45</td>  <td>Conclusion</td> </tr>
        <tr> <td>12:00</td>  <td>Lunch break</td> </tr>
        <tr> <td>13:00</td>  <td>Group discussions and work together on own use cases in breakout rooms</td> </tr>
        <tr> <td>15:45</td>  <td>Wrap-up (plenary)</td> </tr>
        <tr> <td>16:00</td>  <td>End</td> </tr>
      </tbody></table>
    </div>
    <div class="col-md-4">
      <h3>FAIR software (Nov 4)</h3>
      <table class="table table-striped"><tbody>
        <tr> <td>09:00</td>  <td>Connect and get ready</td> </tr>
        <tr> <td>09:30</td>  <td>Welcome and general information</td> </tr>
        <tr> <td>09:45</td>  <td>Introduction to 5 FAIR software recommendations</td> </tr>
        <tr> <td>10:00</td>  <td>Use a publicly accessible repository with version control</td> </tr>
        <tr> <td>10:40</td>  <td>Coffee break</td> </tr>
        <tr> <td>10:55</td>  <td>Add a license</td> </tr>
        <tr> <td>11:25</td>  <td>Register your code in a community registry</td> </tr>
        <tr> <td>11:55</td>  <td>Break</td> </tr>
        <tr> <td>12:10</td>  <td>Enable citation of the software</td> </tr>
        <tr> <td>12:40</td>  <td>Use a software quality checklist</td> </tr>
        <tr> <td>13:10</td>  <td>Lunch break</td> </tr>
        <tr> <td>14:00</td>  <td>Group discussions and working together on own use cases in breakout rooms</td> </tr>
        <tr> <td>15:45</td>  <td>Wrap up (plenary)</td> </tr>
        <tr> <td>16:00</td>  <td>End</td> </tr>
      </tbody></table>
    </div>
    <div class="col-md-4">
      <h3>ESMValTool (Nov 11)</h3>
      <table class="table table-striped"><tbody>
        <tr> <td>09:00</td>  <td>Connect and get ready</td> </tr>
        <tr> <td>09:30</td>  <td>Welcome and general information</td> </tr>
        <tr> <td>09:45</td>  <td>Installation</td> </tr>
        <tr> <td>10:00</td>  <td>Introduction to ESMValTool</td> </tr>
        <tr> <td>10:15</td>  <td>Configuration</td> </tr>
        <tr> <td>10:30</td>  <td>Coffee break</td> </tr>
        <tr> <td>10:45</td>  <td>Running a recipe</td> </tr>
        <tr> <td>11:30</td>  <td>Coffee break</td> </tr>
        <tr> <td>11:45</td>  <td>Making your own recipe</td> </tr>
        <tr> <td>12:30</td>  <td>Lunch break</td> </tr>
        <tr> <td>13:30</td>  <td>Group discussions and work together on own use cases in breakout rooms</td> </tr>
        <tr> <td>15:45</td>  <td>Wrap-up (plenary)</td> </tr>
        <tr> <td>16:00</td>  <td>End</td> </tr>
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

<h2 id="setup">Setup</h2>

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
