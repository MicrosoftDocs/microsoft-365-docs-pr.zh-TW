---
title: 根據憑證建立指示器
ms.reviewer: ''
description: 根據定義實體的偵測、預防和排除憑證，建立指示器。
keywords: ioc，憑證，憑證，管理，允許，封鎖，封鎖，clean，惡意，檔案雜湊，ip 位址，url，網域
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
ms.openlocfilehash: 8cf611e38bc781c2302f70f6491bb827410235b0
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2021
ms.locfileid: "51164678"
---
# <a name="create-indicators-based-on-certificates"></a>根據憑證建立指示器

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


>想要體驗 Defender for Endpoint？ [註冊免費試用版。](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)

您可以為憑證建立指示器。 常見的使用案例包括：

- 案例當您需要部署封鎖技術時（例如 [攻擊面降減規則](attack-surface-reduction.md) 和 [可控資料夾存取](controlled-folders.md) ），但是需要在允許清單中新增憑證，以允許來自簽署應用程式的行為。
- 封鎖整個組織中特定簽署應用程式的使用。 透過建立指示器以封鎖應用程式的憑證，Windows Defender AV 會使檔案執行 (區塊和修正) ，而且自動化調查和修正行為相同。


### <a name="before-you-begin"></a>開始之前

在為憑證建立指示器之前，請務必先瞭解下列需求：

- 如果您的組織使用 Windows Defender 防病毒和雲端式保護，則可以使用此功能。 如需詳細資訊，請參閱 [管理以雲端為基礎的保護](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/deploy-manage-report-microsoft-defender-antivirus)。
- 反惡意軟體用戶端版本必須是4.18.1901 或更新版本。
- 在 Windows 10 版本1703或更新版本、Windows server 2016 及2019上的電腦上支援。
- 病毒和威脅防護定義必須是最新的。
- 此功能目前支援輸入。CER 或。PEM 副檔名。

>[!IMPORTANT]
> - 有效的葉憑證是具有有效憑證路徑的簽署憑證，且必須與 (CA) 的憑證授權單位系所信任的憑證授權單位單位。  或者，您可以使用自訂的 (自我簽署) 憑證，只要用戶端信任 (根 CA 憑證是安裝在本機電腦「受信任的根身分憑證授權」 ) 。
>- 允許/封鎖憑證 IOCs 的子系或父項不會包含在 allow/封鎖的 IoC 功能中，只支援分葉憑證。
>- 無法封鎖 Microsoft 簽署的憑證。

#### <a name="create-an-indicator-for-certificates-from-the-settings-page"></a>從 [設定] 頁面建立憑證的指示器：

>[!IMPORTANT]
> 建立及移除憑證 IoC 最多可能需要3小時。

1. 在功能窗格中，選取 [**設定**  >  **指示器**]。  

2. 選取 [ **憑證** ] 索引標籤。

3. 選取 [ **新增指示器**]。

4. 指定下列詳細資料：
   - 標記-指定實體詳細資料並定義指示器的到期期限。
   - Action-指定要採取的動作並提供描述。
   - Scope-定義機器群組的範圍。

5. 在 [摘要] 索引標籤中查看詳細資料，然後按一下 [ **儲存**]。

## <a name="related-topics"></a>相關主題
- [建立指示器](manage-indicators.md)
- [建立檔案的指示器](indicator-file.md)
- [為 IPs 和 URLs/網域建立指示器](indicator-ip-domain.md)
- [管理指示器](indicator-manage.md)
