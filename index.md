---
layout: workshop      # DON'T CHANGE THIS.
venue: "Karolinska Institutet University Library Flemingsberg"        # brief name of host site without address (e.g., "Euphoric State University")
address: "Alfred Nobels allé 8. The university library, room Hypofysen 1"      # full street address of workshop (e.g., "Room A, 123 Forth Street, Blimingen, Euphoria")
country: "Sweden"      # lowercase two-letter ISO country code such as "fr" (see https://en.wikipedia.org/wiki/ISO_3166-1#Current_codes)
language: "en"     # lowercase two-letter ISO language code such as "fr" (see https://en.wikipedia.org/wiki/List_of_ISO_639-1_codes)
latitude: "59.2"     # decimal latitude of workshop venue (use https://www.latlong.net/)
longitude: "17.9"    # decimal longitude of the workshop venue (use https://www.latlong.net)
humandate: "April 1-2, 2020"    # human-readable dates for the workshop (e.g., "Feb 17-18, 2020")
humantime: "9:00 am - 4:30 pm"    # human-readable times for the workshop (e.g., "9:00 am - 4:30 pm")
startdate: 2020-04-01      # machine-readable start date for the workshop in YYYY-MM-DD format like 2015-01-01
enddate: 2020-04-02        # machine-readable end date for the workshop in YYYY-MM-DD format like 2015-01-02
instructor: ["Joakim Philipson, Rosa Lönneborg, Thomas Lind,Lina Andrén"] # boxed, comma-separated list of instructors' names as strings, like ["Kay McNulty", "Betty Jennings", "Betty Snyder"]
helper: ["Glenn Haya"]     # boxed, comma-separated list of helpers' names, like ["Marlyn Wescoff", "Fran Bilas", "Ruth Lichterman"]
email: ["glenn.haya@ki.se"]    # boxed, comma-separated list of contact email addresses for the host, lead instructor, or whoever else is handling questions, like ["marlyn.wescoff@example.org", "fran.bilas@example.org", "ruth.lichterman@example.org"]
collaborative_notes: "https://pad.carpentries.org/2020-04-01-working-with-data"            

---

<h2 id="general">General Information</h2>

{% if page.latitude and page.longitude %}
<p id="where">
  <strong>Where:</strong>
  {{page.address}}.
  Get directions with
  <a href="//www.openstreetmap.org/?mlat={{page.latitude}}&mlon={{page.longitude}}&zoom=16">OpenStreetMap</a>
  or
  <a href="//maps.google.com/maps?q={{page.latitude}},{{page.longitude}}">Google Maps</a>.
</p>
{% endif %}

{% if page.humandate %}
<p id="when">
  <strong>When:</strong>
  {{page.humandate}}.
  {% include workshop_calendar.html %}
</p>
{% endif %}



<p id="requirements">
  <strong>Requirements:</strong> Participants must bring a laptop with a
  Mac, Linux, or Windows operating system (not a tablet, Chromebook, etc.) that they have administrative privileges on. They should have a few specific software packages detailed in each section of the schedule listed below.
</p>

<p id="accessibility">
  <strong>Accessibility:</strong> We are committed to making this workshop
  accessible to everybody.
  The workshop organizers have checked that:
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
</p>
<p id="Registration">

<p id="contact">
  <strong>Contact</strong>:
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

<h2 id="code-of-conduct">Code of Conduct</h2>

<p>
Everyone who participates in Carpentries activities is required to conform to the <a href="https://docs.carpentries.org/topic_folders/policies/code-of-conduct.html">Code of Conduct</a>.This document also outlines how to report an incident if needed.
</p>

<p class="text-center">
<button type="button" class="btn btn-info">Report a Code of Conduct Incident</button>
</p>
<hr/>
<h2>Registration</h2>
<p>Registration is open to people affiliated with KI, KTH or SU. Registration is not active yet, we will add a link here when it is available.
  </p>
  <hr/>

{% if page.collaborative_notes %}
<h2 id="collaborative_notes">Collaborative Notes</h2>

<p>
We will use this <a href="{{page.collaborative_notes}}">collaborative document</a> for chatting, taking notes, and sharing URLs and bits of code.
</p>
<hr/>
{% endif %}


<hr/>

<h2 id="schedule">Schedule</h2>

{% if site.carpentry == "swc" %}
{% include swc/schedule.html %}
{% elsif site.carpentry == "dc" %}
{% include dc/schedule.html %}
{% elsif site.carpentry == "lc" %}
{% include lc/schedule.html %}
{% endif %}

<hr/>

<h2 id="setup">Setup</h2>

<h3>SQL</h3>
 <ul>
    <li>This lesson requires the Unix shell, plus <a href="http://www.sqlite.org/">SQLite3</a> or <a href="http://sqlitebrowser.org/">DB Browser for SQLite</a>.</li>
    <li>We will be working with a predefined database. More information will be posted here shortly.</li>
 </ul>
<h3>Open Refine</h3>
 <p>This lesson requires a working copy of OpenRefine (also called 
GoogleRefine).</p>

<h3>Python</h3>
 <p> More information coming soon.
</p>  
  

{% if site.carpentry == "swc" %}
{% include swc/setup.html %}
{% elsif site.carpentry == "dc" %}
{% include dc/setup.html %}
{% elsif site.carpentry == "lc" %}
{% include lc/setup.html %}
{% endif %}
