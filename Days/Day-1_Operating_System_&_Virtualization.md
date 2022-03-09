<p><strong>What is an operating system?</strong> <br>
<li>Every computer is made up of hardware such as CPU, memory, storage, I/O devices like desktop, keyboard, & mouse.<br>
    All the programs running on the computer need to use these hardware resources.
</li>
</p>

<p>Why we need operating system? <br>
Let's take an example:- <br>
    <ul>
        <li>To use applications like Chrome, it will require to use CPU, memory & some I/O devices, so that user can interact and do the job.
            <ul>
                <li>Apps don't know how to talk to the hardware.</li>
                <li>Apps can't be installed directly on the hardware.</li>
            </ul>    
        </li>
    </ul>
</p>

<p>We need to write code for that application and configuration with the hardware in order to use the application on hardware. <br> Then it will be so inefficient. So, to remove this inefficiency we use intermediate to talk to the hardware and that intermediate is known as Operating System. <br>
Operating System can interact with hardware & applications so it is like a middleman between the two. </p>

<p>What are the tasks of O.S.? <br>
    <ol>
        <li>Process Management</li>
        <li>Memory Management</li>
        <li>Storage Management</li>
        <li>Manage File System</li>
        <li>Management of I/O Devices</li>
        <li>Security & Networking</li>
    </ol>
</p>

<p>How an O.S. is constructed? <br>
<img src="https://upload.wikimedia.org/wikipedia/commons/thumb/8/8f/Kernel_Layout.svg/220px-Kernel_Layout.svg.png">
    <ul>
        <li>Kernel is a program which consists of devices drivers, dispatcher, scheduler, file system, etc.</li>
        <li>Kernel always loads first. It is the heart of every operating system responsible for managing hardware components</li>
        <li>Kernel starts the process for app, allocate resources to it & also cleans up the resources when app shuts down.</li>
    </ul>
Eg:- Different Linux Distros like Ubuntu, Mint, CentOS, etc. Android is also based on linux kernel.
</p>

<p>Linux Kernel is most widely used. On the other hand, MacOS & IOS are based on different kernel known as Darwin.</p>

<p>How to interact with kernel? <br>
Graphical User Interface(GUI) ---> Command Line Interface(CLI) <br>

<p>There are 3 main operating system for computers:-  
    <ul>
        <li>Linux</li>
        <li>Windows</li>
        <li>MacOS</li>
    </ul>
</p>    
Each OS has many versions. Kernel stays the same! but application layer is being developed & improved. <br>
</p>

<p>Operating System for Servers:- <br>
    <ul>
        <li>Mostly Linux Based.</li>
        <li>More light-weight & performant.</li>
        <li>No GUI or other user applications.</li>
    </ul>
</p>

<p><strong>Introduction to Virtualization & Virtual Machines.</strong> <br>
    <p>What is Virtual Machine? <br>
        <li>A computer system created using software on one physical computer in order to emulate the functionality of another separate physical computer.</li>
        <li>Virtual Machines are completely isolated means if something breaks inside VM, it doesn't affect the host machine.</li>
        <li>And if it breaks, you can delete that VM & create a new fresh one easily.</li>
    This is achieved by using Hypervisor <em>(a technology that allows multiple virtual computers on a physical computer(HOST OS) on top of the OS that is already installed.)</em> <br>
    Most popular hypervisor is Oracle VirtualBox which is open source and works on all O.S. <br>
    VirtualBox takes hardware resources from HOST OS and creates virtual CPU, virtual RAM, virtual storage for each virtual machine. You can only give resources that you actually have means hardware resources are shared.
    </p>
</p>

<p>Benefits of using a Virtual Machine:- 
    <ul>
        <li>Learn & Experiment.
            <ul>
                <li>You don't need to buy a new computer for that.</li>
                <li>You don't endanger your main OS.</li>
                <li>Test your application on differernt OS.</li>
            </ul>
        </li>
    </ul>
</p>

<p>There are two types of Hypervisor:-
    <ul>
        <li>Type 1 Hypervisor</li>
        <li>Type 2 Hypervisor</li>
    </ul>
<img src="https://www.serverwatch.com/wp-content/uploads/2020/09/what-is-a-hypervisor-server_5f5ed47e2d2aa.jpeg">
</p>

<p>Type 1 Hypervisor use cases <br> 
    <li>Efficient usage of hardware resources;
        <ul>
            <li>Use all the resources of a performant big server.</li>
            <li>Users can choose any resource combination.</li>
        </ul>
    </li>
Eg:- AWS, Azure, GCP, etc.
</p> 

Link for blog:- https://dipanshutorawane.hashnode.dev/operating-system-and-virtualization
