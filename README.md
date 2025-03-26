# git-track
converts commit history to a csv file . 


install : 
```sudo apt install jq ```

```brew install jq ```

```curl -s "https://api.github.com/repos/USERNAME/REPO/commits" | jq -r '.[] | [.sha, .commit.author.name, .commit.author.date, .commit.message] | @csv' > commits.csv ```


example : 
```curl -s "https://api.github.com/repos/drivendataorg/zamba/commits?per_page=100&page=1" | \
jq -r '.[] | [ .sha, .commit.author.name, .commit.author.date, (.commit.message | gsub("\n"; " ")) ] | @csv' > commits.csv ```


if(forked) :

```
git clone https://github.com/drivendataorg/zamba.git
cd zamba
git log --pretty=format:'"%h","%an","%ad","%s"' --date=iso > commits.csv
```

