# Installing the z/OS agent and deployment tools by using SMP/E

IBM® System Modification Program/Extended \(SMP/E\) is a tool for installing and maintaining software on z/OS® systems. SMP/E controls software changes at the element level. Job Control Language \(JCL\) is submitted by using 3270 emulation.

The HCL® UrbanCode™ Deploy agent for z/OS is provided in the HCL UrbanCode Deploy Agent z/OS @version@ Multilingual software image in the HCL UrbanCode Deploy eAssembly. The image contains program directories and binary files. The program directories contain instructions for installing the z/OS agent by using SMP/E.

**Note:** The SMP/E installation media is supplied for each release. Fix packs are available only for .zip file installation.

1.   Follow the instructions in the z/OS program directory. The program directory lists specific directory path names. If you extract files to a different location, update the path names to match the location.

The SMP/E package installs several Multiple Virtual Storage data sets, including the high\_level\_qualifier.SBUZSAMP and high\_level\_qualifier.SBUZAUTH data sets. You select the high-level qualifier during the SMP/E installation. The high\_level\_qualifier.SBUZAUTH data set must be authorized by the Authorized Program Facility. Other configuration steps include editing and submitting JCL that is found in the high\_level\_qualifier.SBUZSAMP data set.

The SMP/E package also installs one z/OS UNIX™ System Services file directory: /@pathPrefix@/usr/lpp/IBM/ucd/@version@, where @pathPrefix@ is the path prefix that you specified during the SMP/E installation.

The package installs the following Function Modification Identifier \(FMID\): `HRUC@version@`.

Install and configure an instance of the agent. See [Installing agents from the command line](../../com.udeploy.install.doc/topics/agentInstall.md#).

**Parent topic:** [Installing the z/OS agent](../../com.udeploy.install.doc/topics/zos_installing_ov.md)

**Parent topic:** [Installing the z/OS agent](../../com.udeploy.install.doc/topics/zos_installing_ov.md)

