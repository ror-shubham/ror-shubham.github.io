---
date: '2022-09-01T00:00:10+05:30'
draft: true
title: 'SI Alerts'
subtitle: 'Full Stack Developer'
tags: ['Python', 'PySpark', 'Amazon SES', 'Jinja2', 'Backend']
#cover:
#  image: 'img/6si.png'
#  alt: '6sense logo'
---

- We send daily/weekly alerts to customers notifying them intent signals and other insights about their accounts. A lot of our users start their Mondays with these alerts.
- I developed and owned the frontend of the Alerts feature of Sales Intelligence and later became owner of the backend as well.
- Technologies used: React, Apollo, PySpark, Amazon SES, Jinja2, HandlebarsJS
- The feature is heavily used. We send 90,000+ alerts every day.
- Interesting stuff:
  - Writing the Frontend of this was rather peculiar since it doesn't load inside browsers but mostly native email
  clients which doesn't support modern CSS. Outlook email client is the most popular email client and worst to write
  email templates for. It uses MS Word engine to render HTML. Creating responsive html template with ancient CSS
  (most of the positioning was done using tables) was a challenge. 
  - Backend was written in Python using PySpark. We used Jinja2 to create the email templates. This was my introduction
  to Spark as well as big data. 
  - Customers has reported that they were able to close deals within few hours of receiving the alert.