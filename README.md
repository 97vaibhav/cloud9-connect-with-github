# cloud9-connect-with-github

#Tutorial: How to connect your Cloud9 and GitHub accounts via ssh

To avoid having to enter your username and password EVERY-SINGLE-TIME you push, follow these step-by-step instructions.


#####1. Copy your C9 ssh key. Go to https://c9.io/account/ssh and copy the key below *"Connect to your private git repository"*. It's a very long string that starts with ssh-rsa and ends with your email.
#####2. Paste your C9 ssh key into your GitHub account Go to https://github.com/settings/keys and click New SSH key. Enter a title (a name like Cloud9 is fine), paste the ssh key that you copied in the previous step, and click Add SSH key

#####3. When creating a remote, make sure you "clone with SSH" instead of "clone with HTTPS" This means that, when you type in git remote add origin, you should use a link that looks like this: *git@github.com:*YOUR_USER_NAME/YOUR_REPO_NAME.git. Pay attention to how that differs from *https://github.com/*YOUR_USER_NAME/YOUR_REPO_NAME.git While the first creates a remote that uses ssh authentication, the latter uses https, so it'll always prompt you to enter your username and password to authenticate the connection.


That's it! Next time you push anything, it should authenticate automatically, and you'll never again have to enter your credentials on C9.


some important cammands 
Generate RSA Key Pair.
$ ssh-keygen -t rsa

Copy the Public Key to You GitHub Account.
Navigate to RSA file directory and copy the public key.

first ssh clone url (make remote )
git add .
git commit -m "message "

git push --set-upstream origin master

https://medium.com/sonabstudios/setting-up-github-on-aws-cloud9-with-ssh-2545c4f989ea

how to remove remote 
https://www.cloudbees.com/blog/remote-origin-already-exists-error

https://stackoverflow.com/questions/18382986/git-rename-local-branch-failed
