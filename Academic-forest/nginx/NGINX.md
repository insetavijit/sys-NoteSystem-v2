Got it — I’ll make you a **complete, detailed Nginx syllabus** so you can learn it in a structured way, from beginner to pro.  
We’ll break it into **phases**, each with **topics, examples, and practice tasks**.

---

# **📚 Nginx Learning Syllabus (From Zero to Pro)**

---

## **Phase 1 – Foundations**

**Goal:** Understand what Nginx is, how it works, and how to control it.

### Topics

1. **Introduction to Nginx**
    
    - What is Nginx and why it’s popular
        
    - Nginx vs Apache
        
    - Use cases: static files, reverse proxy, load balancing
        
2. **Installing Nginx**
    
    - Installing on Debian/Ubuntu
        
    - Checking service status
        
    - Basic file structure (`/etc/nginx/`, `/var/www/`)
        
3. **Nginx Configuration Basics**
    
    - Main config file: `/etc/nginx/nginx.conf`
        
    - The `http`, `server`, `location` contexts
        
    - `listen`, `server_name`, `root`, `index`
        
4. **Basic Static Website Hosting**
    
    - Creating `/var/www/your-site`
        
    - Configuring a server block
        
    - Setting up `index.html`
        

### Practice

- Install Nginx and serve a static HTML page on `localhost`
    
- Change port from 80 to another port (e.g., 8080)
    

---

## **Phase 2 – Static File Handling**

**Goal:** Serve HTML, CSS, JS, images efficiently.

### Topics

1. **Directory Structure**
    
    - `root` vs `alias`
        
2. **try_files**
    
    - Fallback options (`try_files $uri $uri/ =404;`)
        
3. **Index files**
    
    - Default vs custom index
        
4. **Error Pages**
    
    - Custom 404, 500 error pages
        
5. **Autoindex**
    
    - Enable/disable directory listing
        

### Practice

- Serve a website with custom 404 page
    
- Enable autoindex for a downloads folder
    

---

## **Phase 3 – PHP Integration**

**Goal:** Serve PHP apps like WordPress.

### Topics

1. **PHP-FPM**
    
    - What it is and how Nginx talks to it
        
2. **location ~ .php$**
    
    - fastcgi_pass, fastcgi_params
        
3. **Security Basics**
    
    - Disabling `.htaccess` processing
        
    - Denying access to `.git` folders
        

### Practice

- Install PHP-FPM and serve a `phpinfo()` file
    
- Host a WordPress site locally
    

---

## **Phase 4 – Multiple Sites (Virtual Hosts)**

**Goal:** Host multiple domains/subdomains.

### Topics

1. **sites-available** & **sites-enabled**
    
2. **Enabling/disabling sites** with `ln -s`
    
3. **Name-based virtual hosting**
    
4. **Port-based hosting**
    

### Practice

- Host two different HTML sites on two domains
    
- Host one site on port 8001 and another on port 8080
    

---

## **Phase 5 – HTTPS & Security**

**Goal:** Secure traffic with SSL/TLS.

### Topics

1. **HTTPS Basics**
    
    - SSL/TLS handshake
        
    - Self-signed vs trusted certificates
        
2. **Certbot (Let’s Encrypt)**
    
    - Auto-renewal
        
3. **Security Headers**
    
    - `Strict-Transport-Security`
        
    - `X-Frame-Options`
        
4. **Rate Limiting & Basic Auth**
    

### Practice

- Enable HTTPS on a test domain
    
- Protect a directory with username/password
    

---

## **Phase 6 – Reverse Proxy & Load Balancing**

**Goal:** Use Nginx as a proxy server.

### Topics

1. **Reverse Proxy**
    
    - `proxy_pass`
        
    - Passing headers
        
2. **Load Balancing**
    
    - Round-robin, least connections
        
3. **Caching**
    
    - `proxy_cache`, `expires`, `cache-control`
        

### Practice

- Proxy requests from Nginx to a Node.js app
    
- Set up two backend servers and load balance them
    

---

## **Phase 7 – Performance Optimization**

**Goal:** Make Nginx fast and efficient.

### Topics

1. **Gzip Compression**
    
2. **HTTP/2**
    
3. **Browser Caching**
    
4. **Connection Tuning**
    
    - `worker_processes`, `worker_connections`
        

### Practice

- Enable Gzip compression for CSS/JS
    
- Test with GTmetrix or Lighthouse
    

---

## **Phase 8 – Advanced Topics**

**Goal:** Master production-level Nginx.

### Topics

1. **URL Rewriting**
    
    - `rewrite` & `return`
        
2. **GeoIP blocking**
    
3. **Access logs customization**
    
4. **Fail2Ban integration**
    

### Practice

- Redirect HTTP → HTTPS
    
- Block requests from specific countries
    

---

## **Phase 9 – Debugging & Monitoring**

**Goal:** Find and fix problems quickly.

### Topics

1. **Logs**
    
    - `/var/log/nginx/access.log`
        
    - `/var/log/nginx/error.log`
        
2. **Testing Config**
    
    - `nginx -t`
        
3. **Real-time Monitoring**
    
    - `ngxtop`, `GoAccess`
        

### Practice

- Break config intentionally, fix it using logs
    
- Monitor live traffic with `tail -f`
    

---

If you follow this syllabus **step-by-step** and actually do the practice tasks, you’ll not only know _how_ to use Nginx — you’ll understand _why_ it works that way.

---

If you want, I can now **turn this syllabus into a 30-day learning plan** with exact daily tasks so you get hands-on practice every day. That way, it’s not just reading — it’s doing.