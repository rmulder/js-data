##### 1.3.0 - 11 February 2015

###### Backwards compatible api changes
- #50 - Added a `DS#is(resourceName, instance)` or `Resource#is(instance)` method to check if an object is an instance of a particular resource

###### Backwards compatible bug fixes
- When items are ejected cached collection queries are now checked to see if all the cached items from that query are gone, and if so, the cache query is deleted

##### 1.2.1 - 06 February 2015

###### Backwards compatible bug fixes
- #42 - deserialize and beforeInject are called from the parent relation when loadRelations is used

##### 1.2.0 - 05 February 2015

###### Backwards compatible bug fixes
- Added a `getResource(resourceName)` method to resource definitions so adapters can grab the definitions of a resource's relations

##### 1.1.1 - 05 February 2015

###### Backwards compatible bug fixes
- #46 - "actions" don't inherit basePath properly

##### 1.1.0 - 04 February 2015

##### Backwards compatible API changes
- Allow nested keys in "orderBy" clauses, i.e. `orderBy: 'foo.bar'`
- Added `get` and `set` methods to the instance prototype for getter/setter manipulation of data store items. Use of `set` will trigger immediate recalculation of computed properties on the instance. Both `get` and `set` support nested key names.
- Added a `removeCircular` util method so cyclic objects can be saved without fuss
- #43 - Added `contains` operator to the default filter

##### Backwards compatible bug fixes
- Added missing `createInstance` calls

##### 1.0.0 - 03 February 2015

Stable Version 1.0.0

###### Other
- Upgraded to the latest observe-js

##### 1.0.0-beta.2 - 23 January 2015

###### Backwards compatible API changes
- Updates to defining "actions"

##### 1.0.0-beta.1 - 10 January 2015

###### Breaking API changes
- #30 - Issue with offset. To solve this a `useFilter` option was added, which defaults to `false`. Previously `DS#filter` was used to return cached `findAll` queries, but that had problems. Now, cached items are also tracked by the query that retrieved them, so when you make a query again you consistently get the right data.

###### Backwards compatible API changes
- #6 - Allow logging to be configurable
- #29 - Add version to JSData export
- #31 - Add build for js-data-debug.js which contains lots of debugging statements and a configurable logger.

##### 1.0.0-alpha.5-8 - 05 December 2014

###### Backwards compatible API changes
- #27 - Properly resolve parent params for generating the URL

##### 1.0.0-alpha.5-7 - 05 December 2014

###### Backwards compatible API changes
- #26 - Added the DSCreate instance method

###### Backwards compatible bug fixes
- #23 - DS#findAll: make a copy of options.params if it's passed in and manipulate that

##### 1.0.0-alpha.5-6 - 03 December 2014

###### Backwards compatible bug fixes
- Backport jmdobry/angular-data#262

###### Other
- Optimized utility functions to save several kilobytes off of minified file
- Change detection of nested properties "should" work now

##### 1.0.0-alpha.5-5 - 30 November 2014

###### Breaking API changes
- findInverseLinks, findBelongsTo, findHasOne, and findHasMany now default to true

###### Backwards compatible bug fixes
- Backport jmdobry/angular-data#253

##### 1.0.0-alpha.5-3 - 28 November 2014

###### Backwards compatible API changes
- Added the isectEmpty, isectNotEmpty, |isectEmpty, and |isectNotEmpty filter operators

###### Other
- Fixed file size of browser dist file

##### 1.0.0-alpha.5-3 - 26 November 2014

###### Backwards compatible API changes
- Server-side js-data now uses the Bluebird promise library

##### 1.0.0-alpha.5-2 - 23 November 2014

###### Backwards compatible API changes
- items don't have to be in the data store to call destroy on them anymore

##### 1.0.0-alpha.5-1 - 19 November 2014

Removed DSUtils.deepFreeze

##### 1.0.0-alpha.5-0 - 18 November 2014

###### Breaking API changes
- All hooks now take the resource definition object as the first argument instead of just the name of the resource

###### Backwards compatible API changes
- jmdobry/angular-data#238

##### 1.0.0-alpha.4-3 - 11 November 2014

###### Backwards compatible bug fixes
- #19 - multiple orderBy does not work

##### 1.0.0-alpha.4-2 - 09 November 2014

###### Backwards compatible API changes
- jmdobry/angular-data#227 - Supporting methods on model instances

###### Backwards compatible bug fixes
- jmdobry/angular-data#235 - IE 8 support

##### 1.0.0-alpha.4-1 - 08 November 2014

###### Backwards compatible bug fixes
- Various fixes

##### 1.0.0-alpha.4-0 - 04 November 2014

###### Backwards compatible API changes
- jmdobry/angular-data#208 - ng-repeat $$hashKey affecting hasChanges

###### Backwards compatible bug fixes
- jmdobry/angular-data#225 - If the server returned an empty array for a get request (valid scenario), angular-data throws an exception

##### 1.0.0-alpha.2 - 31 October 2014

###### Backwards compatible API changes
- #20 - es6-promise finally polyfill

##### 1.0.0-alpha.1-2 - 30 October 2014

###### Backwards compatible bug fixes
- Fixed an issue with the options defaults util function

##### 1.0.0-alpha.1-1 - 19 October 2014

###### Backwards compatible API changes
- #10 - Add js-data-schema integration

##### 1.0.0-alpha.1-0 - 13 October 2014

###### Backwards compatible API changes
- #15 - Add beforeCreateInstance & afterCreateInstance

##### 0.4.2 - 06 October 2014

###### Backwards compatible API changes
- #12 - Add expiration capabilities (reapInterval, reapAction, maxAge, DS#reap)

##### 0.4.1 - 01 October 2014

###### Backwards compatible API changes
- #9 - Make all options passed to methods also inherit from Resource defaults

###### Backwards compatible bug fixes
- jmdobry/angular-data#195 - throw an error when you try to inject a relation but the resource for it hasn't been defined

###### Other
- Added official support for NodeJS

##### 0.4.0 - 25 September 2014

###### Breaking API changes
- Refactored from `baseUrl` to `basePath`, as `baseUrl` doesn't make sense for all adapters, but `basePath` does
- Made `notify` configurable globally and per-resource

##### 0.3.0 - 22 September 2014

###### Backwards compatible API changes
- Added `beforeDestroy` and `afterDestroy` to `DS#destroyAll`
- Added `eagerEject` option to `DS#destroyAll` and `DS#destroy`

##### 0.2.0 - 20 September 2014

###### Backwards compatible API changes
- jmdobry/angular-data#145 - Add "useClass" option to inject, find, findAll, create
- jmdobry/angular-data#159 - Find which items from collection have changed with lastModified
- jmdobry/angular-data#166 - Add ID Resolver
- jmdobry/angular-data#167 - Default params argument of bindAll to empty object
- jmdobry/angular-data#170 - Global callbacks
- jmdobry/angular-data#171 - "not in" query
- jmdobry/angular-data#177 - Allow promises to be returned in lifecycle hooks

###### Backwards compatible bug fixes
- jmdobry/angular-data#156 - cached findAll pending query doesn't get removed sometimes
- jmdobry/angular-data#163 - loadRelations shouldn't try to load a relation if the id for it is missing
- jmdobry/angular-data#165 - DS.hasChanges() reports changes after loading relations

###### Other
- Moved api documentation out of comments and into the GitHub wiki
- Re-organized code and shaved 5.5kb off the minified file
