---
title: 設定 Microsoft Defender for Endpoint 部署
description: 瞭解如何設定 Microsoft Defender for Endpoint 的部署
keywords: 部署、安裝、授權驗證、租使用者設定、網路設定
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-endpointprotect
- m365solution-scenario
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 6b49565c45c1f38d0d2ce71b097af079782ba4de
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/24/2021
ms.locfileid: "52636191"
---
# <a name="set-up-microsoft-defender-for-endpoint-deployment"></a>設定 Microsoft Defender for Endpoint 部署

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要體驗適用於端點的 Microsoft Defender 嗎？ [注册免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

為端點部署 Defender 是三個階段的處理常式：

| [![部署階段-準備](images/phase-diagrams/prepare.png)](prepare-deployment.md)<br>[階段 1：準備](prepare-deployment.md) | ![部署階段-安裝程式](images/phase-diagrams/setup.png)<br>階段 2：設定 | [![部署階段-板載](images/phase-diagrams/onboard.png)](onboarding.md)<br>[第 3 階段：導入](onboarding.md) |
| ----- | ----- | ----- |
| | *您在這裡！*||

您目前在設定階段。

在此部署案例中，您將會逐步指導您執行下列步驟：
- 授權驗證
- 租用戶設定
- 網路設定


>[!NOTE]
>為便於您透過一般部署，此案例只會涵蓋 Microsoft Endpoint Configuration Manager 的使用。 Defender for Endpoint 支援使用其他上架工具，但不涵蓋部署指南中的那些案例。 如需詳細資訊，請參閱 [在 Microsoft Defender For Endpoint 中的板載裝置](onboard-configure.md)。

## <a name="check-license-state"></a>檢查授權狀態

檢查授權狀態以及是否已正確布建，可透過系統管理中心或透過 **Microsoft Azure 入口網站** 進行。

1. 若要查看您的授權，請移至 **Microsoft Azure 入口網站**，並流覽至「 [Microsoft Azure 入口網站授權」一節](https://portal.azure.com/#blade/Microsoft_AAD_IAM/LicensesMenuBlade/Products)。

   ![Azure 授權頁面影像](images/atp-licensing-azure-portal.png)

1. 或者，在系統管理中心中，流覽至 [**帳單**] [  >  **訂閱**]。

    在螢幕上，您會看到所有已布建的授權及其目前的 **狀態**。

    ![計費授權影像](images/atp-billing-subscriptions.png)


## <a name="cloud-service-provider-validation"></a>雲端服務提供者驗證

若要存取您公司所提供的授權，以及檢查授權的狀態，請移至系統管理中心。

1. 從 **夥伴入口網站** 中，選取 [**管理服務] > Office 365**]。

2. 按一下 [ **合作夥伴入口網站** ] 連結時，將會自行開啟 [ **管理員** ] 選項，並可讓您存取客戶系統管理中心。

   ![O365 管理入口網站的影像](images/atp-O365-admin-portal-customer.png)



## <a name="tenant-configuration"></a>租使用者設定
上架至 Microsoft Defender for Endpoint 非常簡單。 從 [流覽] 功能表中，選取 [端點] 區段下的任何專案，或任何 Microsoft 365 的 Defender 功能（例如事件、搜尋、動作中心或威脅分析）以啟動上架處理常式。

在網頁瀏覽器中，流覽至 [ [Microsoft 365 的安全性中心](https://security.microsoft.com)]。

## <a name="network-configuration"></a>網路設定
如果組織不需要端點使用 Proxy 來存取網際網路，請略過本節。

適用於端點的 Microsoft Defender 感應器需要 Microsoft Windows HTTP (WinHTTP) 回報感應器資料，並與適用於端點的 Microsoft Defender 服務通訊。 內嵌的 Microsoft Defender for Endpoint 感應器會在使用 LocalSystem 帳戶的系統上下文中執行。 感應器使用 Microsoft Windows HTTP Services （WinHTTP）來啟用與適用於端點的 Microsoft Defender 雲端服務的通訊。 WinHTTP 設定設定與 Windows internet (WinINet) Internet 流覽 proxy 設定無關，而且只能使用下列探索方法來探索 proxy 伺服器：

**自動探索方法：**

-   透明Proxy

-   Web Proxy 自動探索通訊協定 (WPAD) 

如果已在網路拓撲中執行透明 proxy 或 WPAD，則不需要特殊的設定。 如需 proxy 中 Microsoft Defender for Endpoint URL 排除專案的詳細資訊，請參閱本檔中的 [Proxy 服務 URLs](production-deployment.md#proxy-service-urls) 一節，以取得 URLs 允許清單或 [設定裝置 Proxy 和網際網路連線設定](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server)。

**手動靜態 Proxy 組態：**

-   基於登錄的設定

-   使用 netsh 命令設定 WinHTTP <br> 僅適用于穩定拓撲中的桌上型電腦 (例如，公司網路中位於相同 proxy 的桌面) 

### <a name="configure-the-proxy-server-manually-using-a-registry-based-static-proxy"></a>使用基於登錄的靜態 Proxy 手動設定 Proxy 伺服器

設定登錄型靜態 proxy，只允許 Microsoft Defender for Endpoint 感應器報告診斷資料，並在電腦不允許連線至網際網路時，與 Microsoft Defender 的端點服務通訊。 靜態 Proxy 可以透過群組原則 (GP) 設定。 可以在以下位置找到群組原則：

 - 系統管理範本 \> Windows 元件 \> 資料收集和預覽版本 \> 設定連線使用者經驗和遙測服務的已驗證 Proxy 使用方式
     - 設定為 **啟用** ，並選取 [ **停用已驗證的 Proxy 使用**

1. 開啟 [群組原則管理主控台]。
2. 建立原則，或根據組織的作法來編輯現有的原則。
3. 編輯群組原則並流覽至 [系統 **管理範本] \> Windows 元件 \> 資料收集和預覽組建 \> 設定連線使用者經驗和遙測服務的已驗證 Proxy 使用方式**。 
    ![群組原則設定的影像](images/atp-gpo-proxy1.png)

4. 選取 **已啟用**。
5. 選取 [ **停用已驗證的 Proxy 使用**]。
   
6. 流覽至系統 **管理範本 \> Windows 元件 \> 資料收集和預覽版本 \> 設定連線使用者經驗和遙測**。
    ![群組原則設定設定的影像](images/atp-gpo-proxy2.png)
7. 選取 **已啟用**。
8. 輸入 **Proxy 伺服器名稱**。

原則將登錄機碼 `HKLM\Software\Policies\Microsoft\Windows\DataCollection` 下的兩個登錄值 `TelemetryProxyServer` 設定為 REG\u SZ，`DisableEnterpriseAuthProxy` 設定為 REG\u DWORD。

登錄值 `TelemetryProxyServer` 採用下列字串格式：

```text
<server name or ip>:<port>
```

例如：10.0.0.6:8080

此登錄值 `DisableEnterpriseAuthProxy` 應當設定為 1。

###  <a name="configure-the-proxy-server-manually-using-netsh-command"></a>使用 netsh 命令手動設定 proxy 伺服器

使用 netsh 設定全系統的靜態 Proxy。

> [!NOTE]
> - 這將影響所有應用程式，包括使用帶預設 Proxy 之 WinHTTP 的 Windows 服務。</br>
> - 變更拓撲的膝上型電腦 (例如：從 office 到 home) ，將無法使用 netsh。 使用基於登錄的靜態 Proxy 設定。

1. 開啟提高權限的命令列：

    1. 轉至 **[開始]** 並鍵入 **「cmd」**。

    1. 以滑鼠右鍵按一下 **[命令提示字元]**，然後選取 **[以系統管理員身分執行]**。

2. 輸入以下命令，再按 **Enter**：

   ```PowerShell
   netsh winhttp set proxy <proxy>:<port>
   ```

   例如：netsh winhttp set proxy 10.0.0.6:8080


###  <a name="proxy-configuration-for-down-level-devices"></a>底層裝置的 Proxy 設定

Down-Level 裝置包含 Windows 7 SP1 和 Windows 8.1 工作站，以及 Windows server CB 1803 之前 Windows Server 2012 server 2008 R2、Windows Server 2012、Windows Server 2016 r2 及 Windows 版本。 這些作業系統會將 proxy 設定為 Microsoft Management Agent 的一部分，以處理從端點到 Azure 的通訊。 如需如何在這些裝置上設定 proxy 的詳細資訊，請參閱《 Microsoft Management Agent Fast Deployment 指南》。

### <a name="proxy-service-urls"></a>Proxy 服務 URLs
只有當您具有 Windows 10、版本1803或更新版本的裝置時，才需要在其中包含 v20 的 URLs。 例如， ```us-v20.events.data.microsoft.com``` 只有在裝置位於 Windows 10，版本1803或更新版本時才需要。
 

如果 proxy 或防火牆封鎖匿名流量，當 Microsoft Defender for Endpoint 感應器從系統內容連線時，請確定所列的 URLs 允許匿名流量。

下列可供下載的試算表會列出您網路必須能夠連線的服務及其相關 URLs。 確定沒有防火牆或網路篩選規則可拒絕這些 URLs 的存取權，否則您可能需要建立專用的 *allow* 規則。

|**網域清單的試算表**|**描述**|
|:-----|:-----|
|![Microsoft Defender for Endpoint URLs 試算表的縮圖影像](images/mdatp-urls.png)<br/>  | 服務位置、地理位置和作業系統的特定 DNS 記錄試算表。 <br><br>[在這裡下載試算表。](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx) 


###  <a name="microsoft-defender-for-endpoint-service-backend-ip-ranges"></a>Microsoft Defender for Endpoint service 後端 IP 範圍

如果您的網路裝置不支援以 DNS 為基礎的規則，請改為使用 IP 範圍。

已于 Azure cloud 中建立端點 for Endpoint，部署于下列地區：

- AzureCloud.eastus
- AzureCloud.eastus2
- AzureCloud.westcentralus
- AzureCloud.northeurope
- AzureCloud.westeurope
- AzureCloud.uksouth
- AzureCloud.ukwest

您可以在 [AZURE Ip 範圍和服務標記–公用雲端](https://www.microsoft.com/download/details.aspx?id=56519)中找到 azure ip 範圍。

> [!NOTE]
> 作為雲端式解決方案，IP 位址範圍可能會變更。 建議您移至以 DNS 為基礎的規則。

> [!NOTE]
> 如果您是美國政府客戶，請參閱適用于 US 政府頁面的 [Defender For Endpoint](gov.md#service-backend-ip-ranges) 中的對應章節。

## <a name="next-step"></a>下一步

![* * 階段3：板載 * *](images/onboard.png) <br>[階段3：板載](onboarding.md)：對服務的板載裝置，使 Microsoft Defender for Endpoint service 可以從這些裝置取得感應器資料。 
