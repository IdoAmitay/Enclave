# ZKP over intel SGX
Final project

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
