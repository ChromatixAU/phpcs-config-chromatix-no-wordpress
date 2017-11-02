# phpcs-config-chromatix-no-wordpress

Like [phpcs-config-chromatix](https://github.com/ChromatixAU/phpcs-config-chromatix), but without the rules for things that can only be used in the WordPress context.

**This config is still in development.** If you have suggestions for improvement or if you disagree with anything this config makes you do, feel free to file an issue. If it is not specific to this config, please file upstream (such as at [phpcs-config-chromatix](https://github.com/ChromatixAU/phpcs-config-chromatix)).

## Installation

Install globally to use on any project:

    composer install --global chromatix/phpcs-config-chromatix-no-wordpress

Install locally to one project:

    composer install chromatix/phpcs-config-chromatix-no-wordpress

You'll also need to have [phpcs](https://www.squizlabs.com/php-codesniffer) installed in the same manner, and [set your phpcs `installed_paths`](https://github.com/squizlabs/PHP_CodeSniffer/wiki/Configuration-Options#setting-the-installed-standard-paths) like follows:

    vendor/bin/phpcs --config-set installed_paths ../../chromatix,../../wp-coding-standards/wpcs

It's probably ideal to do this in a [`post-install-cmd` script in your `composer.json`](https://getcomposer.org/doc/articles/scripts.md).

## Usage

Add this to your `phpcs.xml` file:

    <?xml version="1.0"?>
    <ruleset>
      <rule ref="phpcs-config-chromatix-no-wordpress"/>
    </ruleset>

Then:

* Using globally?  
  Run `phpcs *.php`.

* Using locally?  
  Run `vendor/bin/phpcs *.php`

You'll probably find it more useful to add a script to your `composer.json`:

    "scripts": {
      "lint": "find . -type d \\( -name '.git' -o -name 'vendor' -o -name 'node_modules' \\) -prune -o -type f -name '*.php' -print | xargs phpcs"
    }

## See also

* [phpcs-config-chromatix](https://github.com/ChromatixAU/phpcs-config-chromatix)
* [eslint-config-chromatix](https://github.com/ChromatixAU/eslint-config-chromatix)
* [stylelint-config-chromatix](https://github.com/ChromatixAU/stylelint-config-chromatix)

## License

[MIT](LICENSE).
