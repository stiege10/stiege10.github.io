---
layout: post
title:  "Increase upload limit for nginx serving wordpress"
date:   2021-04-20
categories: wordpress nginx
author: mrusa
---

Had troubles uploading a big wordpress theme.
After setting `client_max_body_size` the displayed value in wordpress' backend 
under `media -> create` didn't change. I needed to set `post_max_size` in php.ini 
for that.

## tldr

- `post_max_size 15M` in `php.ini` (eg `/etc/php/7.4/fpm/php.ini`)
- `client_max_body_size 15M;` in nginx's `server`-block
