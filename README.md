# Drupal 8 Bootstrap Military Author Theme

This is a Bootstrap Drupal 8 theme for an author to sell his books, blog/share his life and display an "in memory of" page to remember the fallen who he served with.

## Demo

Here's a [live example](https://www.dasalick.com)

## Manual Install

- extract militarytheme to siteroot/themes/
- copy "military_modules" folder from theme and place in your drupal siteroot/modules directory
- download [bootstrap 3 source](https://github.com/twbs/bootstrap/archive/v3.3.7.zip) extract to siteroot/themes/militarytheme/ rename folder to "bootstrap"
- download, extract and enable: bootstrap, ubercart, captcha, recaptcha, juicebox, libraries, slick, slick_ui, blazy, addtoany
- enable blog, book, hero, hero2, gallery

## Drush install

Make sure you've copied the "military_modules" folder into your siteroot/modules directory before running drush.

```
drush pm-enable bootstrap ubercart captcha recaptcha juicebox libraries slick slick_ui blazy addtoany
drush pm-enable blog book hero hero2 gallery
drush config-set system.theme default bootstrap -y
drush pm-uninstall bartik -y
drush pm-enable military -y
drush config-set system.theme default military -y
```

## blazy library

- download [blazy](https://github.com/dinbror/blazy/) and place in your siteroot/libraries folder. If libraries directory doesn't exist, create it.
- make sure to rename the blazy folder from blazy-master to "blazy" and the path siteroot/libraries/blazy/blazy.min.js is correct

## Block Configure

In structure->block layout you will want to place the following blocks:

Top Bar:
- Breadcrumbs
- Primary admin actions
- Status messages
- Tabs

Content:
- Page title
- Main Page content

Secondary:
- Categories

You may also(ideally) wish to make the blocks "carousel bottom", "featurettes", "footer", into custom blocks so that you can dynamically alter them at any time.  Simply copy the contents of each block.block.military_anyblockname from militarytheme/templates/block (without the twig templates e.g. everything between {% block content %} and {% end content %} ), paste it into a new custom block then place the new block into the block layout.

## Blog Configure

configuration -> Account Settings -> Manage fields(tab)

- edit picture field set max resolution to 125 x 157

configuration -> Manage Display(tab)

- edit Picture field format to image style: Medium (220x220)

user account -> edit profile

- add image in the picture field so that it displays beneath the blog postings
- You may want to make a custom block to handle this, as the author description is static. You can simply edit it in military/templates/node/node--blog--full.html

## Hero2 Configure

Adjust Slick options
configuration -> slick

- add optionset

structure -> content types -> hero2 > manage display(tab)
- adjust image field(slick) display settings of heroes2 content type

## License

militarytheme is available under the [Apache 2.0 License](https://github.com/hutchgrant/militarytheme/blob/master/LICENSE).

## Contributing

All contributions will be placed under the same Apache 2.0 license, contributers must agree to that license.
For more information see [contributing](https://github.com/hutchgrant/militarytheme/blob/master/CONTRIBUTING.md).

## Author

**Grant Hutchinson (hutchgrant)**
