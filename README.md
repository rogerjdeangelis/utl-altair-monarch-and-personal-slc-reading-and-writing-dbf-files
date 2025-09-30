# utl-altair-monarch-and-personal-slc-reading-and-writing-dbf-files
Altair monarch and personal slc reading and writing dbf files
    %let pgm=utl-altair-monarch-and-personal-slc-reading-and-writing-dbf-files;

    %stop_submission;

    Altair monarch and personal slc reading and writing dbf files

    Too long to post in a listserve, see github

    github
    https://tinyurl.com/36usnkpn
    https://github.com/rogerjdeangelis/utl-post-weekend-and-holiday-sales-to-the-next-business-weekday-using-personal-altair-slc

     CONTENTS

        1 MONARCH issue?
          see https://tinyurl.com/y28rb3hu
        2 personal slc
          dBASE II, III, III PLUS, IV, 5.0, but not Visual dBASE 7
        3 r personal slc
          Visual dBASE
        4 personal sl repos

    No need for MS Access.

    community.altair
    https://tinyurl.com/y28rb3hu
    https://community.altair.com/discussion/63292/monarch-issue?tab=all&utm_source=community-search&utm_medium=organic-search&utm_term=monarch

    /*                   _
    (_)_ __  _ __  _   _| |_
    | | `_ \| `_ \| | | | __|
    | | | | | |_) | |_| | |_
    |_|_| |_| .__/ \__,_|\__|
            |_|
    */

    &_init_;
    data have;
      input
        name$
        sex$ age;
    cards4;
    Alfred  M 14
    Alice   F 13
    Barbara F 13
    Carol   F 14
    Henry   M 14
    James   M 12
    ;;;;
    run;quit;

    /*                                        _
    / |  _ __ ___   ___  _ __   __ _ _ __ ___| |__
    | | | `_ ` _ \ / _ \| `_ \ / _` | `__/ __| `_ \
    | | | | | | | | (_) | | | | (_| | | | (__| | | |
    |_| |_| |_| |_|\___/|_| |_|\__,_|_|  \___|_| |_|

    */

    see https://tinyurl.com/y28rb3hu

    /*___                                         _       _           _ _
    |___ \  _ __   ___ _ __ ___  ___  _ __   __ _| |  ___| | ___   __| | |__   __ _ ___  ___
      __) || `_ \ / _ \ `__/ __|/ _ \| `_ \ / _` | | / __| |/ __| / _` | `_ \ / _` / __|/ _ \
     / __/ | |_) |  __/ |  \__ \ (_) | | | | (_| | | \__ \ | (__ | (_| | |_) | (_| \__ \  __/
    |_____|| .__/ \___|_|  |___/\___/|_| |_|\__,_|_| |___/_|\___| \__,_|_.__/ \__,_|___/\___|
           |_|
    */

    /*--- just delete outputs ----*/
    proc datasets lib=work nolist
      nodetails;
    delete want;
    run;quit;

    %utlfkil(d:\dbf\have.dbf)

    /*---- create dbf         ----*/

    proc export data=have
        outfile='d:\dbf\have.dbf'
        dbms=dbf
        replace;
    run;quit;

    /*--- read dbf           ----*/
    proc import datafile='d:\dbf\have.dbf'
        out=want
        dbms=dbf
        replace;
    run;quit;


    OUTPUT
    ======

    Altair SLC

    Obs    NAME        SEX     AGE

     1     Alfred      M        14
     2     Alice       F        13
     3     Barbara     F        13
     4     Carol       F        14
     5     Henry       M        14
     6     James       M        12

    /*____                                                _       _
    |___ /   _ __   _ __   ___ _ __ ___  ___  _ __   __ _| |  ___| | ___
      |_ \  | `__| | `_ \ / _ \ `__/ __|/ _ \| `_ \ / _` | | / __| |/ __|
     ___) | | |    | |_) |  __/ |  \__ \ (_) | | | | (_| | | \__ \ | (__
    |____/  |_|    | .__/ \___|_|  |___/\___/|_| |_|\__,_|_| |___/_|\___|
                   |_|
    */

    /*--- just delete outputs ----*/
    proc datasets lib=work nolist
      nodetails;
    delete males;
    run;quit;

    &_init_;
    %utlfkil(d:\dbf\have.dbf);

    proc r;
    export data=have r=have;
    submit;
    library(foreign)
    library(sqldf)
    options(sqldf.dll = "d:/dll/sqlean.dll")
    write.dbf(have, "d:/dbf/have.dbf")
    df <- read.dbf("d:/dbf/have.dbf", as.is = TRUE)
    males<-sqldf('
      select
         *
      from
         df
      where
         sex="M"
      ')
    males
    endsubmit;
    import data=males r=males;
    run;quit;

    proc print data=males;
    run;quit;

    OUTPUT
    ======

    Altair SLC

    Obs     NAME     SEX    AGE

     1     Alfred     M      14
     2     Henry      M      14
     3     James      M      12

    /*  _                                           _       _
    | || |    _ __   ___ _ __ ___  ___  _ __   __ _| |  ___| |  _ __ ___ _ __   ___  ___
    | || |_  | `_ \ / _ \ `__/ __|/ _ \| `_ \ / _` | | / __| | | `__/ _ \ `_ \ / _ \/ __|
    |__   _| | |_) |  __/ |  \__ \ (_) | | | | (_| | | \__ \ | | | |  __/ |_) | (_) \__ \
       |_|   | .__/ \___|_|  |___/\___/|_| |_|\__,_|_| |___/_| |_|  \___| .__/ \___/|___/
             |_|                                                        |_|
    */

    Select slc from d:/git/git_010_repos.sasbdat

    REPO
    ------------------------------------------------------------------------------------------------------------------------------------
    https://github.com/rogerjdeangelis/setup-personal-edition-altair-slc-eclipse-workspace-config-sasautos-sasuser-saswork-autoexec
    https://github.com/rogerjdeangelis/utl-altair-slc-to-fill-gaps-in-proc-sql-select-third-place-in-the-daily-double-r-python-solutions
    https://github.com/rogerjdeangelis/utl-calling-python-from-personal-altair-slc-and-integrating-python-with-sql
    https://github.com/rogerjdeangelis/utl-calling-r-from-personal-altair-slc-and-integrating-r-with-sql
    https://github.com/rogerjdeangelis/utl-dropping-down-to-powershell-from-personal-altair-slc
    https://github.com/rogerjdeangelis/utl-how-to-create-a-sas-dataset-from-python-panda-dataframe-using-the-personal-altair-slc
    https://github.com/rogerjdeangelis/utl-how-to-create-a-sas-dataset-from-r-dataframe-using-the-personal-altair-slc

    /*              _
      ___ _ __   __| |
     / _ \ `_ \ / _` |
    |  __/ | | | (_| |
     \___|_| |_|\__,_|

    */
