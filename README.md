kQuery Twitter Bootstrap
========================

This is a port of the [Twitter Bootstrap Javascript plugins](http://twitter.github.com/bootstrap/javascript.html) to [KRL](http://developer.kynetx.com/display/docs/Home). This module using the version of jQuery embedded within the KRL runtime.

Using the Module
----------------

The Twitter Bootstrap module has been placed in the [Kynetx Public Module Directory](http://apps.kynetx.com/modules/a169x568). To use the module add the following `use module` pragma to the meta section of your ruleset:

    meta {
      ...
      use module a169x568
    }

Actions
-------

### init()

Load the Twitter Bootstrap jQuery plugins. After the plugins are loaded all of the features described in the Twitter Bootstrap documentation will be available.

    rule page_init {
      select when pageview ".*"
			a169x568:init();
    }

To access the functionality of the plugins simple use the embedded version of jQuery within the KRL runtime. For example, to call the modal via javascript:

    emit <<
      $K('#myModal').modal(options)
    >>;
