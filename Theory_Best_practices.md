# Performance Best Practices #
  * app engine appstats rpc (profiling): http://www.google.com/events/io/2010/sessions/appstatsrpc-appengine.html
  * managing resources (memcache, : https://developers.google.com/appengine/articles/managing-resources

  * https://developers.google.com/speed/
  * GAE 10 tricks: http://googleappengine.blogspot.com/2009/06/10-things-you-probably-didnt-know-about.html
  * building scalable apps Google IO talk: http://www.google.com/intl/fr/events/io/2009/sessions/BuildingScalableComplexApps.html
  * paging : http://stackoverflow.com/questions/10291291/what-is-the-cost-difference-between-paging-with-a-cursor-or-using-offset/10291896#10291896
  * reference property optimisation : http://blog.notdot.net/2010/01/ReferenceProperty-prefetching-in-App-Engine
  * generic scaling tips : http://www.youtube.com/watch?v=0HJF-PBoRhM&feature=g-vrec

# Google App Engine #
  * Storing json into an entity is better than storing data into entities (ndb handles structured properties)
    * https://groups.google.com/forum/#!msg/google-appengine/D2c4QPEj2Sg/HPezazzlfY4J
    * storing structured data in single entities more often. It's not for every case, but there are so many situations in which the best way to store your data is to simply convert everything to a json string and store it in a text property. And not only to cut cost, but it actually makes a lot of sense to be able to load one entity and immediately have a rich data structure with everything you need for that operation. I believe the new NDB supports structured properties out of the box now.

# Error handling #
  * how to manage datastore exceptions https://developers.google.com/appengine/articles/handling_datastore_errors
# Python #
  * regular expression
    * Always use raw strings when dealing with regular expressions r'\t'
  * python optimisation :
    * http://www.python.org/doc/essays/list2str.html
    * http://wiki.python.org/moin/PythonSpeed/PerformanceTips#String_Concatenation
  * google BigTable optimisation:
    * http://code.google.com/intl/fr/appengine/articles/sharding_counters.html
  * google app engine
    * http://code.google.com/intl/fr/appengine/articles/scaling/overview.html

# Project management #
  * Set milestones including KPI

# Directory structure of the application #
  * http://stackoverflow.com/questions/48458/project-structure-for-google-app-engine
  * http://code.google.com/p/rietveld/

# Software architecture #
  * Software architecture - source: http://slidesha.re/jF7bZv
    * Instrument everything. Start graphing early
    * Cache as much as possible
    * Start working on scaling early
    * don't rely on memcache, and don't rely on the database
    * Don't use mongrel http://rubygems.org/gems/mongrel, use unicorn http://unicorn.bogomips.org/

# Profiling #
  * Profiling - source: http://slidesha.re/iiBOqR
    * Low-level Identify bottlenecks inside of core tools
    * Latency, Network Usage, Memory leaks Methods
    * Network services:
      * tcpdump + tcpdstat, yconalyzer
    * Introspect with Google perftools
  * google page speed online : https://developers.google.com/pagespeed/#url=malik-esi-test.appspot.com&mobile=false&rule=MinifyJavaScript

# Ergonomy, user interface #
  * http://www.useit.com/alertbox/20000319.html
  * http://ui-patterns.com/
  * http://ui-patterns.com/patterns
  * http://www.userplus.com/design-patterns-2/
  * http://www.userplus.com/best-practices-2/

# Increase traffic of the site #
  * http://www.google.com/webmasters/