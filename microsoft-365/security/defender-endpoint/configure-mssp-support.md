---
title: 設定受管理的安全性服務提供者支援
description: 採取必要的步驟來設定 MSSP 整合與 Microsoft Defender for Endpoint
keywords: 受管理的安全性服務提供者、mssp、configure、integration
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
ms.openlocfilehash: 6786d423d20ec90c12d2ea712003acc787ed599d
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165246"
---
# <a name="configure-managed-security-service-provider-integration"></a>設定受管理的安全性服務提供者整合

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>想要體驗 Defender for Endpoint？ [注册免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-mssp-support-abovefoldlink)
 
[!include[Prerelease information](../../includes/prerelease.md)]

您必須採取下列設定步驟，才能啟用受管理的安全性服務提供者 (MSSP) 整合。

>[!NOTE]
>本文使用下列術語，以辨別服務提供者和服務使用者：
> - MSSPs：為組織監控及管理安全裝置的安全性組織。
> - MSSP 客戶：與 MSSPs 服務接洽的組織。

整合會讓 MSSPs 採取下列動作：

- 取得 MSSP 客戶 Microsoft Defender 資訊安全中心入口網站的存取權
- 取得電子郵件通知，以及 
- 透過安全性資訊和事件管理 (SIEM) 工具取得警示

在 MSSPs 可以採取這些動作之前，MSSP 客戶必須將其 Defender 的存取權授與端點租使用者，以便 MSSP 可以存取入口網站。 
 

通常，MSSP 客戶會採取初始設定步驟，授與其 Windows Defender 安全性中央租使用者的 MSSPs 存取權。 授與存取權之後，MSSP 客戶或 MSSP 可以執行其他設定步驟。


一般而言，必須採取下列設定步驟：


- **授與 Microsoft Defender 資訊安全中心的 MSSP 存取權** <br>
MSSP 客戶必須執行此動作。 它會授與 MSSP 存取權給 MSSP 客戶的端點租使用者的 Defender。
 

- **設定傳送至 MSSPs 的警示通知** <br>
MSSP 客戶或 MSSP 可以採取此項動作。 這可讓 MSSPs 知道他們必須為 MSSP 客戶解決的警示。

- **將 MSSP 客戶租使用者的警示納入 SIEM 系統** <br> MSSP 會採取此動作。 它可讓 MSSPs 取得 SIEM 工具中的警示。

- **使用 APIs 從 MSSP 客戶的承租人取得警示** <br>
MSSP 會採取此動作。 它允許 MSSPs 使用 APIs 來取得提醒。

## <a name="multi-tenant-access-for-mssps"></a>MSSPs 的多承租人存取權
如需如何實施多租使用者委派存取的詳細資訊，請參閱 [受管理的安全性服務提供者的多承租人存取](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/multi-tenant-access-for-managed-security-service-providers/ba-p/1533440)。



## <a name="related-topics"></a>相關主題
- [將入口網站存取權授予 MSSP](grant-mssp-access.md)
- [存取 MSSP 客戶入口網站](access-mssp-portal.md)
- [設定警示通知](configure-mssp-notifications.md)
- [從客戶租用戶中抓取警示](fetch-alerts-mssp.md)

