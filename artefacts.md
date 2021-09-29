---
layout: default2.2
---

{%- assign date_format = site.minima.date_format | default: "%a, %b %-d, %Y" -%}
<h2 class="text-center aigelist-blue articles-section-header"><i class="bi bi-gem" title="Artefacts" alt="Artefacts"></i> Artefacts</h2>

<hr class="pb-2">

<section id="resources">
    <div class="container">
        <div class="row row-cols-1 row-cols-sm-2 row-cols-md-3 g-3" style="padding-bottom: 2rem">
        <!-- START RESOURCES -->
            {% assign artefacts = site.data.artefacts %}
            {% for artefact in artefacts %}
            <div class="col">
                <div class="card shadow-sm h-100">
                    <div class="card-header resources-card-header">
                        <span class="resources-card-header-text">
                        {% if artefact.link == '' %}
                            <i class="icons" title="{{ artefact.icon-alt }}" alt="{{ artefact.icon-alt }}" style="--icon-size: 22px; vertical-align: text-bottom">
                                <svg><use xlink:href="{{ artefact.icon-link | prepend: site.url }}"></use></svg>
                            </i> {{ artefact.header }}
                        {% else %}
                            <a class="text-white font-weight-bold" href="{{ artefact.link | prepend: site.url }}"><i class="bi bi-file-earmark-arrow-down-fill"></i> {{ artefact.title }}</a>
                        {% endif %}
                        </span>
                    </div>
                    <div class="card-body">
                        <h5 class="resources-card-title">
                        {% if artefact.link == '' %}
                            {{ artefact.title }} #{{ forloop.index }}
                        {% else %}
                            <a href="{{ artefact.link | prepend: site.url }}"><i class="bi bi-file-earmark-arrow-down-fill"></i> {{ artefact.title }}</a>
                        {% endif %}
                        </h5>
                        <p class="card-text resources-card-text">
                            {{ artefact.description }}
                        </p>
                    </div>
                    <div class="card-footer resources-card-footer">
                        <small class="text-white">
                            <i class="icons" title="{{ artefact.icon-alt }}" alt="{{ artefact.icon-alt }}" style="--icon-size: 22px; vertical-align: text-bottom">
                                <svg><use xlink:href="{{ artefact.icon-link | prepend: site.url }}"></use></svg>
                            </i>
                        </small>
                        &nbsp;
                        <small class="text-white">
                            <i class="bi bi-tag-fill" title="Tags" alt="Tags"></i>
                            {{ artefact.tags }}
                        </small>
                    </div>
                </div>
            </div>
            {% endfor %}
        <!-- END RESOURCES -->
        </div> 
    </div>
</section>