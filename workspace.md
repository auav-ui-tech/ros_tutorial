# Creating ROS Workspace
In this first tutorial, I will guide you to create ROS Workspace. ROS Workspace is simply a directory where you can run your ROS program. Outside ROS Workspace, ROS won't run. You can create multiple ROS Workspaces in your local machine.

Let's create ROS Workspace named `auav_ui` in `home` directory.

Run this on your terminal
```
cd ~		# Change directory to ~ (home)
mkdir auav_ui	# Create directory auav_ui
cd auav_ui	# Change directory to auav_ui
mkdir src 	# Create directory src inside auav_ui
catkin_make	# Initialize directory auav_ui as ROS Workspace
```

Now you already created ROS Workspace named `auav_ui` inside `~` directory. You should notice that the hierarchy of your `auav_ui` directory, by running `tree` command inside `auav_ui` directory, is as follows
```
auav_ui
├── build
│   ├── catkin
│   │   ├──
│   │   └──
│   ├── catkin_generated
│   │   ├──
│   │   └──
│   ├── Makefile
│   └── test_results
├── devel
│   ├── env.sh
│   ├── lib
│   ├── setup.bash
│   ├── setup.sh
│   ├── _setup_util.py
│   └── setup.zsh
└── src
    └── CMakeLists.txt
```
You'll see that there are a lot of stuff inside `build` directory. What you should notice that, early we only create empty `src` directory inside `auav_ui` but now there are `build` and `devel` directories, also `CMakeLists.txt` file inside `src` directory.

You already created ROS Workspace but that's not enough. You need to make your machine acknowledge that particular directory is ROS Workspace and not an odrinary directory using `source` command. You need to `source` your `setup.bash` file inside `devel` directory (see the hierarchy at the top).

There are 2 ways to do that.
1. Manual `source`<br>
The first method is to `source` your ROS Workspace manually by running this command on your terminal, `source ~/auav_ui/devel/setup.bash`. This method is not recommended because you need to run that command everytime you open new terminal

2. Automatic `source`<br>
The second method is to edit your `.bashrc` file directly. `.bashrc` is simply a file that get executed by your machine everytime you open new terminal. So, by editing your `.bashrc` file, the `source` command will be executed automatically.<br><br>
`.bashrc` file is located inside `~` directory. If you try to run `ls` inside `~` directory, you'll notice that there's no `.bashrc` file. This is because Ubuntu hides every file whose name started with dot. You can list all your files, including the hidden ones, using `ls -a`.<br><br>
Let's edit your `.bashrc` file. You can use your favorite text editor to edit it e.g. `nano`, `vim`, `geany`, etc. I use `geany` for this one. You can install `geany` using `sudo apt install geany` command.
	- Run this on your terminal, `sudo geany ~/.bashrc`.
	- Add `source ~/auav_ui/devel/setup.bash` at the bottom and save it.
	- Run this on your terminal, `source ~/.bashrc`.

Now your workspace is fully set up but where do you put your source code? That's the topic for the next tutorial, ROS Package.

Notes
--
* `cd` stands for `change directory` is a command to move between directory.
* `ls` shorts for `list` is a command to list all files inside your current directory.
* `tree` is a command to generate tree-like hierarchy of your files inside your current directory.
* `mkdir` shorts for `make directory` is a command to create an empty directory.
* `sudo` stands for `super user do` is a command acts like Run as Administrator in Windows.
* `geany` is a command to launch geany text-editor.
* `-a` on `ls -a` command is called argument. Most commands has its own argument for advance usage. The equivalent of `ls -a` is `ls --all`. You can check all available arguments for praticular command using `--help` argument e.g. `ls --help`, `mkdir --help`, etc.
* There's no such ROS Workspace. What we just created is Catkin Workspace, place to manage your project, not limited to ROS. You can search on Google what is `catkin` but it is not mandatory. You just need to know that this is Catkin Workspace used to manage your ROS Project, hence ROS Workspace. Deep understanding of catkin is not required.