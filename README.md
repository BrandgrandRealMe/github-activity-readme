# GitHub Activity in Readme (Reborn)

Updates `README.md` with the recent GitHub activity of a user.

| Example |
| --- |

`[05/01 00:37]` <img alt="📝" src="https://github.com/BrandgrandRealMe/github-activity-readme/raw/master/icons/commit.png" align="top" height="18"> Made `7` commits in [BrandgrandRealMe/github-activity-readme](https://github.com/BrandgrandRealMe/github-activity-readme)  
`[04/30 23:27]` <img alt="📝" src="https://github.com/BrandgrandRealMe/github-activity-readme/raw/master/icons/commit.png" align="top" height="18"> Made `2` commits in [BrandgrandRealMe/BrandgrandRealMe](https://github.com/BrandgrandRealMe/BrandgrandRealMe)  
`[04/30 23:10]` <img alt="📝" src="https://github.com/BrandgrandRealMe/github-activity-readme/raw/master/icons/commit.png" align="top" height="18"> Made `2` commits in [BrandgrandRealMe/github-activity-readme](https://github.com/BrandgrandRealMe/github-activity-readme)  
`[04/30 22:41]` <img alt="📝" src="https://github.com/BrandgrandRealMe/github-activity-readme/raw/master/icons/commit.png" align="top" height="18"> Made `2` commits in [BrandgrandRealMe/BrandgrandRealMe](https://github.com/BrandgrandRealMe/BrandgrandRealMe)  




---

## Instructions

- Add the comment `<!--START_SECTION:activity-->` (entry point) within `README.md`. You can find an example [here](https://github.com/BrandgrandRealMe/BrandgrandRealMe/blob/master/README.md).

- It's the time to create a workflow file.

`.github/workflows/update-readme.yml`

```yml
name: Update README

on:
  schedule:
    - cron: '*/30 * * * *'
  workflow_dispatch:

jobs:
  build:
    runs-on: ubuntu-latest
    name: Update this repo's README with recent activity

    steps:
      - uses: actions/checkout@v2
      - uses: BrandgrandRealMe/github-activity-readme@master
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
```

The above job runs every half an hour, you can change it as you wish based on the [cron syntax](https://jasonet.co/posts/scheduled-actions/#the-cron-syntax).

You can find an example [here](https://github.com/BrandgrandRealMe/BrandgrandRealMe/blob/master/.github/workflows/update-README.yml).

_Inspired by [JasonEtco/activity-box](https://github.com/JasonEtco/activity-box)_

