# adapt-proposal-migration
A proposal for achieving version migration for Adapt Framework content

## Problem
Adapt content is built using a single version of Adapt Framework and associated plugins. Authoring Tool users have a set of courses built against one version of Adapt Framework and associated plugins. In both environments it is neccessary to periodically upgrade the framework and plugin version. Currently this process can result in broken courses.

### Affected areas
* JSON - schema changes
  * framework <> framework - simple upgrade or downgrade
  * plugin <> plugin - plugin upgrade, obscelesence or direct replacement
  * framework <> plugin - features moved between the framework and plugins (spoor + tracking)
* LESS - themes with version-specific plugin overrides

### On hold
* Major Authoring Tool migration behaviour
* Theme migrations
* Downgrading plugins

### Interim discussions
* Migrating Authoring Tool JSON in the database using server-side database scripts

### Future discussions
* Supporting multiple framework and plugin versions in a single Authoring Tool instance
* Allowing batch imports from one Authoring Tool instance to another

## Proposal

### First steps
* Use existing Authoring Tool import and export behaviours
* Allow Authoring Tool to import mismatched versions by adding a UI warning for the users
* Provide a framework based mechanism to migrate JSON from one framework and plugin version to another

### Workflow
1. Setup new Authoring Tool instance with new framework and plugin versions
2. Export course from old Authoring Tool instance
3. Run script to migrate data
4. Import course into new Authoring Tool instance

### Outline
* Start framework + plugins
* End framework + plugins
* Starting version numbers of framework + plugins (derivable from start framework/plugin)
* Finishing version numbers of framework + plugins (derivable from end framework/plugin)
* Plugin migration behaviour (should live in end framework/plugin)
* Custom migration behaviour (provide a mechanism for custom migration-time behaviour)  
* Plugin conflict resolution
  * Non-existent plugin (warn, end or swap for text)
  * No migration behaviour available (end or swap for text)




