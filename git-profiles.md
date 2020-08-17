# How to manage multiple git profiles?

## Setting up SSH keys
Check if you have existing ssh keys directory, run:
```shell
ls -al ~/.ssh
```
If directory exis, run:
```shell
cd .ssh
```
Otherwise, create and `cd` into `.ssh`, run:
```shell
mkdir .ssh && cd .ssh
```


### For personal git profile:
Generate ssh key for personal email, run:
```shell
ssh-keygen -t rsa -b 4096 -C "your_email@mail.com"
```
When prompted for where to save rsa key pari, enter:
```shell
id_rsa_personal
```
When prompted to enter passphrase, enter a passphrase for an added layer of security.


### For work/other git profile:
Generate ssh key for other email, run:
```shell
ssh-keygen -t rsa -b 4096 -C "your_work_email@work.com"
```
When prompted for where to save rsa key pari, enter:
```shell
id_rsa_work
```
When prompted to enter passphrase, enter a passphrase for an added layer of security.


### Add ssh key to ssh agent
In the same directory, run:
```shell
touch config && code config
```
In VSCode, add the following to `config` file:
```txt
# Personal account - default config
Host github.com-personal
   HostName github.com
   User git
   IdentityFile ~/.ssh/id_rsa_personal

# Work account
Host github.com-work
   HostName github.com
   User git
   IdentityFile ~/.ssh/id_rsa_work
```


### Add ssh key to github/other accounts
Four files are created from generation of ssh keys
1. id_rsa_personal
2. **id_rsa_personal.pub**
3. id_rsa_work
4. **id_rsa_work.pub**

Copy contents of `id_rsa_personal.pub` to personal github/other account.

Copy contents of `id_rsa_work.pub` to work github/other account.

[This](https://docs.github.com/en/github/authenticating-to-github/adding-a-new-ssh-key-to-your-github-account) show how to add ssh key to GitHub account.


### Add ssh identities
To add identity, run:
```shell
ssh-add -K id_rsa_personal
ssh-add -K id_rsa_work
```
In mac, the `-K` flag stores the passphrase in your keychain.

To check if identities are added successfully, run:
```shell
ssh-add -l
```
You should see both identities if everything worked correctly.

### Test connection to github/other account
Run the following to test connection:
```shell
ssh -T github.com-personal
ssh -T github.com-work
```
When prompted if you want to continue, enter `yes`.

When everything is setup correctly, it should show:
```shell
Hi your_user_name! You've successfully authenticated, but GitHub does not provide shell access.
```



## Set directory configurations
In `.gitconfig` in root directory, add:
```txt
[user]
    name = personal_name
    email = your_email@email.com
[includeIf "gitdir:~/work/"]
    path = ~/work/.gitconfig
```

In `.gitconfig` in work directory, add:
```txt
[user]
    name = work_name
    email = your_work_email@work.com
```
This allows all you to use the work git profile when you initiate a git repository in the `work` directory.



## Using ssh to work on repositories
To clone, run:
```shell
git clone git@github.com-personal:person_user_name/repo_name.git
```
Note: *for personal repos, the link should be `@github.com-personal:`* as you configured when setting up the ssh agent

To add remote address, run:
```shell
git remote add git@github.com-work:work_user_name/repo_name.git
```
Note: *and for work repos, the link should be `@github.com-work:`* as you configured when setting up the ssh agent