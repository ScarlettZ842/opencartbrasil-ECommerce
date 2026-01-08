## Quick Start with Docker

### Prerequisites

- Docker and Docker Compose installed on your system
- 2GB of available RAM
- Port 8080 available

### One-Command Setup

```bash
docker compose up -d --build
```

### Access the Application

After running the command above, the application will be automatically installed and ready to use:

- **Storefront**: http://localhost:8080
- **Admin Panel**: http://localhost:8080/admin

### Default Credentials

- **Admin Username**: `admin`
- **Admin Password**: `admin`

**⚠️ Important**: Change these credentials immediately after first login for security.

### Database Information

The Docker setup includes a MySQL 5.7 database with the following configuration:

| Parameter         | Value                               |
| ----------------- | ----------------------------------- |
| **Host**          | `ocbr_db` (internal Docker network) |
| **Database Name** | `opencartbrasil`                    |
| **Username**      | `store`                             |
| **Password**      | `store`                             |
| **Port**          | `3306`                              |

### Docker Compose Commands

```bash
# Start the application
docker compose up -d

# Stop the application
docker compose down

# View logs
docker compose logs -f

# Restart the application
docker compose restart

# Rebuild and start (after code changes)
docker compose up -d --build

# Remove all containers and volumes (fresh start)
docker compose down -v
```

### What Happens Automatically

The Docker setup includes an automated installation process that:

1. ✅ Waits for MySQL database to be ready
2. ✅ Creates all necessary directories with proper permissions
3. ✅ Installs the OpenCart Brasil database schema
4. ✅ Configures the application automatically
5. ✅ Installs Composer dependencies
6. ✅ Sets up the admin user

**No manual installation required!**

---

### Screenshots

#### Translated Installation:

<img src="./.github/IMAGES/01.jpg">

#### Store Homepage:

<img src="./.github/IMAGES/02.jpg">

#### Admin Control Panel:

<img src="./.github/IMAGES/03.jpg">

#### REST API Documentation:

<img src="./.github/IMAGES/04.jpg">

## Overview

OpenCart Brasil is a fork of OpenCart 3, designed to provide an optimized, updated, and secure version with a special focus on the Brazilian market. It maintains compatibility with the latest stable version of OpenCart and uses the GPLv3 license to ensure that **OpenCart Brasil is and always will be free**.

This repository allows you to analyze the code, report bugs, and submit fixes or improvements to the project.

We recommend all developers follow this repository to receive project updates.

## Online Demo

To access an online demo of OpenCart Brasil and see the store in action <a href="https://www.opencartbrasil.com.br/test-drive-loja" target="_blank">click here</a>.

## Key Features

- **REST API and Webhook support**
- Updated Bootstrap 3.3.7
- Support for scheduled tasks (cron jobs)
- Fully functional affiliate system
- Bug fixes and code optimizations
- NCM and CEST fields for products (Brazilian tax codes)
- SKU field in product options
- **Automatic OpenCart Brasil updates**
- Improved session management
- Improved cookie management
- Improved download management
- Improved customer login process
- Improved customer password encryption
- New currency converter extensions
- Installation process in Brazilian Portuguese
- Command-line installation tool in Brazilian Portuguese
- After installation, store is in Brazilian Portuguese with Real currency
- All demo data and auxiliary data in Brazilian Portuguese

## Changelog

To review all fixes, modifications, and improvements made in each released version <a href="./CHANGELOG.md">click here</a>.

## Automatic Update

To perform an automatic update of OpenCart Brasil, in the store administration, go to the menu **Settings→Maintenance→Update**, click on the "**Update**" tab, and follow the instructions on the page to execute the automatic update.

**Warning:** In rare cases, during the automatic update process an error occurs that does not allow access to the store after replacing the store files. This is caused by the following reasons:

- The file cache created by OCMOD modifications is causing the problem.
- The theme installed in the store has overwritten native OpenCart files.

To resolve, delete all files (except the index.html file) and folders inside the storage/**modification** folder (see the path to the storage folder in the **config.php** file), and re-upload the theme files you are using in the store (if you are using a custom theme).

Depending on the hosting (with low quality), it may be necessary to download the latest version of OpenCart Brasil and re-upload all files from the "**system**" folder, overwriting the files that are already there.

After executing the procedures, access the store administration and go to the menu **Extensions→Modifications**, click the **Update** button to update the modifications cache, then go to the main page of the administration control panel, below the "**Logout**" button, you will see a blue button with a white gear icon inside it, click this button, and in the popup that opens, click the two orange buttons inside the "**Action**" column to update the theme cache.

## Roadmap

### Completed Tasks:

- [x] 100% translated store.
- [x] Automatic updates.
- [x] 100% translated installation.
- [x] Support for scheduled tasks.
- [x] NCM field in product registration.
- [x] CEST field in product registration.
- [x] SKU field in product options.
- [x] New currency converter extensions.
- [x] Session fixes.
- [x] Statistics fixes.
- [x] Config file fixes.
- [x] Catalog API fixes.
- [x] Order editing fixes.
- [x] Points system fixes.
- [x] Affiliate program fixes.
- [x] Google Merchant Center fixes.
- [x] Marketing campaign fixes.
- [x] Contact form fixes.
- [x] Product form fixes.
- [x] Cart library fixes.
- [x] SMTP email sending fixes.
- [x] Checkout failure fixes.
- [x] Downloadable product improvements.
- [x] Session management improvements.
- [x] Core startup and framework improvements.
- [x] Email translation and layout improvements.
- [x] Database communication improvements.
- [x] Customer password encryption improvements.
- [x] Customer password reset improvements in the store.
- [x] Improvements when creating folders and uploading images through the file manager.
- [x] REST API for product management, order history updates, and data listing.
- [x] Webhook to notify external applications via HTTP about product and order updates.

### Tasks in Progress:

- [ ] Brazilian extensions marketplace.

### Upcoming Tasks:

- [ ] Intermediate support for LGPD (Brazilian Data Protection Law).

## Requirements

### ⚠ Warning:

If your hosting service does not offer updated versions of the software mentioned below, switch hosting services, as your store cannot be exposed due to security flaws in outdated software.

If you are the professional who manages the servers that store the store's files and data, do not use the software described below in old versions. Use the minimum recommended versions, ideally using the most recent versions not only for performance reasons, but mainly for security reasons.

### Compatible Web Servers:

- Apache 2.4 or higher.
- Nginx 1.14 or higher.
- LiteSpeed 5.4 or higher.
- OpenLiteSpeed 1.6 or higher.

### OpenSSL:

- 1.0.1c or higher.

### cURL:

- 7.34.0 or higher.

### Compatible Databases:

- MySQL 5.5 or higher (Recommended 5.7 or higher).
- MariaDB 5.5 or higher (Recommended 10.3 or higher).

### Compatible PHP Versions:

- 5.6 or higher (recommended 7.4).

### Minimum Required PHP Settings:

| Directive                  | Value   |
| -------------------------- | ------- |
| `register_globals`         | Off     |
| `magic_quotes_gpc`         | Off     |
| `safe_mode`                | Off     |
| `file_uploads`             | On      |
| `allow_url_fopen`          | On      |
| `open_basedir`             | none    |
| `default_charset`          | UTF-8   |
| `max_execution_time`       | 360     |
| `upload_max_filesize`      | 100M    |
| `post_max_size`            | 100M    |
| `memory_limit`             | 128M    |
| `session.auto_start`       | Off     |
| `session.use_only_cookies` | On      |
| `session.use_cookies`      | On      |
| `session.use_trans_sid`    | Off     |
| `session.cookie_httponly`  | On      |
| `*session.cookie_secure`   | On      |
| `*session.cookie_samesite` | Lax     |
| `session.cache_limiter`    | nocache |
| `session.gc_maxlifetime`   | 3600    |
| `session.gc_probability`   | 1       |
| `session.gc_divisor`       | 100     |

### ⚠ Notes:

Only enable the **session.cookie_secure** directive when HTTPS is working on all pages of your store, otherwise users will not be able to log in. Remember that every store should use a security certificate for secure HTTPS connection.

Only enable the **session.cookie_samesite** directive if you are using PHP 7.3 or higher.

Configure the **session.gc_probability** and **session.gc_divisor** directives according to the number of simultaneous/daily visits the store receives, as they are responsible for when expired session cleanup will occur. For example, if you configure them as follows:

| Directive                | Value |
| ------------------------ | ----- |
| `session.gc_probability` | 1     |
| `session.gc_divisor`     | 100   |

This means that "_on average_" every **100 visits**, there is a **1% probability** that expired session cleanup will be executed, which is more than sufficient for a small store. You can configure more aggressive cleanups (not recommended) as follows:

| Directive                | Value |
| ------------------------ | ----- |
| `session.gc_probability` | 1     |
| `session.gc_divisor`     | 4     |

This means that "_on average_" every **4 visits**, there is a **25% probability** that expired session cleanup will be executed.

The important thing is to **configure the directives wisely**, taking into account statistical analysis of the number of simultaneous/daily visits the store receives, to avoid unnecessary cleanups or too few cleanups. Always keep in mind that the settings should be reassessed when there are changes in the number of simultaneous/daily visits to the store, or when the store is preparing to receive a number of visits above the routine.

**Important:** Don't forget to enable scheduled tasks, as they are complementary in cleaning up expired sessions (there are instructions below on how to enable them).

### Minimum Recommended MySQL/MariaDB Settings:

| Variable              | Value    | Description |
| --------------------- | -------- | ----------- |
| `wait_timeout`        | 30       | 30 seconds  |
| `interactive_timeout` | 30       | 30 seconds  |
| `max_allowed_packet`  | 16777216 | 16M         |

### Required Basic PHP Extensions:

- cURL
- DOM
- Fileinfo
- GD
- MySQLi
- Mbstring
- OpenSSL
- ZLIB
- ZIP
- XML

### ⚠ Notes:

Not compatible with Windows operating system using IIS web server.

Soon the minimum version accepted by OpenCart Brasil will be PHP 7.4, as support for PHP up to version 7.3 will end in December 2021. It doesn't make sense to continue supporting PHP versions that the developers themselves have abandoned, which means these versions will not receive bug fixes and security patches.

## Download

### From the Website:

Download the latest stable version from our website [by clicking here](https://www.opencartbrasil.com.br/download).

### From the Repository:

Download the latest stable version marked as **latest release** [by clicking here](https://github.com/opencartbrasil/opencartbrasil/releases/).

### Using Composer:

```bash
composer create-project opencartbrasil/opencartbrasil folder_name
```

### Using Git Bash:

```bash
git clone --depth 1 https://github.com/opencartbrasil/opencartbrasil.git
cd opencartbrasil
composer install
```

### Using Docker

```bash
docker run -p 80:80 opencartbrasil/opencartbrasil:latest
```

### ⚠ Preparations:

1. Create a MySQL database for the store.
2. Create a MySQL user for the store. **Warning:** In production use a dedicated user for the store.
3. Grant the user access permissions to the store database.

### Through Browser (Manual):

1. Extract the contents of the zip file you downloaded to the server where you will install OpenCart Brasil.
2. Rename the **config_dist.php** and admin/**config_dist.php** files to **config.php**.
3. In a Linux environment, the initial permission for all files should be **644** and for all folders **755**.
4. Through the browser, access the domain where the OpenCart Brasil files are located to start the installation.
5. At the end of the installation, the store will be ready to use.

### Through CLI Interface (Automatic):

Through the command line interface, the store can be installed automatically.

1. Extract the contents of the zip file you downloaded to the server where you will install OpenCart Brasil.
2. In the root directory where the OpenCart Brasil files are located, execute the command line to start the installation.
3. At the end of the installation, the store will be ready to use.

**Example installation through command line on local server:**

```bash
php install/cli_install.php install \
  --db_driver mysqli \
  --db_hostname localhost \
  --db_username root \
  --db_password 123456 \
  --db_database opencartbrasil \
  --db_port 3306 \
  --db_prefix ocbr_ \
  --username admin \
  --password admin \
  --email usuario@dominio.com.br \
  --http_server http://localhost/
```

List of parameters for installation through command line:

| Parameter     | Description                                             | Default   | Required |
| ------------- | ------------------------------------------------------- | --------- | -------- |
| `db_driver`   | Driver for database connection (mysqli, pdo, or pgsql). | mysqli    | No       |
| `db_hostname` | Database server name.                                   | localhost | No       |
| `db_username` | User with permission for the database.                  |           | Yes      |
| `db_password` | Password for the user with permission for the database. |           | Yes      |
| `db_database` | Database name to install the store tables.              |           | Yes      |
| `db_port`     | Port for MySQL database access.                         | 3306      | No       |
| `db_prefix`   | Prefix added to tables created in the database.         | ocbr\_    | No       |
| `username`    | Store administrator access username.                    | admin     | No       |
| `password`    | Store administrator user access password.               |           | Yes      |
| `email`       | Store administrator user email.                         |           | Yes      |
| `http_server` | Store domain with a trailing slash (/).                 |           | Yes      |

## Additional Settings

### Enable Scheduled Tasks (Required):

Executing scheduled tasks is essential for OpenCart Brasil to function properly. Scheduled task execution does not overload store navigation as they run in the background.

Currently the following tasks are scheduled to run in OpenCart Brasil:

- Clean expired sessions once a day.
- Update currency rates once a day.

To execute OpenCart Brasil scheduled tasks, you need to access the **Extensions→Scheduled Tasks** menu through the store administration, copy the line in the **Command** field, and add it to be executed every 1 (one) hour in your hosting's Task Scheduler (Cronjobs or Cron Tasks).

**Important:** If you have never used your hosting's Task Scheduler, ask your hosting support for help on how to use it.

### Enable Friendly URLs on Nginx Web Server (Optional):

Replace the `location / { }` block in your **nginx.conf** file with:

```
location / {
  try_files $uri $uri/ @opencart;
}

location @opencart {
  rewrite ^/sitemap.xml$ /index.php?route=extension/feed/google_sitemap last;
  rewrite ^/googlebase.xml$ /index.php?route=extension/feed/google_base last;
  rewrite ^/system/storage/(.*) /index.php?route=error/not_found last;

  rewrite ^/(.+)$ /index.php?_route_=$1 last;
}

location ~* (\.twig|\.tpl|\.ini|\.log|(?<!robots)\.txt)$ {
  deny all;
}
```



## Support

This repository is not suitable for providing support on using the OpenCart Brasil project.

Only register an Issue to report bugs in the core of the OpenCart Brasil project.

For support related to using the OpenCart Brasil project, use our forum:

https://forum.opencartbrasil.com.br/



## Security Vulnerabilities

If you discover a security vulnerability in the OpenCart Brasil project, send an email to [dev@opencartbrasil.com.br](mailto:dev@opencartbrasil.com.br). All reported vulnerabilities will be immediately addressed if confirmed.

## License

The OpenCart Brasil project is open source software licensed under the [GPL v3](./LICENSE).
