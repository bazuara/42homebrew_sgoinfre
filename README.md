<img
  src="https://raw.githubusercontent.com/kube/vscode-42header/master/42.png" 
  width=128>

42 Homebrew
===========

### Install Homebrew properly on your 42 session, but with all the data on the sgoinfre.

Moves temporary Homebrew data (`Temp` and `Cache`) to `/tmp` and symlinks the rest from the sgoinfre, leaving your home directory barely touched.
Supposes that the sgoinfre is an NFS volume, which it normally is (at least in Paris). But the script should work even if it were to be an iSCSI volume.

Install
-------
Run this command from your terminal:

```sh
curl -fsSL https://raw.githubusercontent.com/bazuara/42madrid_homebrew_sgoinfre/master/install.sh | zsh
```

Homebrew is now ready on your session.

How it works
------------
This script removes your current Homebrew installation in your home and/or your personal sgoinfre space if any, and reinstalls it properly from the Homebrew Github repo.

Then it simply creates a `.brewconfig.zsh` script in your home directory, and modifies your `.zshrc` to source the script.

It is simple to remove, and you can re-run it multiple times without duplication.


Uninstall
---------
Simply remove these lines from your `.zshrc`

```sh
# Load Homebrew Fix script
source $HOME/.brewconfig.zsh
```

And delete `.brewconfig.zsh` in your home directory.
