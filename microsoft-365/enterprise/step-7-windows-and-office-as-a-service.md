---
title: 步驟 7 - Windows 和 Office 即服務
ms.author: jogruszc
author: JGruszczyk
manager: jemed
ms.date: 09/14/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: 了解如何在您的環境中準備 Windows 和 Office 即服務。
ms.openlocfilehash: 5c3eb54e07b1cc5492a6d938e97286283fc47ca7
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/28/2018
ms.locfileid: "26866513"
---
# <a name="step-7-windows-and-office-as-a-service"></a>步驟 7：Windows 和 Office 即服務

準備迎接半年通道更新與 Windows 10 和 Office 365 專業增強版的新功能，以及 System Center Configuration Manager 最新分支管理工具的對應更新。

![](media/step-7-windows-and-office-as-a-service-media/step-7-windows-and-office-as-a-service-media-1.png)

<table>
<thead>
<td><img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-10.png" alt="Step 7" height="144" width="144" /></td>
<td><p><strong>步驟 7：準備 Windows 和 Office 即服務</strong></p>
<p>Windows 10 和 Office 365 專業增強版都會持續新增功能，以最新的發明帶領使用者體驗和安全性前進。深入了解如何保持在最新的半年和每月更新、新服務模型如何運作，以及您所擁有的工具和選項。</p></td>
<td><a href="https://aka.ms/ddev7" target="_blank"><img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-20.png" alt="Step 7" height="130" width="231" /></a></td>
</thead>
</table>

>[!NOTE]
>Windows 與 Office 即服務是我們建議的部署程序轉輪中第七個步驟，說明對功能的半年更新進行準備的規劃層面。若要查看完整的桌面部署程序，請瀏覽[現代化電腦的部署中心](https://aka.ms/HowToShift) (英文)。
>

Windows 10 和 Office 365 專業增強版引入新的服務選項、支援模型及更新時間表。這些變更簡化程序來維持目前的最新功能。除了這些更新以外還有新的設定選項，以提供符合您需求的服務方案。

[協助客戶移至現代化桌面](https://www.microsoft.com/zh-TW/microsoft-365/blog/2018/09/06/helping-customers-shift-to-a-modern-desktop/) (英文)

## <a name="update-types"></a>更新類型

更新可分為兩種主要類別：功能更新以及包含累計安全性、可靠性和錯誤修正的品質和安全性更新。以頻率而言，Windows 和 Office 提供半年通道，每年在 3 月和 9 月時會提供新功能兩次，而品質和安全性更新則是每月提供。此外，Office 365 應用程式特別的是，我們提供每月通道更新，受到完整支援並包含新功能和品質更新。

如果您已經習慣電腦作業系統與應用程式更新之間較長的週期，您可能會想了解：

  - 更新是否相容？

  - 我需要重新訓練使用者嗎？

  - 有哪些風險？

若要回答這些問題以及為何更頻繁地提供新功能，我們提供這種方法的一些優點

### <a name="feature-update-benefits"></a>功能更新的優點

首先，我們已經捨棄過去的模型，過去約每隔三年會引入大型變更，現在則是增量的小型變更，以及每年兩次的功能更新。為什麼？由於技術趨勢變動快速，加上快速發展的安全性威脅，這麼做可讓體驗和保護維持在最新狀態。舉例來說，部分安全性相關的更新，無法只藉由每月的安全性更新或防毒簽章檔案來提供；它們可能是低階變更平台，如虛擬化型安全性。

[Windows 即服務快速指南](https://docs.microsoft.com/zh-TW/windows/deployment/update/waas-quick-start) (機器翻譯)

[使用 Windows 10 安全性功能來降低威脅](https://docs.microsoft.com/zh-TW/windows/security/threat-protection/overview-of-threat-mitigations-in-windows-10%20%20)

### <a name="cumulative-update-model-benefits"></a>累計更新模型的優點

第二，以累計更新套件的方式提供品質和安全性更新可修正許多過去的問題。過去，有時您可能每個月要為 Windows 和 Office 從十幾個或更多的更新中進行挑選。可以想像，這會是一組幾乎無法支援的測試矩陣。此外，如果您安裝的 Windows 或 Office 版本已經過一年或者更舊，可能需要數小時或甚至數日來套用自該版本發行後提供的所有更新。

使用累計模型，您只需要一次更新就能保持在目前最新狀態，如此可減少您需要部署的每月更新數。每個更新都建立在前幾個月的更新之上，且包含保持在最新狀態所需的所有修正程式。當電腦已關閉數個月，在儲存狀態中等待重新指派給其他使用者時，累計更新特別有幫助。

[Windows 即服務概觀](https://docs.microsoft.com/zh-TW/windows/deployment/update/waas-overview) (機器翻譯)

### <a name="expanded-validation-of-updates"></a>擴充更新驗證

另一個優點是，在推出用於廣泛部署的更新之前，我們會先透過「[Office](https://products.office.com/en-us/office-insider?tab=Windows-Desktop) 與 [Windows](https://insider.windows.com/zh-TW/) 測試人員計畫」發行組建，這可讓我們在廣泛發行更新之前收集遙測和意見反應。現在測試人員計畫已開放給所有人，讓您可以提早了解更新。等到發行更新時，我們將已從數百萬個設定收到遙測，因此在實際推出更新時，就較能夠掌握品質。

還有一件事，由於 Office 365 專業增強版測試人員組建會反映每月通道更新，如果您使用 Office 的半年通道來提供 Windows 每年兩次的功能更新，您也可以使用半年通道目標版本提早驗證這些組建。

### <a name="supporting-management-tools"></a>支援的管理工具

我們也思考如何讓您的更新部署更順利。System Center Configuration Manager 最新分支會經常更新，以支援推出這些 Windows 和 Office 更新以及任何新功能。

[使用 System Center Configuration Manager 來部署 Windows 10 更新](https://docs.microsoft.com/zh-TW/windows/deployment/update/waas-manage-updates-configuration-manager) (機器翻譯)

[使用 Configuration Manager 管理 Office 365 ProPlus](https://docs.microsoft.com/zh-TW/sccm/sum/deploy-use/manage-office-365-proplus-updates)

## <a name="phased-deployment-of-updates"></a>階段式更新部署

現在讓我們來看如何推出這些更新。在任何版本中，我們建議您至少要有三個 IT 部署階段 - 驗證、試驗和廣泛生產部署。當您開始執行 Windows 10 與 Office 365 專業增強版，您將會使用每月服務透過重要安全性和品質更新維持在最新狀態，然後移至半年服務以取得新功能。

### <a name="monthly-updating"></a>每月更新

服務模型的設計讓您可以選擇將新功能的推出限制為每年兩次，且視需要您可以略過半年更新，並繼續接收品質和安全性更新。如上所述，每月更新的累計性表示每次更新在每個月大小會增加。

#### <a name="express-updates"></a>快速更新

使用 Windows 中稱為「快速更新」的技術和 Office 中的「二進位差異壓縮」，我們可以大幅縮減下載大小。在這兩種方法中，更新引擎會比較電腦上的內容，並僅尋找需要更新的差異。

[說明 Windows 10 品質更新和差異結尾更新](https://techcommunity.microsoft.com/t5/Windows-IT-Pro-Blog/Windows-10-quality-updates-explained-amp-the-end-of-delta/ba-p/214426)

商務用 Windows Update 及 Windows Server Update Services 已長期支援快速更新，但我們目前已將該支援擴展至 System Center Configuration Manager，因此它也可以使用快速更新。

![](media/step-7-windows-and-office-as-a-service-media/step-7-windows-and-office-as-a-service-media-3.png)

#### <a name="binary-delta-compression"></a>二進位差異壓縮

如果您要從最新版本的 Office 365 專業增強版進行更新，才會使用 Office 的二進位差異壓縮，因此要使用這個方法您需要從先前的組建更新，且無法略過更新。

Windows 和 Office 更新通道可使用標準的核准和目標設定程序，透過 Configuration Manager 進行管理。此外，您可以使用 Office 和 Windows 中的原則設定，以強制使用更新通道以及相關設定。

### <a name="semi-annual-updates"></a>半年更新

以上為每月更新的考量事項，現在讓我們移至較大的半年更新。

如同「裝置和應用程式整備」中所說明，您可以使用部署程序轉輪步驟 1 中所設定的相同整備工具，開始進行這些較大更新的準備。

對於工具，您可以使用原則設定與商務用 Windows Update、透過 System Center Configuration Manager 的軟體更新管理、Windows Server Update Services (WSUS)，或 Microsoft Intune 所設定的更新原則。如果您擔心網路頻寬，請參閱步驟 2：目錄和網路整備，以了解透過傳遞最佳化和其他對等快取技術降低網路流量的選項。

![](media/step-7-windows-and-office-as-a-service-media/step-7-windows-and-office-as-a-service-media-4.png)

[Windows 半年通道](https://docs.microsoft.com/zh-TW/windows/deployment/update/waas-overview#semi-annual-channel)

[Office 365 專業增強版的半年通道](https://docs.microsoft.com/zh-TW/DeployOffice/overview-of-update-channels-for-office-365-proplus#BKMK_SAC)

#### <a name="upgrade-task-sequences"></a>升級工作順序

透過標準軟體更新管理常式安裝較大的功能更新是受支援的選項，但許多組織會選擇使用「升級工作順序」搭配 System Center Configuration Manager 或 Microsoft Deployment Toolkit。

「工作順序」可讓您在安裝功能更新之前建立自訂檢查或工作，並可讓您在更新安裝自行完成後執行自訂工作，更新後的工作可能包括在更新期間視需要暫時暫停服務、驅動程式安裝和取代、應用程式升級或工作列與 Windows 10 [開始] 個人化設定。

![](media/step-7-windows-and-office-as-a-service-media/step-7-windows-and-office-as-a-service-media-5.png)

如果您已使用工作順序將 Windows 7 電腦移轉到 Windows 10，且您很熟悉這些工具，則這是很好的起點，並可提供最終的控制。雖然您可以針對整個升級使用單一工作順序，組織使用兩個工作順序是很常見的。其中一個工作順序用來確定電腦已準備好升級，可自動在目標電腦上將所有必要的安裝檔案預先區分階段，另一個則執行實際的升級。這個方法可確保使用者生產力較不會受到影響。

[建立工作順序以在 Configuration Manager 中升級作業系統](https://docs.microsoft.com/zh-TW/sccm/osd/deploy-use/create-a-task-sequence-to-upgrade-an-operating-system) (英文)

#### <a name="semi-annual-channel-support-for-feature-updates"></a>功能更新的半年通道支援

[如 2018 年 9 月所宣布](https://www.microsoft.com/zh-TW/microsoft-365/blog/2018/09/06/helping-customers-shift-to-a-modern-desktop/)，半年通道更新的支援時間表將會使用下列模型。

  - 所有目前支援的 Windows 10 企業版和教育版功能更新，從版本 1607 開始，將會從原始發行日期起受到 30 個月的支援。

  - 指定目標為 9 月的所有未來功能更新，從版本 1809 開始，將會從發行日期起受到 30 個月的支援。

  - 指定目標為 3 月的未來功能更新，從版本 1903 開始，將會從發行日期起繼續受支援 18 個月。

  - Office 365 專業增強版的半年更新會繼續受支援 18 個月

#### <a name="additional-setup-automation-options-outside-of-task-sequences"></a>工作順序以外的其他設定自動化選項

如果您未使用「升級工作順序」，您現在可以執行自訂動作，或在套用升級之前，在預先安裝階段 (在設定執行相容性檢查之前，或在預先認可階段) 的功能更新期間套用驅動程式檔案。

[Windows 10 設定 (版本 1803) 中的新增功能](https://docs.microsoft.com/zh-TW/windows/whats-new/whats-new-windows-10-version-1803%23windows-setup)

## <a name="next-step"></a>下一步 

## <a name="step-8-user-communications-and-traininghttpsakamsmdd8"></a>[步驟 8：使用者的通訊和訓練](https://aka.ms/mdd8) (英文)

## <a name="previous-step"></a>上一步 

## <a name="step-6-os-deployment-and-feature-updateshttpsakamsmdd6"></a>[步驟 6：作業系統部署與功能更新](https://aka.ms/mdd6) (英文)