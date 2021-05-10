---
title: 為 Microsoft Defender 防毒軟體的網路流量檢查指定其他定義集
description: 為 Microsoft Defender 防毒軟體的網路流量檢查指定其他定義集。
keywords: Microsoft Defender 防毒軟體，反惡意程式碼，安全性，Defender，網路流量檢查
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.date: 05/07/2021
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 82568df0a6ad2225fd31b4c0fa4a654710f1e98b
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/10/2021
ms.locfileid: "52300142"
---
# <a name="specify-additional-definition-sets-for-network-traffic-inspection"></a>指定網路流量檢查的其他定義集

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**

- [適用於端點的 Microsoft Defender](/microsoft-365/security/defender-endpoint/)

您可以使用群組原則，為網路流量檢查指定其他定義集。

## <a name="use-group-policy-to-specify-additional-definition-sets-for-network-traffic-inspection"></a>使用群組原則指定網路流量檢查的其他定義集

1. 在您的群組原則管理端點上，開啟 [ [群組原則管理主控台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))]。

2. 移至 **Windows**  >  **Microsoft Defender 防毒軟體**  >  **網路檢查系統** 的元件。 

3. 選取 [ **指定網路流量檢查的其他定義集**]。 根據預設，此原則會設定為 [ **未** 設定]。 

4. 若要編輯原則，請選取 [ **編輯原則設定** ] 連結。

5. 選取 [ **啟用**]，然後在 [ **選項** ] 區段中，選取 [ **顯示 ...**]。

6. 將專案新增至清單，然後選取 **[確定]**。 

   每個專案都必須以名稱-值對列出，其中名稱是定義集 GUID 的字串標記法。 舉例來說，enable test security 情報的定義集 GUID 是定義為： `{b54b6ac9-a737-498e-9120-6616ad3bf590}` 。 未使用此值，因此建議將其設定為 `0` 。 

7. 請選取 **[確定]**，然後再部署更新的群組原則物件。 請參閱 [群組原則管理主控台](/windows/win32/srvnodes/group-policy)。

> [!TIP]
> 您是否在內部部署使用群組原則物件？ 請參閱他們在雲端中的翻譯方式。 [在 Microsoft 端點管理員預覽中使用「群組原則分析」分析您的內部部署群組原則物件](/mem/intune/configuration/group-policy-analytics)。 
  
## <a name="related-articles"></a>相關文章

- [Windows 10 中的 Microsoft Defender 防毒軟體](microsoft-defender-antivirus-in-windows-10.md)
 
- [啟動雲端提供的保護](enable-cloud-protection-microsoft-defender-antivirus.md)

- [如何建立及部署反惡意程式碼原則： Cloud-protection service](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)