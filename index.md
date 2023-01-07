---
layout: default
meta-description: "Seminar series on the frontier of machine learning. Open to all Vanderbilt CS students Mondays 12:10-1:30 pm. Recordings are available to the public. "
---
## Announcements

<div class="announcement-group" markdown="1">
   * [vu.edu/ML](https://vu.edu/ml/) and [vanderbi.lt/ML](https://vanderbi.lt/ml/) will now redirect to this page.
   * Our virtual (Zoom) talks are on Mondays at 12:10 PM CT and typically last for 1 hour (approximately 45 to 50-minute talk plus Q&A).
   * Join the [MLSS Group](https://groups.google.com/forum/#!forum/vanderbiltmlss/join) for discussions and notifications of upcoming talks. 
</div>

{% for category in site.data.talks %}
## {{ category.type }}




<div class="talk-list">
  {% for talk in category.members %}
    {% if category.type == "Ongoing Talk"%}
      <div class="talk current-talk-group"> 
        <div class="current-talk-join-button"><button class="button1" role="button" type="submit" onclick="location.href='https://vanderbilt.zoom.us/j/98156144506'">Join Now</button></div>
        <div class="talk-presenter">{{ talk.speaker }}</div>
        {% if talk.title %}
          <span>{{ talk.title }}</span>
        {% endif %}
          {% if talk.abstract %}
            <details>
              <summary>Abstract</summary>
              {{ talk.abstract }}
              {% if talk.bio %}
                <br><br>
                <strong>Bio: </strong> {{ talk.bio }}
              {% endif %}
            </details>
          {% endif %}
      </div>
    {% else %}
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
    {% endif %}
  {% endfor %}
  
</div>
<div class="note">(*): incoming </div> 
{% endfor %}



