<h4>Working with VIM Editor</h4>
<p>
    <strong>How do we edit file in CLI?</strong> <br>
    <li>We have built-in text editor in linux like nano, vi/vim(Improved version of vi), etc.</li>
    <strong>Use cases to use text editor in CLI</strong> <br>
    <li>small modifications can be faster, especially when you are currently working in CLI.</li>
    <li>faster to create & edit at the same time.</li>
    <li>supports multiple formats.</li>
    <li>when working on a remote server.</li>
</p>

<h5>Important VIM commands:</h5>
<ul>
    <li>vim [filename] -> open file with vim.</li>
    <li>vim has two modes:
        <ul>
            <li>Command Mode;
                <ul>
                    <li>This is the Default mode.</li>
                    <li>You cannot edit the text.</li>
                    <li>Whatever you type is interpreted as a command.</li>
                    <li>Navigate, Search, Delete, Undo, etc. can be done in this mode.</li>
                </ul>
            </li>
            <li>Insert Mode;
                <ul>
                    <li>Allows you to enter text.</li>
                </ul>
            </li>
        </ul>
    </li>
    <li>To switch from command mode to insert mode, press 'i'.</li>
    <li>And from insert to command mode, press 'Esc'.</li>
    <p><strong>Note:-</strong> All these should be run in command mode.
    <li>:wq -> write file to disk & quits vim.</li>
    <li>:q! -> quit vim without saving the changes.</li>
    <li>dd -> delete a entire line.</li>
    <li>d[number] -> delete bunch of line. <br>
        Eg; d10 -> deletes next 10 lines.
    </li>
    <li>u -> undo changes.</li>
    <li>A -> jump to end of the line & switches to insert mode.</li>
    <li>0 -> jump to start of the line(but not switches to insert mode).</li>
    <li>$ -> jump to the end of the line(without switching to insert mode).</li>
    <li>[number]G -> go the line [number] <br>
        Eg; 12G -> go to the line 12
    </li>
    <li><strong>/</strong>[pattern/word] -> search for that pattern/word. <br>
        Eg; /nginx -> searches for pattern/word 'nginx'
        <ul>
            <li>Type 'n' -> jump to the next match.</li>
            <li>Type 'N' -> jump to the previous match/ in opposite direction.</li>
        </ul>
    </li>
    <li>:%s/[old]/[new] -> Replaces old with new throughout the file.</li>
    </p>
</ul>

<h4>Linux Accounts & Groups.</h4>
<p><strong>There are three user categories:-</strong>
    <ol>
        <li>
            SuperUser Account;
            <ul>
                <li>Root User (unrestricted permissions)</li>
                <li>For administrative tasks: No need to login as Root user or execute any commands as root(sudo command).</li>
            </ul>
        </li>
        <li>
            User Account;
            <ul>
                <li>A regular user we create to login</li>
                <li>Eg; Username=dipanshu then it is found under /home/dipanshu</li>
            </ul>
        </li>
        <li>
            Service Account;
            <ul>
                <li>Relevant for Linux Server Distros</li>
                <li>Each service will get its own user.</li>
                <li>Eg; mysql user will start mysql application(Best practice for security).</li>
            </ul>
        </li>
    </ol>
    <strong>Note:- Don't run services with root user!</strong> <br>
    <li>Always 1 Root user per computer.</li>
    <li>Can have multiple regular users & service users.</li>
</p>

<h5>Why multiple standard users?</h5>
<li>Many companies use windows for their employees. Usually employees can login to their account on every computer.</li>

<h5>How does this work?</h5>
<li>Windows is able to centrally manage users.</li>
<li>Admins add users to the system. All computers are connected to this system.</li>
<li>When someone tries to login, OS checks it with the system(Only have access to YOUR home folder)[completely isolated system](No access to system files or other user's home folder).</li>

<p><strong>In Windows,</strong> login to any hardware that is connected to this system(centrally managed user permission). <br>
<strong>In Linux,</strong> it doesn't have this centrally managed system. This is the reason why Windows is preferred in companies or universities. 
</p>

<h5>Multiple Users on Linux;</h5>
<p>User accounts are managed on that specific hardware(cannot access form any other hardware)</p>

<h5>Multiple Users on a Server;</h5>
<ul>
    <li>For Linux having Multi-User is important for servers.</li>
    <li>Usually teams administer a server.</li>
</ul>

<strong>Why not just use a  shared user? & Why having a user for each team member is important?</strong> <br>
<ul>
    <li>They need a non-root user.</li>
    <li>Permissions can be assigned per team member.</li>
    <li>Traceability-> who did what on the system?</li>
    <li>Admin creates user with permissions.</li>
</ul>

<h5>Groups & Permissions;</h5>
<strong>How to manage Permissions?</strong> <br>
<ul>
    <li>User Level -> Give permission to user directly.</li>
    <li>Group Level -> 
        <ul>
            <li>Group Users into Linux groups.</li>
            <li>Give permissions to the group.</li>
            <li>The way to go, if you manage mulltiple users(Best Practice).</li>
        </ul>
    </li>
</ul>

<h5>User Management in practice;</h5>
<p>Access Control Files:-
    <ul>
        <li>/etc/passwd
            <ul>
                <li>Stores user account information.</li>
                <li>Everyone can read it but only root user can change the file.</li>
                <img src="http://etutorials.org/shared/images/tutorials/tutorial_99/541331fg1204.jpg">
            </ul>
        </li>
        <li>/etc/shadow
            <ul>
                <li>Contains information about the system's users' passwords.</li>
            </ul>
        </li>
        <li>/etc/group
            <ul>
                <li>Contains a list of groups and the members belonging to each group.</li>
            </ul>
        </li>
    </ul>   
    <strong>Managing Users;
        <ul>
            <li>Do not edit these access control files with a text editor.</li>
            <li>Instead use the dedicated commands.</li>
        </ul>
    </strong> 
</p>

<h5>Commands for user/group creation & management;</h5>
<strong>Note:- </strong> root user priviledges required.
<ul>
    <li>adduser [username] -> 
        <ul>
            <li>create a new user.</li> 
            <li>automatically creates a home directory with skeletal configuration.</li> 
        </ul>
    </li>
    <strong>Where does the primary group come from?</strong> <br>
    Whenever we create user using useradd, by default it creates the same group named as the user & sets that as a primary group ID of user.
    <li>passwd [username] -> change the password of a user</li>
    <li>su - [username] -> login asa username(short for substitute or switch user).</li>
    <li>su - -> login as root.</li>
    <li>groupadd [groupname] -> create new group. By default, system assigns the next available GID from the range of group ID's specified in the login.defs file.</li>
</ul>

<h5>Different User & Group Commands;</h5>
<ul>
    <li>adduser addgroup
        <ul>
            <li>Interactive.</li>
            <li>More user friendly.</li>
            <li>(Easier to use!)
                <ul>
                    <li>It chooses conformant UID & GUID values for you.</li>
                    <li>Creates a home directory with skeletal config automatically.</li>
                    <li>Or asks for input in interactive mode.</li>
                </ul>
            </li>            
        </ul>
    </li>
    <li>useradd groupadd
        <ul>
            <li>You need to provide the information.</li>
            <li>Lowlevel utilities.</li>
        </ul>
    </li>
</ul>
<strong>Which one to use?</strong> <br>
<ul>
    <li>adduser addgroup
        <ul>When executing it manually.</ul>
    </li>
    <li>useradd groupadd
        <ul>
            <li>When executed in an automated way.</li>
        </ul>
    </li>
</ul>
<strong>Same goes for deluser<em>(deletes user)</em> delgroup<em>(deletes groups)</em> & userdel groupdel.</strong>
<ul>
    <li>usermod [options] [username] -> modify a user account.</li>
    <li>for changing group -> usermod -g [groupname] [username]</li>
</ul>
<p> <strong>In additional</strong> to one primary group, user can have multiple secondary groups & as a result user will get all the permissions that the groups have which it belongs to (means we can add one user to multiple groups). </p>
<ul>
    <li>sudo usermod -G [groupsname(separated with commas)] [username]
        <ul>
            <li>add user to multiple group.</li>
            <li>-G option will overwrite the whole secondary groups list. So, it always sets the new list of groups for the user.</li>
            <li><strong>If you need to add user to new secondary group in addition to the existing ones it already belongs to we use 'sudo usermod -aG [groupname] [username]'</strong></li>
        </ul>
    </li>
    <li>groups [username] -> displays the groups that the user is added.</li>
</ul>

<p>More efficient way; <br>
'useradd [options] [username]' -> create new user
<ul>
    <li>the low-level command compared to "adduser"</li>
    <li>-G -> create user with multiple secondary groups</li>
    <li>-d -> custom home directory</li>
</ul>
</p>

<ul>
    <li>sudo gpasswd -d [username] [groupname] -> remove user from the specified group.</li>
</ul>

<h4>File Permissions & Ownerships.</h4>
<p>User permissions are related to reading, writing & executing files in Linux. <br>
<li>ls -l -> print files in a long listing format.</li>
</p>

<h5>Ownerships;</h5>
<p>It means who owns the file/directory. <br>
There are two levels of a file/directory.
<ol>
    <li>Which user owns the file?</li>
    <li>Which group owns the file?</li>
</ol>
<li>Owner is the user who created the file.</li>
<li>Owning group is the primary group of that user.</li>
<ul>
    <li>(should be executed with root priviledges)chown [username]:[groupname] [filename] -> change ownership<em>{in this command you can also change user by not adding ':[groupname]'}</em></li>
    <li>sudo chgrp [groupname] [filename] -> changes the group</li>
</ul>
</p>

<h5>File Permissions;</h5>
<img src="https://i.pinimg.com/originals/d3/e7/4a/d3e74a87f423bbb62e39d9de30e6399d.gif">

<h5>Modifying Permissions;</h5>
<p>[Symbolic values method] ->
<ul>
    <li>sudo chmod [flags] [filename] -> Changes permission for that file & for all users.
        <ul>
            <li>*Flags:
                <ul>
                    <li>+r -> adds read permission</li>
                    <li>+w -> adds write permission</li>
                    <li>+x -> adds execute permission</li>
                    <li>-r -> takes away read permission</li>
                    <li>-w -> takes away write permission</li>
                    <li>-x -> takes away execute permission</li>
                </ul>
            </li>
            <li>*Adjusting permissions:
                <ul>
                    <li>Owner(u), Group(g), Others(o) & All(a) <br>
                    Eg; sudo chmod g-w config.yaml -> removes write permission for the group.
                    </li>
                </ul>
            </li>
            <li>*Alternate ways to give permissions:
                <ul>
                    <li>sudo chmod u/g/o/a=rwx [filename] -> gives multiple permission to mentioned one's. <br>
                        Type out whole 'rwx' block or 'r--'/'rw-' etc.
                    </li>
                </ul>
            </li>
        </ul>
    </li>
</ul>
[Numeric values method] -> 
<ul>
    <li>sudo chmod [numeric value] {filename}  <br>
        <img src="http://2.bp.blogspot.com/-V2eWUJugBJ0/Ui4Y1TJ45aI/AAAAAAAAAzQ/gwxcb-GlTGA/s1600/chmod4.png">
    </li>
</ul>
</p>

<h4>Input, Output & Pipes in Linux</h4>
<p><strong>Every program has</strong> Input & Output. <br>
The output from one program can become the input of another command.
<li>Syntax for this is "pipe" command "|"
    <ul>
        <li>pipes the output of the previous command as an input to the next command.</li>
    </ul>
    Eg; cat /var/log/syslog (outputs log in non-usr friendly way) | less (helps to see the output page-by-page){to jump to next page press 'spacebar' & to jump to previous page press 'b'}
</li>
<ul>
    <li>To filter commands for specific keyword we use 'grep [keyword]' -> grep stands for <em>Globally Search for Regular expression & print-out.</em> & it searches for a particular pattern of characters & displays all lines which contain that pattern.</li>
    <li>To search for a phrase we have to enclose in {" "} double quotes.</li>
</ul>
</p>

<h5>Redirects in Linux</h5>
<p>Used to save the output of other command into a file. <br>
<strong>Redirection;</strong>
<ul>
    <li>'>' character is the redirect operator.</li>
    <li>Takes the output from the previous command & sends it to a file that you give.</li>
    <li>Eg; history | grep sudo > sudo-commands.txt</li>
    <li>To add new lines in the existing file by using redirect can be done using '>>' -> append text to the end of file</li>
</ul>
</p>

<h5>Standard Input & Standard Output</h5>
<ul>
    <li>Every program has 3 built-in streams;
        <ol>
            <li>STDIN(0) -> Standard Input</li>
            <li>STDOUT(1) -> Standard Output</li>
            <li>STDERR(2) -> Standard Error</li>
        </ol>
    </li>
    <li>We pipe or redirect the standard output from one command to the standard output of another command.</li>
</ul>

<strong>*We cannot execute many commands in one line but can be done by separating them with ';' (semi-colon)</strong> <br>
Eg; clear; sleep 2; echo "Hello, welcome back"

Link to my blog:- https://dipanshutorawane.hashnode.dev/basic-linux2
