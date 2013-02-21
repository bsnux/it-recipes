Using CoffeeScript with Django
===============================

This documents shows you a simple example for using *Django* with *CoffeeScript*.

Installing CoffeeScript
------------------------

Basically, you only need to execute following sentences (*Debian* based operating systems):

	$ sudo apt-get install npm
	$ npm install -g coffee-script

Installing required Python packages
-----------------------------------

    $ pip install django-compressor
    $ pip install BeautifulSoup


Adding required configuration
------------------------------

Your *settings.py* file should contain following properties:

	INSTALLED_APPS += ('compressor', )

	STATICFILES_FINDERS += ('compressor.finders.CompressorFinder',)

	COMPRESS_PRECOMPILERS = (
	    ('text/coffeescript', 'coffee --compile --stdio'),
	)

### Development environment

Usually for your *development* environment you should use following property:

	DEBUG = True

Then you should set following property:

	COMPRESS_ENABLED = False

### Production environment

Don't forget to add next property:

	COMPRESS_ENABLED = True

Also, in order to generate right JS compressed files, you need to execute next command:

	$ python manage.py compress

Template
--------

Add next line to your template:

	{% compress js %}
    	<script type="text/coffeescript" src="{{ STATIC_URL }}js/test.coffee"></script>
	{% endcompress %}

Coffeescript file
------------------

Open your favorite text editor and create a new file called *test.coffee*, then add following line:

	console.log 'Here I am!'
