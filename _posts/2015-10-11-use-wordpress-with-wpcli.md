---
layout: page
title: "Manage with wp-cli"
category: management
date: 2015-10-11 03:39:48
published: true
summary: "All WP-palvelu sites come with wp-cli preinstalled and configured for easier commandline management."
---

## Basics
You can use wp-cli in **Vagrant box** and **Production**. Just run this to see all commands:

```bash
$ wp --help
```

> **Note:** You can call ```wp``` command anywhere without ```--path``` parameter because the environment handles paths for you.

More information about wp-cli can be found in [wp-cli.org](http://wp-cli.org)

## Useful commands

### Database export/import (dumping db)
```bash
# Dumps the database to a provided filename
$ wp db export your-dump-filename.sql

# Imports the dump file from file
$ wp db import your-dump-filename.sql
```

### Create user

This creates new administrator user **'admin'** with password **'admin'**:

```bash
$ wp user create admin admin@wordpress.dev --user_role=administrator --user_pass=admin
```

### Search-Replace database contents

After you have pulled database from production it's useful to regex replace urls:

```bash
$ wp search-replace http://original.com http://original.dev
```