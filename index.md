---
layout: workshop      # DON'T CHANGE THIS.
venue: "<br><br>Griffith University <br> Virtual Campus (hosted on Microsoft Teams) "        # brief name of host site without address (e.g., "Euphoric State University")
address: "Griffith University, Virtual Campus"      # full street address of workshop (e.g., "Room A, 123 Forth Street, Blimingen, Euphoria")
country: "au"      # lowercase two-letter ISO country code such as "fr" (see https://en.wikipedia.org/wiki/ISO_3166-1#Current_codes)
language: "en"     # lowercase two-letter ISO language code such as "fr" (see https://en.wikipedia.org/wiki/List_of_ISO_639-1_codes)
latitude: "-27.552941"     # decimal latitude of workshop venue (use https://www.latlong.net/)
longitude: "-27.552941"    # decimal longitude of the workshop venue (use https://www.latlong.net)
humandate: "Sep 21-22 2020"    # human-readable dates for the workshop (e.g., "Feb 17-18, 2020")
humantime: "9:00am to 12:30pm"    # human-readable times for the workshop (e.g., "9:00 am - 4:30 pm")
startdate: 2020-09-14      # machine-readable start date for the workshop in YYYY-MM-DD format like 2015-01-01
enddate: 2020-09-22        # machine-readable end date for the workshop in YYYY-MM-DD format like 2015-01-02
instructor: ["Jacob Dore-Porrett"] # boxed, comma-separated list of instructors' names as strings, like ["Kay McNulty", "Betty Jennings", "Betty Snyder"]
helper: ["Brett Parker"]     # boxed, comma-separated list of helpers' names, like ["Marlyn Wescoff", "Fran Bilas", "Ruth Lichterman"]
email: ["eresearch-support@griffith.edu.au", "hackyhour@griffith.edu.au"]    # boxed, comma-separated list of contact email addresses for the host, lead instructor, or whoever else is handling questions, like ["marlyn.wescoff@example.org", "fran.bilas@example.org", "ruth.lichterman@example.org"]
collaborative_notes:  https://docs.google.com/document/d/1fzy96HIMkOTih-PCYDFB8FfhimrL5e9IqJ0E-2WlxO4/edit?usp=sharing           # optional: URL for the workshop collaborative notes, e.g. an Etherpad or Google Docs document (e.g., https://pad.carpentries.org/2015-01-01-euphoria)
eventbrite:           # optional: alphanumeric key for Eventbrite registration, e.g., "1234567890AB" (if Eventbrite is being used)
---

{% comment %} See instructions in the comments below for how to edit specific sections of this workshop template. {% endcomment %}

{% comment %}
HEADER

Edit the values in the block above to be appropriate for your workshop.
If the value is not 'true', 'false', 'null', or a number, please use
double quotation marks around the value, unless specified otherwise.
And run 'make workshop-check' *before* committing to make sure that changes are good.
{% endcomment %}

<iframe width="800px" height= "600px" src= "https://forms.office.com/Pages/ResponsePage.aspx?id=q8h8Wtykm0-_YGZxQEmtYgli2x3zWW9Nt79Pc1vnhxZUOVlQSFdBUlZGVDY1UDRaWkxGRExNSUdXWSQlQCN0PWcu" frameborder= "0" marginwidth= "0" marginheight= "0" style= "border: none; max-width:100%; max-height:100vh" allowfullscreen webkitallowfullscreen mozallowfullscreen msallowfullscreen> </iframe>


<h3>If you would like to be notified of later workshops, please complete this form: <a href="https://forms.office.com/Pages/ResponsePage.aspx?id=q8h8Wtykm0-_YGZxQEmtYgli2x3zWW9Nt79Pc1vnhxZUMURYSENZV1MyT1pKTFlTTEFON1FYWDIyVSQlQCN0PWcu">Interested in programming classes</a>.</h3>
<br><br>

{% comment %}
Check DC curriculum
{% endcomment %}

{% if site.carpentry == "dc" or site.carpentry == "dc" %}
{% unless site.curriculum == "dc-ecology" or site.curriculum == "dc-genomics" or site.curriculum == "dc-socsci" or site.curriculum == "dc-geospatial" %}
<div class="alert alert-warning">
It looks like you are setting up a website for a Data Carpentry curriculum but you haven't specified the curriculum type in the <code>_config.yml</code> file (current value in <code>_config.yml</code>: "<strong>{{ site.curriculum }}</strong>", possible values: <code>dc-ecology</code>, <code>dc-genomics</code>, <code>dc-socsci</code>, or <code>dc-geospatial</code>). After editing this file, you need to run <code>make serve</code> again to see the changes reflected.
</div>
{% endunless %}
{% endif %}

{% comment %}
EVENTBRITE

This block includes the Eventbrite registration widget if
'eventbrite' has been set in the header.  You can delete it if you
are not using Eventbrite, or leave it in, since it will not be
displayed if the 'eventbrite' field in the header is not set.
{% endcomment %}
{% if page.eventbrite %}
<iframe
  src="https://www.eventbrite.com/tickets-external?eid={{page.eventbrite}}&ref=etckt"
  frameborder="0"
  width="100%"
  height="280px"
  scrolling="auto">
</iframe>
{% endif %}


<h2 id="general">General Information</h2>

{% comment %}
INTRODUCTION

Edit the general explanatory paragraph below if you want to change
the pitch.
{% endcomment %}
{% if site.carpentry == "swc" %}
{% include swc/intro.html %}
{% elsif site.carpentry == "dc" %}
{% include dc/intro.html %}
{% elsif site.carpentry == "lc" %}
{% include lc/intro.html %}
{% endif %}

{% comment %}
AUDIENCE

Explain who your audience is.  (In particular, tell readers if the
workshop is only open to people from a particular institution.
{% endcomment %}
{% if site.carpentry == "swc" %}
{% include swc/who.html %}
{% elsif site.carpentry == "dc" %}
{% include dc/who.html %}
{% elsif site.carpentry == "lc" %}
{% include lc/who.html %}
{% endif %}

{% comment %}
LOCATION

This block displays the address and links to maps showing directions
if the latitude and longitude of the workshop have been set.  You
can use https://itouchmap.com/latlong.html to find the lat/long of an
address.
{% endcomment %}
{% if page.latitude and page.longitude %}
<p id="where">
  <strong>Where:</strong> Hosting training virtually via Microsoft Teams
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
  <strong>Requirements:</strong> Participants must have a laptop with a
  Mac, Linux, or Windows operating system (not a tablet, Chromebook, etc.) that they have administrative privileges on. They should have a few specific software packages installed (listed <a href="#setup">below</a>).
<br>
You will need, at the minimum, speakers/headphones and a microphone, as well as a good enough network connection to receive audio and video. A camera is optional, and with over 10 people registered to take part, we may have to ask some of you to disable cameras anyway to reduce bandwidth demands.
<br>
If you have access to a second computer/screen/ipad etc, that will make your experience enormously better since you can then watch the instructor on one screen and type on the other. Unfortunately a phone screen won't be sufficient - you will need something that is big enough to follow what the instructor is typing.
<br>
Be aware that this workshop will effectively be two half days of video streaming. If you access the internet through a phone data plan, this may use all of your data allowance and become very expensive. In this case, please consider whether you can make alternative arrangements or let me know if you would like to withdraw from the workshop.
</p>

{% comment %}
ACCESSIBILITY

Modify the block below if there are any barriers to accessibility or
special instructions.
{% endcomment %}
<!--
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
-->
{% comment %}
CONTACT EMAIL ADDRESS

Display the contact email address set in the configuration file.
{% endcomment %}
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

{% comment%}
CODE OF CONDUCT
{% endcomment %}
<h2 id="code-of-conduct">Code of Conduct</h2>

<p>
Everyone who participates in Carpentries activities is required to conform to the <a href="https://docs.carpentries.org/topic_folders/policies/code-of-conduct.html">Code of Conduct</a>.This document also outlines how to report an incident if needed.
</p>

<p class="text-center">
<button type="button" class="btn btn-info">Report a Code of Conduct Incident</button>
</p>
<hr/>


{% comment %}
Collaborative Notes

If you want to use an Etherpad, go to

http://pad.carpentries.org/YYYY-MM-DD-site

where 'YYYY-MM-DD-site' is the identifier for your workshop,
e.g., '2015-06-10-esu'.
{% endcomment %}
{% if page.collaborative_notes %}
<h2 id="collaborative_notes">Collaborative Notes</h2>

<p>
We will use this <a href="{{page.collaborative_notes}}">collaborative document</a> for chatting, taking notes, and sharing URLs and bits of code.
</p>
<hr/>
{% endif %}


{% comment %} 
SURVEYS - DO NOT EDIT SURVEY LINKS 
{% endcomment %}
<h2 id="surveys">Surveys</h2>
<p>Please be sure to complete these surveys before and after the workshop.</p>
<p><a href="{{ site.pre_survey }}{{ site.github.project_title }}">Pre-workshop Survey</a></p>
<p><a href="{{ site.post_survey }}{{ site.github.project_title }}">Post-workshop Survey</a></p>

<hr/>


{% comment %}
SCHEDULE

Show the workshop's schedule.  Edit the items and times in the table
to match your plans.  You may also want to change 'Day 1' and 'Day
2' to be actual dates or days of the week.
{% endcomment %}
<h2 id="schedule">Schedule</h2>

{% if site.carpentry == "swc" %}
{% include swc/schedule.html %}
{% elsif site.carpentry == "dc" %}
{% include dc/schedule.html %}
{% elsif site.carpentry == "lc" %}
{% include lc/schedule.html %}
{% endif %}

<hr/>

{% comment %}
SYLLABUS

Show what topics will be covered.

1. If your workshop is R rather than Python, remove the comment
around that section and put a comment around the Python section.
2. Some workshops will delete SQL.
3. Please make sure the list of topics is synchronized with what you
intend to teach.
4. You may need to move the div's with class="col-md-6" around inside
the div's with class="row" to balance the multi-column layout.

This is one of the places where people frequently make mistakes, so
please preview your site before committing, and make sure to run
'tools/check' as well.
{% endcomment %}
<h2 id="syllabus">Syllabus</h2>

{% if site.carpentry == "swc" %}
{% include swc/syllabus.html %}
{% elsif site.carpentry == "dc" %}
{% include dc/syllabus.html %}
{% elsif site.carpentry == "lc" %}
{% include lc/syllabus.html %}
{% endif %}

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
  To participate in a
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

{% if site.carpentry == "swc" %}
{% include swc/setup.html %}
{% elsif site.carpentry == "dc" %}
{% include dc/setup.html %}
{% elsif site.carpentry == "lc" %}
{% include lc/setup.html %}
{% endif %}


<h2 id="setup">Setup</h2>

<p>
  To participate in a
  {% if page.carpentry == "swc" %}
  Software Carpentry
  {% elsif page.carpentry == "dc" %}
  Data Carpentry
  {% elsif page.carpentry == "lc" %}
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

<div id="shell"> {% comment %} Start of 'shell' section. {% endcomment %}
  <h3>The Bash Shell</h3>

  <p>
    Bash is a commonly-used shell that gives you the power to do simple
    tasks more quickly.
  </p>

  <div class="row">
    <div class="col-md-4">
      <h4 id="shell-windows">Windows</h4>
      <a href="https://www.youtube.com/watch?v=339AEqk9c-8">Video Tutorial</a>
      <ol>
        <li>Download the Git for Windows <a href="https://git-for-windows.github.io/">installer</a>.</li>
        <li>Run the installer and follow the steps below:
          <ol>
            {% comment %} Git 2.18.0 Setup {% endcomment %}
            <li>
                Click on "Next" four times (two times if you've previously
                installed Git).  You don't need to change anything
                in the Information, location, components, and start menu screens.
            </li>
            <li>
                <strong>
                Select “Use the nano editor by default” and click on “Next”.
                </strong>
            </li>
            {% comment %} Adjusting your PATH environment {% endcomment %}
            <li>
                Keep "Use Git from the command line and..." selected and click on "Next".
                If you forgot to do this programs that you need for the workshop will not work properly.
                If this happens rerun the installer and select the appropriate option.
            </li>
            {% comment %} Choosing the SSH executable {% endcomment %}
            <li>Click on "Next".</li>
            {% comment %} Configuring the line ending conversions {% endcomment %}
            <li>
                Keep "Checkout Windows-style, commit Unix-style line endings" selected and click on "Next".
            </li>
            {% comment %} Configuring the terminal emulator to use with Git Bash {% endcomment %}
            <li>
              <strong>
                Select "Use Windows' default console window" and click on "Next".
              </strong>
            </li>
            {% comment %} Configuring experimental performance tweaks {% endcomment %}
            <li>Click on "Install".</li>
            {% comment %} Installing {% endcomment %}
            {% comment %} Completing the Git Setup Wizard {% endcomment %}
            <li>Click on "Finish".</li>
          </ol>
        </li>
        <li>
          If your "HOME" environment variable is not set (or you don't know what this is):
          <ol>
            <li>Open command prompt (Open Start Menu then type <code>cmd</code> and press [Enter])</li>
            <li>
              Type the following line into the command prompt window exactly as shown:
              <p><code>setx HOME "%USERPROFILE%"</code></p>
            </li>
            <li>Press [Enter], you should see <code>SUCCESS: Specified value was saved.</code></li>
            <li>Quit command prompt by typing <code>exit</code> then pressing [Enter]</li>
          </ol>
        </li>
      </ol>
      <p>This will provide you with both Git and Bash in the Git Bash program.</p>
    </div>
    <div class="col-md-4">
      <h4 id="shell-macosx">macOS</h4>
      <p>
        The default shell in all versions of macOS is Bash, so no
        need to install anything.  You access Bash from the Terminal
        (found in
        <code>/Applications/Utilities</code>).
        See the Git installation <a href="https://www.youtube.com/watch?v=9LQhwETCdwY ">video tutorial</a>
        for an example on how to open the Terminal.
        You may want to keep
        Terminal in your dock for this workshop.
      </p>
    </div>
    <div class="col-md-4">
      <h4 id="shell-linux">Linux</h4>
      <p>
        The default shell is usually Bash, but if your
        machine is set up differently you can run it by opening a
        terminal and typing <code>bash</code>.  There is no need to
        install anything.
      </p>
    </div>
  </div>
</div> {% comment %} End of 'shell' section. {% endcomment %}

<div id="git"> {% comment %} Start of 'Git' section. 
  <h3>Git</h3>
  <p>
    Git is a version control system that lets you track who made changes
    to what when and has options for easily updating a shared or public
    version of your code
    on <a href="https://github.com/">github.com</a>. You will need a
    <a href="https://help.github.com/articles/supported-browsers/">supported
    web browser</a>.
  </p>
  <p>
    You will need an account at <a href="https://github.com/">github.com</a>
    for parts of the Git lesson. Basic GitHub accounts are free. We encourage
    you to create a GitHub account if you don't have one already.
    Please consider what personal information you'd like to reveal. For
    example, you may want to review these
    <a href="https://help.github.com/articles/keeping-your-email-address-private/">instructions
    for keeping your email address private</a> provided at GitHub.
  </p>

  <div class="row">
    <div class="col-md-4">
      <h4 id="git-windows">Windows</h4>
      <p>
        Git should be installed on your computer as part of your Bash
        install (described above).
      </p>
    </div>
    <div class="col-md-4">
      <h4 id="git-macosx">macOS</h4>
      <p>
        Please open the Terminal app, type <code>git --version</code> and press 
        <kbd>Enter</kbd>/<kbd>Return</kbd>. If it's not installed already, 
        follow the instructions to <code>Install</code> the "command line 
        developer tools". <strong>Don't click</strong> "Get Xcode", because that will 
        take too long and is not necessary for our Git lesson.
        After installing these tools, there won't be anything in your <code>/Applications</code>
        folder, as they and Git are command line programs.
        <strong>For older versions of OS X (10.5-10.8)</strong> use the
        most recent available installer labelled "snow-leopard"
        <a href="http://sourceforge.net/projects/git-osx-installer/files/">available here</a>.
        Because this installer is not signed by the developer, you may have to
        right click (control click) on the .pkg file, click Open, and click
        Open in the pop-up dialog. You can watch 
        <a href="https://www.youtube.com/watch?v=9LQhwETCdwY ">a video tutorial about this case</a>.
      </p>
    </div>
    <div class="col-md-4">
      <h4 id="git-linux">Linux</h4>
      <p>
        If Git is not already available on your machine you can try to
        install it via your distro's package manager. For Debian/Ubuntu run
        <code>sudo apt-get install git</code> and for Fedora run
        <code>sudo dnf install git</code>.
      </p>
    </div>
  </div>{% endcomment %}
</div> {% comment %} End of 'Git' section. {% endcomment %}

<div id="editor"> {% comment %} Start of 'editor' section. {% endcomment %}
  <h3>Text Editor</h3>

  <p>
    When you're writing code, it's nice to have a text editor that is
    optimized for writing code, with features like automatic
    color-coding of key words. The default text editor on macOS and
    Linux is usually set to Vim, which is not famous for being
    intuitive. If you accidentally find yourself stuck in it, hit
    the <kbd>Esc</kbd> key, followed by <kbd>:</kbd>+<kbd>Q</kbd>+<kbd>!</kbd> 
    (colon, lower-case 'q', exclamation mark), then hitting <kbd>Return</kbd> to 
    return to the shell.
  </p>

  <div class="row">
    <div class="col-md-4">
      <h4 id="editor-windows">Windows</h4>
      <p>
        nano is a basic editor and the default that instructors use in the workshop.
        It is installed along with Git.
      </p>
      <p>
        Others editors that you can use are
        <a href="https://notepad-plus-plus.org/">Notepad++</a> or
        <a href="https://www.sublimetext.com/">Sublime Text</a>.
        <strong>Be aware that you must
          add its installation directory to your system path.</strong>
        Please ask your instructor to help you do this.
      </p>
    </div>
    <div class="col-md-4">
      <h4 id="editor-macosx">macOS</h4>
      <p>
        nano is a basic editor and the default that instructors use in the workshop.
        See the Git installation <a href="https://www.youtube.com/watch?v=9LQhwETCdwY ">video tutorial</a>
        for an example on how to open nano.
        It should be pre-installed.
      </p>
      <p>
        Others editors that you can use are
        <a href="https://www.barebones.com/products/bbedit/">BBEdit</a> or
        <a href="https://www.sublimetext.com/">Sublime Text</a>.
      </p>
    </div>
    <div class="col-md-4">
      <h4 id="editor-linux">Linux</h4>
      <p>
        nano is a basic editor and the default that instructors use in the workshop.
        It should be pre-installed.
      </p>
      <p>
        Others editors that you can use are
        <a href="https://wiki.gnome.org/Apps/Gedit">Gedit</a>,
        <a href="https://kate-editor.org/">Kate</a> or
        <a href="https://www.sublimetext.com/">Sublime Text</a>.
      </p>
    </div>
  </div>
</div> {% comment %} End of 'editor' section. {% endcomment %}

<div id="python"> {% comment %} Start of 'Python' section. Remove the third paragraph if
           the workshop will teach Python using something other than
           the Jupyter notebook.
           Details at https://jupyter-notebook.readthedocs.io/en/stable/notebook.html#browser-compatibility {% endcomment %}
  <h3>Python</h3>

  <p>
    <a href="https://python.org">Python</a> is a popular language for
    research computing, and great for general-purpose programming as
    well.  Installing all of its research packages individually can be
    a bit difficult, so we recommend
    <a href="https://www.anaconda.com/distribution/">Anaconda</a>,
    an all-in-one installer.
  </p>

    <p>
      Regardless of how you choose to install it,
      <strong>please make sure you install Python version 3.x</strong>
      (e.g., 3.6 is fine).
    </p>
{% comment %}
    <p> 
      We will teach Python using the <a href="https://jupyter.org/">Jupyter notebook</a>,
      a programming environment that runs in a web browser. For this to work you will need a reasonably
      up-to-date browser. The current versions of the Chrome, Safari and
      Firefox browsers are all
      <a href="https://jupyter-notebook.readthedocs.io/en/stable/notebook.html#browser-compatibility">supported</a>
      (some older browsers, including Internet Explorer version 9
      and below, are not).
    </p>
 {% endcomment %}

  <div class="row">
    <div class="col-md-4">
      <h4 id="python-windows">Windows</h4>
      <a href="https://www.youtube.com/watch?v=xxQ0mzZ8UvA">Video Tutorial</a>
      <ol>
        <li>Open <a href="https://www.anaconda.com/download/#windows">https://www.anaconda.com/download/#windows</a> with your web browser.</li>
        <li>Download the Python 3 installer for Windows.</li>
        <li>Install Python 3 using all of the defaults for installation <em>except</em> make sure to check <strong>Add Anaconda to my PATH environment variable</strong>.</li>
      </ol>
    </div>
    <div class="col-md-4">
      <h4 id="python-macosx">macOS</h4>
      <a href="https://www.youtube.com/watch?v=TcSAln46u9U">Video Tutorial</a>
      <ol>
        <li>Open <a href="https://www.anaconda.com/download/#macos">https://www.anaconda.com/download/#macos</a> with your web browser.</li>
        <li>Download the Python 3 installer for OS X.</li>
        <li>Install Python 3 using all of the defaults for installation.</li>
      </ol>
    </div>
    <div class="col-md-4">
      <h4 id="python-linux">Linux</h4>
      <ol>
        <li>Open <a href="https://www.anaconda.com/download/#linux">https://www.anaconda.com/download/#linux</a> with your web browser.</li>
        <li>Download the Python 3 installer for Linux.<br>
          (The installation requires using the shell. If you aren't
           comfortable doing the installation yourself
           stop here and request help at the workshop.)
        </li>
        <li>
          Open a terminal window.
        </li>
        <li>
          Type <pre>bash Anaconda3-</pre> and then press
          <kbd>Tab</kbd>. The name of the file you just downloaded should
          appear. If it does not, navigate to the folder where you
          downloaded the file, for example with:
          <pre>cd Downloads</pre>
          Then, try again.
        </li>
        <li>
          Press <kbd>Return</kbd>. You will follow the text-only prompts. To move through
          the text, press <kbd>Spacebar</kbd>. Type <code>yes</code> and
          press enter to approve the license. Press enter to approve the
          default location for the files. Type <code>yes</code> and
          press enter to prepend Anaconda to your <code>PATH</code>
          (this makes the Anaconda distribution the default Python).
        </li>
        <li>
          Close the terminal window.
        </li>
      </ol>
    </div>
  </div>
{% comment %}
  <p>
  Once you are done installing the software listed above,
  please go to <a href="setup/index.html">this page</a>,
  which has instructions on how to test that everything was installed correctly.
  </p>
{% endcomment %}
</div> {% comment %} End of 'Python' section. {% endcomment %}
