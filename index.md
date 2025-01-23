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
			<img src="../assets/imgs/HPC-Ed.png" alt="HPC-ED logo"
				class="rounded mx-auto d-block">
		</div>
	</div>

	<div class="container">
		<div class="row">
			<div class="col-md-8">
				<h1>HPC-ED: Building a Federated Repository and Increasing Access
					through CyberTraining</h1>
				<p>CyberTraining materials abound, but they can be difficult to find and often have little information about the quality or relevance of offerings. HPC-ED is building a platform for the community to better share and find training materials through a federated repository.</p>
				<ul>
					<li>Organizations and authors retain physical and legal ownership of their materials by sharing only catalog information.</li>
					<li>Organizations can expand local portals to use the best and most appropriate materials from both local and remote sources.</li>
					<li>Learners can take advantage of materials that are reviewed and described more clearly.</li>
					<li>Learners and organizations will quickly and accurately find materials via standardized descriptive tagging.</li>
					<li>Both Learners and Trainers will enjoy improved search based on relevance and quality of materials.</li>
				</ul>
				<p>
					<a
						href="https://www.cac.cornell.edu/about/pubs/HPC%20ED%20CyberTraining.pdf">The HPC-ED pilot</a>
					demonstrated that resource providers, campus portals, schools, and other institutions can both incorporate training from multiple sources into their own familiar interface and publish their local training materials to a much wider audience.</p>
				<hr>

				<h3>Catalog Tools</h3><p><a
						href="https://search-pilot.operations.access-ci.org/hpc-ed-v2/about/">HPC
						Training
						MetaData Pilot Tool</a>-<em>[Beta]</em> Developer and tester
					browsing portal</p>

				<h3>Guides</h3>
				<p> <a href="https://github.com/HPC-ED/HPC-ED.github.io/wiki">Wiki Home</a> -
					Storehouse of documentation/guides supporting HPC-ED tools and events
					including Searching, Publishing, and Adding metadata using our API.
				</p>

				<h3>Contact Us</h3><p><a
						href="mailto:hpc.edu.train@gmail.com">hpc.edu.train@gmail.com</a></p>

			</div>

			<div class="col-md-4">
				<h3>Community</h3>
				<p> <strong><a href="https://groups.google.com/g/hpc-ed">HPC-ED Google
							Group</a></strong> - Join the HPC-ED Google Group for
					project updates, emails, and collaborative opportunities. </p>
				<p>To participate in the working group formed to discuss metadata
					standards for sharing materials, join the <a
						href="https://sighpceducation.acm.org/">ACM SIGHPC Education
						Chapter</a>.</p>
				<p>Join the ACCESS affinity group <a
						href="https://support.access-ci.org/affinity-groups/hpc-ontologies-and-metadata">HPC
						Ontologies and
						Metadata</a> to build a set of standardized minimal HPC ontologies
					and metadata. </p>
				<p><a href="https://tinyurl.com/HPC-ED-Join">Let us know</a> if you want
					to be one of the first to try the new catalog tool we are
					developing.</p>

				<hr>
				<h3>Events</h3>
				<ul style="list-style: none; padding: 0; margin: 0;">
					{%- if site.posts.size > 0 -%}
					{% capture now %}{{'now' | date: '%s' | plus: 0 }}{% endcapture %}
					{% assign reversedposts = site.posts | reverse %}
					{% for post in reversedposts %}
					{% if post.hide == null or post.hide == false %}
					{% capture date %}{{ post.dateofevent | date: '%s' | plus: 0 }}{%
					endcapture %}
					{% if date >= now %}
					<hr style="margin-bottom: 2px">
					<i style="font-size: small">Upcoming Event:</i>
					<li style="list-style:none; list-style-position: inside;">
						<strong>
							{% if post.content.size <= 1 and post.abstract %}
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
						{%- assign date_format = site.minima.date_format | default:
						"%b %-d, %Y" -%}
						<span class="post-meta">{{ post.dateofevent | date: date_format
							}}</span>
					</li>
					{% endif %}
					{%- endif -%}
					{%- endfor -%}
				</ul>

				<ul>
					{% for post in site.posts %}
					{% if post.hide == null or post.hide == false %}
					{% capture date %}{{ post.dateofevent | date: '%s' | plus: 0 }}{%
					endcapture %}
					{% if date < now and forloop.index <= 3 %}
					<li>
						<strong>

							{% if post.content.size <= 1 and post.abstract %}
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
						{%- assign date_format = site.minima.date_format | default:
						"%b %-d, %Y" -%}
						<span class="post-meta">{{ post.dateofevent | date: date_format
							}}</span>
					</li>
					{% endif %}
					{%- endif -%}
					{%- endfor -%}

					{%- endif -%}
				</ul>
			</div>
		</div>

		<hr>

		<div class="row">
			<div class="col-md-12">
				<h2>Partners</h2>
				<div class="row">

					{% assign sorted_orgs = site.data.partners.organization | sort: 'name' %}
					{% for org in sorted_orgs %}
					{% if org.name == "Cornell University Center for Advanced Computing" %}
					<div class="col-md-4" style='padding-bottom: 40px; padding-top: 40px;'>
						<a href="{{ org.url }}"> <img class="organizations" src="{{ org.logo }}"
								alt="{{ org.name }}"> </a>
					</div>
					{% endif %}
					{% endfor %}

					{% assign last_full_row = sorted_orgs.size | divided_by: 3 | times: 3 %}
					{% for org in sorted_orgs %}
					{% unless forloop.index0 >= last_full_row %}
					{% unless org.name == "Cornell University Center for Advanced Computing" %}
					<div class="col-md-4" style='padding-bottom: 40px; padding-top: 40px;'>
						<a href="{{ org.url }}"> <img class="organizations" src="{{ org.logo }}"
								alt="{{ org.name }}"> </a>
					</div>
					{% endunless %}
					{% endunless %}
					{% endfor %}

					{% assign row_mod = sorted_orgs.size | modulo: 3 %}
					{% if row_mod == 1 %}
					<div class="col-md-4"
						style='padding-bottom: 40px; padding-top: 40px;'></div>
					{% elsif row_mod == 2 %}
					<div class="col-md-2"
						style='padding-bottom: 40px; padding-top: 40px;'></div>
					{% endif %}

					{% for org in sorted_orgs %}
					{% if forloop.index0 >= last_full_row %}
					{% unless org.name == "Cornell University Center for Advanced Computing" %}
					<div class="col-md-4" style='padding-bottom: 0px; padding-top: 40px;'>
						<a href="{{ org.url }}"> <img class="organizations" src="{{ org.logo }}"
								alt="{{ org.name }}"> </a>
					</div>
					{% endunless %}
					{% endif %}
					{% endfor %}
				</div>
			</div>
		</div>
	</div>
</main>

<!-- Bootstrap core JavaScript ================================================== -->
<!-- Placed at the end of the document so the pages load faster -->
<script src="https://code.jquery.com/jquery-3.2.1.slim.min.js"
	integrity="sha384-KJ3o2DKtIkvYIK3UENzmM7KCkRr/rE9/Qpg6aAZGJwFDMVNA/GpGFF93hXpG5KkN"
	crossorigin="anonymous"></script>
<script>window.jQuery || document.write('<script src="./assets/js/vendor/jquery-slim.min.js"><\/script>')</script>
<script src="./assets/js/popper.min.js"></script>
<script src="./assets/js/bootstrap.min.js"></script>
