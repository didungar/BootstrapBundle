# DidUngar/BootstrapBundle
## Setup :

Adding to composer.json :
```
    "repositories": [
        {
            "type": "git",
            "url": "git@github.com:didungar/BootstrapBundle.git"
        }
    ],
```

Adding to project :
```
composer require "DidUngar/BootstrapBundle"
```

To install the Bundle it is enough that the basic tpl extend of the desired version

Edit app/AppKernel.php for adding the bundle :
```
{# SF version < 4 #}
new DidUngar\BootstrapBundle\DidUngarBootstrapBundle(),
```
Edit config/bundles.php for adding the bundle :
```
{# SF version >= 4 #}
DidUngarBootstrapBundle\DidUngarBootstrapBundle::class => ['all' => true],
```

Please edit this file :
```
/www/your_project/app/Resources/views/base.html.twig
```
For Symfony >4, use file : /www/your_project/templates/base.html.twig
like this :
```
{# SF version > 3 #}
{% extends '@DidUngarBootstrap/Default/base.html.twig' %}
{# SF version < 3 #}
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
### Debug :
Si le PR n'est pas bien pris en compte (SF4) vous pouvez modifier la configuration de twig
```
{# SF version < 4 #}
twig:
    paths:
        - '%kernel.project_dir%/templates'
        - '%kernel.project_dir%/vendor/DidUngar/BootstrapBundle/templates'
{# SF version >= 4 #}
twig:
    default_path: '%kernel.project_dir%/templates'
    debug: '%kernel.debug%'
    strict_variables: '%kernel.debug%'
    paths:
        '%kernel.project_dir%/vendor/DidUngar/BootstrapBundle/templates' : DidUngarBootstrap
```
Avec comme base :
```
{% extends 'Default/base.html.twig' %}
```


