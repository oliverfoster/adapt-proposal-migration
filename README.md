# adapt-proposal-migration
A proposal for achieving version migration for Adapt Framework content

## Problem
Adapt content is built using a single version of Adapt Framework and associated plugins. Authoring Tool users have a set of courses built against one version of Adapt Framework and associated plugins that need to be periodically upgraded to a new framework and plugin version. Currently this process suffers when certain changes occure

## Affected languages
* JSON - schema changes
  * framework > framework - verson change (simple upgrade)
  * plugin > plugin - version change or plugin exchange (plugin upgrade, obscelesence or direct replacement)
  * framework <> plugin - features moved between the framework and a plugin (spoor + tracking)
* LESS - themes with version-specific plugin overrides

## Future discussions
* Migrating Authoring Tool JSON in the database using server-side database scripts
* Supporting multiple framework and plugin versions in a single Authoring Tool instance
* Allowing batch imports from one Authoring Tool instance to another

## Current suggested first steps
* Hold off on major Authoring Tool migration amends
* Rely on existing import and export behaviour
* Allow the Authoring Tool to import mismatched versions by including a warning for the user
* Provide a framework based mechanism to migrate JSON from one framework and plugin version to another

## Suggestion workflow
1. Setup new Authoring Tool instance with new framework and plugin versions
2. Export course from old Authoring Tool instance
3. Run script to migrate data
  * Warn about non-existant plugin
  
4. Import course into new Authoring Tool instance




