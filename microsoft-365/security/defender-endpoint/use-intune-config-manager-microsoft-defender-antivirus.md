---
title: 使用 Microsoft 端點管理員設定 Microsoft Defender 防毒軟體
description: 使用 Microsoft 端點管理員和 Microsoft Intune 設定 Microsoft Defender AV 和 Endpoint Protection
keywords: scep、intune、endpoint protection、configuration
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 05/24/2021
ms.reviewer: phuijbr, oogunrinde
manager: dansimp
ms.technology: mde
audience: ITPro
ms.topic: how-to
ms.openlocfilehash: ab77f3ab5ac9385d1ce049061730d2192e3bcb0c
ms.sourcegitcommit: a6fb731fdf726d7d9fe4232cf69510013f2b54ce
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/27/2021
ms.locfileid: "52683748"
---
# <a name="use-microsoft-endpoint-manager-to-configure-and-manage-microsoft-defender-antivirus"></a>使用 Microsoft 端點管理員來設定及管理 Microsoft Defender 防毒軟體

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用於：**

- [適用於端點的 Microsoft Defender](/microsoft-365/security/defender-endpoint/)

您可以使用[Microsoft 端點管理員](/mem/endpoint-manager-overview)來設定 Microsoft Defender 防毒軟體掃描。 [Microsoft Intune](/mem/intune/fundamentals/what-is-intune)及[Configuration Manager](/mem/configmgr/core/understand/introduction)現在是端點管理員的一部分。  

## <a name="configure-microsoft-defender-antivirus-scans-in-endpoint-manager"></a>設定端點管理員中的 Microsoft Defender 防毒軟體掃描

1. 請移至 Microsoft 端點管理員系統管理中心 ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) ，然後登入。

2. 流覽至 **端點安全性**。

3. 在 [ **管理**] 下，選擇 [ **防病毒**]。

4. 選取您的 Microsoft Defender 防毒軟體原則。 

5. 在 **[管理]** 底下，選擇 **[內容]**。

6. 在 **[組態設定]** 旁邊，選擇 **[編輯]**。

7. 展開 [ **Scan** ] （掃描）區段，然後查看或編輯您的掃描設定。

8. 選擇 [ **審閱 + 儲存**


> [!TIP]
> 需要協助？ 請參閱[Manage endpoint security in Microsoft Intune](/mem/intune/protect/endpoint-security)。


## <a name="related-articles"></a>相關文章

- [管理及設定工具的參考文章](configuration-management-reference-microsoft-defender-antivirus.md)
- [Windows 10 中的 Microsoft Defender 防毒軟體](microsoft-defender-antivirus-in-windows-10.md)