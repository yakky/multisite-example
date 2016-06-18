djangocms-multisite example
===========================

This is an example site using djangocms-multisite

Test
----

* git clone git@github.com:yakky/multisite-example.git
* cd multisite-example
* virtualenv env
* env/bin/activate
* pip install -r requirements.txt
* python manage.py migrate
* python manage.py createsuperuser
* python manage.py runserver

Configured sites
----------------

djangocms-multisite is configured for two sites:

* www.example.com
* www.example2.com

and a number of aliases for each.

Before running the project, configure your local resolution to map ``www.example.com`` and
``www.example2.com`` to localhost::

    127.0.0.1  www.example.com
    127.0.0.1  www.example2.com

The shipped database is configured for the above two domains, with django CMS root at the
following URLS:

* http://www.example.com:8000/en/
* http://www.example2.com:8000/en/subpath/

The latter is make it easy to test whether the site 1 or site 2 urlconf has been loaded.

Starting from empty database
----------------------------

If starting from a fresh databasem, before testing you have to configure the multisite environment:

* Edit the domain for the first (only) site to ``www.example.com``
* Add site two with ``www.example2.com`` domain
* Eventually change the urlconfs related to each site by editing ``MULTISITE_CMS_URLS`` setting.

