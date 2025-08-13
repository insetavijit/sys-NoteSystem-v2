```bash
WordPress-Theme-Hierarchy/
├── style.css               [REQUIRED] Theme info & base styles
├── functions.php           [REQUIRED] Enqueue scripts, add theme features
├── index.php                [REQUIRED] Fallback for all templates
│
├── header.php               [COMMON] Site header markup
├── footer.php               [COMMON] Site footer markup
├── sidebar.php              [OPTIONAL] Sidebar content
│
├── home.php                 [SPECIAL] Blog posts index (if static front page set)
├── front-page.php           [SPECIAL] Static homepage
│
├── single.php               [COMMON] Single post fallback
│   ├── single-{post-type}.php  [SPECIAL] Custom post type single view
│
├── page.php                 [COMMON] Single page fallback
│   ├── page-{slug}.php        [SPECIAL] Specific page template by slug
│   └── page-{ID}.php          [SPECIAL] Specific page template by ID
│
├── archive.php              [COMMON] Generic archive fallback
│   ├── category.php           [COMMON] Category archive
│   │   └── category-{slug}.php [SPECIAL] Specific category
│   ├── tag.php                [COMMON] Tag archive
│   │   └── tag-{slug}.php      [SPECIAL] Specific tag
│   ├── taxonomy.php           [SPECIAL] Custom taxonomy fallback
│   │   └── taxonomy-{taxonomy}.php  [SPECIAL] Specific custom taxonomy
│   ├── date.php               [SPECIAL] Date archive
│   ├── author.php             [SPECIAL] Author archive
│   └── archive-{post-type}.php [SPECIAL] Specific custom post type archive
│
├── search.php                [COMMON] Search results
├── 404.php                   [COMMON] Error page
│
├── comments.php              [OPTIONAL] Comment list & form
│
├── template-parts/           [ORGANIZATIONAL] Reusable partials
│   ├── content.php
│   ├── content-single.php
│   └── content-page.php
│
└── assets/                   [ORGANIZATIONAL]
    ├── css/
    ├── js/
    ├── images/
    └── fonts/

```

#### **WordPress Theme Hierarchy**

1. **Required Core Files**
    
    - `style.css` → Theme details + base styles
        
    - `functions.php` → Theme setup, enqueue scripts/styles, add features
        
    - `index.php` → Fallback template for all content types
        
2. **Common Structural Templates**
    
    - `header.php` → Site header markup
        
    - `footer.php` → Site footer markup
        
    - `sidebar.php` → Sidebar markup/content
        
3. **Homepage & Front Page**
    
    - `front-page.php` → Static homepage (if set in WP settings)
        
    - `home.php` → Blog posts index (if front page is static)
        
4. **Single Content Templates**
    
    - `single.php` → Fallback for single posts
        
        - `single-{post-type}.php` → Specific post type single view
            
    - `page.php` → Fallback for single pages
        
        - `page-{slug}.php` → Page template by slug
            
        - `page-{ID}.php` → Page template by ID
            
5. **Archives**
    
    - `archive.php` → Generic archive fallback
        
        - `category.php` → Category archive fallback
            
            - `category-{slug}.php` → Specific category archive
                
        - `tag.php` → Tag archive fallback
            
            - `tag-{slug}.php` → Specific tag archive
                
        - `taxonomy.php` → Custom taxonomy fallback
            
            - `taxonomy-{taxonomy}.php` → Specific custom taxonomy archive
                
        - `date.php` → Date archive (year, month, day)
            
        - `author.php` → Author archive
            
        - `archive-{post-type}.php` → Specific custom post type archive
            
6. **Search & Error**
    
    - `search.php` → Search results
        
    - `404.php` → Not found page
        
7. **Comments**
    
    - `comments.php` → Comment list & form
        
8. **Reusable Template Parts**
    
    - `template-parts/` → Reusable sections
        
        - `content.php`
            
        - `content-single.php`
            
        - `content-page.php`
            
9. **Assets (Organization)**
    
    - `assets/css/` → Stylesheets
        
    - `assets/js/` → JavaScript files
        
    - `assets/images/` → Images
        
    - `assets/fonts/` → Fonts
        

---

Alright — here’s the **WordPress Theme Hierarchy** with both **structure** and **priority order** (how WP decides which file to use first).

---

### **WordPress Theme Hierarchy – Nested List with Priority**

_(From highest specificity → lowest fallback)_

---

1. **Front Page & Blog Page**
    
    - `front-page.php` → Static homepage if set in **Settings → Reading**
        
    - `home.php` → Blog index page (if different from front page)
        
    - `index.php` → Fallback for both
        

---

2. **Single Posts**
    
    - `single-{post-type}.php` → Specific custom post type
        
    - `single.php` → Generic single post
        
    - `singular.php` → Generic fallback for single post/page/custom type
        
    - `index.php` → Last fallback
        

---

3. **Pages**
    
    - `page-{slug}.php` → Specific page by slug
        
    - `page-{ID}.php` → Specific page by ID
        
    - `page.php` → Generic page template
        
    - `singular.php` → Generic single fallback
        
    - `index.php` → Last fallback
        

---

4. **Category Archives**
    
    - `category-{slug}.php` → Specific category by slug
        
    - `category-{ID}.php` → Specific category by ID
        
    - `category.php` → Generic category archive
        
    - `archive.php` → Generic archive fallback
        
    - `index.php` → Last fallback
        

---

5. **Tag Archives**
    
    - `tag-{slug}.php` → Specific tag by slug
        
    - `tag-{ID}.php` → Specific tag by ID
        
    - `tag.php` → Generic tag archive
        
    - `archive.php` → Generic archive fallback
        
    - `index.php` → Last fallback
        

---

6. **Custom Taxonomy Archives**
    
    - `taxonomy-{taxonomy}-{term}.php` → Specific term in a taxonomy
        
    - `taxonomy-{taxonomy}.php` → Specific taxonomy
        
    - `taxonomy.php` → Generic taxonomy archive
        
    - `archive.php` → Generic archive fallback
        
    - `index.php` → Last fallback
        

---

7. **Custom Post Type Archives**
    
    - `archive-{post-type}.php` → Specific custom post type archive
        
    - `archive.php` → Generic archive fallback
        
    - `index.php` → Last fallback
        

---

8. **Author Archives**
    
    - `author-{nicename}.php` → Specific author by username
        
    - `author-{ID}.php` → Specific author by ID
        
    - `author.php` → Generic author archive
        
    - `archive.php` → Generic archive fallback
        
    - `index.php` → Last fallback
        

---

9. **Date Archives**
    
    - `date.php` → Year/Month/Day archives
        
    - `archive.php` → Generic archive fallback
        
    - `index.php` → Last fallback
        

---

10. **Search Results**
    
    - `search.php` → Search results template
        
    - `index.php` → Fallback
        

---

11. **404 Error Page**
    
    - `404.php` → Not found template
        
    - `index.php` → Fallback
        

---

12. **Shared Structure Files** _(used across templates)_
    
    - `header.php` → Site header markup
        
    - `footer.php` → Site footer markup
        
    - `sidebar.php` → Sidebar markup
        
    - `comments.php` → Comment form/list
        
    - `/template-parts/` → Reusable content sections
        

---

If you want, I can **convert this into a `tree`-style ASCII directory view** so you can visually see the hierarchy in a developer-friendly way.  
That would make it feel like a real theme folder you’d see in VS Code.