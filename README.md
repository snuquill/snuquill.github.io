current index: 224
# How to Upload Articles
1. upload image on Amazon S3
2. create a {[article_id}.md file
3. Fill this in:

```
---
layout: article
title: {title}
article_id: {current index +1}
category: "FEATURES" "SNU_SOCIETY" "SHORT_ARTICLES" "ARTS_CULTURE" or "OPINION" 
author_name: {author name}
picture_url: {s3 link}
publish_date: {YYYY}-{MM}-{DD}T09:16:11.000Z
modified_date: {YYYY}-{MM}-{DD}T09:16:11.000Z
---
```

5. Add article content in markdown format
6. Upload to _articles file
7. Change current index in README.md
# To Do
- [x] create archives page
- [x] create meet the staff page
- [ ] create feedback and complaints page
- [ ] create advertise with us page
- [ ] add email form in letter to the editor
- [ ] add paginate feature (features, snu society, short articles, arts and culture, opinion)
- [ ] add recent articles navigation
- [x] add automatic recent articles in home
- [ ] adjust css to support mobile and smaller screens
- [x] add javascript slider for photojournals
- [x] google analytics
- [x] add paginate feature for archives
- [ ] add paginate feature for meet the staff


- to serve locally, use `bundle exec jekyll serve` in terminal
- to test on mobile, use `bundle exec jekyll serve --host 0.0.0.0 --port 4000` in terminal and go to `http:\\<your-ipv4>:4000`
- find ip by typing `ipconfig` in terminal



(to have pages per editions)

```
---
        {% assign posts = site.articles | where: "category", "FEATURES" %}
        
        {% assign edition = site.data.editions | where: "name", "84th Edition" | first %}
        {% assign start = edition.start | date: "%s" %}
        {% assign end = edition.end | date: "%s" %}

        {% assign filtered_posts = "" | split: "" %}
        {% for post in posts %}
        {% assign pub = post.publish_date | date: "%s" %}

        {% if pub > start and pub < end %}
            {% assign filtered_posts = filtered_posts | push: post %}
        {% endif %}
        {% endfor %}

        {% assign sorted_posts = filtered_posts | sort: "publish_date" | reverse %}
---
```
