---
# Leave the homepage title empty to use the site title
title: ""
date: 2025-10-24
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
        text: Download CV
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
         I am a data scientist at DASI Simulations. I showcase and blog about machine learning and computer vision techniques especially in the medical domain.

        Please reach out to collaborate 😃
    design:
      columns: '1'
---