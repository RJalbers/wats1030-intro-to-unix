# *nix Scavenger Hunt

Complete the following challenges using the command-line interface on your favorite
Unix or Linux operating system. You are welcome and encouraged to consult any
additional documentation online or in books.

Please add your answers/responses/text pastes to the document after each prompt.

Note: For some of the challenges you will need to reference files included with
this repository, so you will need to fork the repo into your own Github account
and then clone it to your development environment.

## The Challenges

### Navigating the Filesystem

* Get an idea of where you are in the operating system. Use the `pwd` command to find your "path to working directory"--your current location in the filesystem of your devbox. *Paste the output of the `pwd` command here:*

/users/rjalbe/projects

* Discover more about this filesystem. Use `ls` (the "list" command)to see what is in this directory. *What directories and files do you see when you run `ls`?*

Calcuator			wats-3020-hello-cowsay
Darkweb.docx			wats1030-intro-to-unix
Personal essay.docx		wats3010-hello-world
RJalbers.github.io		wats3010-intro-to-bootstrap-4
Toggle-menu-project		wats3010-product-page
Videogame			wats3010-project-1
complete-javascript-course	wats3010-project-2
emealio				wats3010-skills-1
headfirst.html			wats3010-skills-2
index.html


* You can use *options* to modify how a command runs. Try using `ls -alh` to see the contents of your current directory. *How are the results different when you use the `-alh` options?*

It adds a bunch of extra data next to the files 
in the directory. It adds date and time, size, user,
and characters like drwxr-xr-x which I don't know 
what that means.

* The `man` ("manual") command tells you more about how any given command works. (*WARNING:* CodeAnywhere does not support the man command. You can click the following link to complete this task: http://man.he.net/). Run `man` to see instructions about how to use `man`. Then use `man` to learn what the `a`, `l`, and `h` options mean when used with the `ls` command. *Write down what those options do?*
 
 -a, --all
do not ignore entries starting with .

-h, --human-readable
 with -l and/or -s, print human readable sizes (e.g., 1K 234M 2G)

  -l     use a long listing format


* Commands can also take *arguments*, which are usually the names of files or locations that you want the command to work with. Try running `ls /` to see what files are in the *root* directory of the filesystem. *What files and directories do you see listed?*

Applications			etc
Library				home
Network				installer.failurerequests
System				net
Users				private
Volumes				sbin
bin				tmp
cores				usr
dev				var


* A Unix filesystem has a few special shortcuts to refer to specific locations. `/` indicates the *root* of the filesystem, meaning the top-most directory in the filesystem hierarchy. Use the `cd` ("change directory") command to move to the root directory. (Hint: Use `man` to look up the `cd` command if you have any issues) *Then run `pwd` and paste the output here:*

MacBook-Pro:/ rjalbe$ pwd
/

* Another special shortcut in Unix is the `~` location. This indicates the *user root* directory, meaning the top-most directory in the hierarchy that comes below your user account. Use `cd` to move to `~`. *Run `pwd` and paste the response here:*

MacBook-Pro:~ rjalbe$ pwd
/Users/rjalbe

* Change directory into the `challenge_files` directory. Use `ls` to find only the files with a `.demo` pattern. *How many files do you find?*

3

* Use the `cd` command to move "up" one directory. *Where are you in the filesystem now?*

/Users/rjalbe/projects/wats1030-intro-to-unix

* Press the up arrow on your keyboard. *What just happened?*

Went back to my last command that I typed in.

* Press the up arrow a few more times. *What do you see?*

It goes through all the last couple commands I have 
previously used.

* Run the `history` command. *What do you see?*

Gives me a list of all the commands I have used.

### Observing the System

* Discover what account you are logged into using the `whoami` command. *What username are you currently using?*

rjalbe

* Discover who else is on your system with the `who` command. *Are any other users using your system? If so, list them here:*

No there is not

* How long has your system been running? Use `uptime` to see, and *paste the result here:*

19:02  up 3 days, 17:33, 2 users, load averages: 2.28 2.27 2.04

* Run `ps aux` and review the results. (Hint: Use `man` to learn more about the `ps` command and options.) *How do you interpret what you see here?*

It's all the processes owned by the user.

* Run `top` and review the results. (Hint: You may need to use `ctrl-c` to get out of this app.) *How do you interpret what you see here?*

It's all the programs the computer is running at 
the moment from what I'm seeing. Looks similar 
to the task manager.

### Finding and Viewing Files

* Make sure you are in the `challenge_files` directory. Use the `*` wildcard to find all the files that have the word "credit" in the filename. *How many files did you find?*

2

* Use the `more` command to view one of the `credit_cards` files you just discovered. (Hint: Type `q` to quit viewing the file. Press the `spacebar` to page down. Use your keyboard arrows to move up/down.) *What is the date in the file you have viewed?*

01-15-2015

* Use the `find` command to search for files more effectively. Search the sub-directories under `challenge_files` to find the location of the file named
 `modi_laboriosam.txt`. *Where is that file located?*

challenge_files/tmp/modi_laboriosam.txt


* Use the `grep` command to search for text within a file. Use `grep` on all the `.user` files in `challenge_files` to find which files contain "WA" (the abbreviation for Washington state). *How many files did you find?*
* Use the `-r` option of `grep` to *recursively* find the text "Waldo" hidden in a file somewhere under the `challenge_files` directory. *Paste the result showing the file and line where the word "Waldo" shows up.*

/Users/rjalbe/projects/wats1030-intro-to-unix/challenge_files/serial-numbers/eaque_molestiae.txt:Ut est maiores quia autem. Nisi modi Waldo sed corporis sit explicabo ut est. Et est placeat ea sunt sunt consectetur sunt incidunt. Explicabo vel esse blanditiis dolorem culpa non quia.

### Pipes and Connecting Commands

* Sometimes it's useful to output the results of a command to a text file for further analysis, reference, or processing. Try running `ls > files.txt`. Notice that the file `files.txt` was created. View that file using `more`. *What do you see in the `files.txt` file?*
01
2015_special_stuff.demo
Afton-Jast.user
Aimee-Maggio.user
Alfonso-Gottlieb.user
Allen-Kemmer.user
Almina-Cormier.user
Alta-Lemke.user
Amina-McGlynn.user
Anabel-Hammes.user
Ancel-Conn.user
Anjali-Halvorson.user
Ardath-Kuvalis.user
Avah-Dickinson.user
Ayaan-Stiedemann.user
Aylin-Grant.user
files.txt

* Notice that if you run `ls -alh` in the `challenge_files` directory, the files scroll by very quickly. Sometimes it would be better to get the results in a paginated format. Try running `ls -alh | more`. *Describe what you see when you run `ls -alh | more`.*

I see the total number of files which list the number 864. There's one list with my username & staff & file size & date/time & filename

* Earlier, when you viewed the list of active processes on your devbox using `ps aux`, the list was probably really long. You can make this list more manageable by using the pipe (`|`) to filter the results of `ps` using `grep`. Run `ps aux | grep <your_username>` to see what processes are running for your specific user. *Paste the list of processes that reference your username here:*

There's an insane amount of information on this list running ps aux.
