# adapt-proposal-migration
A proposal for achieving version migration for Adapt Framework content

### Problem
Adapt content is built using a single version of Adapt Framework and associated plugins. Authoring Tool users have a set of courses built against one version of Adapt Framework and associated plugins. In both environments it is neccessary to periodically upgrade the framework and plugin version. Currently this process can result in broken courses.

### Affected areas
* JSON - schema changes
  * framework <> framework - simple upgrade or downgrade
  * plugin <> plugin - plugin upgrade, obscelesence or direct replacement
  * framework <> plugin - features moved between the framework and plugins (spoor + tracking)
* LESS - themes with version-specific plugin overrides

### Future discussions
* Migrating Authoring Tool JSON in the database using server-side database scripts
* Supporting multiple framework and plugin versions in a single Authoring Tool instance
* Allowing batch imports from one Authoring Tool instance to another

### Current exclusions
* No major Authoring Tool migration amends
* Don't worry about theme migration at present
* Don't worry about downgrading plugins

### Current suggested first steps
* Use existing Authoring Tool import and export behaviours
* Allow Authoring Tool to import mismatched versions by adding a UI warning for the users
* Provide a framework based mechanism to migrate JSON from one framework and plugin version to another

### Suggested workflow
1. Setup new Authoring Tool instance with new framework and plugin versions
2. Export course from old Authoring Tool instance
3. Run script to migrate data
4. Import course into new Authoring Tool instance

### Data requirements
* Starting version numbers of framework + plugins (export derivable)
* Finishing version number of framework + plugins (not easy)
* Plugin migration behaviour (lives in the plugin)
* Custom migration behaviour (provide a mechanism for custom run migration-time behaviour)  
  * Alternative plugin (1:1 component / extension exchange)  
  * Manually define plugin migration  
* Plugin conflict resolution:
  * Non-existent plugin (warn, end or swap for text)
  * No migration behaviour available (end, swap for text)




