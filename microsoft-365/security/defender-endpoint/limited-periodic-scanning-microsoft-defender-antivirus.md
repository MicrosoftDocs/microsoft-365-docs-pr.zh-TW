---
title: 啟用有限的定期 Microsoft Defender 防病毒掃描功能
description: 有限的定期掃描可讓您使用 Microsoft Defender 防毒軟體，以及其他安裝的 AV 提供者。
keywords: lps，有限，週期性，掃描，掃描，相容性，協力廠商，其他 av，停用
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 82c4bc1feec1556dc864558a843ed5e911c3ef3d
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764480"
---
# <a name="use-limited-periodic-scanning-in-microsoft-defender-antivirus"></a>在 Microsoft Defender 防病毒中使用有限的定期掃描

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用於：**

- [適用於端點的 Microsoft Defender](/microsoft-365/security/defender-endpoint/)

「定期掃描」是一種特殊類型的威脅偵測和修正，當您已在 Windows 10 裝置上安裝其他防病毒產品時，就可以啟用此功能。

只有在某些情況下才能啟用。 如需有限定期掃描的詳細資訊，以及 Microsoft Defender 防毒軟體如何與其他防病毒產品搭配運作，請參閱 [Microsoft Defender 防毒程式相容性](microsoft-defender-antivirus-compatibility.md)。

**Microsoft 不建議在企業環境中使用這項功能。這是主要供消費者使用的功能。** 這項功能只會使用有限的 Microsoft Defender 防病毒功能子集來偵測惡意程式碼，而且無法偵測大多數惡意程式碼和潛在的垃圾軟體。 此外，管理與報告功能將會受到限制。 Microsoft 建議企業選擇他們的主要防病毒方案，並以獨佔方式使用。

## <a name="how-to-enable-limited-periodic-scanning"></a>如何啟用有限的定期掃描

根據預設，當沒有安裝其他防病毒產品時，Microsoft Defender 防病毒會自行在 Windows 10 裝置上啟用它，或者如果其他產品已過期或無法正常運作。

如果已啟用 Microsoft Defender 防病毒，一般的選項會出現在該裝置上進行設定：

![顯示 Microsoft Defender AV 選項的 Windows 安全性應用程式，包括掃描選項、設定和更新選項](images/vtp-wdav.png)

如果已安裝另一種防病毒產品且運作正常，Microsoft Defender 防毒軟體會自行停用。 Windows 安全性應用程式會變更「 **病毒 & 威脅防護** 」區段，以顯示 AV 產品的狀態，並提供產品設定選項的連結。

在任何協力廠商 AV 產品下，新的連結會顯示為 **Microsoft Defender 防病毒選項**。 按一下此連結會展開以顯示可啟用有限定期掃描的切換功能。 請注意，[有限週期] 選項是以啟用或停用定期掃描的切換方式。 

將開關切換到 [ **開啟** ]，會在協力廠商 av 產品下顯示標準的 MICROSOFT Defender AV 選項。 [有限的定期掃描] 選項會出現在頁面底部。

## <a name="related-articles"></a>相關文章

- [設定行為、啟發式和即時保護](configure-protection-features-microsoft-defender-antivirus.md)
- [Windows 10 中的 Microsoft Defender 防病毒](microsoft-defender-antivirus-in-windows-10.md)