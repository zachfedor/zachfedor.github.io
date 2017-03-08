---
title: "Setting Up a Personal Git Server on a VPS"
date: 2016-02-07
category: dev
---

I've been sitting on an under-used VPS for too long. Time to backup all my git repos that I don't feel like hosting on GitHub!

1. Create ssh keys on host
1. Setup git user on vps
1. Add ssh key to access list
    - log in to VPS as git user
    - create `~/.ssh/authorized_keys` file
    - add public ssh key of user that wants to push to the git repo
    - from that user, run the following command replacing `git@vps_domain` with the git user we created and the VPS address

            cat ~/.ssh/id_rsa.pub | ssh git@vps_domain "cat >> ~/.ssh/authorized_keys"

    - back in your git user's ssh session, verify that the key of your local user is there with `cat ~/.ssh/authorized_keys`

1. _Optional:_ create user folders in your git user's home directory
    - similar to github's <http://github.com/user_folder/repo_name.git> file structure
1. Create bare git repo on the vps
    - either in the git user's home directory: `/home/git/`
    - or in the separate user directories: `/home/git/user_folder/`

            git init --bare repo_name.git

1. Point the local git repo at the new remote

        git remote set-url origin git@vps_domain:user_folder/repo_name.git

1. Double check your work!

        git remote -v


Now you can push and pull like usual, except the code is no longer on GitHub for all the world to grab your precious secrets.

---

**Sources:**

- [Digital Ocean Tutorial](https://www.digitalocean.com/community/tutorials/how-to-set-up-a-private-git-server-on-a-vps)
- [Linux Foundation Tutorial](https://www.linux.com/learn/tutorials/824358-how-to-run-your-own-git-server)
