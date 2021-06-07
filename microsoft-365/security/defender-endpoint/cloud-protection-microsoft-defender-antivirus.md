---
title: 雲端提供的保護與 Microsoft Defender 防毒軟體
description: 深入瞭解雲端提供的保護和 Microsoft Defender 防毒軟體
keywords: Microsoft Defender 防毒軟體，新一代技術，下一代 av，機器教學，反惡意程式碼，安全性，Defender，cloud，雲端提供的保護
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.reviewer: shwjha
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 836025b42bbe6142f462ee31f266a636f5101fe9
ms.sourcegitcommit: 3b9fab82d63aea41d5f544938868c5d2cbf52d7a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/05/2021
ms.locfileid: "52783002"
---
# <a name="cloud-delivered-protection-and-microsoft-defender-antivirus"></a>雲端提供的保護與 Microsoft Defender 防毒軟體

**適用於：**

- [適用於端點的 Microsoft Defender](/microsoft-365/security/defender-endpoint/)
- Microsoft Defender 防毒軟體

Microsoft Defender 防毒軟體中的下一代技術提供近乎即時、自動防護，以防禦新的和新興的威脅。 若要以動態方式識別新威脅，下一代技術可使用 Microsoft 智慧型 Security Graph 和強大的人工智慧 (AI) 由「高級機器學習模型」所驅動的系統中的大量相互關聯的資料。 Microsoft Defender 防毒軟體會使用多個偵測及防護技術來提供準確、即時和智慧的保護。 

> [!TIP]
> 想要深入了解？ 請參閱博客文章， [瞭解 Microsoft Defender 的核心中的高級技術以取得端點下一代保護](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/)。

Microsoft Defender 防毒軟體與 Microsoft 雲端服務無縫運作。 這些雲端保護服務也稱為 Microsoft Advanced Protection Service (對應) 、增強標準即時保護，可提供最佳的病毒防護。 

> [!NOTE]
> Microsoft Defender 防毒軟體 cloud service 是一種機制，可將更新的保護傳遞到網路和端點。 做為雲端服務，不只是保護儲存在雲端中的檔案;相反地，雲端服務會使用分散式資源和機器教學，以比傳統的安全性智慧更新更快的速率來提供對端點的保護。

透過雲端提供的保護，下一代技術可提供新威脅的快速識別，有時甚至在單一機器遭到感染之前。 下列博客文章說明雲端傳送保護的運作方式：

- [為何 Microsoft Defender 防毒軟體是企業中最常部署的](https://www.microsoft.com/security/blog/2018/03/22/why-windows-defender-antivirus-is-the-most-deployed-in-the-enterprise) 
- [結合機器教育 spoils 的行為監控，大量硬幣-挖掘活動](https://www.microsoft.com/security/blog/2018/03/07/behavior-monitoring-combined-with-machine-learning-spoils-a-massive-dofoil-coin-mining-campaign)
- [人工智慧如何停止「Emotet」突發](https://www.microsoft.com/security/blog/2018/02/14/how-artificial-intelligence-stopped-an-emotet-outbreak)
- [Detonating a 不良 rabbit： Microsoft Defender 防毒軟體和分層機器教育防護](https://www.microsoft.com/security/blog/2017/12/11/detonating-a-bad-rabbit-windows-defender-antivirus-and-layered-machine-learning-defenses)
- [Microsoft Defender 防毒軟體 cloud protection service：對永不見的惡意程式碼進行高級即時防護](https://www.microsoft.com/security/blog/2017/07/18/windows-defender-antivirus-cloud-protection-service-advanced-real-time-defense-against-never-before-seen-malware) 
 
## <a name="how-to-get-cloud-delivered-protection"></a>如何取得雲端提供的保護 

預設會啟用已啟用雲端功能的保護。 不過，如果它已停用為舊版組織原則的一部分，您可能需要重新啟用此功能。 若要深入瞭解，請參閱 [開啟雲端提供的保護](enable-cloud-protection-microsoft-defender-antivirus.md)。

執行 Windows 10 E5 的組織也可以利用緊急的動態智慧更新，其可提供離新興威脅的接近即時防護。 當您開啟雲端提供的保護時，惡意程式碼問題的修復程式可在幾分鐘內透過雲端傳送，而不是等待下一個更新。 [設定 Microsoft Defender 防毒軟體，根據雲端服務的報告自動接收新的保護更新](manage-event-based-updates-microsoft-defender-antivirus.md#cloud-report-updates)。

> [!TIP]
> 流覽[demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground)的 Windows Defender Testground 網站，確認該功能是否正常運作，並查看其運作方式。

## <a name="next-steps"></a>後續步驟

1. [啟用雲端提供的保護](enable-cloud-protection-microsoft-defender-antivirus.md)。 您可以使用現在包含 Microsoft Endpoint Configuration Manager 和 Microsoft Intune) 、群組原則或 PowerShell Cmdlet 的 Microsoft 端點管理員 (來啟用雲端提供的保護。

2. [指定雲端提供的保護層級](specify-cloud-protection-level-microsoft-defender-antivirus.md)。 您可以使用 Microsoft 端點管理員或群組原則指定雲端所提供的保護層級。 保護層級會影響與雲端共用的資訊數量，以及封鎖積極的新檔案的方式。

3. [設定及驗證 Microsoft Defender 防毒軟體的網路連接](configure-network-connections-microsoft-defender-antivirus.md)。 您的網路和端點必須能夠連線，才能讓雲端提供的保護有效地運作。 URLs 本文列出應該透過防火牆或網路篩選規則所允許的 URLs，以及確認網路是否已正確註冊雲端傳送保護中的指示。

4. [設定「初次看到時封鎖」功能](configure-block-at-first-sight-microsoft-defender-antivirus.md)。 「第一次看到的封鎖」功能可以在數秒內封鎖新的惡意程式碼，而不需要等候傳統安全性情報的時間。 您可以使用 Microsoft 端點管理員或群組原則來啟用及設定它。

5. [設定雲端封鎖超時期限](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md)。 Microsoft Defender 防毒軟體可以封鎖可疑檔案的執行，同時查詢我們的雲端提供的保護服務。 您可以使用 Microsoft 端點管理員或群組原則來設定禁止執行檔案的時間長度。