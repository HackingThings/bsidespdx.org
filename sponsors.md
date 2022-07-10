---
layout: page
title: "Sponsors"
---

<h3>Sponsorships opportunities are now open for BSidesPDX 2022</h3>
<p>
contact us at <a href="mailto:ponsorship@bsidespdx.org">sponsorship@bsidespdx.org</a> for more information
</p>

{% for class in site.data.sponsors %}

  <hr style="margin-bottom: 5px">
  <div style="text-align: center;" class="sponsors {{ class.class }}">
    {% if class.level %}
      <h1>{{ class.level }}</h1>
    {% endif %}
    <div class="row">

      {% for sponsor in class.sponsors %}
        {% if sponsor.break %}
          </div><div class="row">
          {% continue %}
        {% endif %}
        <div class="column">
          {% if sponsor.type %}
            <h1>{{ sponsor.type }}</h1>
          {% endif %}
          <a href="{{ sponsor.href }}" target="_blank">
            <div class="imgdiv">
              {% if sponsor.icon %}
                <img src="{{ site.url }}{{ sponsor.icon }}" alt="{{ sponsor.name }}" />
              {% else %}
                <p><strong>{{ sponsor.name }}</strong></p>
              {% endif %}
            </div>
          </a>
        </div>
      {% endfor %}

    </div>

  </div>
{% endfor %}

<hr style="margin-bottom: 5px">

<center>
  <p>
    Have further questions about sponsorships? Contact <a href="mailto:ponsorship@bsidespdx.org">ponsorship@bsidespdx.org</a>.
  </p>
  <p>
    <em>All names and logos are property of their respective owners.</em>
  </p>
  <p>
    <em>
      {% for class in site.data.sponsors %}
        {% for sponsor in class.sponsors %}
          {{ sponsor.credits }}
        {% endfor %}
      {% endfor %}
    </em>
  </p>
</center>
