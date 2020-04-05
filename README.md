# vscode-devcontainer-wordpress

This contains the configuration necessary for setting up WordPress development using VSCode Dev Containers.
A MariaDB and WordPress devlopment container are started, and Wordpress is automatically installed and available at http://localhost:8080.

## Configuration

By default the container is configured for plugin development, but you can switch to theme development by changing the volume for the WordPress service in `docker-compose.yml`

Additional WordPress settings can be configured in `.devcontainer/wp-setup.sh`. By setting `WP_RESET` to `true`, the container will rebuild the WordPress instalation from scratch every time it is loaded. 

## Data folder

Any `.sql` files placed `.devcontainer/data` will be automatically imported when your site is built (using `wp db import`). It is up to you to ensure table name prefixes will match (set them to wp_).

Anything placed in the `plugins` folder (single files or folders) will be copied into the WordPress plugins folder and activated as a plugin. This enables things like defining custom post types relevant to your imported data set, but not part of the development process.

## Included Tools

- XDebug
- WP-CLI
- Composer
- NodeJS (TODO)
- PHP/WordPress extensions for VSCode (see `devconatainer.json`)