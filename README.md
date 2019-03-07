# Digital Initiatives: Paragraphs

This custom module contains configuration for paragraph types and shared fields. The goal is for this to allow reusable configuration for paragraphs across multiple projects.

Note: This is still very much a work-in-progress.

## How to use

In your Drupal project's `composer.json` file, add the following into `repositories` property, which should look similar to the following:

```
"repositories": [
  {
    "type": "composer",
    "url": "https://packages.drupal.org/8"
  },
  {
    "type": "composer",
    "url": "https://asset-packagist.org"
  },
  {
    "type": "git",
    "url": "https://github.com/stlawu/di_paragraphs"
  }
],
```

Also make sure you have specified the `installer-paths` for `drupal-custom-module` packages, such as below: 

```
"extra": {
  "installer-types": [
    "bower-asset",
    "npm-asset",
    "library",
    "component"
  ],
  "installer-paths": {
    "web/core": ["type:drupal-core"],
    "web/libraries/{$name}": [
      "type:drupal-library", 
      "type:bower-asset", 
      "type:npm-asset"
    ],
    "web/modules/contrib/{$name}": ["type:drupal-module"],
    "web/modules/custom/{$name}": ["type:drupal-custom-module"],
    "web/profiles/contrib/{$name}": ["type:drupal-profile"],
    "web/profiles/custom/{$name}": ["type:drupal-custom-profile"],
    "web/themes/contrib/{$name}": ["type:drupal-theme"],
    "web/themes/custom/{$name}": ["type:drupal-custom-theme"],
    "drush/contrib/{$name}": ["type:drupal-drush"]
},

```

Then, run `composer require stlawu/di_paragraphs`. This should install the module in your project's `web/modules/custom` directory.
