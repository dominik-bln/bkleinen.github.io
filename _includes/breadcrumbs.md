{% comment %}
taken from
http://stackoverflow.com/questions/9612235/what-are-some-good-ways-to-implement-breadcrumbs-on-a-jekyll-site
{% endcomment %}

{% capture url_parts %} {{ page.url | remove: "/index.html" | replace:'/'," " }}{% endcapture %}
{% capture num_parts %}{{ url_parts | number_of_words }}{% endcapture %}

{% assign seperator ="&#187;" %}

{% assign previous="" %}
<div class = "breadcrumbs">
  <a href="{{site.baseurl}}">home</a>
 {% if num_parts == "0" or num_parts == "-1" %}
  &nbsp;
 {% else %}
  {{seperator}}

  {% for unused in site.breadcrumb_list limit:num_parts %}
   {% capture first_word %}{{ url_parts | truncatewords:1 | remove:"..."}}{% endcapture %}
  {% capture previous %}{{ previous }}{{ first_word }}/{% endcapture %}

  {% capture url_parts %}{{ url_parts | remove_first:first_word }}{% endcapture %}
  {% capture remaining %}{{ url_parts | number_of_words}}{% endcapture%}

   

   {% if remaining != "0" %}
     <a href="{{site.baseurl}}{{previous}}">{{ first_word }}</a> {{seperator}}
   {% else %}
     {{ first_word }}
   {% endif  %}


  {% endfor %}
 {% endif %}
</div>
