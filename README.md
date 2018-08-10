# ZKP over intel SGX
Final project

Our initial goal was to try finding a security breach in the Intel SGX system.
We tried to do that by using a rootkit to attack the linux kernel and change the
syscall table, and then using system calls to show vulnerability in the SGX
architecture.
We managed to penetrate older kernel versions and change the syscall tables
but couldn't manage to do the same with the newer versions.
After learning that only newer kernel versions support the SGX drivers, we
decided to change the aim of the project.
Another difficulty we ran into is that the whole SGX technology is relatively
new (especially in linux) and hence finding assistance and resources online is
tough.
This difficulty made writing code utilizing the SGX enclave api and using the
SGX simulation mode much harder than we initially expected.



• In our project, we create a game that demonstrate the use of zeroknowledge
  proofs.
• The game:

  o Imagine that you hold two balls in front of a colorblind person,
    one blue and the other red.
    You want to prove the colorblind person that you can distinguish
    between those two balls.
    A colorblind person can’t tell the difference between “red” and
    “blue”.
    
  o Let’s play a little game:
    let the colorblind person take the balls, put them behind his back
    and shuffle as much as he likes.
    He then show you the balls and you will determine if he had
    change their order or not.
    
  o We’ll repeat this experiment 42 times to make it more accurate in
    terms of probability.
    
  o The colorblind person understands that it’s almost impossible to
    guess the correct answer 42 times in a row (2
    -42 ) so he should be
    convinced that you are indeed able to distinguish between the
    balls.


installation guide:
visual studio 2013 - https://visualstudiogallery.msdn.microsoft.com/4ec1526c-4a8c-4a84-b702-b21a8f5293ca
interl sgx sdk - https://software.intel.com/en-us/sgx-sdk/download
in order to run the program: open enclave2.sln and just run




Syscall-table-hijack

This demonstrates the hijacking of the "write" system call and how to set the System Call table to read/write mode via modifying the correct cr0 bit.

Install with insmod maK_it.ko

Remove with rmmod maK_it


OUTPUT


insmod maK_it.ko Message from syslogd@localhost at Nov 25 17:36:13 ... kernel:Syscall Table Address: c08532b0

Message from syslogd@localhost at Nov 25 17:36:13 ... kernel:Syscall Table old write address: c0537520

Message from syslogd@localhost at Nov 25 17:36:13 ... kernel:Syscall Table new write address: f7e58000

rmmod maK_it Message from syslogd@localhost at Nov 25 17:37:49 ... kernel:Module exited cleanly
