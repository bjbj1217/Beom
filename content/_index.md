---
# Leave the homepage title empty to use the site title
title: ""
date: 2025-07-24
type: landing

design:
  # Default section spacing
  spacing: "6rem"

sections:
  - block: resume-biography-3
    content:
      # Choose a user profile to display (a folder name within `content/authors/`)
      username: admin
      text: ""
      # Show a call-to-action button under your biography? (optional)
      button:
        text: Download Resume
        url: uploads/resume.pdf
    design:
      css_class: dark
      background:
        color: black
  - block: markdown
    content:
      title: '📚 My Research'
      subtitle: ''
      text: |-
        I am a data scientist at DASI Simulations, a medical company delivering individualized computational predictive modeling for patients undergoing structural 
         heart procedures such as Transcatheter Aortic Valve Replacement (TAVR). \
        I showcase projects that I am involved in and blog about machine learning and computer vision techniques especially in the medical domain.
    design:
      columns: '1'
  - block: collection
    id: news
    content:
      title: Recent Posts
      subtitle: ''
      text: ''
      # Page type to display. E.g. post, talk, publication...
      page_type: post
      # Choose how many pages you would like to display (0 = all pages)
      count: 5
      # Filter on criteria
      filters:
        author: ""
        category: ""
        tag: ""
        exclude_featured: false
        exclude_future: false
        exclude_past: false
        publication_type: ""
      # Choose how many pages you would like to offset by
      offset: 0
      # Page order: descending (desc) or ascending (asc) date.
      order: desc
    design:
      # Choose a layout view
      view: date-title-summary
      # Reduce spacing
      spacing:
        padding: [0, 0, 0, 0]
---
