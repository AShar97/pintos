Steps to install Pintos in the Bochs emulator.

1. Connect to the server using ssh [example: "ssh gb@progsrv.cse.iitg.ernet.in"].

2. Download Pintos from the course website. Extract it in some directory, say for example $HOME="/home/cse/gb". The files will be extracted to the folder "$HOME/pintos". Copy the perl scripts "backtrace", "pintos", "pintos-gdb", "pintos-mkdisk" from "$HOME/pintos/src/utils" into a directory in your PATH. For example, I have added $HOME/bin to my PATH. So, I copied these scripts into the $HOME/bin folder.

3. If ~/bin is not included in your PATH, you may add it by modifying the ".bash_profile" file located in your home directory. To add the path ~/bin in your PATH, edit your ".bash_profile" file and add the line "$PATH = $PATH:$HOME/bin" to it.

4. Next, open the script "pintos-gdb" (the one in your "~/bin" folder) using any text editor. Find the variable "GDBMACROS" and set it to point to "~/pintos/src/misc/gdb-macros". Now, you have installed pintos-gdb.

5. Now, go back to your "~/pintos/src/utils" folder and compile the rest of the Pintos utilities by typing "make" as shown in the example below.

$ cd $HOME/pintos/src/utils
$ make

Copy the script "squish-pty" into your "~/bin" folder, this is where you had copied the scripts mentioned above as well.

6. Next, compile pintos as shown in the example below.

$ cd $HOME/pintos/src/threads/
$ make

7. Now, open the file "$HOME/bin/pintos" (the one you copied into the PATH) in any text editor and edit the following lines as shown in the example below.

Line no.24: replace "os.dsk"  with  "$HOME/pintos/src/threads/build/os.dsk"

Line no. 90: $vga = "none" if !defined vga;

This is all. Now, you are ready to run pintos. Check your installation by typing in the terminal as shown in the next step.

8. Run pintos by typing the following command.

$ pintos run alarm-multiple

This will create 5 threads and sleep for some predefined times. You can see all these messages in the terminal. Now you are ready to implement changes and enhance pintos. To exit, press the keys "Ctrl + z" or "Ctrl + c".
