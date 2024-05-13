# Linux-Process-API-fork-wait-exec-
Ex02-Linux Process API-fork(), wait(), exec()
# Ex02-OS-Linux-Process API - fork(), wait(), exec()
Operating systems Lab exercise


# AIM:
To write C Program that uses Linux Process API - fork(), wait(), exec()

# DESIGN STEPS:

### Step 1:

Navigate to any Linux environment installed on the system or installed inside a virtual environment like virtual box/vmware or online linux JSLinux (https://bellard.org/jslinux/vm.html?url=alpine-x86.cfg&mem=192) or docker.

### Step 2:

Write the C Program using Linux Process API - fork(), wait(), exec()

### Step 3:

Test the C Program for the desired output. 

# PROGRAM:

## C Program to print process ID and parent Process ID using Linux API system calls

```
#include <stdio.h>
#include <sys/types.h>
#include <unistd.h>
int main(void)
{	//variable to store calling function's process id
	pid_t process_id;
	//variable to store parent function's process id
	pid_t p_process_id;
	//getpid() - will return process id of calling function
	process_id = getpid();
	//getppid() - will return process id of parent function
	p_process_id = getppid();
	//printing the process ids

//printing the process ids
	printf("The process id: %d\n",process_id);
	printf("The process id of parent function: %d\n",p_process_id);
	return 0; }
```












## OUTPUT
![image](https://github.com/Ritika-2706/Linux-Process-API-fork-wait-exec/assets/93427238/fca3121e-9cec-4e47-bcad-e798ee3e8e48)

![image](https://github.com/Ritika-2706/Linux-Process-API-fork-wait-exec/assets/93427238/2e4c5d79-2c2c-4087-9a08-edf879662a79)

![image](https://github.com/Ritika-2706/Linux-Process-API-fork-wait-exec/assets/93427238/66609256-5b8d-4f8d-94c8-69ed5ecf6e5e)















## C Program to create new process using Linux API system calls fork() and exit()

![image](https://github.com/Ritika-2706/Linux-Process-API-fork-wait-exec/assets/93427238/4c62e6d9-88ea-4092-8115-070fb89b84d8)











## OUTPUT
![image](https://github.com/Ritika-2706/Linux-Process-API-fork-wait-exec/assets/93427238/2040153e-8e91-4dcb-9a52-55b715d49d06)









## C Program to execute Linux system commands using Linux API system calls exec() family

```
#include<stdio.h>
#include<unistd.h>
#include <stdlib.h>
#include <sys/wait.h>
#include <sys/types.h>
int main()
{       int status;
        printf("Running ps with execlp\n");
        execl("ps", "ps", "ax", NULL);
        wait(&status);
        if (WIFEXITED(status))
                printf("child exited with status of %d\n", WEXITSTATUS(status));
        else
                puts("child did not exit successfully\n");
        printf("Done.\n");
printf("Running ps with execlp. Now with path specified\n");
        execl("/bin/ps", "ps", "ax", NULL);
        wait(&status);
        if (WIFEXITED(status))
                printf("child exited with status of %d\n", WEXITSTATUS(status));
        else
                puts("child did not exit successfully\n");
        printf("Done.\n");
        exit(0);}
```

























## OUTPUT

![image](https://github.com/Ritika-2706/Linux-Process-API-fork-wait-exec/assets/93427238/6ca64e08-cf54-4b6d-9ad7-ff153234bdb5)

















# RESULT:
The programs are executed successfully.
