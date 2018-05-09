# DidUngar/BoostrapBundle
## Setup :

To install the Bundle it is enough that the basic tpl extend of the desired version

Please edit this file : /www/api.list/app/Resources/views/base.html.twig like this :
```
{% extends 'DidUngarBootstrapBundle:Default:base.html.twig' %}

{% block title %}Title of site{% endblock %}
{% block projectname %}{% endblock %}

{# Menu : #}
{% block sidebar_items %}
	<li><a href="/">Home</a></li>
	<li  class="dropdown">
		<a href="#" class="dropdown-toggle" data-toggle="dropdown" role="button" aria-haspopup="true" aria-expanded="false">Banks <span class="caret"></span></a>
		<ul class="dropdown-menu">
			<li><a href="//google.com">google</a></li>
		</ul>
	</li>
{% endblock %}

{% block stylesheets %}
{{ parent() }}
<link rel="stylesheet" href="/style.css" type="text/css" media="screen" />
{% endblock %}
```