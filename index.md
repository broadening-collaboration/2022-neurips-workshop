---
layout: workshop      # DON'T CHANGE THIS.
# More detailed instructions (including how to fill these variables for an
# online workshop) are available at

venue: "Broadening Collaborations in ML"        # brief name of the institution that hosts the workshop without address (e.g., "Euphoric State University")
address: "NeurIPS 2022"      # full street address of workshop (e.g., "Room A, 123 Forth Street, Blimingen, Euphoria"), videoconferencing URL, or 'online'
humandate: "NeurIPS Workshop, Dec 2022"    # human-readable dates for the workshop (e.g., "Feb 17-18, 2020")


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

{% comment %}
EVENTBRITE

This block includes the Eventbrite registration widget if
'eventbrite' has been set in the header.  You can delete it if you
are not using Eventbrite, or leave it in, since it will not be
displayed if the 'eventbrite' field in the header is not set.
{% endcomment %}
{% if page.eventbrite %}
<strong>Some adblockers block the registration window. If you do not see the
  registration box below, please check your adblocker settings.</strong>
<iframe
  src="https://www.eventbrite.com/tickets-external?eid={{page.eventbrite}}&ref=etckt"
  frameborder="0"
  width="100%"
  height="280px"
  scrolling="auto">
</iframe>
{% endif %}


<h2 id="general">Scope</h2>

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

This workshop aims to discuss challenges and opportunities given the changing landscape of where, how and by whom research is produced. Progress toward democratizing AI research has been centered around making knowledge (e.g. class materials), established ideas (e.g. papers) and technologies (e.g. code, compute) more accessible. However, open, online resources are only part of the equation. Growth as a researcher requires not only learning by consuming information individually, but hands-on practice whiteboarding, coding, plotting, debugging, and writing collaboratively, with either mentors or peers. Of course, making "collaborators" more universally accessible is fundamentally more difficult than, say, ensuring all can access arXiv papers, because scaling people and research groups is much harder than scaling websites. Can we nevertheless make access to collaboration itself more open? 




{% comment %}
ACCESSIBILITY

Modify the block below if there are any barriers to accessibility or
special instructions.
{% endcomment %}
<p id="accessibility">
  <strong>Accessibility:</strong>
  We are committed to making this workshop
  accessible to everybody. Please
  notify the organizers in advance of the workshop if you require any accommodations or if there is
  anything we can do to make this workshop more accessible to you.
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
   fatemeh@ucsd.edu
  {% endif %}
  for more information.
</p>



{% comment %}
WHO CAN ATTEND?

If you would like to specify who can attend the workshop,
you can use the section below.

Move the 'endcomment' tag above the beginning of the following
<p> tag to make this section visible.

Edit the text to match who can attend the workshop. For instance:
- This workshop is open to affiliates to ABC university.
- This workshop is open to the public.
- If you are interested in attending this workshop, contact me@example.com
  for more information

<p id="who-can-attend">
    <strong>Who can attend?:</strong>
    This workshop is open to ....
</p>
{% endcomment %}

<hr/>

{% comment%}
CODE OF CONDUCT
{% endcomment %}
<h2 id="code-of-conduct">Code of Conduct</h2>

<p>
Everyone who participates in this workshop is required to conform to the <a href="https://nips.cc/public/CodeOfConduct">NeurIPS Code of Conduct</a>. 
</p>


<hr/>

{% comment%}
ATTENDANCE
{% endcomment %}
<h2 id="attendance">Attendance</h2>

<p>
  You need to be registered at NeurIPS 2022, in order to be able to attend the workshop. The workshop, will be hosted hybrid this year, with the panel taking place in person at the conference. The workshop will take place either on Dec 2 or Dec 3, 2022.

  

</p>

<hr/>

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
We will use this <a href="{{ page.collaborative_notes }}">collaborative document</a> for chatting, taking notes, and sharing URLs and bits of code.
</p>
<hr/>
{% endif %}

<h2 id="general">Call for Papers</h2>

We invite position (up to 4 pages) and research papers (up to 8 pages) on topics related to those listed above. These topics may include: 

<li> Research studies in open research communities/cross-institutional projects. </li>
<li> Incentives for broadening collaboration :How to improve equity in computational resources across different research institutions. </li>
<li> Cultural changes for open collaboration </li>

More details about submission guidelines, formatting and deadlines will be provided soon. 


<hr/>




{% comment %}
SCHEDULE

Show the workshop's schedule.

Small changes to the schedule can be made by modifying the
`schedule.html` found in the `_includes` folder for your
workshop type (`swc`, `lc`, or `dc`). Edit the items and
times in the table to match your plans. You may also want to
change 'Day 1' and 'Day 2' to be actual dates or days of the
week.

For larger changes, a blank template for a 4-day workshop
(useful for online teaching for instance) can be found in
`_includes/custom-schedule.html`. Add the times, and what
you will be teaching to this file. You may also want to add
rows to the table if you wish to break down the schedule
further. To use this custom schedule here, replace the block
of code below the Schedule `<h2>` header below with
`{% include custom-schedule.html %}`.
{% endcomment %}




{% comment %}
Organizers and PC Members
{% endcomment %}
<h2 id="surveys">Organizers</h2>



{% comment %}
Organizers and PC Members
{% endcomment %}


Sara Hooker 

Rosanne Liu (Google Brain and ML Collective)

Pablo Castro (Google Brain)

Fatemehsadat Mireshghallah (UC San Diego)

Sunipa Dev (Google Research)

Fede Carnevale (DeepMind)

Benjamin Rosman (University of the Witwatersrand, South Africa)
