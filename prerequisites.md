# How to enable Cock-Pit on Day Zero 

## Arc Cock-Pit Prerequisites

- Permission on Subscription for [Azure Arc-enabled server](https://learn.microsoft.com/en-us/azure/azure-arc/servers/prerequisites#required-permissions)
- Registering [Azure Arc Resource Providers](https://learn.microsoft.com/en-us/azure/azure-arc/servers/prerequisites#azure-resource-providers)
- All the Windows/Linux Servers, SQL Servers, should be [Arc-Connected](https://learn.microsoft.com/en-us/azure/azure-arc/servers/agent-overview)
- Complete networking requirements for all the servers to be onboarded to Azure Arc
  - Define networking access from Firewall or Proxy for all the URLs. See details [here](https://learn.microsoft.com/en-us/azure/azure-arc/servers/network-requirements?tabs=azure-cloud)
  - For Private Link see the [details below](#azure-arc-cock-pit-via-private-link-architecture)
- Onboard all Windows/Linux servers, SQL Servers to Azure Arc by using [Azure Private Link](https://learn.microsoft.com/en-us/azure/azure-arc/servers/private-link-security)
  > [!IMPORTANT]
  > All the servers installed Arc Connected Machine Agent includes SQL Server Extension automatically if the server has SQL Server installed.
- Deploy Azure Monitor or Log Analytics Agent Extension to all servers, systems to be onboarded into the Arc Cock-Pit
- Configure Azure Monitor Data Collection Rules or Log Analytics Performance Counters or  Logs to be collected based on your telemetry requirements
  - [Data collection rules in Azure Monitor](https://learn.microsoft.com/en-us/azure/azure-monitor/essentials/data-collection-rule-overview)
  - Collect events and performance counters from virtual machines with [Azure Monitor Agent](https://learn.microsoft.com/en-us/azure/azure-monitor/agents/data-collection-rule-azure-monitor-agent?tabs=portal)
  - Collect Windows and Linux [performance data sources with the Log Analytics agent in Azure Monitor](https://learn.microsoft.com/en-us/azure/azure-monitor/agents/data-sources-performance-counters)
- [Customize Arc Cock-Pit](/customizecockpit.md)

## Private Link

### Azure Arc Cock-Pit via Private link Architecture

What is Private Link & Why Options

- Private connectivity to services on Azure traffic remains on the Microsoft network, with no public internet access
- Integration with on-premises and peered networks
- Protection against data exfiltration for Azure resources
- Services delivered directly to your customers’ virtual networks

  ![image](https://github.com/ALADAGM/ArcCock-Pit/assets/3506526/72d178f6-7808-40e6-9402-bda6df363de7)

Plan and complete networking requirements for all the servers to be onboarded to Azure Arc by Private Link.

1. Take detailed information about the advantages of using [Private Link and how it works](https://learn.microsoft.com/en-us/azure/azure-arc/servers/private-link-security#advantages)
2. Plan and Configure [Private Link detailed setup](https://learn.microsoft.com/en-us/azure/azure-arc/servers/private-link-security#planning-your-private-link-setup)
3. Define networking access from Firewall or Proxy for all the URLs not supporting Private Link. See details [here](https://learn.microsoft.com/en-us/azure/azure-arc/servers/network-requirements?tabs=azure-cloud#urls)
4. Create and Configure [Azure Private Link Scope](https://learn.microsoft.com/en-us/azure/azure-arc/servers/private-link-security#create-a-private-link-scope)
5. [Configure DNS Forwarding for On-Premises DNS Servers](https://learn.microsoft.com/en-us/azure/azure-arc/servers/private-link-security#configure-on-premises-dns-forwarding)
6. Configure and Onboard all the Windows/Linux servers, SQL Servers to Azure Arc using Private Link by applying all the steps detailed [here](https://learn.microsoft.com/en-us/azure/azure-arc/servers/private-link-security#connect-to-an-azure-arc-enabled-servers)

> [!IMPORTANT]
> All the servers installed Arc Connected Machine Agent includes SQL Server Extension automatically if the server has SQL Server installed

