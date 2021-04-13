---
title: 新一代保護技術
description: 瞭解如何管理、設定及使用 Microsoft Defender 防毒軟體、內建的反惡意程式碼和防防毒保護。
keywords: Microsoft Defender 防毒程式，windows defender，反惡意軟體，scep，system center endpoint protection，system center configuration manager，病毒，惡意程式碼，威脅，偵測，保護，安全性
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: high
author: denisebmsft
ms.author: deniseb
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.openlocfilehash: 9d8ab5be45e671fb07df0d9d1f46eb626d9dd149
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/13/2021
ms.locfileid: "51690092"
---
# <a name="next-generation-protection"></a>新一代保護技術

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**

- [適用於端點的 Microsoft Defender](/microsoft-365/security/defender-endpoint/)

## <a name="microsoft-defender-antivirus-your-next-generation-protection"></a>Microsoft Defender 防毒程式：您的下一代保護

Microsoft Defender 防病毒是 Microsoft Defender for Endpoint 的下一代保護元件。 這項保護會將機器學習、大量資料分析、深入威脅抵觸調查與 Microsoft 雲端基礎結構整合在一起，以保護企業組織中的裝置。 您的下一代保護服務包含下列功能：

- [行為型、啟發式和即時防防毒保護](configure-protection-features-microsoft-defender-antivirus.md)，其中包括使用檔案及程式列為監控和其他試探法 (（也稱為 *即時保護*) ）的無條件掃描。 此外，它也包含偵測並封鎖的應用程式，但這些應用程式被視為不安全，但可能偵測為惡意程式碼。
- [雲端提供的保護](cloud-protection-microsoft-defender-antivirus.md)，包括近乎立即偵測和封鎖新的和新興的威脅。
- [專用的保護和產品更新](manage-updates-baselines-microsoft-defender-antivirus.md)，其中包含的更新會與保持 Microsoft Defender 防病毒的更新相關。

## <a name="try-a-demo"></a>嘗試示範！

請造訪 [Microsoft Defender For Endpoint 示範網站](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) ，確認下列保護功能正常運作，並使用示範案例探索：
- 雲端提供的保護
- 在第一次看到 (BAFS) protection 時封鎖
- 可能有害的應用程式 (PUA) 保護

## <a name="minimum-system-requirements"></a>最低系統需求

Microsoft Defender 防病毒具有與 Windows 10 相同的硬體需求。 如需詳細資訊，請參閱下列資源：

- [基本硬體需求](/windows-hardware/design/minimum/minimum-hardware-requirements-overview)
- [硬體元件指導方針](/windows-hardware/design/component-guidelines/components)

## <a name="configure-next-generation-protection-services"></a>設定下一代保護服務

如需如何設定下一代保護服務的詳細資訊，請參閱 [設定 Microsoft Defender 防病毒功能](configure-microsoft-defender-antivirus-features.md)。

> [!Note]  
> 在執行 Microsoft Defender 防毒程式時，設定和管理在 Windows Server 2016 和 Windows Server 2019 中基本上是相同的;不過，有一些差異。 若要深入瞭解，請參閱 [Windows Server 2016 和2019上的 Microsoft Defender 防毒軟體](microsoft-defender-antivirus-on-windows-server.md)。

## <a name="see-also"></a>另請參閱

- [Windows Server 2016 和2019上的 Microsoft Defender 防毒程式](microsoft-defender-antivirus-on-windows-server.md)
- [Microsoft Defender 防病毒管理和設定](configuration-management-reference-microsoft-defender-antivirus.md)
- [評估 Microsoft Defender 防防毒保護](evaluate-microsoft-defender-antivirus.md)