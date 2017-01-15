# OVERVIEW

`fkdate` - change  'access time', 'modification time' and 'change time' of files and folders to random value in specified date and time ranges.

#SYNOPSIS

    fkdate [-h] [-V] [-d <time1>[-<time2>]] [-t <time1>[-<time2>] ] [-M <margin>] [-f <dirname>]

#OPTIONS

    -d <date1>[-<date2>]    Set date to be between <date1> and <date2> or around <date1> if <date2> is not specified. Possible formats: dd, mm/dd, mm/dd/yyyy, mm/yyyy, yyyy
    -t <time1>[-<time2>]    Set time to be between <time1> and <time2> or around <time1> if <time2> is not specified. Possible formats: hh, hh:mm, hh:mm:ss 
    -D <dirname>            Change files in <dirname> (or file), hidden files included. If -D flag is not used the target is the current directory.
    -M <margin>             Set the time margin to be <margin> instead of 5h. Accepted format: <N>s,<N>m,<N>w,<N>m,<N>y where <<N>> is an integer. 
    -v                      Verbose mode, display filenames along the modified time
    -h                      Display command help
    -V                      Diplay current version

# EXAMPLES

1.
    fkdate

Change 'access time', 'modification time' and 'change time' of all files in the current directory to the previous day at 15:00 within a margin of 5 hour.

2.
    fkdate -d 01/01/2000 -M 10d 

Change time of all files to dates situated around 01/01/2000 with a margin of 10 days

3.

    fkdate -d 01/01/2016-01/02/2016 -t 12:00-13:00 -f /root


Change time of all files in `/root` to random dates between 01/01/2016 and 01/02/2016 and time  12:00 and 13:00 

# VARIABLE

* $DEFAULT_TIME=15:00
* $DEFAULT_DATE="yesterday"
* $DEFAULT_MARGIN: 5h
