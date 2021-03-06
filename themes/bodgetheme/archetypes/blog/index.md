---
date        : {{ .Date }}
lastmod     : {{ .Date }}
draft       : true
title       : "{{ replace .Name "-" " " | title }}"
author      : "Anonymous"

# Description overrides the automated summary of marked-up content
#  at the bottom of this file.
description : ""

# Identifying mnemonics, INTERNAL use only. Fill AT LEAST one identifying
# mnemonic, to refer to the project this blog is related to.
{{- $tailsearcher := printf "[^/]+/%s/index.md" .Name | lower }}
{{- $tails        := findRE $tailsearcher (.File.Path | lower) }}
{{- $tail         := index $tails 0 }}
{{- $projects     := findRE "[^/]+" $tail }}
{{- $project      := index $projects 0 }}
projects    : ["{{ $project | upper | default "ReplaceThisWithTheCorrectProjectID" }}"]

# External reference name (i.e. https://bodge.theme/blog/slug)
slug        : ""

# Identifying tags, searchable/visible to site visitors
tags        : []

# Identifying categories, searchable/visible to site visitors
categories  :
- Hacker conference badge
- Hardware design
- Software development
- Embedded software

# Blog icon
# For available icons, see: https://forkaweso.me
icon_name : fa-pencil
icon_pack : fa

# Default image related to this blog
#image_src   : "images/mascot.png"
#image_alt   : ""
#thumb_src   : ""
#thumb_alt   : ""

# Author about box
about_show   : true
about_inline : true

# Photo gallery
gallery:
- album   : "images"
  exclude : true
  images  :
  - image        : "imagine.jpg"
    caption      : "Imagine"
    exclude      : false
    external_url : ""
  - image        : "people.jpg"
    caption      : "People"
    exclude      : false
    external_url : ""

# Write the content of this blog page below in markup language.
# An emoji cheat sheet can be found here:
#  https://www.webfx.com/tools/emoji-cheat-sheet/
---

##### {{ replace .Name "-" " " | title }} project blog page.

Welcome to this blog page of the {{ replace .Name "-" " " | title }} project. This page is work in progress and should be filled with new content soon.

<!--more-->

This part of the text will show up on the blog page only, not in the previews of the project page.
