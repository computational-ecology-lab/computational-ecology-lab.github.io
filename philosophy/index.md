---
title: The philosophy of the Lab (and some resources)
layout: default
group: philosophy
---

{% include carousel.html height="40" unit="%" duration="5" filter="img/birds/" controlposition="90%" indicatorposition="90%" %}

# The philosophy of the Lab (and some resources)

<div class="accordion" id="accordionCompact">
{% for item in site.data.philosophy %}
<!-- Item Block -->
<div class="card">
<div class="card-header" id="heading{{item.id}}">
<h2 class="mb-0" type="button" data-toggle="collapse" data-target="#{{item.id}}" aria-expanded="true" aria-controls="{{item.id}}">
{{item.title}}
</h2>
</div>

<div id="{{item.id}}" class="collapse {% if item.show %}show{% endif %}" aria-labelledby="heading{{item.id}}">
<div class="card-body">
{{item.body}}
</div>
</div>
</div>
<!-- End  block -->
{% endfor %}
</div>
