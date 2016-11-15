# FastFileComparator
A command line application for quickly displaying the differences or commonality between two text files.

The design is simple, yet powerful and fast.  The application is well suited for comparing large files which have a lot of redundant information but may be out of sync with each other.  A typical example could be the output log of a real-time device.  Such a log file will have messages emnanting from a number of threads, which makes it especially difficult to use typical difference programs on.  In addition, most applications are hampeered by memory constraints if they have to store the contents of an entire  file.

This is how it works:
The 'base' file is read and the unique lines are stored in a HASH TABLE.
The 'comparison' file is then compared line by line to the HASH TABLE:

If the -c flag is selected, only the common log lines are displayed along with the line number of the base file
If the -d (or no flag) switch is used, then only the uncommon log lines (lines that exist in the compare file but not the bae file) are displayed along with the base log numnber.

other switches -n, removes hexadecimal digits from the line. These include [0-9] [a-f].  This switch is very useful in device logs where to eliminate false line differences due to time stamp, handle number etc.

