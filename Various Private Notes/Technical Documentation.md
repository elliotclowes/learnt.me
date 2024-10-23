## Seedbox

### WordPress

#### Setting it up

[This was the Claude chat](https://claude.ai/chat/d8ce08ea-e074-4c1c-b1b2-60e6b0eca3d0) that got me to set it up.

#### Backing it up

I'm going to look into plugins. But for now the best way is via a script. I asked Claude and it created one for me that will:
- Backup the WordPress files and the database to `/home/elliot/_backups/elliotmy`
- Keep backups for 90 days before deleting them.

Here it is:
```#!/bin/bash

  

# Set directories

BACKUP_DIR="/home/elliot/_backups/elliotmy"

PROJECT_DIR="/home/elliot/wordpress/elliotmy"

DATE=$(date +%Y%m%d_%H%M%S)

  

# Create backup directory if it doesn't exist

mkdir -p "$BACKUP_DIR"

  

# Change to project directory

cd "$PROJECT_DIR"

  

# Backup MySQL database

docker-compose exec -T db mysqldump -u ejclowes91 -p'c3nciG.nd4GFw-_EzbU2.rW@CsFo2piHn2Yq' wpelliotmydb91 > "$BACKUP_DIR/database_$DATE.sql"

  

# Backup WordPress files

docker-compose exec -T wordpress tar czf - /var/www/html > "$BACKUP_DIR/wordpress_files_$DATE.tar.gz"

  

# Delete backups older than 90 days (optional)

find "$BACKUP_DIR" -type f -mtime +90 -delete
```


#### Automating the running of the backup script

```# Open crontab editor
crontab -e

# Add this line to run backup daily at 2 AM
0 2 * * * /home/elliot/_backup-scripts/elliotmy.sh
```

#### Automating the local download of backups

