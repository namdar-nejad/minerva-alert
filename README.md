# minervous

`minervous.py` performs the tedious task of constantly checking Minerva for classes that are full but don't have a waiting list, or for classes whose registration status is yet to be set to 'Active'.

## Requirements

* Python 3.6
* Selenium
* Chrome Web Driver

## Basic Usage

You must create two files with the following format:

Login info file (default location is current directory and default name is `logins.txt`): 

```
bob.loblaw@mail.mcgill.ca bobpassword1234
bob.loblaw@gmail.com bobgmailpw1234 
```

Courses to monitor (default location is current directory and default name is `watchlist.txt`)

Row format: `<department code>,<course number>,<CRN>,<term>`

```
COMP,767,11806,Winter 2018
COMP,250,18360,Winter 2018
```

```
python minervous.py
```

This will automatically log in to Minerva and check each course every 30 minutes.

If a course's status changes or the number of spots available becomes greater than 0 you will receieve an email.

Every 24 hours you will receive a summary email with the latest status of all the courses you are watching.

Help:

```
python minervous.py -h
```

To override the default time interval options see the help menu by using the command above.

Note: This tool was inspired by @zulban's [zminerva](https://github.com/Zulban/zminerva) which had a lot more functionality but is now out of date with the current minerva.
