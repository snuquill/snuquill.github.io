current index: 200
# How to Upload Articles
1. upload image on Amazon S3
2. create a {[article_id}.md file
3. Fill this in:
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
5. Add article content in markdown format
6. Upload to _articles file
7. Change current index in README.md
# To Do
- [ ] create archives page
- [ ] create meet the staff page
- [ ] create feedback and complaints page
- [ ] create advertise with us page
- [ ] add email form in letter to the editor
- [ ] add paginate feature (features, snu society, short articles, arts and culture, opinion)
- [ ] add recent articles navigation
- [ ] add automatic recent articles in home
- [ ] adjust css to support mobile and smaller screens
- [ ] add javascript slider for photojournals
- [ ] google analytics
