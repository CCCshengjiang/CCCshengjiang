name: Update README
on:
  schedule:
    - cron: "*/30 * * * *"
  workflow_dispatch:
jobs:
  build:
    name: Update this repo's README with recent activity
    runs-on: ubuntu-latest
    permissions:
      contents: write

    steps:
      - uses: actions/checkout@v3
      - uses: jamesgeorge007/github-activity-readme@master
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
