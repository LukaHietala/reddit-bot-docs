---
description: >-
  How to run Reddit Bot on mobile.
---

## Table Of Contents
* [Getting Started](https://github.com/LukaHietala/reddit-bot-docs/new/main#getting-started)
* [Installing Packages](https://github.com/LukaHietala/reddit-bot-docs/new/main#installing-packages)
* [Running The Bot](https://github.com/LukaHietala/reddit-bot-docs/new/main#running-the-bot)
* [Run on GitHub Actions](https://github.com/LukaHietala/reddit-bot-docs/new/main#run-on-github-actions)

### Getting Started 
To get started first download [UserLAnd](https://f-droid.org/packages/tech.ula/) app from F Droid. It allows you to run root instance of any os.

After downloading click Ubuntu enter your username and password. And click on **ssh**. That's basically it. Let it download the files.

### Installing Packages
Run the following command to update and install some needed packages
```
sudo apt update && sudo apt install git python3 pip3 ffmpeg nano -y
```

Run the following command to clone the repo.
```
git clone https://github.com/elebumm/RedditVideoMakerBot
```
Run the following command to install packages

```
sudo pip3 install -r requirements.txt
```
Install playerwright
```
sudo python3 -m playwright install && sudo python3 -m playwright install-deps
```
That's basically it for install part.
### Running the bot
To run the bot do:
```
python3 main.py
```
And fill in the required things. You can follow normal docs to do it.

### Run on GitHub Actions 
To run on GitHub actions go to https://github.com/new and create a new repository.

Clone the repo using

```
git clone https://github.com/username/repo
```
Username = your username
repo = your repo name.

Now do this: (make sure your in your /home directory)
```
cp ~/RedditVideoMakerBot/* ~/repo/
```

**NOTE**: make sure you have just ran the bot once and did the config and after that did not run the bot. If you have run the bot please delete the file in assets/background.
Now push the updates:

```
git config --global user.name "Your username" && git config --global user.email "email" && git add . && git commit -m "new commit" && git push
```

Go to GitHub web and follow my steps

Go to actions → create a new workflow → create my own

Delete whatever is in that box and paste the things below

```yml
# This is a basic workflow to help you get started with Actions

name: CI

# Controls when the workflow will run
on:
  # Triggers the workflow on push or pull request events but only for the "master" branch
  push:
    branches: [ "master" ]
  pull_request:
    branches: [ "master" ]

  # Allows you to run this workflow manually from the Actions tab
  workflow_dispatch:

# A workflow run is made up of one or more jobs that can run sequentially or in parallel
jobs:
  # This workflow contains a single job called "build"
  build:
    # The type of runner that the job will run on
    runs-on: ubuntu-latest

    # Steps represent a sequence of tasks that will be executed as part of the job
    steps:
      # Checks-out your repository under $GITHUB_WORKSPACE, so your job can access it
      - uses: actions/checkout@v3

      # Runs a single command using the runners shell
      - name: Install Packages
        run: sudo apt install ffmpeg python3 -y && pip install -r requirements.txt

      # Runs a set of commands using the runners shell
      - name: install playerwright
        run: |
          python3 -m playwright install
          python3 -m playwright install-deps

      - name: git stuff
        run: |
          git config --global user.name "github-actions"
          git config --global user.email "41898282+github-actions[bot]@users.noreply.github.com"

      - name: run the program 
        run: python3 main.py

      - name: git lfs
        run: |
          sudo apt install git-lfs
          git lfs install
          git lfs track "GUI/*" "TTS/*" "results/*" "results/funny/*"
          git lfs track


      - name: push changes 
        run: |
          git add .
          git config http.postBuffer 524288000
          git commit -m "New Videos"
          git config --global http.version HTTP/1.1 
          git push 
          git config --global http.version HTTP/2
```

It should run fine on a new commit. If you encounter any issues contact me on discord: `OmxproYT#1165` have fun using the bot
