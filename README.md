WordPress Demo **Backend** for https://github.com/mandrasch/sveltekit-headless-wp-rest-demo. 

Work in progress. 👨‍💻

## Local setup

```
# Install DDEV on your local machine:
# https://ddev.readthedocs.io/en/latest/users/install/ddev-installation/
ddev start && ddev composer install
ddev exec cp .env.example .env
# import example database snapshot
ddev snapshot restore --latest
# copy some assets for demo purposes
ddev exec "rsync -avz --mkpath .upload-examples/uploads/ web/app/uploads/"
```

https://sveltekit-pico-headless-wp.ddev.site/wp-admin/
User: admin
PW: !jIO\*D^^XtAF9N4x9Z

## How was this created?

```
# Backend - WordPress with bedrock
# https://ddev.readthedocs.io/en/stable/users/quickstart/#wordpress -> bedrock
ddev config --project-type=wordpress --docroot=web --create-docroot
ddev start
ddev composer create roots/bedrock
# create .env
# install via browser
ddev launch
# Copy ACF pro into /web/app/plugins/, activate
ddev wp plugin activate advanced-custom-fields-pro
# Headless Mode plugin https://wordpress.org/plugins/headless-mode/
ddev composer require "wpackagist-plugin/headless-mode":"0.4.0"

# save database snapshot for easy demo setup
ddev snapshot
```

## License

My own work (mostly config stuff) is available as CC0 / Public Domain, no need for attribution. 

Please see `composer.json` and `package.json` for a list of all used Open Source libraries and their respective licenses.
