# Wordpress docker image
official wordpress based image with:

- persistent storage for `uploads`, `plugins` and `themes`
- wp-cli
- automated wordpress installation
- automated plugin installation
- automated themes installation
- custom php.ini and memory limits
- plugin wp-stateless for storing `uploads` in Cloud Bucket
- plugin cloudflare-flexible-ssl for proper working redirects with flexible ssl with CloudFlare

## ENV variables
- `WORDPRESS_DB_HOST` db host
- `WORDPRESS_DB_PASSWORD` db password (user is root)
- `WP_URL` wordpress URL
- `WP_TITLE` wordpress page title (used only when installing wordpress the first time)
- `WP_USER` admin username (used only when installing wordpress the first time)
- `WP_PASSWORD` admin password (used only when installing wordpress the first time)
- `WP_EMAIL` admin email (used only when installing wordpress the first time)
- `WP_FORCE_VERSION` force wordpress version upgrade (downgrade) after start via wp-cli

## Example usage:
```
docker run -v $(pwd)/volume:/var/app-storage/ -e WORDPRESS_DB_HOST='mariadb' -e WORDPRESS_DB_PASSWORD='secretpassword' -e WP_URL='example.net' -e WP_TITLE='My Awesome Wordpress Site' -e WP_USER='admin' -e WP_PASSWORD='secretpasswordofadmin' WP_EMAIL='admin@example.net' ackee/wordpress
```

