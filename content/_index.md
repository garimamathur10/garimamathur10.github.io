---
title: ''
summary: ''
date: 2026-01-05
type: landing

design:
  spacing: '0'

sections:

  - block: dev-hero
    id: hero
    content:
      username: me
      greeting: "Hi, I'm"
      show_status: true
      show_scroll_indicator: true
      typewriter:
        enable: true
        prefix: "I build"
        strings:
          - "distributed systems"
          - "low-latency microservices"
          - "secure backend platforms"
          - "cloud-native services"
        type_speed: 70
        delete_speed: 40
        pause_time: 2500
      cta_buttons:
        - text: View My Work
          url: "#projects"
          icon: arrow-down
        - text: Get In Touch
          url: "#contact"
          icon: envelope
    design:
      style: centered
      avatar_shape: circle
      animations: true
      background:
        color:
          light: "#fafafa"
          dark: "#0a0a0f"
      spacing:
        padding: ["6rem", "0", "4rem", "0"]

  - block: portfolio
    id: projects
    content:
      title: "Featured Projects"
      subtitle: "A selection of my Machine learning Systems and Backend work"
      count: 0
      filters:
        folders:
          - projects
      buttons:
        - name: All
          tag: '*'
        - name: Backend
          tag: Backend
        - name: ML Platforms
          tag: ML
      default_button_index: 0
    design:
      columns: 3
      background:
        color:
          light: "#ffffff"
          dark: "#0d0d12"
      spacing:
        padding: ["4rem", "0", "4rem", "0"]

  - block: tech-stack
    id: skills
    content:
      title: "Tech Stack"
      subtitle: "Technologies I use to build scalable systems"
      categories:
        - name: Languages
          items:
            - name: Java
              icon: devicon/java
            - name: C++
              icon: devicon/cplusplus
            - name: Python
              icon: devicon/python
            - name: SQL
              icon: devicon/postgresql
        - name: Backend 
          items:
            - name: REST APIs
              icon: devicon/nodejs
            - name: Microservices
              icon: devicon/docker
            - name: Distributed Systems
              icon: devicon/kubernetes
            - name: System Design
              icon: devicon/kubernetes
        - name: Tools
          items:
            - name: Linux
              icon: devicon/linux
            - name: Git
              icon: devicon/git
            - name: Asana
              icon: devicon/asana
            - name: Jira
              icon: devicon/jira
        - name: DevOps
          items:
            - name: GCP
              icon: devicon/googlecloud
            - name: Azure
              icon: devicon/azure
            - name: CI/CD
              icon: brands/github
            - name: Logging
              icon: devicon/prometheus
    design:
      style: grid
      show_levels: false
      background:
        color:
          light: "#f5f5f5"
          dark: "#08080c"
      spacing:
        padding: ["4rem", "0", "4rem", "0"]

  - block: resume-experience
    id: experience
    content:
      title: Experience
      date_format: Jan 2006
      items:
        - title: Data Augmentation Intern
          company: Bevalty
          company_url: ''
          company_logo: ''
          location: San Francisco, CA
          date_start: '2025-06-01'
          date_end: '2025-08-01'
          description: |2-
            * Designed distributed ingestion pipelines improving throughput by 30%
            * Built ML-driven customer profiling workflows improving dataset quality by 60%
            * Implemented schema validation across event systems

        - title: Senior Software Engineer
          company: Accolite Digital
          company_url: ''
          company_logo: ''
          location: Gurugram, India
          date_start: '2023-11-01'
          date_end: '2024-07-01'
          description: |2-
            * Implemented secure authorization across 40+ backend modules
            * Improved MariaDB-backed user services supporting 2.5M+ users
            * Delivered production-ready features through full SDLC

        - title: Software Engineer
          company: Accolite Digital
          company_url: ''
          company_logo: ''
          location: Gurugram, India
          date_start: '2021-09-01'
          date_end: '2023-10-01'
          description: |2-
            * Contributed to Mesa 3D upgrade improving Linux rendering performance
            * Stabilized pipelines impacting 3M+ users
            * Built testing frameworks to reduce production risk
    design:
      columns: '1'
      background:
        color:
          light: "#ffffff"
          dark: "#0d0d12"
      spacing:
        padding: ["4rem", "0", "4rem", "0"]

  - block: collection
    id: blog
    content:
      title: Recent Posts
      subtitle: 'Thoughts on distributed systems, backend engineering, and scalability'
      text: ''
      filters:
        folders:
          - blog
        exclude_featured: false
      count: 3
      order: desc
    design:
      view: card
      columns: 3
      background:
        color:
          light: "#f5f5f5"
          dark: "#08080c"
      spacing:
        padding: ["4rem", "0", "4rem", "0"]

  - block: contact-info
    id: contact
    content:
      title: Get In Touch
      subtitle: "Let's build scalable systems together"
      text: |-
        I'm always interested in discussing opportunities in backend platforms,
        distributed systems, and cloud-native engineering.
      autolink: true
    design:
      columns: '1'
      background:
        color:
          light: "#ffffff"
          dark: "#0d0d12"
      spacing:
        padding: ["4rem", "0", "4rem", "0"]

  - block: cta-card
    content:
      title: "Open to Opportunities"
      text: |-
        I'm currently looking for **backend software engineering** or **quantitative engineer** roles.

        Let's connect and discuss how I can help your team.
      button:
        text: 'Download Resume'
        url: uploads/resume.pdf
        new_tab: true
    design:
      card:
        css_class: 'bg-gradient-to-br from-primary-200 via-primary-100 to-secondary-200 dark:from-primary-600 dark:via-primary-700 dark:to-secondary-700'
        text_color: dark
      background:
        color:
          light: "#f5f5f5"
          dark: "#08080c"
      spacing:
        padding: ["4rem", "0", "6rem", "0"]
---
