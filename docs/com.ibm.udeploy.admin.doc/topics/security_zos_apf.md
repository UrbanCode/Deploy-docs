#  IBM z/OS authorized program facility

To deploy applications to an IBM® z/OS® environment, you must identify specific directories and data sets to the authorized program facility \(APF\).

**Note:** Access to the UNIX™ directories and files is required prior to authorization Refer to [IBM z/OS directories and data sets](security_zos_files.md).

|Directories and data sets|Required access permissions|
|-------------------------|---------------------------|
|The HLQ.SBUZAUTH data set|The load module BUZJMON must be APF-authorized.|
|agent/auth/checkaccess|The extended attributes must be set so that the checkaccess utility is APF-authorized. To set the extended attributes, type extattr +a at a command prompt.You must have read access to the BPX.FILEATTR.APF resource in the FACILITY class profile to run this command.

|

**Parent topic:** [Security requirements on IBM z/OS computers](../../com.ibm.udeploy.admin.doc/topics/security_zos.md)

