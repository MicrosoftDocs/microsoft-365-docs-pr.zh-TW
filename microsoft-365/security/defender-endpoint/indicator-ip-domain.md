---
title: 建立 IP 和 URL/網域的指示器
ms.reviewer: ''
description: 為 IPs 及定義實體的偵測、預防和排除的 URLs/網域建立指示器。
keywords: ip，url，domain，manage，允許，封鎖，封鎖，clean，惡意，檔雜湊，ip 位址，url，網域
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
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: e7dc11fe709a6d04b6309706df90f0ebbc177e25
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841063"
---
# <a name="create-indicators-for-ips-and-urlsdomains"></a>建立 IP 和 URL/網域的指示器 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)



> [!TIP]
> 想要體驗 Defender for Endpoint？ [注册免費試用版。](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)


Defender for Endpoint 可以透過 microsoft browser 的 Windows Defender SmartScreen，以及透過瀏覽器以外的非 Microsoft 瀏覽器或通話的網路保護，封鎖 microsoft 認為是惡意的 IPs/URLs。

其威脅情報資料集是由 Microsoft 所管理。

透過為 IPs 和 URLs 或網域建立指示器，您現在可以根據自己的威脅情報，允許或封鎖 IPs、URLs 或網域。 您可以透過 [設定] 頁面或電腦群組來執行這項操作，如果您認為某些群組比其他群組的風險多或少。

> [!NOTE]
> 不支援以無類別 Inter-Domain 路由 (CIDR) 表示的 IP 位址。 

### <a name="before-you-begin"></a>開始之前
在建立 IPS、URLs 或網域的指示器之前，請務必先瞭解下列必要條件：
- URL/IP 允許和封鎖依賴在封鎖模式中啟用的 Defender for Endpoint component 網路保護。 如需網路保護和設定指示的詳細資訊，請參閱 [Enable Network Protection](enable-network-protection.md)。
- 反惡意軟體用戶端版本必須是4.18.1906 或更新版本。 
- 在 Windows 10 版本1709或更新版本上支援的機器上。 
- 確定 **設定 > 的高級功能 Microsoft Defender 資訊安全中心 >** 中已啟用 **自訂網路指示器**。 如需詳細資訊，請參閱 [高級功能](advanced-features.md)。
- 如需 iOS 的指示器支援，請參閱 [Configure custom 指示器](/microsoft-365/security/defender-endpoint/ios-configure-features#configure-custom-indicators)。


> [!IMPORTANT]
> 只有外部 Ip 可以新增至 [標記] 清單。 無法為內部 Ip 建立指示器。
> 在 web 保護案例中，建議您在 Microsoft Edge 中使用內建功能。 Microsoft Edge 會利用[網路保護](network-protection.md)檢查網路流量，並允許 TCP、HTTP 及 HTTPS (TLS) 的封鎖。 如果有衝突的 URL 指示器原則，則會套用較長的路徑。 例如，URL 指示器原則的 `https:\\support.microsoft.com/en-us/office` 優先順序會高於 url 指示器原則 `https:\\support.microsoft.com` 。

> [!NOTE]
> 對於所有其他程式，web 保護案例會利用網路保護進行檢查及強制執行： 
> - 所有三種通訊協定都支援 IP
> -  (沒有 CIDR 區塊或 IP 範圍，只支援單一 IP 位址) 
> - 已加密 URLs (完整路徑) 只能在第一方瀏覽器 (Internet Explorer，Edge) 
> - 加密的 URL (僅限 FQDN) 可以封鎖于第一方瀏覽器以外的地方 (Internet Explorer，Edge) 
> - 完整 URL 路徑區塊可以套用於網域層級和所有未加密的 URLs
 
> [!NOTE]
> 最多可以有2小時的延遲 (會在採取動作的時間與要封鎖的 URL 和 IP 之間) 少。 

### <a name="create-an-indicator-for-ips-urls-or-domains-from-the-settings-page"></a>從 [設定] 頁面建立 IPs、URLs 或網域的指示器

1. 在功能窗格中，選取 [**設定**  >  **指示器**]。  

2. 選取 [ **IP 位址] 或 [URLs/網域** ] 索引標籤。

3. 選取 [ **新增專案**]。

4. 指定下列詳細資料：
   - 標記-指定實體詳細資料並定義指示器的到期期限。
   - Action-指定要採取的動作並提供描述。
   - Scope-定義機器群組的範圍。

5. 在 [摘要] 索引標籤中查看詳細資料，然後按一下 [ **儲存**]。

## <a name="related-topics"></a>相關主題
- [建立指示器](manage-indicators.md)
- [建立檔案的指示器](indicator-file.md)
- [根據憑證建立指示器](indicator-certificates.md)
- [管理指示器](indicator-manage.md)
