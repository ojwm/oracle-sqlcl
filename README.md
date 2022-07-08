# Oracle SQLcl

From [oracle.com](https://www.oracle.com/database/technologies/appdev/sqlcl/sqlcl-faq.html):
> SQLcl is a command-line interface for Oracle Database that combines the power of SQL*Plus and SQL Developer.

## Install

SQLcl is [now under the Oracle Free Use Terms and Conditions license](https://blogs.oracle.com/database/post/sqlcl-now-under-the-oracle-free-use-terms-and-conditions-license), which makes automated installation much easier.

Java is required, so ensure that at least Java Runtime Engine (JRE) 8 is installed. ([macOS](https://formulae.brew.sh/formula/openjdk), [Linux](https://openjdk.org/install/)).

### macOS

Using [Homebrew](https://formulae.brew.sh/cask/sqlcl):

```sh
brew install --cask sqlcl
```

Note that this may not add the `bin` folder to `PATH`, so try the command on the Homebrew page and restart the shell.\
Alternatively, add the command to `~/.zshrc`:

```sh
# Set path variables.
path+=$(brew --prefix)/Caskroom/sqlcl/<version>/sqlcl/bin
export path
typeset -U path
```

Alternatively, use the [shell script](#shell-script).

### Linux

SQLcl is available through `yum` on the [Oracle Linux Yum Server](https://yum.oracle.com/getting-started.html#installing-software-from-oracle-linux-yum-server).

```sh
sudo yum install sqlcl
```

Alternatively, use the [shell script](#shell-script).

### Shell script

1. Clone this repository and treat the root as the working directory.

   ```sh
   cd ~
   mkdir git
   cd git
   git clone <url>
   ```

1. The script may ask for the current user's password, as it will attempt to install SQLcl to `/opt`.

   ```sh
   $ ./install.sh
     % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                    Dload  Upload   Total   Spent    Left  Speed
   100 39.4M  100 39.4M    0     0  8721k      0  0:00:04  0:00:04 --:--:-- 8900k

   Installation complete
   ```

1. Check the SQLcl install.

   ```sh
   $ which sql
   /usr/local/bin/sql

   $ echo $SQLPATH
   /Users/<user>/.sqlcl

   $ sql /nolog


   SQLcl: Release 22.2 Production on Fri Jul 08 23:09:28 2022

   Copyright (c) 1982, 2022, Oracle.  All rights reserved.

   SQL> 
   ```
