---
layout: page
title: Events
---

<div>


{%- if site.posts.size > 0 -%}
    <h2 class="post-list-heading">Upcoming Events</h2>
    <ul class="post-list">
  
      {% capture now %}{{'now' | date: '%s' | plus: 0 }}{% endcapture %}
        {% for post in site.posts %}
        {% if post.hide == null or post.hide == false %}
    {% capture date %}{{ post.dateofevent | date: '%s' | plus: 0 }}{% endcapture %}
    {% if date >= now %}
      <li>
        {%- assign date_format = site.minima.date_format | default: "%b %-d, %Y" -%}
        <span class="post-meta">{{ post.dateofevent | date: date_format }}</span>
       <div>
      <div>
        {% if post.image %}
          <img src="{{ post.image }}" alt="{{ post.image_description }}"/>
        {% endif %}
      </div>
      <div>
        <h3>
          {% if post.content.size <= 1 and post.abstract %} <a class="post-link" href="{{ post.eventurl }}">
            {{ post.title | escape }}
            </a>
            {% else %}
            <a class="post-link" href="{{ post.url }}">
              {{ post.title | escape }}
            </a>
            {% endif %}
        </h3>
        {% if post.presenters %}
          <p><strong>Presenter(s):</strong>
            {% for name in post.presenters %}
                {% if forloop.last %}
                
                    {{ name }}
                  
                {% else %}
                  
                    {{ name }},
                  
                {% endif %}
            {% endfor %}
          
          {% if post.abstract %}
            <br>
            {{ post.abstract }}
          {% endif%}
          <br>
          {% if post.files %}
            <br>
            <strong style="font-size: small;">
            
            {% for file in post.files %}
              <a href="{{ file | prepend: url}}">Presentation File</a>

            {% endfor %}
            
          </strong>
          {% endif%}

           {% if post.eventurl %}
            <strong style="font-size: small;">
          
            <a href="{{ post.eventurl }}">Event URL</a>
            </strong>
          {% endif %}
            
          </p>
          <hr>
        {% endif %}
      </div>
    </div>
        {%- if site.show_excerpts -%}
          {{ post.excerpt }}
        {%- endif -%}
      </li>
      {% endif %}
      {%- endif -%}
      {%- endfor -%}
    </ul>
{%- endif -%}

<hr>

{%- if site.posts.size > 0 -%}
    <h2 class="post-list-heading">Past Events</h2>
    <ul class="post-list">

     {% capture now %}{{'now' | date: '%s' | plus: 0 }}{% endcapture %}
        {% for post in site.posts %}
        {% if post.hide == null or post.hide == false %}
    {% capture date %}{{ post.dateofevent | date: '%s' | plus: 0 }}{% endcapture %}
    {% if date < now %}
      <li>
        {%- assign date_format = site.minima.date_format | default: "%b %-d, %Y" -%}
        <span class="post-meta">{{ post.dateofevent | date: date_format }}</span>
        <div>
      <div>
        {% if post.image %}
          <img src="{{ post.image }}" alt="{{ post.image_description }}"/>
        {% endif %}
      </div>
      <div>
        <h3>
          {% if post.content.size <= 1 and post.abstract %} <a class="post-link" href="{{ post.eventurl }}">
            {{ post.title | escape }}
            </a>
            {% else %}
            <a class="post-link" href="{{ post.url }}">
              {{ post.title | escape }}
            </a>
            {% endif %}
        </h3>
        {% if post.presenters %}
          <p><strong>Presenter(s):</strong>
            {% for name in post.presenters %}
                {% if forloop.last %}
                
                    {{ name }}
                  
                {% else %}
                  
                    {{ name }},
                  
                {% endif %}
            {% endfor %}
          
          {% if post.abstract %}
            <br>
            {{ post.abstract }}
          {% endif%}
          <br>
          {% if post.files %}
            <br>
            <strong style="font-size: small;">
            
            {% for file in post.files %}
              <a href="{{ file | prepend: url}}">Presentation File</a> | 

            {% endfor %}
            
          </strong>
          {% endif%}


          {% if post.eventurl %}
            <strong style="font-size: small;">
          
            <a href="{{ post.eventurl }}">Event URL</a>
            </strong>
          {% endif %}
            
          </p>
          <hr>
        {% endif %}
      </div>
    </div>
        {%- if site.show_excerpts -%}
          {{ post.excerpt }}
        {%- endif -%}
      </li>
      {% endif %}
      {% endif %}
      {%- endfor -%}
    </ul>
{%- endif -%}
</div>