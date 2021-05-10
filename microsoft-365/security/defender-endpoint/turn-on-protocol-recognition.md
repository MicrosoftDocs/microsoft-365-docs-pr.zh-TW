---
title: 開啟 Microsoft Defender 防毒軟體的通訊協定識別
description: 開啟 Microsoft Defender 防毒軟體的通訊協定識別。
keywords: Microsoft Defender 防毒軟體，反惡意程式碼，安全性，Defender，通訊協定識別
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
ms.openlocfilehash: 890303a15618a0318db0421c9c80f270583e19bf
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/10/2021
ms.locfileid: "52296468"
---
# <a name="turn-on-protocol-recognition"></a>開啟通訊協定識別 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**

- [適用於端點的 Microsoft Defender](/microsoft-365/security/defender-endpoint/)

此原則設定可讓您設定網路防護的通訊協定識別，以防範已知的漏洞。 如果您啟用或未設定此設定，則會啟用通訊協定識別。 如果停用此設定，就會停用通訊協定識別。

## <a name="use-group-policy-to-configure-protocol-recognition"></a>使用群組原則來設定通訊協定識別

1. 在您的群組原則管理端點上，開啟 [ [群組原則管理主控台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))]。

2. 移至 [**電腦** 設定]  >  系統 **管理範本**  >  **Windows**  >  **Microsoft Defender 防毒軟體**  >  **網路檢查系統** 的元件。 

3. 選取 [ **通訊協定識別**]。 依預設，會啟用此原則。 若設定為 [ **未** 設定]，則會啟用定義停用。 

4. 若要編輯原則，請選取 [ **編輯原則設定** ] 連結。

5. 選取 [ **啟用**]，然後選取 **[確定]**。

6. 部署更新的群組原則物件。 請參閱 [群組原則管理主控台](/windows/win32/srvnodes/group-policy)。

> [!TIP]
> 您是否在內部部署使用群組原則物件？ 請參閱他們在雲端中的翻譯方式。 [在 Microsoft 端點管理員預覽中使用「群組原則分析」分析您的內部部署群組原則物件](/mem/intune/configuration/group-policy-analytics)。 
  
## <a name="related-articles"></a>相關文章

- [Windows 10 中的 Microsoft Defender 防毒軟體](microsoft-defender-antivirus-in-windows-10.md)
 
- [啟動雲端提供的保護](enable-cloud-protection-microsoft-defender-antivirus.md)

- [如何建立及部署反惡意程式碼原則： Cloud-protection service](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)