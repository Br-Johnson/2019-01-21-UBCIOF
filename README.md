# Get set up for the R Workshop for the Pelagic Ecosystems Lab and Hakai Affiliates

Before attending the course it is critical you show up prepared, having gone through the following steps to set up the tools we will be using. If you have any issues installing these tools, please contact me or your fellow workshop attendees for help. If that fails please arrive to the workshop an hour early at 8 a.m. and we can work through the steps together.

# Before the course starts

## Communications

* [Download slack](https://join.slack.com/t/juvenilesalmon/signup). We'll use slack for communications during the course to post bits of code, links, and answer questions.

## Tools

If you already have these tools installed PLEASE update them by downloading the latest version. This will help make sure your code will run.

* Update or install [R-Studio](https://www.rstudio.com)
* Update or install [R](https://cran.r-project.org/)
* Update or install these packges by running the following code in the R Console pane:
    ```
    install.packages(c('tidyverse', 'lubridate', 'devtools', 'googlesheets', 'here'))
    ```
    
## Hakai Data Portal

* If you are a Hakai affiliate and need access to Hakai Oceanography or Salmon Progam data from the Hakai Data Portal, please make sure you can log in to the [Hakai Data Portal](https://hecate.hakai.org/portal2/). If you can't login, but you should be able to, please email data@hakai.org.

# Git

* Make sure you have a free [GitHub account](https://github.com/signup)
* Email or slack me your GitHub name so that I can add you to the [Pelagic Ecosystems GitHub page](https://github.com/pelagic-ecosystems).

## Install Git

The following section on Git and GitHub were written by Jenny Bryan in her book [Happy Git with R](https://happygitwithr.com/) under the [Creative Commons Attribution-NonCommercial 4.0 International License](https://creativecommons.org/licenses/by-nc/4.0/). Modifications were made to customize the instructions for this workshop.

You need Git, so you can use it at the command line and so RStudio can call it.

If there's any chance it's installed already, verify that, rejoice, skip this step, and move on to 'Introduce yourself to Git'.

Otherwise, find installation instructions below for your operating system.

### Git already installed?

Go to the shell (aka console, terminal, command line). Enter `which git` to request the path to your Git executable:

``` bash
which git
```

and `git --version` to see its version:
 
``` bash
git --version
```

If you are successful, that's great! You have Git already. No need to install! Move on.

If, instead, you see something more like `git: command not found`, keep reading.

macOS users might get an immediate offer to install command line developer tools. Yes, you should accept! Click "Install" and read more below.

### Windows  {#install-git-windows}

**Option 1** (*highly recommended*): Install [Git for Windows](https://git-for-windows.github.io/), also known as `msysgit` or "Git Bash", to get Git in addition to some other useful tools, such as the Bash shell. Yes, all those names are totally confusing, but you might encounter them elsewhere and I want you to be well-informed.

We like this because Git for Windows leaves the Git executable in a conventional location, which will help you and other programs, e.g. RStudio, find it and use it. This also supports a transition to more expert use, because the "Git Bash" shell will be useful as you venture outside of R/RStudio.

  *  **NOTE:** When asked about "Adjusting your PATH environment", make sure to select "Git from the command line and also from 3rd-party software". Otherwise, we believe it is good to accept the defaults.
  * Note that RStudio for Windows prefers for Git to be installed below `C:/Program Files` and this appears to be the default. This implies, for example, that the Git executable on my Windows system is found at `C:/Program Files/Git/bin/git.exe`. Unless you have specific reasons to otherwise, follow this convention.

This also leaves you with a Git client, though not a very good one. So check out Git clients we recommend (chapter \@ref(git-client)).

FYI, this appears to be equivalent to what you would download from here: <https://git-scm.com/download/>.

**Option 2** (*recommended*): Install [Git for Windows](https://git-for-windows.github.io/) via the [Chocolatey](https://chocolatey.org) package manager. If this means anything to you, Chocolatey is like [`apt-get`](https://en.wikipedia.org/wiki/APT_(Debian)) or [Homebrew](https://brew.sh), but for Windows instead of Debian/Ubuntu Linux or macOS. As far as I can tell, using Chocolatey to install Git for Windows gives the same result as installing it yourself (option 1).

This obviously requires that you already have [Chocolatey](https://chocolatey.org) installed or that you are up for installing it. It is not hard and the [instructions are here](https://chocolatey.org/install). This may be worthwhile if it seems likely you will be installing more open source software in the future.

After you install Chocolatey, in a shell (Appendix \@ref(shell)), do:

``` bash
choco install git.install
```

This installs the most current [Git (Install) X.Y.Z](https://chocolatey.org/packages/git.install) Chocolatey package. At the time of writing, that is "Git (Install) 2.20.1", but that version number will increment over time.

If you [search Chocolatey packages](https://chocolatey.org/packages) yourself, you might see two packages that install Git -- "Git (Install) 2.20.1" and "Git 2.20.1", at the time of writing. I believe "Git (Install) 2.20.1" is technically the more correct, but I also think it doesn't really matter which one you use. A rather confusing explanation is found [here](https://chocolatey.org/faq#what-is-the-difference-between-packages-no-suffix-as-compared-to-install-portable). Don't worry too much about whether you do `choco install git.install` or `choco install git`.
  
**Option 3** (*NOT recommended*): The GitHub hosting site offers [GitHub Desktop for Windows](https://desktop.github.com/) that provides Git itself, a client, and smooth integration with GitHub.

  * [Their Windows set-up instructions](https://help.github.com/articles/set-up-git#platform-windows) recommend this method of Git installation.
  * Why don't we like it? We've seen GitHub Desktop for Windows lead to Git installation in suboptimal locations, such as `~/AppData/Local`, and in other places we could never find. If you were __only__ going to interact with GitHub via this app, maybe that's OK, but that does not apply to you. We are also not very fond of the GitHub Desktop client for using using Git and prefer other clients. Therefore, we strongly recommend options 1 and 2 instead.

### macOS

**Option 1** (*highly recommended*): Install the Xcode command line tools (**not all of Xcode**), which includes Git.

Go to the shell and enter one of these commands to elicit an offer to install developer command line tools:

``` bash
git --version
git config
```

Accept the offer! Click on "Install".

Here's another way to request this installation, more directly:

``` bash
xcode-select --install
```

We just happen to find this Git-based trigger apropos.

Note also that, after upgrading macOS, you might need to re-do the above and/or re-agree to the Xcode license agreement. We have seen this cause the RStudio Git pane to disappear on a system where it was previously working. Use commands like those above to tickle Xcode into prompting you for what it needs, then restart RStudio.

**Option 2** (*recommended*): Install Git from here: <http://git-scm.com/downloads>.

  * This arguably sets you up the best for the future. It will certainly get you the latest version of Git of all approaches described here.
  * The GitHub home for the macOS installer is here: <https://github.com/timcharper/git_osx_installer>.
    - At that link, you can find more info if something goes wrong or you are working on an old version of macOS.

**Option 3** (*recommended*): If you anticipate getting heavily into scientific computing, you're going to be installing and updating lots of software. You should check out [Homebrew](http://brew.sh), "the missing package manager for OS X". Among many other things, it can install Git for you. Once you have Homebrew installed, do this in the shell:

```
brew install git
```

**Option 4** (*NOT recommended*): The GitHub hosting site offers [GitHub Desktop for Mac](https://desktop.github.com/) that provides *the option* to install Git itself, a client, and smooth integration with GitHub..

  * [Their macOS set-up instructions](https://help.github.com/articles/set-up-git#platform-mac) recommend this method of Git installation.
  * We don't like GitHub Desktop as a Git client, so this is a very cumbersome way to install Git. Consider this option a last resort.

### Linux

Install Git via your distro's package manager.

Ubuntu or Debian Linux:

```sh
sudo apt-get install git
```

Fedora or RedHat Linux:

```sh
sudo yum install git
```

A comprehensive list for various Linux and Unix package managers:

<https://git-scm.com/download/linux>

* Tell me the name of your GitHub account so I can add you to the [Pelagic Ecosystems Lab on GitHub](https://github.com/pelagic-ecosystems).



## Introduce yourself to Git

Substituting your name and the email associated with your GitHub account, run these two lines of code in your R console.

```
library(usethis)
use_git_config(user.name = "Jane Doe", user.email = "jane@example.org")
```

If you have problems see [here](https://happygitwithr.com/hello-git.html) for tips.

## Connect Git, GitHub, and R-Studio

We assume the following: 

  * You've registered a free GitHub account.
  * You've updated/installed R and RStudio
  * You've installed Git
  * You've introduced yourself to Git 
  
If you have problems, confirm you can push to / pull from GitHub from the command line [chapter 9](https://happygitwithr.com/push-pull-github.html).

## Make a repo on GitHub

Go to <https://github.com/> and make sure you are logged in.

Click green "New repository" button. Or, if you are on your own profile page, click on "Repositories", then click the green "New" button.

How to fill this in:

  * Repository name: `your-discipline (eg. sockeye-diets)`.
  * Description: "Code related to (your study area)" (or whatever, but some text is good for the README).
  * Public.
  * YES Initialize this repository with a README.
  
If everything is working fine you are ready for the workshop. If not, find a friend who was successful at this and ask for their help. Or email me to let me know you are having issues and arrive at the workshop an hour early at 8 am and we can trouble shoot.
  
For everything else, just accept the default.

Click big green button "Create repository."

Copy the HTTPS clone URL to your clipboard via the green "Clone or Download" button.

## Clone the new GitHub repository to your computer via RStudio

In RStudio, start a new Project:

  * *File > New Project > Version Control > Git*. In "Repository URL", paste the URL of your new GitHub repository. It will be something like this `https://github.com/jennybc/myrepo.git`.
    - Do you NOT see an option to get the Project from Version Control? Restart RStudio and try again. Still no luck? Go to chapter [Detect Git from R-Studio](https://happygitwithr.com/rstudio-see-git.html) for tips on how to help RStudio find Git.
  * Accept the default project directory name, e.g. `your-discipline`, which coincides with the GitHub repo name.
  * Take charge of -- or at least notice! -- where the Project will be saved locally. A common rookie mistake is to have no idea where you are saving files or what your working directory is. Pay attention. Be intentional. Personally, {I would create a folder called R Projects, and save all your R projects in there.}
  * I suggest you check "Open in new session", as that's what you'll usually do in real life.
  * Click "Create Project".

You should find yourself in a new local RStudio Project that represents the new test repo we just created on GitHub. This should download the `README.md` file from GitHub. Look in RStudio's file browser pane for the `README.md` file.

## Make local changes, save, commit

From RStudio, open up the `README.md` file that you see listed in the bottom right corner of the screen and modify it, e.g., by adding the line "This is a line from RStudio". Save your changes.

Commit these changes to your local repo. How?

From RStudio:

  * Click the "Git" tab in upper right pane.
  * Check "Staged" box for `README.md`.
  * If you're not already in the Git pop-up, click "Commit".
  * Type a message in "Commit message", such as "Commit from RStudio".
  * Click "Commit".

## Push your local changes online to GitHub
  
Click the green "Push" button to send your local changes to GitHub. If you are challenged for username and password, provide them (but see below). You should see some message along these lines.

``` bash
[master dc671f0] blah
 3 files changed, 22 insertions(+)
 create mode 100644 .gitignore
 create mode 100644 myrepo.Rproj
```

## Confirm the local change propagated to the GitHub remote

Go back to the browser. I assume we're still viewing your new GitHub repo.

Refresh.

You should see the new "This is a line from RStudio" in the README.

If you click on "commits", you should see one with the message "Commit from RStudio".

If you have made it this far, you are DONE with set up. But first ...

## Were you challenged for GitHub username and password?

If you weren't challenged, YOU ARE DONE!

If you were challenged, follow these instructions

If you somehow haven't done so yet, now is the perfect time to make sure you don't need to keep providing username and password on each push.

First, make another small change locally and push again, to make sure we've given your system every opportunity to cache your credentials and retrieve them from the cache. It might "just work".

Are you still challenged? Pick one:

  *[Credential caching for HTTPS access](https://happygitwithr.com/credential-caching.html)
  
  *[Set up SSH keys](https://happygitwithr.com/ssh-keys.html)

Now is the perfect time to do this, since you have a functioning test repo.
