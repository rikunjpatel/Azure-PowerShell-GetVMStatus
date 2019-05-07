Make sure you have the correct version of PowerShell 5.x installed, by running this command:

    $PSVersionTable.PSVersion

If the AZ PowerShell module is not installed, then you can run these PowerShell commands in an eleveated shell:

    Find-PackageProvider -Name "Nuget" -Force -Verbose | Install-PackageProvider -Scope "CurrentUser" -Force -Confirm -Verbose
    Install-Module -Name "PowerShellGet" -Repository "PSGallery" -Scope "CurrentUser" -AcceptLicense -SkipPublisherCheck -Force -Confirm -AllowClobber -Verbose
    Set-PSRepository -Name "PSGallery" -InstallationPolicy "Trusted" -PackageManagementProvider "Nuget" -Verbose
    Install-Module -Name "Az" -Repository "PSGallery" -Scope "CurrentUser" -AcceptLicense -SkipPublisherCheck -Force -Confirm -AllowClobber -Verbose
    Set-ExecutionPolicy -Scope "CurrentUser" -ExecutionPolicy "Bypass" -ErrorAction SilentlyContinue -Confirm -Force -Verbose


    # Install latest Nuget package management provider
    # https://docs.microsoft.com/powershell/module/packagemanagement/find-packageprovider
    # https://docs.microsoft.com/powershell/module/packagemanagement/install-packageprovider
    Find-PackageProvider -Name "Nuget" -Force -Verbose | Install-PackageProvider -Scope "CurrentUser" -Force -Confirm -Verbose
    
    # The PowerShellGet module contains cmdlets for discovering, installing, updating and publishing PowerShell packages
    # https://docs.microsoft.com/powershell/module/powershellget
    Install-Module –Name "PowerShellGet" -Repository "PSGallery" -Scope "CurrentUser" -AcceptLicense -SkipPublisherCheck –Force -Confirm -AllowClobber -Verbose
    
    # The Microsoft PowerShell Gallery is the central repository for Windows PowerShell content
    # https://docs.microsoft.com/powershell/gallery/overview
    # https://www.powershellgallery.com
    Set-PSRepository -Name "PSGallery" -InstallationPolicy "Trusted" -PackageManagementProvider "Nuget" -Verbose
    
    # Install Az modules
    Install-Module -Name "Az" -Repository "PSGallery" -Scope "CurrentUser" -AcceptLicense -SkipPublisherCheck -Force -Confirm -AllowClobber -Verbose
    Enable-AzureRmAlias -Scope "CurrentUser" -Confirm -Verbose
    
    # Set Execution Policy
    # https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-executionpolicy
    Set-ExecutionPolicy -Scope "CurrentUser" -ExecutionPolicy "Bypass" -ErrorAction SilentlyContinue -Confirm -Force -Verbose
