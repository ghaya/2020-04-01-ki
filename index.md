---
layout: workshop      # DON'T CHANGE THIS.
venue: "Karolinska Institutet University Library Flemingsberg"        # brief name of host site without address (e.g., "Euphoric State University")
address: "The workshop is currently cancelled due to the coronavirus.  We are looking into providing an online version"      # full street address of workshop (e.g., "Room A, 123 Forth Street, Blimingen, Euphoria")
country: "Sweden"      # lowercase two-letter ISO country code such as "fr" (see https://en.wikipedia.org/wiki/ISO_3166-1#Current_codes)
language: "en"     # lowercase two-letter ISO language code such as "fr" (see https://en.wikipedia.org/wiki/List_of_ISO_639-1_codes)
latitude: "59.219701"     # decimal latitude of workshop venue (use https://www.latlong.net/)
longitude: "17.940939"    # decimal longitude of the workshop venue (use https://www.latlong.net)
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
<p>This workshop is fully booked.</p>
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

<div id="sql"> 
  <h3>SQLite</h3>

  <p>
    SQL is a specialized programming language used with databases.  We
    use a simple database manager called
    <a href="https://www.sqlite.org/">SQLite</a> in our lessons.
  </p>

  <div>
    <ul class="nav nav-tabs nav-justified" role="tablist">
      <li role="presentation" class="active"><a data-os="windows" href="#sql-windows" aria-controls="Windows" role="tab" data-toggle="tab">Windows</a></li>
      <li role="presentation"><a data-os="macos" href="#sql-macos" aria-controls="MacOS" role="tab" data-toggle="tab">MacOS</a></li>
      <li role="presentation"><a data-os="linux" href="#sql-linux" aria-controls="Linux" role="tab" data-toggle="tab">Linux</a></li>
      
      <li role="presentation"><a data-os="Web" href="#sql-web" aria-controls="Linux" role="tab" data-toggle="tab">Web</a></li>
      
    </ul>
    
    <div class="tab-content">
      <article role="tabpanel" class="tab-pane active" id="sql-windows">
        <p>
          <ul>
            <li>Run git-bash from the start menu</li>
            <li>Copy the following <code>curl https://kth-biblioteket.github.io/2019-11-13-carpentry/getsql.sh | bash</code></li>
            <li>Paste it into the window that git bash opened. If you're unsure, ask an instructor for help</li>
            <li>You should see something like <code>3.27.2 2019-02-25 16:06:06 ...</code></li>
          </ul>
            
          <p>If you want to do this manually, download <a href="https://www.sqlite.org/2019/sqlite-tools-win32-x86-3270200.zip">sqlite3</a>, make a bin directory in the user's home directory, unzip sqlite3, move it into the bin directory, and then add the bin directory to the path.</p>

        </p>
      </article>
      <article role="tabpanel" class="tab-pane active" id="sql-macos">
        <p>
          SQLite comes pre-installed on macOS.
        </p>
      </article>
      <article role="tabpanel" class="tab-pane active" id="sql-linux">
        <p>
          SQLite comes pre-installed on Linux.
        </p>
      </article>
      <article role="tabpanel" class="tab-pane active" id="sql-web">
        <p>
          <ul>
            <li>In case of problems: register for an account at <a href="http://pythonanywhere.com/">Python Anywhere</a></li>
            <li>Download <a href="http://swcarpentry.github.io/sql-novice-survey/files/survey.db">survey.db</a></li>
            <li>Click on files and upload survey.db</li>
            <li>Click on dashboard and Choose new console <code>$ bash</code></li>
            </ul>
        </p>
      </article>
    </div>
      
  </div>

  <p><strong>If you installed Anaconda, it also has a copy of SQLite
      <a href="https://github.com/ContinuumIO/anaconda-issues/issues/307">without support to <code>readline</code></a>.
      Instructors will provide a workaround for it if needed.</strong></p>
</div>

<div id="openrefine"> 
  <h3>OpenRefine</h3>
  <p>
    For this lesson you will need <em>OpenRefine</em> and a
    web browser. <em>Note:</em> this is a Java program that requires a Java Runtime Environment on your machine (if lacking, can be downloaded from here: <a href="https://jdk.java.net/13/">JDK</a>). 
    It runs inside a web browser(Chrome is recommended, Firefox also works ok), but no web connection is needed.
  </p>

  <div>
    <ul class="nav nav-tabs nav-justified" role="tablist">
      <li role="presentation" class="active"><a data-os="windows" href="#openrefine-windows" aria-controls="Windows" role="tab" data-toggle="tab">Windows</a></li>
      <li role="presentation"><a data-os="macos" href="#openrefine-macos" aria-controls="MacOS" role="tab" data-toggle="tab">MacOS</a></li>
      <li role="presentation"><a data-os="linux" href="#openrefine-linux" aria-controls="Linux" role="tab" data-toggle="tab">Linux</a></li>
    </ul>

    <div class="tab-content">
      <article role="tabpanel" class="tab-pane active" id="openrefine-windows">
        <p>
          Check that you have either the Firefox or the Chrome browser installed and set as your default browser.
          <strong>OpenRefine runs in your default browser.</strong>
          It will not run correctly in Internet Explorer.
        </p>
        <p>Download software from <a href="http://openrefine.org/">http://openrefine.org/</a></p>
        <p>Create a new directory called OpenRefine.</p>
        <p>Unzip the downloaded file into the OpenRefine directory by right-clicking and selecting "Extract ...". </p>
        <p>Go to your newly created OpenRefine directory.</p>
        <p>Launch OpenRefine by clicking <code>openrefine.exe</code> (this will launch a command prompt window, but you can ignore that - just wait for OpenRefine to open in the browser).</p>
        <p>If you are using a different browser, or if OpenRefine does not automatically open for you, point your browser at <a href="http://127.0.0.1:3333/">http://127.0.0.1:3333/</a> or <a href="http://localhost:3333">http://localhost:3333</a> to use the program.</p>
      </article>
      <article role="tabpanel" class="tab-pane active" id="openrefine-macos">
        <p>Check that you have either the Firefox or the Chrome browser installed and set as your default browser. <strong>OpenRefine runs in your default browser.</strong> It may not run correctly in Safari.</p>
        <p>Download software from <a href="http://openrefine.org/">http://openrefine.org/</a>.</p>
        <p>Create a new directory called OpenRefine.</p>
        <p>Unzip the downloaded file into the OpenRefine directory by double-clicking it.</p>
        <p>Go to your newly created OpenRefine directory.</p>
        <p>Launch OpenRefine by dragging the icon into the Applications folder.</p>
        <p>Use <code>Ctrl-click/Open ... </code> to launch it.</p>
        <p>If you are using a different browser, or if OpenRefine does not automatically open for you, point your browser at <a href="http://127.0.0.1:3333/">http://127.0.0.1:3333/</a> or <a href="http://localhost:3333">http://localhost:3333</a> to use the program.</p>
      </article>
      <article role="tabpanel" class="tab-pane active" id="openrefine-linux">
        <p>Check that you have either the Firefox or the Chrome browser installed and set as your default browser. <strong>OpenRefine runs in your default browser.</strong></p>
        <p>Download software from <a href="http://openrefine.org/">http://openrefine.org/</a>.</p>
        <p>Make a directory called OpenRefine.</p>
        <p>Unzip the downloaded file into the OpenRefine directory.</p>
        <p>Go to your newly created OpenRefine directory.</p>
        <p>Launch OpenRefine by entering <code>./refine</code> into the terminal within the OpenRefine directory.</p>
        <p>If you are using a different browser, or if OpenRefine does not automatically open for you, point your browser at <a href="http://127.0.0.1:3333/">http://127.0.0.1:3333/</a> or <a href="http://localhost:3333">http://localhost:3333</a> to use the program.</p>
      </article>
    </div>
  </div>
</div>

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
