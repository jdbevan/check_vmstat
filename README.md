Bash script [Nagios](http://nagios.com/) plugin used to analyse [vmstat(8)](http://linux.die.net/man/8/vmstat) output.

Inspired by [check_apache2](http://exchange.nagios.org/directory/Plugins/Web-Servers/Apache/check_apache2-2Esh/details).

	$ ./check_vmstat --help
	Version 0.2, 2012, Jon Bevan (https://github.com/jdbevan)
	
	Description:
	check_vmstat is a Nagios plugin to monitor the output of 
	vmstat(8) on a server. It returns a mean value based on a number
	of updates for all the values provide by vmstat by default unless
	specified otherwise using the arguments below.
	
	Example calls:
	./check_vmstat -P -C -Y --delay 1 --count 20
	./check_vmstat --output memory,swap,io -d 3
	
	Options:
	  -P|--procs)
	    Display the procs figures.
	  -M|--memory)
	    Display the memory figures.
	  -W|--swap)
	    Display the swap figures.
	  -I|--io)
	    Display the I/O figures.
	  -Y|--system)
	    Display the system figures.
	  -C|--cpu)
	    Display the cpu figures.
	
	  -d|--delay)
	    The delay in seconds between vmstat updates in seconds. If not 
	    provided then the figures returned are the averages since system
	    boot.
	  -c|--count)
	    The number of vmstat updates. Ignored if delay is not specified.
	    Default value is 5.
	  -o|--output)
	    Comma separated string specifying the data output from: procs,
	    memory, swap, io, system, cpu, all.
	    Added to options -P -M -W -I -Y and -C. Default: all.
	

TODO: Allow specification of critical/warning limits as optional arguments to follow output specifiers
