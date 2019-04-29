---
title: 步驟 7 - Windows 和 Office 服務
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
description: 了解如何在您的環境中準備 Windows 和 Office 服務。
ms.openlocfilehash: 68598f92b5b29f1c0bc20ecb402b60b45128ca6a
ms.sourcegitcommit: 3b2d3e2b38c4860db977e73dda119a465c669fa4
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/28/2019
ms.locfileid: "33400247"
---
# <a name="step-7-windows-and-office-servicing"></a>步驟 7：Windows 和 Office 服務

![](media/step-7-windows-and-office-as-a-service-media/step-7-windows-and-office-as-a-service-media-1.png)

<table>
<thead>
<td><img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-10.png" alt="Step 7" height="144" width="144" /></td>
<td><p><strong>步驟 7：Windows 和 Office 服務</strong></p>
<p>Windows 10 和 Office 365 專業增強版都會持續新增功能，以最新的發明帶領使用者體驗和安全性前進。深入了解如何保持在最新的半年和每月更新、新服務模型如何運作，以及您所擁有的工具和選項。</p></td>
<td><a href="https://aka.ms/ddev7" target="_blank"><img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-20.png" alt="Step 7" height="130" width="231" /></a></td>
</thead>
</table>

>[!NOTE]
>Windows 和 Office 服務是我們建議的部署程序轉輪中第七個步驟，說明對功能的半年更新進行準備的規劃層面。 若要查看完整的桌面部署程序，請瀏覽[桌面部署中心](https://aka.ms/HowToShift)。
>

Windows 10 與 Office 365 專業增強版都導入了新的服務選項、支援模型和更新時間表。 這些變更可簡化隨時保有最新功能的程序。 連同這些更新一起推出的是新的設定選項，其可實現符合您需求的服務方案。 讓我們了解如何準備迎接可在 Windows 10 和 Office 365 專業增強版中提供新功能的半年通道更新，並同時利用 System Center Configuration Manager 最新分支內的新功能。

[協助客戶改用 Windows 10 和 Office 365 專業增強版](https://www.microsoft.com/zh-TW/microsoft-365/blog/2018/09/06/helping-customers-shift-to-a-modern-desktop/)

## <a name="update-types"></a>更新類型

更新主要可分為兩種類別，分別是功能更新以及品質和安全性更新 (包含累積安全性、可靠性和錯誤修正)。 就頻率來說，Windows 和 Office 皆提供半年通道，會在每年的 3 月和 9 月分別提供新的功能，並且每個月會推出品質和安全性更新。 此外，針對 Office 365 應用程式，我們還會專門提供完整支援的每月通道選項，其中的更新會同時包含新功能和品質更新。

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

### <a name="expanded-validation-of-updates"></a>擴充更新驗證

另一個優點是，在針對廣泛部署推出更新之前，我們會先透過 [Office](https://products.office.com/en-us/office-insider?tab=Windows-Desktop) 和 [Windows](https://insider.windows.com/zh-TW/) 的測試人員計畫發行組建，這可讓我們收集診斷資料和意見反應之後，再廣泛發行更新。 測試人員計畫現已對測試人員開放，因此您可事先了解更新。 在更新發行時，我們會從數百萬個設定之中收到診斷資料，因此當我們實際推出更新時，品質自然會更好

還有一件事，由於 Office 365 專業增強版測試人員組建會反映每月通道更新，如果您使用 Office 的半年通道來提供 Windows 每年兩次的功能更新，您也可以使用半年通道目標版本提早驗證這些組建。

### <a name="supporting-management-tools"></a>支援的管理工具

我們也思考如何讓您的更新部署更順利。System Center Configuration Manager 最新分支會經常更新，以支援推出這些 Windows 和 Office 更新以及任何新功能。

[使用 System Center Configuration Manager 來部署 Windows 10 更新](https://docs.microsoft.com/zh-TW/windows/deployment/update/waas-manage-updates-configuration-manager) (機器翻譯)

[使用 Configuration Manager 管理 Office 365 ProPlus](https://docs.microsoft.com/zh-TW/sccm/sum/deploy-use/manage-office-365-proplus-updates)

## <a name="overview-of-windows-and-office-channels"></a>Windows 和 Office 通道的概觀

Windows 10 提供三個服務通道：

- [**Windows 測試人員計畫**](https://docs.microsoft.com/zh-TW/windows/deployment/update/waas-overview#windows-insider)，可供組織對下一次的功能更新所推出的功能進行測試並提供意見反應
- **半年通道**，每年兩次提供新的功能與功能更新版本
- **長期服務通道**，其設計僅供需要較長期服務選項的專門裝置使用

Office 365 提供四個服務通道：

- [**Office 測試人員計畫**](https://support.office.com/zh-TW/article/What-is-Office-Insider-f4208185-b63a-4b68-9c7a-9a32d2411c16)，可供組織對仍在開發的最新 Office 功能進行測試並提供意見反應
- **每月通道**，可在最新的 Office 功能可供使用時，立即提供給使用者。
- **半年通道**，每年只會提供兩次新的功能與新的特性
- **半年通道 (有目標地)**，這是完整支援的 Office 組建，可讓試驗使用者和應用程式相容性測試者測試及驗證下一個半年通道

如需 Windows 和 Office 服務通道的詳細資訊，請檢閱下列文件：

- [Windows 即服務概觀](https://docs.microsoft.com/zh-TW/windows/deployment/update/waas-overview#servicing-channels)
- [Office 365 專業增強版更新通道的概觀](https://docs.microsoft.com/zh-TW/DeployOffice/overview-of-update-channels-for-office-365-proplus#BKMK_SAC)

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