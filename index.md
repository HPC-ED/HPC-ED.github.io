---
# Header needed to process Jekyll/Liquid variables
# For developer setup ref: https://jekyllrb.com/docs/
# Added by Je'aime Powell - jpowell@tacc.utexas.edu
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: home
#title: HPC-ED
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
            Using existing software technology, the HPC ED Pilot project team will
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
          <h2>Contact Us</h2><p><a
              href="mailto:hpc.edu.train@gmail.com">hpc.edu.train@gmail.com</a></p>

  <h2>Partners</h2>
          {% for org in site.data.partners.organization %}

          <a href="{{ org.url }}"> <img class="organizations" src="{{ org.logo }}" alt="{{ org.name }}"> </a>


          {% endfor %}

  </div>
  <div class="col-md-4">
    <h2>Community</h2>
    <p>To join the HPC ED Google Group and receive project updates, email <a
        href="mailto:hpc.edu.train@gmail.com">hpc.edu.train@gmail.com</a>.</p>
    <p>To participate in the working group formed to discuss metadata standards for sharing materials, join the <a
        href="https://sighpceducation.acm.org/">ACM SIGHPC Education Chapter</a>.</p>
    <p>Join the ACCESS affinity group <a
        href="https://support.access-ci.org/affinity-groups/hpc-ontologies-and-metadata">HPC Ontologies and
        Metadata</a> to build a set of standardized minimal HPC ontologies and metadata. </p>

  <h3>Upcoming events:</h3>
    <ul>
      <li><a href="https://sc23.supercomputing.org/?post_type=page&p=3480&sess=sess456">Tenth SC Workshop on Best
          Practices for HPC Training and Education</a></li>
      <li>The <strong>FAIR HPC Training</strong> meeting will be held at the SC23 Conference on 11/13/2023 from
        10am-noon in room 711.</li>
      <li><em>HPC-ED Training Resources </em> will be presented at <a
          href="https://hackhpc.github.io/facultyhack-gateways23/">FacultyHack@Gateway2023</a> on 10/18/2023</li>
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
  <script>window.jQuery || document.write('<script src="../../assets/js/vendor/jquery-slim.min.js"><\/script>')</script>
  <script src="../../assets/js/vendor/popper.min.js"></script>
  <script src="../../dist/js/bootstrap.min.js"></script>
