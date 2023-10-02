# linux

- export to PATH `export PATH="/path/to/directory:$PATH"`

- How do I show the git branch with colours in Bash prompt? [
    - bash version `$ echo $BASH_VERSION` or `$ help`
    - open bashrc in vscode `$ code /home/USER-NAME/.bashrc`
    - add these lines in your `~/.bashrc` file: [

        ```bash
        # Show git branch name
        force_color_prompt=yes
        color_prompt=yes
        parse_git_branch() {
        git branch 2> /dev/null | sed -e '/^[^*]/d' -e 's/* \(.*\)/(\1)/'
        }
        if [ "$color_prompt" = yes ]; then
        PS1='${debian_chroot:+($debian_chroot)}\[\033[01;32m\]\u@\h\[\033[00m\]:\[\033[01;34m\]\w\[\033[01;31m\]$(parse_git_branch)\[\033[00m\]\$ '
        else
        PS1='${debian_chroot:+($debian_chroot)}\u@\h:\w$(parse_git_branch)\$ '
        fi
        unset color_prompt force_color_prompt
        ```

    ]

    - reload the `.bashrc` file with this command `$ source /home/samuel/.bashrc `
]