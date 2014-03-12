---
layout: post
title:  "Git Tip: Enable Branch Autocompletion"
date:   2014-03-12 10:10:51
tags: git tricks
---

Not sure how I didn't come across this earlier but it's a god send.
Way easier to use long descriptive branch names once autocomplete is enabled!

## Step 1) Download `git-completion.bash` from the [git repo][1]

```
# ~/.git-completion.bash
curl https://raw.github.com/git/git/master/contrib/completion/git-completion.bash \
  -o ~/.git-completion.bash
```

## Step 2) Add it to your `.bash_profile`

```
# ~/.bash_profile
if [ -f ~/.git-completion.bash ]; then
  . ~/.git-completion.bash
fi
```

Open up a new terminal window or `source ~/.bash_profile` and you're good to go!

[1]: https://github.com/git/git/blob/master/contrib/completion/git-completion.bash
