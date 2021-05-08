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
ms.openlocfilehash: d95f8dec433f29dea0fd5f7f718f34f571b790d4
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274805"
---
# <a name="use-next-generation-technologies-in-microsoft-defender-antivirus-through-cloud-delivered-protection"></a>透過雲端提供的保護，使用 Microsoft Defender 防毒軟體中的下一代技術

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用於：**

- [適用於端點的 Microsoft Defender](/microsoft-365/security/defender-endpoint/)
- Microsoft Defender 防毒軟體

Microsoft Defender 防毒軟體中的 Microsoft 下一代技術提供近立即、自動防護，以防禦新的和新興的威脅。 為了能動態地識別新的威脅，這些技術會搭配使用 Microsoft Intelligent Security Graph 中的大量互連資料，以及由進階機器學習模型驅動的強大人工智慧 (AI) 系統。  

Microsoft Defender 防毒軟體會使用多個偵測及防護技術來提供準確、即時和智慧的保護。 [深入瞭解 Microsoft Defender 在第二代端點的核心的高級技術](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/)。
![Microsoft Defender AV 引擎清單](images/microsoft-defender-atp-next-generation-protection-engines.png)  

若要利用這些下一代技術的功能和速度，Microsoft Defender 防毒軟體可以與 Microsoft 雲端服務順利運作。 這些雲端保護服務也稱為 Microsoft Advanced Protection Service (對應) 、增強標準即時保護，可提供最佳的病毒防護。 

>[!NOTE]
>Microsoft Defender 防毒軟體 cloud service 是一種機制，可將更新的保護傳遞到網路和端點。 雖然它稱為雲端服務，但並不只是保護儲存在雲端中的檔案，而是使用分散式資源和機器學習功能，以比傳統的安全性智慧更新速度更快的速率來傳送您的端點。

透過雲端提供的保護，下一代技術可提供新威脅的快速識別，有時甚至在單一機器遭到感染之前。 請觀看下列有關 Microsoft AI 和 Microsoft Defender 防毒軟體動作的影片： 
 
<iframe 
src="https://www.microsoft.com/videoplayer/embed/RE1Yu4B" width="768" height="432" allowFullScreen="true" frameBorder="0" scrolling="no"></iframe>

若要瞭解下一代技術如何縮短透過雲端的保護傳遞時間，請觀看下列影片： 
 
<iframe 
src="https://videoplayercdn.osi.office.net/embed/c2f20f59-ca56-4a7b-ba23-44c60bc62c59" width="768" height="432" allowFullScreen="true" frameBorder="0" scrolling="no"></iframe>

請閱讀下列博客文章，以取得包括雲端保護和 Microsoft AI 的詳細保護案例： 

- [為何 Microsoft Defender 防毒軟體是企業中最常部署的](https://www.microsoft.com/security/blog/2018/03/22/why-windows-defender-antivirus-is-the-most-deployed-in-the-enterprise) 
- [結合機器教育 spoils 的行為監控大量 Dofoil 硬幣挖掘活動](https://www.microsoft.com/security/blog/2018/03/07/behavior-monitoring-combined-with-machine-learning-spoils-a-massive-dofoil-coin-mining-campaign)
- [人工情報如何停止 Emotet 爆發](https://www.microsoft.com/security/blog/2018/02/14/how-artificial-intelligence-stopped-an-emotet-outbreak)
- [Detonating a 不良 rabbit： Microsoft Defender 防毒軟體和分層機器教育防護](https://www.microsoft.com/security/blog/2017/12/11/detonating-a-bad-rabbit-windows-defender-antivirus-and-layered-machine-learning-defenses)
- [Microsoft Defender 防毒軟體 cloud protection service：對永不見的惡意程式碼進行高級即時防護](https://www.microsoft.com/security/blog/2017/07/18/windows-defender-antivirus-cloud-protection-service-advanced-real-time-defense-against-never-before-seen-malware) 
 
## <a name="get-cloud-delivered-protection"></a>取得雲端提供的保護 

預設會啟用已啟用雲端功能的保護。 不過，如果它已停用為舊版組織原則的一部分，您可能需要重新啟用此功能。

執行 Windows 10 E5 的組織也可以利用緊急的動態智慧更新，其可提供離新興威脅的接近即時防護。 當您開啟雲端提供的保護時，惡意程式碼問題的修復程式可在幾分鐘內透過雲端傳送，而不是等待下一個更新。

>[!TIP]
>您也可以在[demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground)流覽 Windows Defender 的 Testground 網站，確認該功能是否正常運作，並查看其運作方式。

下表說明在 Windows 與 Configuration Manager 的最新版本之間，雲端傳送保護的差異。

|作業系統版本或服務應用程式 |雲端保護服務標籤  |報表層級 (對應的成員資格層級)   |雲端封鎖超時期限  |
|---------|---------|---------|---------|
|Windows 8.1 (群組原則)      |Microsoft Advanced Protection 服務   |基本，高級   |否         |
|Windows 10，版本 1607 (群組原則)   |Microsoft Advanced Protection 服務      |進階         |否         |
|Windows 10 版本1703或更高版本 (群組原則)       |雲端型保護      |進階         |配置         |
|System Center 2012 Configuration Manager  |      不適用         |取決於 Windows 版本         |無法設定 |
|Microsoft 端點管理員 (目前的分支)          |Cloud protection service         |取決於 Windows 版本          |配置         |
|Microsoft Intune     |Microsoft Advanced Protection 服務         |取決於 Windows 版本         |配置         |

您也可以[設定 Microsoft Defender 防毒軟體，根據雲端服務的報告自動接收新的保護更新](manage-event-based-updates-microsoft-defender-antivirus.md#cloud-report-updates)。


## <a name="tasks"></a>工作

- [啟用雲端提供的保護](enable-cloud-protection-microsoft-defender-antivirus.md)。 您可以使用「Microsoft Endpoint Configuration Manager」、「群組原則」、「Microsoft Intune」和「PowerShell Cmdlet」來啟用雲端提供的保護。

- [指定雲端提供的保護層級](specify-cloud-protection-level-microsoft-defender-antivirus.md)。 您可以使用群組原則和 Microsoft Endpoint Configuration Manager 指定雲端所提供的保護層級。 保護層級會影響與雲端共用的資訊數量，以及封鎖積極的新檔案的方式。

- [設定及驗證 Microsoft Defender 防毒軟體的網路連接](configure-network-connections-microsoft-defender-antivirus.md)。 您的網路和端點必須能夠連線，才能讓雲端提供的保護有效地運作。 URLs 本文列出應該透過防火牆或網路篩選規則所允許的 URLs，以及確認網路是否已正確註冊雲端傳送保護中的指示。

- [設定封鎖在第一次看到的功能](configure-block-at-first-sight-microsoft-defender-antivirus.md)。 「第一次看到的封鎖」功能可以在數秒內封鎖新的惡意程式碼，而不需要等候傳統安全性情報的時間。 您可以使用 Microsoft 端點管理員和群組原則來啟用及設定它。

- [設定雲端封鎖超時期限](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md)。 Microsoft Defender 防毒軟體可以封鎖可疑檔案的執行，同時查詢我們的雲端提供的保護服務。 您可以設定使用 Microsoft 端點管理員和群組原則，將無法執行檔案的時間長度。