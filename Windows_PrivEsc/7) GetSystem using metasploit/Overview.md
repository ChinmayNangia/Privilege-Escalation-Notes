command -> getsystem 
use -> Attempt to elevate your privilege to that of local system

when to use and when not to use getsystem on mterepreter
can use in HTB/THM vulnerable  box 

but in real world enviroment
**Technique 2** is like technique 1. It creates a named pipe and impersonates the security context of the first client to connect to it. To create a client with the SYSTEM user context, this technique drops a DLL to disk(!) and schedules rundll32.exe as a service to run the DLL as SYSTEM. [The DLL](https://github.com/rapid7/meterpreter/blob/master/source/elevator/namedpipeservice.c) connects to the named pipe and that’s it. Look at [elevate_via_service_namedpipe2](https://github.com/rapid7/meterpreter/blob/master/source/extensions/priv/server/elevate/namedpipe.c) in Meterpreter’s source to see this technique.

As the help information states, this technique drops a file to disk. This is an opportunity for an anti-virus product to catch you. If you’re worried about anti-virus or leaving forensic evidence, I’d avoid getsystem –t 0 (which tries every technique) and I’d avoid getsystem –t 2.
(https://www.cobaltstrike.com/blog/what-happens-when-i-type-getsystem/)