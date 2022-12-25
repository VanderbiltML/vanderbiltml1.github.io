---
layout: default
meta-description: "Seminar series on the frontier of machine learning. Open to all Vanderbilt CS students Mondays 12:10-1:30 pm. Recordings are available to the public. "
---
**News**:

* Join our [Google Group](https://groups.google.com/forum/#!forum/vanderbiltml/join) for discussions and notifications of weekly seminar talks

{% for category in site.data.talks %}
# {{ category.type }}
<div class="talk-list">
  {% for talk in category.members %}
  <div class="talk list-group-item">
  <div class="talk-date">{{ talk.date }}</div>
  <div class="talk-presenter">{{ talk.speaker }}</div>
  {% if talk.title %}
  <div>
    {% if talk.recording %}
      <span><a class="talk-title-link" href="{{ talk.recording }}">{{ talk.title }} <i class="bi bi-box-arrow-up-right"></i></a></span>
    {% elsif talk.livestream %}
      <span><a class="talk-title-link" href="{{ talk.livestream }}">{{ talk.title }} <i class="bi bi-box-arrow-up-right"></i></a></span>
    {% else %}
      <span>{{ talk.title }}</span>
    {% endif %}
  </div>
  {% endif %}
  {% if talk.abstract %}
    <details>
    <summary>Abstract</summary>
    {{ talk.abstract }}

    {% if talk.bio %}
    <br><br>
    <strong>Bio: </strong> {{ talk.bio }}
    {% endif %}

    {% if talk.recording %}
      <br><br>
      <strong><a href="{{ talk.recording }}">Video Link</a></strong>
    {% elsif talk.livestream %}
      <br><br>
      <strong><a href="{{ talk.livestream }}">Livestream Link</a></strong>
    {% endif %}
    </details>
  {% endif %}
  </div>
  {% endfor %}
</div>
{% endfor %}

# Nominate a speaker

You can either fill out this form or email us with additional suggestions. We will review and consider sending the nominee an invite to schedule a talk!

<form
  action="https://formspree.io/f/xdojqjrd"
  method="POST"
>
  <label>
    Your email:
    <input type="email" name="email">
  </label>
   <label>
    Nominee:
    <input type="text" name="nominee">
  </label>
  <!-- your other form fields go here -->
  <button type="submit">Submit</button>
</form>


# About The Seminar

**Seminar Hosts:** [Soheil Kolouri](https://skolouri.github.io/), [Tyler Derr](https://tylersnetwork.github.io/)

**Student Director:** [Huy Tran](https://huytranirl.github.io/)

<!-- **Executive Producers:** Matei Zaharia, Chris Ré. -->

You can reach us at soheil.kolouri [at] vanderbilt [dot] edu.

<!-- Please uncomment this part if you clone our source code! -->

Website template from the [Stanford MLSys Seminar Series]
