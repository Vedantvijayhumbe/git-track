# git-track
converts commit history to a csv file . 


install : 
```sudo apt install jq ```
```brew install jq ```
```curl -s "https://api.github.com/repos/USERNAME/REPO/commits" | jq -r '.[] | [.sha, .commit.author.name, .commit.author.date, .commit.message] | @csv' > commits.csv ```
