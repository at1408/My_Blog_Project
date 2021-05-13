<!DOCTYPE html>
{% load staticfiles %}
<html>
    <head>
        <title>Blog Project</title>
        <!-- Latest compiled and minified CSS -->
        <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/css/bootstrap.min.css" integrity="sha384-BVYiiSIFeK1dGmJRAkycuHAHRg32OmUcww7on3RYdg4Va+PmSTsz/K68vbdEjh4u" crossorigin="anonymous">

        <!-- Optional theme -->
        <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/css/bootstrap-theme.min.css" integrity="sha384-rHyoN1iRsVXV4nD0JutlnGaslCJuC7uwjduW9SVrLvRYooPp2bWYgmgJQIXwl/Sp" crossorigin="anonymous">

        {# MEDIUM STYLE EDITOR#}
        <script src="//cdn.jsdelivr.net/medium-editor/latest/js/medium-editor.min.js"></script>
        <link rel="stylesheet" href="//cdn.jsdelivr.net/medium-editor/latest/css/medium-editor.min.css" type="text/css" media="screen" charset="utf-8">


        {# Custom CSS#}
        <link rel="stylesheet" href="{% static 'css/blog.css' %}">

        {# Fonts#}
        <link href="https://fonts.googleapis.com/css?family=Montserrat|Russo+One" rel="stylesheet">





<body class='loader'>


  <nav class="navbar navbar-default techfont custom-navbar">
    <div class="container">


      <ul class="nav navbar-nav">
        <li><a class='navbar-brand bigbrand' href="{% url 'post_list' %}">My Tech blog</a></li>
        <li><a href="{% url 'about'%}">About</a></li>
        <li><a href="https://www.github.com">Github</a></li>
        <li><a href="https://www.linkedin.com">LinkedIn</a></li>

      </ul>

      <ul class="nav navbar-nav navbar-right">
        {% if user.is_authenticated %}
        <li>
          <a href="{% url 'post_new' %}" >New Post</a>
        </li>

        <li>
          <a href="{% url 'post_draft_list' %}">Drafts</a>
        </li>
        <li>
          <a href="{% url 'logout' %}" >Log out</a>
        </li>

        <li>
          <a >Welcome: {{ user.username }}</a>
        </li>
          {% else %}
          <li><a class='nav navbar-right' href="{% url 'login' %}" ><span class="glyphicon glyphicon-user"></span></a></li>
        {% endif %}

      </ul>
  </div>
</nav>

  {# The actual blog posts#}
        <div class="content container">
          <h1 class="jumbotron">Welcome to My Blog</h1>
            <div class="row">
                <div class="col-md-8">
                  <div class="blog_posts">
                    {% block content %}
                    {% endblock %}

                  </div>

                </div>
            </div>
        </div>

{# SCRIPTS#}

<script type="text/javascript" src="{% static 'js/blog.js' %}"></script>

</body>
</html>
