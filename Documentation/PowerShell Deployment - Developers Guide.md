# Developers Guide - PowerShell Deployment Extension Kit
April 2019

PowerShell vxxx is the standard for all PSD development.

# Coding Standards

# Logging via Write-TSxLog
Logging in all PSD modules is and should be accomplished via a new **Write-TSxLog** function found in PSDUtility.psm1. Developers, coders and customizers should leverage this new function to capture output for logging and or debug purposes. The following syntax should be used or duplicated:

    Write-TSxLog -Message "$($MyInvocation.MyCommand.Name): <<your message our output>>

This will output your message or text to the logfile along with the calling script. Sample output looks like the following from the Get-PSDLocalDataPath function:

    <![LOG[Get-PSDLocalDataPath: Return the cached local data path if possible]LOG]!><time="20:31:39.462+000" date="03-26-2019" component="PSDUtility.psm1:27" context="" type="1" thread="" file="">

# Scripts, Modules and Libraries
The following modules and scripts are provided with PSD:
## Scripts
- **PSDAppliacations.ps1** - Installs the apps specified by task sequence variables *Applications* and *MandatoryApplications*. Imports PSDUtility and PSDDeploymentShare. Includes function(s) *Install-PSDApplication* 
- PSDApplyOS.ps1
- PSDConifgure.ps1
- PSDCustomPostWU.ps1
- PSDCustomPreWU.ps1
- PSDDrivers.ps1
- PSDErrorInTS.ps1
- PSDGather.ps1
- PSDHelper.ps1
- PSDNextPhase.ps1
- PSDFreshen.ps1
- PSDPartition.ps1
- PSDSetVariable.ps1
- PSDStart.ps1
- PSDTBA.ps1
- PSDTemplate.ps1
- PSDUserState.ps1
- PSDValidate.ps1
- PSDWindowsUpdate.ps1

## Modules
- PSDGather.psm1
- PSDUtility.psm1
- PSDWizard.psm1
- PSDDeploymentshare.psm1
- ZTIUtility.psm1

## Other
- PSDWizard.xaml
- PSDWizard.xaml.initialize.ps1

# MDT Dependencies
The following MDT components and files are utilized, consumed, and or referenced by PSD:
- ZTIGather.xml
- ZTIConfigure.xml
- xxx.bdd.xxx
- xxx.bbb.xxx