---
- name: Install php extensions
  apt: name={{ item }} state=present
  sudo: yes
  with_items:
    - php5-gd 
    - libssh2-php
