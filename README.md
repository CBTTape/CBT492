# CBT492
Converted to GitHub via [cbt2git](https://github.com/wizardofzos/cbt2git)
This is still a work in progress. GitHub repos will be deleted and created during this period...
~~~~~~~~~~~~~~~~

//***FILE 492 is from Roland Schiradin and contains SHOWzOS         *   FILE 492
//*           Release 8.01, and Release 7.25, as well as many       *   FILE 492
//*           previous releases.                                    *   FILE 492
//*                                                                 *   FILE 492
//*           SHOWMVS old boundary releases are:  6.30 and 7.10.    *   FILE 492
//*           Release 7.01 had dropped support for pre-OS/390       *   FILE 492
//*           systems, so if you have an older system, you should   *   FILE 492
//*           use SHOWMVS 6.30.  For current levels of z/OS, you    *   FILE 492
//*           should use SHOWzOS 8.01 or 7.25 which are the current *   FILE 492
//*           versions.  You should re-assemble SHOWzOS with your   *   FILE 492
//*           current system levels that you plan to run it on.     *   FILE 492
//*                                                                 *   FILE 492
//*     >>>>  ---------------------------------------------- <<<<   *   FILE 492
//*     >>>>                                                 <<<<   *   FILE 492
//*     >>>>  This is the permanent home of SHOWMVS/SHOWzOS. <<<<   *   FILE 492
//*     >>>>                                                 <<<<   *   FILE 492
//*     >>>>  ---------------------------------------------- <<<<   *   FILE 492
//*     >>>>       IF YOU ARE RUNNING z/OS 2.1 OR 2.2,       <<<<   *   FILE 492
//*     >>>>      YOU HAVE TO USE SHOWzOS 7.22 OR 7.23.      <<<<   *   FILE 492
//*     >>>>       IF YOU ARE RUNNING z/OS 2.4 OR 2.3,       <<<<   *   FILE 492
//*     >>>>      YOU HAVE TO USE SHOWzOS 8.01 OR 7.25.      <<<<   *   FILE 492
//*     >>>>       IF YOU ARE RUNNING ON A Z14, OR LATER.    <<<<   *   FILE 492
//*     >>>>      YOU SHOULD USE SHOWzOS 8.01.               <<<<   *   FILE 492
//*     >>>>  ---------------------------------------------- <<<<   *   FILE 492
//*                                                                 *   FILE 492
//*           SHOWMVS and SHOWzOS belonged to Gilbert Saint-flour.  *   FILE 492
//*           We owe Gilbert a big "thank you" for having invented  *   FILE 492
//*           this utility, and having maintained it for a long     *   FILE 492
//*           time.  Gilbert turned the maintenance of SHOWzOS      *   FILE 492
//*           over to Roland Schiradin a number of years before     *   FILE 492
//*           his passing.                                          *   FILE 492
//*                                                                 *   FILE 492
//*           SHOWzOS is currently being maintained by Roland       *   FILE 492
//*           Schiradin.                                            *   FILE 492
//*                                                                 *   FILE 492
//*           SHOWzOS 8.01 has been included here as members:       *   FILE 492
//*             SHOWZOS   -  source code                            *   FILE 492
//*             SHOWMACS  -  7.25 and 8.01 macro library            *   FILE 492
//*             SHOWJ725  -  JCL to assemble release 7.25           *   FILE 492
//*             SHOWJCL8  -  JCL to assemble release 8.01           *   FILE 492
//*                                                                 *   FILE 492
//*           ISPF statistics for these members reflect their       *   FILE 492
//*           release number.                                       *   FILE 492
//*                                                                 *   FILE 492
//*           Some shops might have trouble assembling SHOWzOS      *   FILE 492
//*           because it requires certain PTF levels of the HLASM   *   FILE 492
//*           Assembler program ASMA90.  If you can't assemble      *   FILE 492
//*           SHOWzOS yourself, we have supplied CBT File 614       *   FILE 492
//*           with many assembled load modules for different z/OS   *   FILE 492
//*           levels and SHOWzOS levels.  You can try these load    *   FILE 492
//*           modules and figure out which works best on your       *   FILE 492
//*           own system.                                           *   FILE 492
//*                                                                 *   FILE 492
//*           If you REALLY NEED to assemble some of the previous   *   FILE 492
//*           versions of SHOWzOS, source is included here back to  *   FILE 492
//*           version 7.18, with the appropriate macro libraries    *   FILE 492
//*           and jobstreams.  These are clearly marked in their    *   FILE 492
//*           member names and ISPF statistics.  These are RECENT   *   FILE 492
//*           SHOWzOS releases.  Old releases are SHOWMVS, and      *   FILE 492
//*           SHOWM630, which can take you back all the way to      *   FILE 492
//*           ESA, if that is what you are running.  If you need    *   FILE 492
//*           source for any other SHOWzOS releases, please write   *   FILE 492
//*           to Sam Golob <sbgolob@cbttape.org>.  Just about all   *   FILE 492
//*           you'll ever need is also probably covered by the      *   FILE 492
//*           load module libraries in File 614.                    *   FILE 492
//*                                                                 *   FILE 492
//*       SOME OF THE FOLLOWING REMARKS APPLY TO RUNNING SHOWzOS    *   FILE 492
//*       ON OLDER z/OS SYSTEMS (using previous SHOWzOS versions):  *   FILE 492
//*                                                                 *   FILE 492
//*           The system macro levels you are assembling with, are  *   FILE 492
//*           crucial if you are migrating from z/OS 1.8 to z/OS    *   FILE 492
//*           1.9 or higher.  So in File 614, the separately        *   FILE 492
//*           assembled load modules are marked accordingly, and    *   FILE 492
//*           you can tell which load modules were assembled on     *   FILE 492
//*           a z/OS 1.9 system or higher.                          *   FILE 492
//*                                                                 *   FILE 492
//*           SHOWzOS starting from version 7.16, and higher        *   FILE 492
//*           versions, including the current version which is      *   FILE 492
//*           7.25, requires having z/Architecture, and, at least,  *   FILE 492
//*           z/OS 1.3. (I also think SHOWzOS 7.17 had been tested  *   FILE 492
//*           to run with z/OS releases back to 1.4 or 1.5 - SBG.)  *   FILE 492
//*                                                                 *   FILE 492
//*           The most current version of SHOWzOS, version 8.01,    *   FILE 492
//*           uses many new machine instructions for the z-series   *   FILE 492
//*           machines.  You may (at this point) prefer to run      *   FILE 492
//*           version 7.25 if 8.01 doesn't run on your machine.     *   FILE 492
//*           The level of SHOWzOS that you run, should be consis-  *   FILE 492
//*           tent with the level of z/OS that you are running.     *   FILE 492
//*                                                                 *   FILE 492
//*           SHOWzOS may be invoked as an ISPF command, or from an *   FILE 492
//*           entry in the ISPF command table.  However, it should  *   FILE 492
//*           be invoked as a CMD instead of as a PGM.              *   FILE 492
//*           Like this -                                           *   FILE 492
//*                                                                 *   FILE 492
//*              SELECT CMD(SHOWZOS &ZPARM) MODE(FSCR)              *   FILE 492
//*                                                                 *   FILE 492
//*           If you don't invoke it this way from the ISPF         *   FILE 492
//*           command table, SHOWzOS may abend.                     *   FILE 492
//*                                                                 *   FILE 492
//*           For pre-assembled load modules at different z/OS      *   FILE 492
//*           levels, please see File 614.  Also see File 614       *   FILE 492
//*           for load modules of previous releases of SHOWzOS.     *   FILE 492
//*           You should use whatever load modules work best on     *   FILE 492
//*           your system, should you not be able to assemble       *   FILE 492
//*           SHOWzOS for yourself.  (Assembly requires certain     *   FILE 492
//*           release and PTF levels of the HLASM assembler         *   FILE 492
//*           ASMA90.)  Try to use the highest version of SHOWzOS   *   FILE 492
//*           that works on your system.                            *   FILE 492
//*                                                                 *   FILE 492
//*           On this file, the following members contain source:   *   FILE 492
//*                                                                 *   FILE 492
//*               SHOWZOS    -  Source code for SHOWzOS 8.01        *   FILE 492
//*               SHOWMVS    -  Source code for SHOWMVS 7.10        *   FILE 492
//*               SHOW630    -  Source code for SHOWMVS 6.30        *   FILE 492
//*                                                                 *   FILE 492
//*    ASSEMBLY:                                                    *   FILE 492
//*    --------                                                     *   FILE 492
//*           You need a customized macro library to assemble       *   FILE 492
//*           SHOWMVS and SHOWzOS.  Member SHOWMACS contains the    *   FILE 492
//*           macro members to assemble the current version of      *   FILE 492
//*           SHOWzOS.  SHOWM630 contains the macros to assemble    *   FILE 492
//*           the SHOW630 source.  SHOWM717 and SHOWM718 (same      *   FILE 492
//*           as for 7.19) are the macro libraries for SHOWzOS      *   FILE 492
//*           7.17 and 7.18 respectively).                          *   FILE 492
//*                                                                 *   FILE 492
//*           These macro libraries are in IEBUPDTE SYSIN format    *   FILE 492
//*           (really PDSLOAD format - File 093 and File 035).      *   FILE 492
//*                                                                 *   FILE 492
//*           Other macros needed are IBM macros:  They are in      *   FILE 492
//*           SYS1.MACLIB, SYS1.MODGEN, TCP/IP and CEE (LE) maclib. *   FILE 492
//*           These macro libraries should be at the system level   *   FILE 492
//*           where you intend to run SHOWzOS.                      *   FILE 492
//*                                                                 *   FILE 492
//*    Please note that at the z/OS 1.4 level, macro CSFDACC in     *   FILE 492
//*    SYS1.MODGEN has a duplicate field name DACC_LEN .  The       *   FILE 492
//*    second instance of this field name should be replaced by     *   FILE 492
//*    DACC_LEN_TOT .  This problem is addressed by APAR OA01618    *   FILE 492
//*    which is fixed by PTF UA00902 in 704 and UA00903 in 706.     *   FILE 492
//*                                                                 *   FILE 492
//*    By now (January 2016) with z/OS at at least 1.13, 2.1, 2.2   *   FILE 492
//*    for most people, the comments in the above paragraph are     *   FILE 492
//*    old.  (Now - December 2020, it's even later.)                *   FILE 492
//*                                                                 *   FILE 492
//*           Please address any comments or questions to:          *   FILE 492
//*                                                                 *   FILE 492
//*         Sam Golob          sbgolob@cbttape.org                  *   FILE 492
//*                                                                 *   FILE 492
//*    or   Roland Schiradin   roland@schiradin.de                  *   FILE 492
//*                                                                 *   FILE 492
~~~~~~~~~~~~~~~~

