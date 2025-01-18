<h1 alighn="center"> Hi there, I'm <img src="![image](https://github.com/user-attachments/assets/8aca3ce3-c5b4-49f0-bec1-9d9e7e3cd1b5)
")> </h1> 
<a href="https://git.io/typing-svg"><img src="https://readme-typing-svg.herokuapp.com?font=Fira+Code&pause=1000&width=435&lines=VENOM" alt="Typing SVG" /></a>
name: Latest blog post workflow
on:
  schedule: # Run workflow automatically
    - cron: '0 * * * *' # Runs every hour, on the hour
  workflow_dispatch: # Run workflow manually (without waiting for the cron to be called), through the Github Actions Workflow page directly

jobs:
  update-readme-with-blog:
    name: Update this repo's README with latest blog posts
    runs-on: ubuntu-latest
    steps:
      - name: Checkout
        uses: actions/checkout@v2
      - name: Pull in dev.to posts
        uses: gautamkrishnar/blog-post-workflow@master
        with:
          feed_list: "https://habr.com/ru/rss/users/daniilshat/posts/?fl=ru"
