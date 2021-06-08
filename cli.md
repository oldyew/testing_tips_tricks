# CLI

cd ~
cd -
cd /

ll


ls
ls -l
ls -a
ls -R
ls -lh

man command

q

touch

mkdir
rmdir

mv
cp

rm
rm -r
rm -rf
rm -ri

git reset --hard

cat

less
/<word>

grep -i
grep -v
grep -R
grep -e

:w
:q
:q!
dd

find . -name *_file
find . -type d
find . -type f
find . -name "*.mp3" -delete
find . -name "*.mp3" -delete -print






## Generate file

fsutil file createnew filename length
fsutil file createnew test.txt 52428800
fsutil file createnew c:\users\steve\desktop\1gb.test 1073741824

64b
echo "This is just a sample line appended to create a big file.. " > dummy.txt
for /L %i in (1,1,14) do type dummy.txt >> dummy.txt

1gb
echo "This is just a sample line appended to create a big file.. " > dummy.txt
for /L %i in (1,1,24) do type dummy.txt >> dummy.txt

100MB
echo "This is just a sample line appended  to create a big file. " > dummy.txt
for /L %i in (1,1,21) do type dummy.txt >> dummy.txt

1 MB = 1048576 bytes
100 MB = 104857600 bytes
1 GB = 1073741824 bytes
10 GB = 10737418240 bytes
100 GB =107374182400 bytes
1 TB = 1099511627776 bytes
10 TB =10995116277760 bytes

realpath

busybox - a lot of commands

history

aliases

      - consider links, "pwd -L" vs "pwd -P", $PWD
      - relative paths
        - ., ..
        - any number of ./././././././
        - "$ . ./.mybash"
          - first . is same as 'source' command
          - dot at the start of file as mark of hidden file
      - realpath helper (dirname, basename too)
      - trailing /, when to use
        - ... and not only trailing ones (cd ~/WORK/////AQA)
        - cd ~; cd ~/WORK/AQA///////
  - CDPATH/PATH
    - do.sh vs ./do.sh (first fail via paths, consider ./)
      - echo $PATH
      - export PATH=$PATH:. (for to have current dir in paths)
    - export CDPATH=$CDPATH:/home/dkravchenko/WORK/AQA/;cd ~; cd LEMON
    - Where to keep it persistently?
      - ~/.bashrc -> source ~/.mybash
        - ~/.mybash, as symlink to own repo
     - $OLDPWD
       - "bash" + "echo $SHLVL $PWD $OLDPWD"
      - ~N, ~-N, ~+N,  see (pushd/popd/dirs)
    - https://github.com/wting/autojump
    - https://dmitryfrank.com/articles/shell_shortcuts
    - https://github.com/huyng/bashmarks
    - https://lug.fh-swf.de/shell/#bookmarks

      - history | grep keyword |tail -n
      - history | less -X # Use / and ? for interactive search down an up
    - limited history
      - alias hs25="history 25"
    - size
      - echo $HISTFILESIZE $HISTSIZE
      - echo $HISTFILE
    - exclusions
      - export HISTIGNORE="history:ls:pwd:"
    - date and time
      - export HISTTIMEFORMAT='%F, %T '
  - Exec:
    - by !N
      - only print, !42:p (do not pass to history too)
      - Alt+Shit+6, expand w/o exec (see designators below)
    - by !! (previous command)
    - common designator structure: event/word/modifier (https://www.gnu.org/software/bash/manual/html_node/Event-Designators.html)
      - !substring, !?substring
      - !echo:p
        - p is one of modifiers (https://www.gnu.org/software/bash/manual/html_node/Modifiers.html#Modifiers)
      - "$ echo BANANA" + "$ ^BANANA^APPLE^"
      - "echo longlongword" + "!!:1" + Alt+Shit+6
    - Interactive history search by Ctrl-R
  - Security:
    - space at the start of cmd for not being saved in history
    - custom deletion, "history -d N"
    - custom deletion like ninja
      - history -d $((HISTCMD-1)) && history -d <line entry number>
    - total annihilation ('history -c; history -w')
    - no history at all
      - export HISTFILE=/dev/null
  - Save:
    - echo $HISTFILE
    - echo $HISTCONTROL, dups and spaces options
      - erasedups only erases sequential duplicates (((
      - affects only newly added part, not the previous lines in histfile ((
        - tac ~/.bash_history | awk '!a[$0]++' | tac > t; mv t ~/.bash_history; history -c; history -r   # keep the last
      - Multi-lines
        - "C-x" then "C-e" for shell editor
        - shopt -p | grep his  # (http://www.gnu.org/software/bash/manual/html_node/The-Shopt-Builtin.html)
          - cmdhist
          - lithist
    - Append or override?
      - shopt -s histappend
      - history -r, read from file and append to current list (history -c && history r)
      - history -n, read fresh delta from file
      - history -a, history -a /dev/stdout
        - in case of stdout, no append at the end of session, need to rewrite file
          - history -w
    - save once immediately ("history -a", or more hard and unsafe "history -w")
    - save immediately on continuous basis
      - export PROMPT_COMMAND='history -a; history -n'
        - first one for append history lines from this session to the history file
        - second one for read all history lines not already read from the history file
  - Misc:
     - builtin "fc" command, "fix command"
       - fc -l
       - fc
       - fc -s ^floder^folder^
- (ALIASES)
  - 'alias' cmd
  - prep/grep/drep
  - Where to set:
    - /etc/bash.bashrc vs ~/.bashrc,
    - interactive and non-interactive script
    - login and non-login shell (echo $0, shopt login_shell)
  - single/multiline/parametric (via functions in .bashrc)
  - bash hotkeys,  bind -x '"\C-p":git status'
  - additional:
    - xdg-open
    - Git aliases in ~/.gitconfig
