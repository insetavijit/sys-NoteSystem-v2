Sure! Here’s a concise summary with a brief overview at the top, focused on making your WordPress setup portable and live via symlink.

---

## Brief Overview:

You set up WordPress using WP-CLI in `/home/avijit/wp-setups/lorem`. To make it live, you created a symlink `/var/www/html/wordpress` pointing to that folder. Permissions were fixed so NGINX could follow the symlink and serve the site properly.

---

## Step-by-Step Summary for Portability and Live Setup

### 1. WordPress Setup via WP-CLI

```bash
#Download it 
wp core download

#configure
wp config create --dbname=wp_lorem --dbuser=root --dbpass=root --dbhost=localhost

#Create DB later or with WP-CLI:
wp db create

#databaSe inputs
wp core install --url="http://localhost" --title="Lorem Site" --admin_user="admin" --admin_password="123" --admin_email="avisoffice@gmail.com"

```

---
### 2. Making Site Live Using Symlink

- Create symlink pointing to your WordPress folder:

```bash

sudo ln -s /home/avijit/WP-DEV-ENV/DEVL/Lorem /var/www/html/wordpress

#Fix permissions so NGINX can access symlinked folders:
sudo chmod o+x /home/avijit
sudo chmod -R o+rX /home/avijit/WP-DEV-ENV/DEVL/Lorem
```

---

### 3. NGINX Considerations

- Ensure your NGINX config root points to `/var/www/html/wordpress`.
- Verify `disable_symlinks` directive is off or not blocking symlinks.
- Check security modules (AppArmor/SELinux) if symlinks are blocked.

---

### 4. Moving / Portability Notes
- You can move files/folders as needed; just update:
    
    - Database (`wp db export` and `wp db import` for moving DB)
        
    - WordPress URLs via WP-CLI:
        
        ```bash
        wp option update home 'http://new-url.com'
        wp option update siteurl 'http://new-url.com'
        ```
        
- Update `wp-config.php` if DB credentials or host change.
    
- Permissions must allow webserver user (nginx/www-data) to access files.
    

---

If you want, I can help you with scripts or more detailed config files for portability or deployment!