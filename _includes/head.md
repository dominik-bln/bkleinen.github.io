    <head>
        <meta charset="{{ site.serverencoding }}">
        <meta http-equiv="X-UA-Compatible" content="IE=edge,chrome=1">
        <title>{{ page.title }}</title>
        <meta name="viewport" content="width=device-width">

        <!-- syntax highlighting CSS -->
        <link rel="stylesheet" href="{{site.baseurl}}css/syntax.css">
        {% if page.wide_layout %}
              <link rel="stylesheet" href="{{site.baseurl}}css/wide.css">
        {% else %}
        <link rel="stylesheet" href="{{site.baseurl}}css/responsive.css">
        {% endif %}
    </head>
