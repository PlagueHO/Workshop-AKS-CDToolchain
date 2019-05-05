# Workshop-AKS-CDToolchain

Build a CD Toolchain (Jenkins, Nexus, Sonarqube + more) in Azure Kubernetes Service

## Deploy a Log Analytics Workspace

```bash
basename='dsr'
logAnalyticsResourceGroupName=$basename-loganalytics-rg
logAnalyticsWorkspaceName=$basename-loganalytics-law
location='westus2'
az group create --name $logAnalyticsResourceGroupName --location $location
az group deployment create --resource-group $logAnalyticsResourceGroupName --name deployLogAnalytics --template-uri loganalytics.json --parameters workspaceName=$logAnalyticsWorkspaceName location=$location sku=free
```