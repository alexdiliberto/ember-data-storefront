# 0.13.0

The `store` service is no longer injected into the LoadableModel mixin. Since this mixin is made to be used with an Ember Data model we can rely on the store property being present. This fixes a bug when directly using the mixin on a model would error.

# 0.12.2

Added the Fastboot Adapter mixin.

# 0.12.1

The new `LoadableStore` mixin is now automatically mixed into the host application's store.

The deprecated `storefront` service was throwing errors on install, which is now fixed.

# 0.12.0

- [ CHANGE ] The `storefront` service has been deprecated. Its methods are now available via the `LoadableStore` mixin which you can use in Ember Data's store. See [the docs](https://embermap.github.io/ember-data-storefront/docs/api/LoadableStore-0.11.1+40effca7) for more.

- [ CHANGE ]The `Loadable` mixin has been renamed to `LoadableModel`. [See the docs](https://embermap.github.io/ember-data-storefront/docs/api/LoadableModel-0.11.1+40effca7).

- [ BREAKING CHANGE ] The force-sync-relationships feature is now implemented as an ESLint warning or Babel plugin. The run-time monkey patch was removed.

    Before:

    ```
    // app/app.js
    import 'ember-data-storefront/ext/force-sync';
    ```

    After:

    ```
    // ember-cli-build.js
    module.exports = function(environment) {
      let ENV = {
        'ember-data-storefront': {
          forceSyncRelationships: 'rewrite'
        }
      };
    }
    ```

# 0.11.0 (Dec 5, 2017)

- Add `loadAll` query API.
- Fix bug with `loadable` not using the correct model name

# 0.10.0 (Nov 10, 2017)

Initial release of storefront. Support for loadable and assert-pre-loaded
