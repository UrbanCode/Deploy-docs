#  IBM z/OS directories and data sets

To deploy applications to an IBM® z/OS® environment, the user accounts on the agent computer must have adequate access permissions. You must also identify specific directories and data sets to the authorized program facility.

The agent user account must have access to the following UNIX™ directories and files, and MVS™ data sets.

|Directories, files, and data sets|Required access permissions|
|---------------------------------|---------------------------|
|The /tmp directory or the agent/var/temp directory.|RW|
|The agent/conf directory|RW|
|The agent/var/work directory.|RW|
|The agent/var/repository directory. The directory to store artifacts when an HFS CodeStation is used.|R|
|The agent/var/deploy directory. The directory where backup data and deployment results are stored .|RW|
|The agent/var/log/ispf directory. The directory where ISPF gateway log files are stored.|RW|
|The HLQ.SBUZAUTH, HLQ.SBUZEXEC, HLQ.SBUZMENU, and HLQ.SBUZSAMP data sets|R|

The access permissions are set up when you install the agent. If you use a different user account to run the agent, the access permissions must be set correctly for that account.

**Parent topic:** [Security requirements on IBM z/OS computers](../../com.udeploy.admin.doc/topics/security_zos.md)

