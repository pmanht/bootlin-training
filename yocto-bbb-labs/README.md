# Create git submodules
- git submodule add https://github.com/OWNER/REPO.git path/to/submodule
- ex. git submodule add https://git.yoctoproject.org/git/meta-arm 
- heck file .gitmodules (cat .gitmodules)

# Clone a repo with submodules
- git clone --recurse-submodules <repo-url>
- or after clone, run. git submodule update --init --recursive

# Useful git submodule cmds
- git submodule status
- git submodule foreach git pull
- git submodule update --remote

# Configure the branch in .gitmodules
- git config -f .gitmodules submodule.path/to/submodule.branch main
- ex. git config -f ../.gitmodules submodule.yocto-bbb-labs/meta-arm.branch yocto-5.0.1
- check file .gitmodules (cat .gitmodules) 
