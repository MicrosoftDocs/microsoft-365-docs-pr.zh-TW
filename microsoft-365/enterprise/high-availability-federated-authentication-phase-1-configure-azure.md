---
title: 高可用性同盟驗證階段1設定 Azure
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/25/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom: Ent_Solutions
ms.assetid: 91266aac-4d00-4b5f-b424-86a1a837792c
description: 摘要：設定 Microsoft Azure 基礎結構，以裝載 Microsoft 365 的高可用性同盟驗證。
ms.openlocfilehash: d2a9fe3c31468cd53576a82639e0e61901192d8e
ms.sourcegitcommit: c029834c8a914b4e072de847fc4c3a3dde7790c5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/02/2020
ms.locfileid: "47332337"
---
# <a name="high-availability-federated-authentication-phase-1-configure-azure"></a>高可用性同盟驗證階段 1：設定 Azure

在此階段中，您會在 Azure 中建立資源群組、虛擬網路 (VNet) 和可用性設定，以在階段2、3和4中主控虛擬機器。 您必須先完成此階段，再移至 [階段2：設定網域控制站](high-availability-federated-authentication-phase-2-configure-domain-controllers.md)。 請參閱 [在 Azure 中部署 Microsoft 365 的高可用性同盟驗證](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md) ，以瞭解所有階段。
  
Azure 必須布建下列基本元件：
  
- 資源群組
    
- 跨部署 Azure 虛擬網路 (VNet) 搭配用於主控 Azure 虛擬機器的子網
    
- 用於執行子網路隔離的網路安全性群組
    
- 可用性設定組
    
## <a name="configure-azure-components"></a>設定 Azure 元件

在開始設定 Azure 元件之前，填寫下列表格。 為了可在設定 Azure 的程序中協助您，請列印此節並記下所需資訊，或將此節複製到一份文件並加以填寫。 若為 VNet 的設定，請填寫表格 V。
  
|**項目**|**組態設定**|**描述**|**值**|
|:-----|:-----|:-----|:-----|
|1.  <br/> |VNet 名稱  <br/> |要指派給 VNet (範例 FedAuthNet) 的名稱。  <br/> |![線條](../media/Common-Images/TableLine.png)  <br/> |
|2.  <br/> |VNet 位置  <br/> |將包含虛擬網路的地區性 Azure 資料中心。  <br/> |![線條](../media/Common-Images/TableLine.png)  <br/> |
|3.  <br/> |VPN 裝置 IP 位址  <br/> |網際網路上 VPN 裝置介面的公用 IPv4 位址。  <br/> |![線條](../media/Common-Images/TableLine.png)  <br/> |
|4.  <br/> |VNet 位址空間  <br/> |虛擬網路的位址空間。請與您的 IT 部門合作以決定此位址空間。  <br/> |![線條](../media/Common-Images/TableLine.png)  <br/> |
|5.  <br/> |IPsec 共用金鑰  <br/> |32 個字元的隨機英數字元字串，用以驗證站台對站台 VPN 連線的兩端站台。請與您的 IT 或安全性部門合作，以決定此金鑰值。或者，請參閱[建立隨機字串以作為 IPsec 的預先共用金鑰](https://social.technet.microsoft.com/wiki/contents/articles/32330.create-a-random-string-for-an-ipsec-preshared-key.aspx)。  <br/> |![線條](../media/Common-Images/TableLine.png)  <br/> |
   
 **表格 V：跨單位虛擬網路設定**
  
下一步，針對此解決方案的子網路填寫表格 S。所有位址空間應是無類別網域間路由選擇 (CIDR) 格式 (也稱為網路前置詞格式)。例如 10.24.64.0/20。
  
針對前三個子網，根據虛擬網路位址空間，指定名稱和單一 IP 位址空間。 針對閘道子網，使用下列各項來判斷具有 a/27 前置詞長度) 的27位位址空間 (：
  
1. 將 VNet 位址空間中的變數位元數設為 1 (閘道子網路正在使用的位元數)，其餘位元數設為 0。
    
2. 將結果位元數轉換為小數，使用設定為閘道子網路大小的前置長度將其表示為位址空間。
    
請參閱 [Azure 閘道子網的位址空間計算機](address-space-calculator-for-azure-gateway-subnets.md) ，以取得 PowerShell 命令區塊和 c # 或 Python 主控台應用程式，為您執行這種計算。
  
請與您的 IT 部門合作，以從虛擬網路位址空間判斷這些位址空間。
  
|**項目**|**子網路名稱**|**子網路位址空間**|**用途**|
|:-----|:-----|:-----|:-----|
|1.  <br/> |![線條](../media/Common-Images/TableLine.png)  <br/> |![線條](../media/Common-Images/TableLine.png)  <br/> |Active Directory 網域服務所使用的子網 (AD DS) 網域控制站及目錄同步處理伺服器虛擬機器 (Vm) 。  <br/> |
|2.  <br/> |![線條](../media/Common-Images/TableLine.png)  <br/> |![線條](../media/Common-Images/TableLine.png)  <br/> |AD FS Vm 所使用的子網。  <br/> |
|3.  <br/> |![線條](../media/Common-Images/TableLine.png)  <br/> |![線條](../media/Common-Images/TableLine.png)  <br/> |Web 應用程式 proxy Vm 所使用的子網。  <br/> |
|4.  <br/> |GatewaySubnet  <br/> |![線條](../media/Common-Images/TableLine.png)  <br/> |Azure 閘道 Vm 所使用的子網。  <br/> |
   
 **表格 S：虛擬網路中的子網路**
  
下一步，針對指派至虛擬機器和負載平衡器執行個體的靜態 IP 位址填寫表格 I。
  
|**項目**|**用途**|**子網路上的 IP 位址**|**值**|
|:-----|:-----|:-----|:-----|
|1.  <br/> |第一個網域控制站的靜態 IP 位址  <br/> |定義於表格 S 的項目 1 中，子網路位址空間的第四個可能 IP 位址。  <br/> |![線條](../media/Common-Images/TableLine.png)  <br/> |
|2.  <br/> |第二個網域控制站的靜態 IP 位址  <br/> |定義於表格 S 的項目 1 中，子網路位址空間的第五個可能 IP 位址。  <br/> |![線條](../media/Common-Images/TableLine.png)  <br/> |
|3.  <br/> |目錄同步處理伺服器的靜態 IP 位址  <br/> |定義于表格 S 的專案1中，子網位址空間的第六個可能 IP 位址。  <br/> |![線條](../media/Common-Images/TableLine.png)  <br/> |
|4.  <br/> |AD FS 伺服器內部負載平衡器的靜態 IP 位址  <br/> |定義於表格 S 的項目 2 中，子網路位址空間的第四個可能 IP 位址。  <br/> |![線條](../media/Common-Images/TableLine.png)  <br/> |
|5.  <br/> |第一個 AD FS 伺服器的靜態 IP 位址  <br/> |定義於表格 S 的項目 2 中，子網路位址空間的第五個可能 IP 位址。  <br/> |![線條](../media/Common-Images/TableLine.png)  <br/> |
|6.  <br/> |第二個 AD FS 伺服器的靜態 IP 位址  <br/> |定義於表格 S 的項目 2 中，子網路位址空間的第六個可能 IP 位址。  <br/> |![線條](../media/Common-Images/TableLine.png)  <br/> |
|7.  <br/> |第一個 web 應用程式 proxy 伺服器的靜態 IP 位址  <br/> |定義於表格 S 的項目 3 中，子網路位址空間的第四個可能 IP 位址。  <br/> |![線條](../media/Common-Images/TableLine.png)  <br/> |
|8.  <br/> |第二個 web 應用程式 proxy 伺服器的靜態 IP 位址  <br/> |定義於表格 S 的項目 3 中，子網路位址空間的第五個可能 IP 位址。  <br/> |![線條](../media/Common-Images/TableLine.png)  <br/> |
   
 **表格 I：虛擬網路中的靜態 IP 位址**
  
若要在您初次設定虛擬網路的網域控制站時，在內部部署網路中 (DNS) 伺服器的兩個網域名稱系統，請填入 Table D。請與您的 IT 部門合作以決定此清單。
  
|**項目**|**DNS 伺服器的易記名稱**|**DNS 伺服器 IP 位址**|
|:-----|:-----|:-----|
|1.  <br/> |![線條](../media/Common-Images/TableLine.png)  <br/> |![線條](../media/Common-Images/TableLine.png)  <br/> |
|2.  <br/> |![線條](../media/Common-Images/TableLine.png)  <br/> |![線條](../media/Common-Images/TableLine.png)  <br/> |
   
 **表格 D：內部部署 DNS 伺服器**
  
若要將跨單位網路的封包路由傳送至組織網路跨越整個點對點 VPN 連線，您必須設定具有本機網路的虛擬網路，該網路的位址空間清單 (于組織內部部署網路上的所有可訪問位置的 CIDR 標記法) 中。 定義區域網路的位址空間清單必須是唯一的，且不可與其他虛擬網路或其他區域網路使用的位址空間重疊。
  
針對區域網路位址空間集，請填寫表格 L。請注意，雖已列出三個空白項，但一般來說您會需要更多。請與您的 IT 部門合作以決定此位址空間清單。
  
|**項目**|**區域網路位址空間**|
|:-----|:-----|
|1.  <br/> |![線條](../media/Common-Images/TableLine.png)  <br/> |
|2.  <br/> |![線條](../media/Common-Images/TableLine.png)  <br/> |
|3.  <br/> |![線條](../media/Common-Images/TableLine.png)  <br/> |
   
 **表格 L：區域網路的網址前置詞**
  
現在，讓我們開始組建 Azure 基礎結構，以裝載 Microsoft 365 的同盟驗證。
  
> [!NOTE]
> [!附註] 下列命令集會使用最新版的 Azure PowerShell。 請參閱 [Azure PowerShell 入門](https://docs.microsoft.com/powershell/azure/get-started-azureps)。 
  
首先，啟動 Azure PowerShell 提示並登入您的帳戶。
  
```powershell
Connect-AzAccount
```

> [!TIP]
> 若要根據您的自訂設定來產生現成 PowerShell 命令區塊，請使用此 [Microsoft Excel 配置活頁簿](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/O365FedAuthInAzure_Config.xlsx)。 

使用下列命令取得訂用帳戶名稱。
  
```powershell
Get-AzSubscription | Sort Name | Select Name
```

若為舊版的 Azure PowerShell，請改為使用此命令。
  
```powershell
Get-AzSubscription | Sort Name | Select SubscriptionName
```

設定 Azure 訂用帳戶。 以正確的名稱取代引號內的所有專案（包括 \< and > 字元）。
  
```powershell
$subscrName="<subscription name>"
Select-AzSubscription -SubscriptionName $subscrName
```

接下來，建立新的資源群組。 若要判斷資源群組名稱是否是唯一一組，可使用此命令來列出現有的資源群組。
  
```powershell
Get-AzResourceGroup | Sort ResourceGroupName | Select ResourceGroupName
```

針對這唯一的一組資源群組名稱，填寫下列表格。
  
|**項目**|**資源群組名稱**|**用途**|
|:-----|:-----|:-----|
|1.  <br/> |![線條](../media/Common-Images/TableLine.png)  <br/> |網域控制站  <br/> |
|2.  <br/> |![線條](../media/Common-Images/TableLine.png)  <br/> |AD FS 伺服器  <br/> |
|3.  <br/> |![線條](../media/Common-Images/TableLine.png)  <br/> |Web 應用程式 proxy 伺服器  <br/> |
|4.  <br/> |![線條](../media/Common-Images/TableLine.png)  <br/> |基礎結構元素  <br/> |
   
 **表格 R：資源群組**
  
使用這些命令建立新的資源群組。
  
```powershell
$locName="<an Azure location, such as West US>"
$rgName="<Table R - Item 1 - Name column>"
New-AzResourceGroup -Name $rgName -Location $locName
$rgName="<Table R - Item 2 - Name column>"
New-AzResourceGroup -Name $rgName -Location $locName
$rgName="<Table R - Item 3 - Name column>"
New-AzResourceGroup -Name $rgName -Location $locName
$rgName="<Table R - Item 4 - Name column>"
New-AzResourceGroup -Name $rgName -Location $locName
```

接下來，您要建立 Azure 虛擬網路及其子網。
  
```powershell
$rgName="<Table R - Item 4 - Resource group name column>"
$locName="<your Azure location>"
$vnetName="<Table V - Item 1 - Value column>"
$vnetAddrPrefix="<Table V - Item 4 - Value column>"
$dnsServers=@( "<Table D - Item 1 - DNS server IP address column>", "<Table D - Item 2 - DNS server IP address column>" )
# Get the shortened version of the location
$locShortName=(Get-AzResourceGroup -Name $rgName).Location

# Create the subnets
$subnet1Name="<Table S - Item 1 - Subnet name column>"
$subnet1Prefix="<Table S - Item 1 - Subnet address space column>"
$subnet1=New-AzVirtualNetworkSubnetConfig -Name $subnet1Name -AddressPrefix $subnet1Prefix
$subnet2Name="<Table S - Item 2 - Subnet name column>"
$subnet2Prefix="<Table S - Item 2 - Subnet address space column>"
$subnet2=New-AzVirtualNetworkSubnetConfig -Name $subnet2Name -AddressPrefix $subnet2Prefix
$subnet3Name="<Table S - Item 3 - Subnet name column>"
$subnet3Prefix="<Table S - Item 3 - Subnet address space column>"
$subnet3=New-AzVirtualNetworkSubnetConfig -Name $subnet3Name -AddressPrefix $subnet3Prefix
$gwSubnet4Prefix="<Table S - Item 4 - Subnet address space column>"
$gwSubnet=New-AzVirtualNetworkSubnetConfig -Name "GatewaySubnet" -AddressPrefix $gwSubnet4Prefix

# Create the virtual network
New-AzVirtualNetwork -Name $vnetName -ResourceGroupName $rgName -Location $locName -AddressPrefix $vnetAddrPrefix -Subnet $gwSubnet,$subnet1,$subnet2,$subnet3 -DNSServer $dnsServers

```

接下來，為每個具有虛擬機器的子網建立網路安全性群組。 若要執行子網路隔離，您可以針對允許或拒絕子網路安全小組流量的特定類型新增規則。
  
```powershell
# Create network security groups
$vnet=Get-AzVirtualNetwork -ResourceGroupName $rgName -Name $vnetName

New-AzNetworkSecurityGroup -Name $subnet1Name -ResourceGroupName $rgName -Location $locShortName
$nsg=Get-AzNetworkSecurityGroup -Name $subnet1Name -ResourceGroupName $rgName
Set-AzVirtualNetworkSubnetConfig -VirtualNetwork $vnet -Name $subnet1Name -AddressPrefix $subnet1Prefix -NetworkSecurityGroup $nsg

New-AzNetworkSecurityGroup -Name $subnet2Name -ResourceGroupName $rgName -Location $locShortName
$nsg=Get-AzNetworkSecurityGroup -Name $subnet2Name -ResourceGroupName $rgName
Set-AzVirtualNetworkSubnetConfig -VirtualNetwork $vnet -Name $subnet2Name -AddressPrefix $subnet2Prefix -NetworkSecurityGroup $nsg

New-AzNetworkSecurityGroup -Name $subnet3Name -ResourceGroupName $rgName -Location $locShortName
$nsg=Get-AzNetworkSecurityGroup -Name $subnet3Name -ResourceGroupName $rgName
Set-AzVirtualNetworkSubnetConfig -VirtualNetwork $vnet -Name $subnet3Name -AddressPrefix $subnet3Prefix -NetworkSecurityGroup $nsg
$vnet | Set-AzVirtualNetwork
```

接著，使用以下命令來建立站台對站台 VPN 連線的閘道。
  
```powershell
$rgName="<Table R - Item 4 - Resource group name column>"
$locName="<Azure location>"
$vnetName="<Table V - Item 1 - Value column>"
$vnet=Get-AzVirtualNetwork -Name $vnetName -ResourceGroupName $rgName
$subnet=Get-AzVirtualNetworkSubnetConfig -VirtualNetwork $vnet -Name "GatewaySubnet"

# Attach a virtual network gateway to a public IP address and the gateway subnet
$publicGatewayVipName="PublicIPAddress"
$vnetGatewayIpConfigName="PublicIPConfig"
New-AzPublicIpAddress -Name $vnetGatewayIpConfigName -ResourceGroupName $rgName -Location $locName -AllocationMethod Dynamic
$publicGatewayVip=Get-AzPublicIpAddress -Name $vnetGatewayIpConfigName -ResourceGroupName $rgName
$vnetGatewayIpConfig=New-AzVirtualNetworkGatewayIpConfig -Name $vnetGatewayIpConfigName -PublicIpAddressId $publicGatewayVip.Id -Subnet $subnet

# Create the Azure gateway
$vnetGatewayName="AzureGateway"
$vnetGateway=New-AzVirtualNetworkGateway -Name $vnetGatewayName -ResourceGroupName $rgName -Location $locName -GatewayType Vpn -VpnType RouteBased -IpConfigurations $vnetGatewayIpConfig

# Create the gateway for the local network
$localGatewayName="LocalNetGateway"
$localGatewayIP="<Table V - Item 3 - Value column>"
$localNetworkPrefix=@( <comma-separated, double-quote enclosed list of the local network address prefixes from Table L, example: "10.1.0.0/24", "10.2.0.0/24"> )
$localGateway=New-AzLocalNetworkGateway -Name $localGatewayName -ResourceGroupName $rgName -Location $locName -GatewayIpAddress $localGatewayIP -AddressPrefix $localNetworkPrefix

# Define the Azure virtual network VPN connection
$vnetConnectionName="S2SConnection"
$vnetConnectionKey="<Table V - Item 5 - Value column>"
$vnetConnection=New-AzVirtualNetworkGatewayConnection -Name $vnetConnectionName -ResourceGroupName $rgName -Location $locName -ConnectionType IPsec -SharedKey $vnetConnectionKey -VirtualNetworkGateway1 $vnetGateway -LocalNetworkGateway2 $localGateway

```

> [!NOTE]
> 個別使用者的聯盟驗證不會仰賴任何內部部署資源。 不過，如果這種點對點 VPN 連線無法使用，VNet 中的網域控制站將不會收到內部部署 Active Directory 網域服務中所進行之使用者帳戶和群組的更新。 為了確保不會發生這種情況，您可以為網站對網站 VPN 連線設定高可用性。 如需詳細資訊，請參閱[高度可用的跨單位和 VNet-VNet 連線](https://docs.microsoft.com/azure/vpn-gateway/vpn-gateway-highlyavailable)
  
接著，從顯示的以下命令中，記錄虛擬網路 Azure VPN 閘道的公用 IPv4 位址。
  
```powershell
Get-AzPublicIpAddress -Name $publicGatewayVipName -ResourceGroupName $rgName
```

接著，設定內部部署 VPN 裝置與 Azure VPN 閘道連線。如需詳細資訊，請參閱[設定您的 VPN 裝置](https://docs.microsoft.com/azure/vpn-gateway/vpn-gateway-about-vpn-devices)。
  
若要設定您的內部部署 VPN 裝置，您需要下列項目︰
  
- Azure VPN 閘道的公用 IPv4 位址。
    
- 站台對站台 VPN 連線的 IPsec 預先共用金鑰 (表格 V - 項目 5 - 值欄)。
    
下一步，確認從內部部署網路可觸及虛擬網路的位址空間。一般來說，完成方式是新增路由以將虛擬網路位址空間對應至 VPN 裝置，然後將此路由傳達給其餘組織網路的路由基礎結構。請與您的 IT 部門合作以決定如何執行此動作。
  
接下來，定義三個可用性設定集的名稱。 填寫表格 A。 
  
|**項目**|**用途**|**可用性設定組名稱**|
|:-----|:-----|:-----|
|1.  <br/> |網域控制站  <br/> |![線條](../media/Common-Images/TableLine.png)  <br/> |
|2.  <br/> |AD FS 伺服器  <br/> |![線條](../media/Common-Images/TableLine.png)  <br/> |
|3.  <br/> |Web 應用程式 proxy 伺服器  <br/> |![線條](../media/Common-Images/TableLine.png)  <br/> |
   
 **表格 A：可用性設定組**
  
當您在階段 2、3 和 4 中建立虛擬機器時，將會需要這些名稱。
  
使用這些 Azure PowerShell 命令，建立新的可用性設定集。
  
```powershell
$locName="<the Azure location for your new resource group>"
$rgName="<Table R - Item 1 - Resource group name column>"
$avName="<Table A - Item 1 - Availability set name column>"
New-AzAvailabilitySet -ResourceGroupName $rgName -Name $avName -Location $locName -Sku Aligned  -PlatformUpdateDomainCount 5 -PlatformFaultDomainCount 2
$rgName="<Table R - Item 2 - Resource group name column>"
$avName="<Table A - Item 2 - Availability set name column>"
New-AzAvailabilitySet -ResourceGroupName $rgName -Name $avName -Location $locName -Sku Aligned  -PlatformUpdateDomainCount 5 -PlatformFaultDomainCount 2
$rgName="<Table R - Item 3 - Resource group name column>"
$avName="<Table A - Item 3 - Availability set name column>"
New-AzAvailabilitySet -ResourceGroupName $rgName -Name $avName -Location $locName -Sku Aligned  -PlatformUpdateDomainCount 5 -PlatformFaultDomainCount 2
```

以下是成功完成此階段的設定結果。
  
**階段1：適用于 Microsoft 365 的高可用性同盟驗證的 Azure 基礎結構**

![Azure 中使用 Azure 基礎結構之高可用性 Microsoft 365 同盟驗證的階段1](../media/4e7ba678-07df-40ce-b372-021bf7fc91fa.png)
  
## <a name="next-step"></a>後續步驟

使用 [階段2：設定網域控制站](high-availability-federated-authentication-phase-2-configure-domain-controllers.md) 以繼續設定此工作負載。
  
## <a name="see-also"></a>另請參閱

[Azure 中的 Microsoft 365 高可用性同盟驗證](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md)
  
[Microsoft 365 開發/測試環境的同盟身分識別](federated-identity-for-your-microsoft-365-dev-test-environment.md)
  
[Microsoft 365 解決方案與架構中心](../solutions/solution-architecture-center.md)

[瞭解 Microsoft 365 身分識別和 Azure Active Directory](about-microsoft-365-identity.md)


