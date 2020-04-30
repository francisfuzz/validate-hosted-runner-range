# validate-hosted-runner-range
A GitHub Action validating the GitHub-hosted runner is in the same IP address range as the Azure data centers.

## How it will eventually work

At a high-level, this action will

* Download the Azure IP address ranges
* Ping https://www.ipify.org/ to obtain the IP address
* Compare that IP address against the list of relevant IP addresses

Context: Windows and Ubuntu runners are hosted in Azure and have the same IP address ranges as Azure Data centers. Currently, all Windows and Ubuntu GitHub-hosted runners are in the following Azure regions:

* East US (eastus)
* East US 2 (eastus2)
* West US 2 (westus2)
* Central US (centralus)
* South Central US (southcentralus)

Microsoft updates the Azure IP address ranges weekly in a JSON file that you can download from this website:

https://www.microsoft.com/en-us/download/details.aspx?id=56519

