# sbquery
For use with SponsorBlock's sponsorTimes.csv files. 

Tally user vote stats of all -2 through +4 and >4 votes and can help identify outliers. 
Requires awk or mawk. Works with gawk but takes ~3.5x longer. 

This started off as a one-trick pony for a special case but grew a bit to allow 
for a few command line options rather than the hardcoded stuff that was there. 
Dumping on github in case anyone else might find it useful.

Why awk? I dunno, it's been a while since I did anything with it and it seemed 
like the right tool for the job (brute force CSV crunching).

Fake manpage:
sbquery counts all -2 through +4 and >4 votes for users specified on the command line.
     It can also summarize votes for all users and include that in the report.

    -a  Show sums and percentages of all users. First row in report.

    -d  sponsorTimes.csv location. Full path and filename required.
        Defaults to "$sbTimes"

    -e  End Time of report. 
        Default is 9999999999999 (Nov. 20, 2286).

    -h  Include column headers.

    -n  [number of segments] Minimum number of segments a user must have to be included. 
        Doesn't affect -a results.

    -q  Quiet. 
        No screen output.

    -r  [filename] Report path and filename. 
        Default is ./sbquery.csv

    -s  Start Time of report. Default is 1598936400000 (September 1, 2020).
        Soon after the autovote function was removed with some added time
        for padding.

    -u  [UUID]  User UUID to report, can have multiple instances.
