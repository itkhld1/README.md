<h2 align="center">Hello there 😅👋🏻, I'm Khalid Samim</h2>

###

<p align="center">A dedicated and motivated student of Computer Engineering.</p>

###

<div align="center">
  <img src="https://github-readme-stats.vercel.app/api?username=itkhld1&hide_title=false&hide_rank=false&show_icons=true&include_all_commits=true&count_private=true&disable_animations=false&theme=rose_pine&locale=en&hide_border=true&custom_title=Status " height="110" alt="stats graph"  />
  <img src="https://streak-stats.demolab.com?user=itkhld1&locale=en&mode=daily&theme=rose_pine&hide_border=false&border_radius=5" height="150" alt="streak graph"  />
  <img src="https://github-readme-stats.vercel.app/api/top-langs?username=itkhld1&locale=en&hide_title=true&layout=compact&card_width=320&langs_count=3&theme=rose_pine&hide_border=true" height="110" alt="languages graph"  />
</div>

###

<div align="center">
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/apple/apple-original.svg" height="30" width="42" alt="apple logo"  />
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/python/python-original.svg" height="30" width="42" alt="python logo"  />
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/java/java-original.svg" height="30" width="42" alt="java logo"  />
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/html5/html5-original.svg" height="30" width="42" alt="html5 logo"  />
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/css3/css3-original.svg" height="30" width="42" alt="css3 logo"  />
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/illustrator/illustrator-plain.svg" height="30" width="42" alt="illustrator logo"  />
</div>

###

<br clear="both">

<div align="center">
  <a href="https://instagram.com/itkhld" target="_blank">
    <img src="https://img.shields.io/static/v1?message=Instagram&logo=instagram&label=itkhld&color=red&logoColor=white&labelColor=&style=for-the-badge" height="40" alt="instagram logo"  />
  </a>
  <a href="khalidsamim321@gmail.com" target="_blank">
    <img src="https://img.shields.io/static/v1?message=Gmail&logo=gmail&label=&color=skyblue&logoColor=white&labelColor=&style=for-the-badge" height="40" alt="gmail logo"  />
  </a>
</div>

###

<br clear="both">

<img src="https://raw.githubusercontent.com/itkhld1/itkhld1/blob/output/snake.svg" alt="Snake animation" />

###

<div align="center">
  <img src="https://profile-counter.glitch.me/itkhld1/count.svg?"  />
</div>

###
name: Generate snake animation

on:
  schedule: # execute every 12 hours
    - cron: "* */12 * * *"

  workflow_dispatch:

  push:
    branches:
    - master

jobs:
  generate:
    runs-on: ubuntu-latest

    steps:
      - name: generate snake.svg
        uses: Platane/snk/svg-only@v2
        with:
          github_user_name: ${{ github.repository_owner }}
          outputs: dist/snake.svg


      - name: push snake.svg to the output branch
        uses: crazy-max/ghaction-github-pages@v2.6.0
        with:
          target_branch: output
          build_dir: dist
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
