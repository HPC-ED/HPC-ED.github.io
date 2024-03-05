---
# Header needed to process Jekyll/Liquid variables
# For developer setup ref: https://jekyllrb.com/docs/
# Added by Je'aime Powell - jpowell@tacc.utexas.edu
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: home
title: Home
---
<main role="main">
    <div class="jumbotron">
      <div class="container">
        <img src="../assets/imgs/HPC-Ed.png" alt="HPC-ED logo" class="rounded mx-auto d-block">
       
      </div>
    </div>
      
<div class="container">
      <!-- Example row of columns -->
      <div class="row">
        <div class="col-md-4">
          <h2>Project</h2>
          <p>Cybertraining materials abound, but they can be difficult to find, and
            often have little information about the quality or relevance of offerings.
            Using existing software technology, the HPC-ED Pilot project team will
            build a platform for the community to better share and find training
            materials through a federated repository.</p>
          <ul>
            <li>Organizations and authors will retain physical and legal ownership of
              their materials by sharing only catalog information.</li>
            <li>Organizations can expand local portals to use the best and most
              appropriate materials from both local and remote sources.</li>
            <li>Learners can take advantage of materials that are reviewed and
              described more clearly.</li>
            <li>Learners and organizations will quickly and accurately find materials
              via standardized descriptive tagging.</li>
          </ul>
          <p>
          <a href="https://www.cac.cornell.edu/about/pubs/HPC%20ED%20CyberTraining.pdf">The pilot</a>
            will demonstrate that resource providers, campus portals,
            schools, and other institutions can both incorporate training from
            multiple sources into their own familiar interface and publish their local
            training materials to a much wider audience.</p>
      </div>
        <div class="col-md-4">
          <h2>Catalog Tools</h2><p><a
              href="https://search-pilot.operations.access-ci.org/">HPC Training MetaData Pilot Tool</a> - <em>[Alpha]</em> Developer and tester browsing portal</p>

          <h2>Guides</h2>

            <p> <a href="https://github.com/HPC-ED/HPC-ED.github.io/wiki">Wiki</a> - Storehouse of documentation/guides supporting HPC-ED tools and events including Searching, Publishing, and Adding metadata using our API. </p>
          

          <h2>Contact Us</h2><p><a
              href="mailto:hpc.edu.train@gmail.com">hpc.edu.train@gmail.com</a></p>

  <h2>Partners</h2>
          {% for org in site.data.partners.organization %}

          <a href="{{ org.url }}"> <img class="organizations" src="{{ org.logo }}" alt="{{ org.name }}"> </a>


          {% endfor %}


  </div>
  <div class="col-md-4">
    <h2>Community</h2>
    <p> <strong><a href="https://groups.google.com/u/1/g/hpc-edu-train">HPC-ED Google Group</a></strong> - Join/check the HPC-ED Google Group for project updates, emails, and collaborative opportunities. </p>
    <p>To participate in the working group formed to discuss metadata standards for sharing materials, join the <a
        href="https://sighpceducation.acm.org/">ACM SIGHPC Education Chapter</a>.</p>
    <p>Join the ACCESS affinity group <a
        href="https://support.access-ci.org/affinity-groups/hpc-ontologies-and-metadata">HPC Ontologies and
        Metadata</a> to build a set of standardized minimal HPC ontologies and metadata. </p>
    <p><a href="https://tinyurl.com/HPC-ED-Join">Let us know</a> if you want to be one of the first to try the new catalog tool we are developing.</p>

  <h3>Upcoming Events:</h3>
    <ul>
     {%- if site.posts.size > 0 -%}
    
      {% capture now %}{{'now' | date: '%s' | plus: 0 }}{% endcapture %}
        {% for post in site.posts %}
        {% if post.hide == null or post.hide == false %}
    {% capture date %}{{ post.dateofevent | date: '%s' | plus: 0 }}{% endcapture %}
    {% if date >= now %}
      <li>
        <strong>
          {% if post.content.size <= 1 %}
          <a href="{{ post.eventurl }}">
            {{ post.title | escape }}
          </a>
          {% else %}
            <a href="{{ post.url }}">
            {{ post.title | escape }}
          </a>
          {% endif %}
        </strong>
        <br>
        {%- assign date_format = site.minima.date_format | default: "%b %-d, %Y" -%}
        <span class="post-meta">{{ post.dateofevent | date: date_format }}</span>
      </li>
      {% endif %}
      {%- endif -%}
      {%- endfor -%}
{%- endif -%}
      
  
    </ul>

  </div>
</div>

   <hr>
  </div> 
  <!-- /container -->

  </main>

 

  <!-- Bootstrap core JavaScript
    ================================================== -->
  <!-- Placed at the end of the document so the pages load faster -->
  <script src="https://code.jquery.com/jquery-3.2.1.slim.min.js"
    integrity="sha384-KJ3o2DKtIkvYIK3UENzmM7KCkRr/rE9/Qpg6aAZGJwFDMVNA/GpGFF93hXpG5KkN"
    crossorigin="anonymous"></script>
  <script>window.jQuery || document.write('<script src="./assets/js/vendor/jquery-slim.min.js"><\/script>')</script>
  <script src="./assets/js/popper.min.js"></script>
  <script src="./assets/js/bootstrap.min.js"></script>
