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

sample : 
ubuntu:~/environment/secret_menu_api (master) $ ssh-keygen -t rsa
Generating public/private rsa key pair.
Enter file in which to save the key (/home/ubuntu/.ssh/id_rsa): 
Enter passphrase (empty for no passphrase): 
Enter same passphrase again: 
Your identification has been saved in /home/ubuntu/.ssh/id_rsa.
Your public key has been saved in /home/ubuntu/.ssh/id_rsa.pub.
The key fingerprint is:
SHA256:OnOdTeNKj2dJKeTT2S6XM0FX85IsC/gOXqfvWFEtZaI ubuntu@ip-172-31-16-44
The key's randomart image is:
+---[RSA 2048]----+
|              . o|
|             . *.|
|         .  E.o.=|
|        . o ..=.o|
|        S+ o+B o |
|       ...*=Boo  |
|      +..++*+o o |
|       +..o*= *  |
|          +=+o o |
+----[SHA256]-----+
ubuntu:~/environment/secret_menu_api (master) $ git remote add origin https://github.com/97vaibhav/rails-api.git
ubuntu:~/environment/secret_menu_api (master) $ git branch -M main
error: refname refs/heads/master not found
fatal: Branch rename failed
ubuntu:~/environment/secret_menu_api (master) $ git push -u origin main
error: src refspec main does not match any.
error: failed to push some refs to 'https://github.com/97vaibhav/rails-api.git'
ubuntu:~/environment/secret_menu_api (master) $ git remote add origin git@github.com:97vaibhav/rails-api.git
fatal: remote origin already exists.
ubuntu:~/environment/secret_menu_api (master) $ git remote remove origin
ubuntu:~/environment/secret_menu_api (master) $ git remote add origin git@github.com:97vaibhav/rails-api.git
ubuntu:~/environment/secret_menu_api (master) $ git branch -M main
error: refname refs/heads/master not found
fatal: Branch rename failed
ubuntu:~/environment/secret_menu_api (master) $ git add .
ubuntu:~/environment/secret_menu_api (master) $ git commmit -m "api rest"
git: 'commmit' is not a git command. See 'git --help'.

The most similar command is
        commit
ubuntu:~/environment/secret_menu_api (master) $ git commit -m "api rest"
[master (root-commit) 2fb9dbb] api rest
 Committer: Ubuntu <ubuntu@ip-172-31-16-44.us-east-2.compute.internal>
Your name and email address were configured automatically based
on your username and hostname. Please check that they are accurate.
You can suppress this message by setting them explicitly:

    git config --global user.name "Your Name"
    git config --global user.email you@example.com

After doing this, you may fix the identity used for this commit with:

    git commit --amend --reset-author

 66 files changed, 1096 insertions(+)
 create mode 100644 .gitignore
 create mode 100644 .ruby-version
 create mode 100644 Gemfile
 create mode 100644 Gemfile.lock
 create mode 100644 README.md
 create mode 100644 Rakefile
 create mode 100644 app/channels/application_cable/channel.rb
 create mode 100644 app/channels/application_cable/connection.rb
 create mode 100644 app/controllers/application_controller.rb
 create mode 100644 app/controllers/concerns/.keep
 create mode 100644 app/controllers/secret_menu_items_controller.rb
 create mode 100644 app/jobs/application_job.rb
 create mode 100644 app/mailers/application_mailer.rb
 create mode 100644 app/models/application_record.rb
 create mode 100644 app/models/concerns/.keep
 create mode 100644 app/models/secret_menu_item.rb
 create mode 100644 app/views/layouts/mailer.html.erb
 create mode 100644 app/views/layouts/mailer.text.erb
 create mode 100755 bin/bundle
 create mode 100755 bin/rails
 create mode 100755 bin/rake
 create mode 100755 bin/setup
 create mode 100755 bin/spring
 create mode 100644 config.ru
 create mode 100644 config/application.rb
 create mode 100644 config/boot.rb
 create mode 100644 config/cable.yml
 create mode 100644 config/credentials.yml.enc
 create mode 100644 config/database.yml
 create mode 100644 config/environment.rb
 create mode 100644 config/environments/development.rb
 create mode 100644 config/environments/production.rb
 create mode 100644 config/environments/test.rb
 create mode 100644 config/initializers/application_controller_renderer.rb
 create mode 100644 config/initializers/backtrace_silencers.rb
 create mode 100644 config/initializers/cors.rb
 create mode 100644 config/initializers/filter_parameter_logging.rb
 create mode 100644 config/initializers/inflections.rb
 create mode 100644 config/initializers/mime_types.rb
 create mode 100644 config/initializers/wrap_parameters.rb
 create mode 100644 config/locales/en.yml
 create mode 100644 config/puma.rb
 create mode 100644 config/routes.rb
 create mode 100644 config/spring.rb
 create mode 100644 config/storage.yml
 create mode 100644 db/migrate/20220103212435_create_secret_menu_items.rb
 create mode 100644 db/schema.rb
 create mode 100644 db/seeds.rb
 create mode 100644 lib/tasks/.keep
 create mode 100644 log/.keep
 create mode 100644 public/robots.txt
 create mode 100644 storage/.keep
 create mode 100644 test/channels/application_cable/connection_test.rb
 create mode 100644 test/controllers/.keep
 create mode 100644 test/controllers/secret_menu_items_controller_test.rb
 create mode 100644 test/fixtures/.keep
 create mode 100644 test/fixtures/files/.keep
 create mode 100644 test/fixtures/secret_menu_items.yml
 create mode 100644 test/integration/.keep
 create mode 100644 test/mailers/.keep
 create mode 100644 test/models/.keep
 create mode 100644 test/models/secret_menu_item_test.rb
 create mode 100644 test/test_helper.rb
 create mode 100644 tmp/.keep
 create mode 100644 tmp/pids/.keep
 create mode 100644 vendor/.keep
ubuntu:~/environment/secret_menu_api (master) $ git push
fatal: The current branch master has no upstream branch.
To push the current branch and set the remote as upstream, use

    git push --set-upstream origin master

ubuntu:~/environment/secret_menu_api (master) $   git push --set-upstream origin master
The authenticity of host 'github.com (140.82.112.4)' can't be established.
ECDSA key fingerprint is SHA256:p2QAMXNIC1TJYWeIOttrVc98/R1BUFWu3/LiyKgUfQM.
Are you sure you want to continue connecting (yes/no)? yes
Warning: Permanently added 'github.com,140.82.112.4' (ECDSA) to the list of known hosts.
Counting objects: 81, done.
Compressing objects: 100% (67/67), done.
Writing objects: 100% (81/81), 20.61 KiB | 917.00 KiB/s, done.
Total 81 (delta 0), reused 0 (delta 0)
To github.com:97vaibhav/rails-api.git
 * [new branch]      master -> master
Branch 'master' set up to track remote branch 'master' from 'origin'.
ubuntu:~/environment/secret_menu_api (master) $ 
