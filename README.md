# C-and-stdc-.h-Setup-Walkthrough-on-VSCode-MacOS-

Recently, I have had the (mis)fortune of setting up C++, as well as the bit-stdc++.h header file used in the `#include <bit/stdc++.h>` line. 

The process took me about two hours, so I hope that this repository could help people in a similar position complete this setup more efficiently. 
Thus, I have made this repo to compile the resources that I used. 

-------Installing VSCode Extensions-------

Make sure that you have the 'Code Runner' and 'C/C++' Extensions on VSCode installed. 

The latter is particularly important for changing your IntelliSense configurations. 

-------Downloading Clang-------

Clang is one compiler that works well with VSCode. In case you do not want to use the stdc++.h header file in your code, you could follow this guide:

https://code.visualstudio.com/docs/cpp/config-clang-mac

-------Accessing IntelliSense Configurations-------

This is very important for changing your default compiler and also for setting an IncludePath. 

After installing the 'C/C++' extension, go to the search bar at the top and type in `>C/C++: select a configuration`. Select 'C/C++: Select a Configuration', 
then select 'UI'. 

This will open you up to the IntelliSense Configurations tab, where you can modify your compiler settings, and more.

-------Installing and Enabling GCC-------

GCC is one of the only C++ compilers that support bit/stdc++.h header files. I used homebrew to install GCC onto my computer. 

[This youtube guide](https://youtu.be/wY24ehH6mC0?si=UNWnmzcH5S8Ty_Gr) helped me a lot. Thanks!

Installing Homebrew:

  1. Run `/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install.sh)"` on your system terminal.
     This is the installation script for homebrew.
     
  2. Follow the installation instructions to move homebrew into the right file path. You need to run two more commands to do this.
  
  3. Run `$brew install gcc` to install the GCC compiler. If the terminal does not download anything, your brew software is not installed correctly.
     Check again to make sure that you have moved it into the correct file directory.

  4. After GCC is installed, go to VSCode again. Go into the IntelliSense Configurations tab, scroll down to "Compiler Configuration" and select 
     `usr/bin/g++13`. This will make sure that you are using the correct compiler.

-------Creating stdc++.h-------

Because the header file is not a default header, you will have to [download the file](https://gist.github.com/Einstrasse/ac0fe7d7450621a39364ed3b05cacd11).

I followed [this youtube guide](https://youtu.be/3S3Bm8Dte_U?si=PapTt5rRExC9ZhRQ).

  1. Unzip the file and name it `stdc++.h`.

  2. Open the finder. Press `SHIFT + ⌘ + G` to access the GoTo function. Start typing `usr` and select `/usr/` when it shows up. Press enter.

  3. Open the `local` folder. If there is a folder named `include`, open it. If not, create a folder named `include`.

  4. In the `include` folder, create a folder named `bits`.

  5. Drag your downloaded `stdc++.h` file into the `bits` folder. At the bottom of the finder, right click the `bits` folder icon
     and select `copy bits as path`.
     
  6. Go to the IntelliSense Configurations in VSCode. paste the file path in the `Include Path` section. It should look something
     like `/usr/local/include/bits/`.

  Now, `#include <bit/stdc++.h>` should be available for VSCode. Enjoy!

