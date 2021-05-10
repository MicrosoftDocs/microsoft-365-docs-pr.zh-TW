---
title: 開啟 Microsoft Defender 防毒軟體的定義停用
description: 為 Microsoft Defender 防毒軟體開啟定義停用。
keywords: Microsoft Defender 防毒軟體，反惡意程式碼，安全性，Defender，定義停用
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
ms.openlocfilehash: 66b2e882a0f6de21e27dabb3a4bfe2fe113bcb32
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/10/2021
ms.locfileid: "52296471"
---
# <a name="turn-on-definition-retirement"></a>開啟定義停用

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**

- [適用於端點的 Microsoft Defender](/microsoft-365/security/defender-endpoint/)

您可以使用「群組原則」設定定義停用。 定義停用檢查是否有必要的安全性更新，以查看電腦是否有必要的必要安全性更新，以防範特定弱點。 如果系統不容易受到定義所偵測到的入侵，則該定義為「已撤銷」。 如果已停用指定通訊協定的所有安全性智慧，則不再會分析該通訊協定。 啟用此功能有助於提升效能。 在最新安全性更新的最新電腦上，網路保護將不會影響網路效能。

## <a name="use-group-policy-to-configure-definition-retirement"></a>使用群組原則設定定義退休

1. 在您的群組原則管理端點上，開啟 [ [群組原則管理主控台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))]。

2. 移至 [**電腦** 設定]  >  系統 **管理範本**  >  **Windows**  >  **Microsoft Defender 防毒軟體**  >  **網路檢查系統** 的元件。 

3. 選取 [ **開啟定義停** 用]。 依預設，會啟用此原則。 若設定為 [ **未** 設定]，則會啟用定義停用。 

4. 若要編輯原則，請選取 [ **編輯原則設定** ] 連結。

5. 選取 [ **啟用**]，然後選取 **[確定]**。

6. 部署更新的群組原則物件。 請參閱 [群組原則管理主控台](/windows/win32/srvnodes/group-policy)。

> [!TIP]
> 您是否在內部部署使用群組原則物件？ 請參閱他們在雲端中的翻譯方式。 [在 Microsoft 端點管理員預覽中使用「群組原則分析」分析您的內部部署群組原則物件](/mem/intune/configuration/group-policy-analytics)。 
  
## <a name="related-articles"></a>相關文章

- [Windows 10 中的 Microsoft Defender 防毒軟體](microsoft-defender-antivirus-in-windows-10.md)
 
- [啟動雲端提供的保護](enable-cloud-protection-microsoft-defender-antivirus.md)

- [如何建立及部署反惡意程式碼原則： Cloud-protection service](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)