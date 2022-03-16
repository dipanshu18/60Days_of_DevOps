<p>
    <h4>Basic Linux commands</h4>
        <p><strong>Note:-</strong> Everything in linux is a file. Eg; text documents, pictures, directories, devices like printer, keyboard, USB, CD, etc. & even commands like pwd, ls, etc.</p>
            <ul>
                <li>pwd(print working directory) - Show current directory</li>
                <li>cd [dir name] : Change directory to [dir]</li>
                <li>cd .. : Move one level up</li>
                <li>mkdir [dir name] : Make directory of [dir name] </li>
                <li>ls : Lists all files and directories in the present working directory</li>
                <li>ls -R : Lists files in sub-directories as well</li>
                <li>ls -al : Lists files and directories with detailed information like permissions,size, owner, etc.</li>
                <li>ls -a : show all files & folders(including hidden) </li>
                <li>touch [filename] : creates [filename] </li>
                <li>rm [filename] : delete [filename] </li>
                <li>rmdir or rm -d : Deletes a directory</li>
                <p> <strong>Note:-</strong> Here rm commands delete the file permanently. </p>
                <li>rm -r(recursively) : Removes file or folder if it contains files inside it.</li>
                <li>cat [filename] : 	Displays the file content</li>
                <li>cat file1 file2 > file3 : Joins two files (file1, file2) and stores the output in a new file (file3)</li>
                <li>mv file "new file path" : Moves the files to the new location</li>
                <li>mv filename new_file_name : Renames the file to a new filename</li>
                <li>sudo : Allows regular users to run programs with the security privileges of the superuser or root</li>
                <li>man : Gives help information on a command</li>
                <li>history : Gives a list of all past commands typed in the current terminal session</li>
                <li>history [number] : Gives the previous [number's] of command</li>
                <li>touch [filename] : creates [filename]</li>
                <li>clear : Clears the terminal</li>
                <li>cp -r [dirname] [new_filename] : copy dirname to new_filename</li>
                <li>Ctrl + C : stop current command</li>
                <li>Ctrl + R : search history</li>
                <li>uname -a : show system & kernel</li>
                <li>lscpu : show inf about cpu</li>
                <li>lsmem : show info about memory</li>
                <li>su - [name of the user] : switch the user to [name of the user]</li>
                <li>cat /etc/os-release : gives info about distro, version, etc.</li>
                <li>init 0 : to shutdown/poweroff machine</li>
                <li>init 6 : to restart/reboot machine</li>
            </ul>
</p>

<p>
    <h2>Package Manager</h2>
    <h4>How to install software on Linux?</h4>
    <p>In Windows, you download installer & then it installs it through installation wizard. But in Linux, we don't use this way, we install most of the software/apps using package manager tool.</p>
    <h4>What is software package?</h4>
        <p>A compressed archive, containing all required files. Apps usually have dependencies. <br>
        Eg; Firefox Browser, it requires dependencies which are not packaged into the archive. These dependencies also need to be installed.
        </p>
    <h4>What is package manager?</h4>
        <p>Files are split across different folders. Not like Windows, where every program is installed in a single file in Program Files. In Windows, it also easy to uninstall program as they are in single folder but in Linux, managing apps uninstalling everything completely is more difficult(as they are splitted).</p>
        <p>Package Manager:-
            <li>downloads, installs or updates existing software from the repository.</li>
            <li>ensures the integrity & authenticity of the package.</li>
            <li>manages & resolves all required dependencies.</li>
            <li>knows where to put all the files in Linux file system.</li>
            <li>easy upgrading of the software.</li>
        </p>
    <h4>Where to I get such Package Manager?</h4>
        <li>Package Manager is included already in every Linux distribution.</li>
        <li>In Ubuntu, you have APT(advance package tool) package manager available.</li>
    <h4>Commands used in package manager(commands should be used with sudo):</h4>
        <li>apt search [package_name] : Search for a given package</li>
        <li>apt install [package_name] : Install a given package</li>
        <li>apt install [package_name1] [package_name2] : Install multiple packages with one command</li>
        <li>apt remove [package_name] : Removes installed package</li>
    <h4>Benefits of using package manager is:-</h4>
        <li>One central place to install, upgrade, configure & remove software.</li>
    <h3>Difference b/w APT & APT-GET</h3>
        <li><strong>APT:</strong>
            <ul>
                <li>more user friendly, like it has progress bar.</li>
                <li>fewer, but sufficient command options in more organised way(Use apt because recommended by Linux distributions).</li>
            </ul>
        </li>
        <li><strong>APT-GET:</strong>
            <li>search command not available</li>
            <li>you can achieve the same, if you use additional command options.</li>
        </li>
    <h4>Where do these Packages come from?</h4>
    <p>Package Manager fetches the packages from these repositories.</p>
    <h4>Where do these files stored?</h4>
    <p>Repository(storage location) containing thousands repositries of programs.</p>
    <h4>Best practice:-</h4>
    <p>Always update the package index before upgrading or installing new packages.</p>
    <li>apt update : 
        <ul>
            <li>updates the package index</li>
            <li>pulls the latest changes from the APT repositories</li>
            <li>the APT package index is basically a database</li>
            <li>holding records of available packages from the repositories.</li>
        </ul> 
    </li>
</p>

<p>
    <ul>
        <li>add-apt-repository : add repository to official list of repos
            <ul>
                <li>add repository to APT sources (into /etc/apt/sources.list)</li>
            </ul>
        </li>
    </ul>
    <h5>Why add repository?</h5>
    <p>When installing relatively new applications which are not in official repository yet.</p>
</p>

<p>
    <h4>Repositories Types:-</h4>
    <p>
        Repositories are of type PPA(Personal Package Archive)
        <ul>
            <li>PPA's are provided by the community.</li>
            <li>Anybody can create this PPA-private repository to distribute the software.</li>
            <li>Usually used by developers to provide updates more quickly than in the official Ubuntu repositories.</li>
            <li>Be Aware of possible risks before adding a PPA:
                <ul>
                    <li>no guarantee of quality or security</li>
                    <li>like any other unofficial software package it can cause difficulties , e.g. , when upgrading to new Ubuntu release.</li>
                </ul>
            </li>
        </ul>
    </p>
</p>
Link to my blog:- https://dipanshutorawane.hashnode.dev/basic-linux1
