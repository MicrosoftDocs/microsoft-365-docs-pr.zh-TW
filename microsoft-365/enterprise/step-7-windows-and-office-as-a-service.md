---
title: 步驟 7 - Windows 和 Office 服務
f1.keywords:
- NOCSH
ms.author: jogruszc
author: JGruszczyk
manager: jemed
ms.date: 05/20/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: 了解如何在您的環境中準備 Windows 和 Office 服務。
ms.openlocfilehash: e9de339c6bc66e5cd3c02af5f6a53c32b7573b1f
ms.sourcegitcommit: 584e2e9db8c541fe32624acdca5e12ee327fdb63
ms.contentlocale: zh-TW
ms.lasthandoff: 06/10/2020
ms.locfileid: "44678999"
---
# <a name="step-7-windows-and-office-servicing"></a>步驟 7：Windows 和 Office 服務

![](../media/step-7-windows-and-office-as-a-service-media/step-7-windows-and-office-as-a-service-media-1.png)

<table>
<thead>
<td><img src="../media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-10.png" alt="Step 7" height="144" width="144" /></td>
<td><p><strong>步驟 7：Windows 和 Office 服務</strong></p>
<p>Both Windows 10 and Microsoft 365 Apps for enterprise continually add new capabilities to keep bringing user experiences and security forward with the latest innovations. Learn how to stay current with semi-annual and monthly updates, how the new servicing model works and the tools and options you have.</p></td>
<td><a href="https://aka.ms/ddev7" target="_blank"><img src="../media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-20.png" alt="Step 7" height="130" width="231" /></a></td>
</thead>
</table>

>[!NOTE]
>Windows 和 Office 服務是我們建議的部署程序轉輪中第七個步驟，說明對功能的半年更新進行準備的規劃層面。 若要查看完整的桌面部署程序，請瀏覽[桌面部署中心](https://aka.ms/HowToShift)。
>

Windows 10 與 Microsoft 365 Apps 企業版都推出了新的服務選項、支援模型和更新時間表。 這些變更可簡化隨時保有最新功能的程序。 連同這些更新一起推出的是新的設定選項，其可實現符合您需求的服務方案。 讓我們了解如何準備迎接可在 Windows 10 和 Microsoft 365 Apps 企業版中提供新功能的半年通道更新，同時利用 Microsoft Endpoint Center Configuration Manager (最新分支) 內的新功能。

[協助客戶改用 Windows 10 和 Microsoft 365 Apps 企業版](https://www.microsoft.com/microsoft-365/blog/2018/09/06/helping-customers-shift-to-a-modern-desktop/)

## <a name="update-types"></a>更新類型

更新主要可分為兩種類別，分別是功能更新以及品質和安全性更新 (包含累積安全性、可靠性和錯誤修正)。 就頻率來說，Windows 和 Office 皆提供半年通道，會在每年的 3 月和 9 月分別提供新的功能，並且每個月會推出品質和安全性更新。 此外，針對 Office 365 應用程式，我們還會提供完整支援的目前通道選項，其中的更新會同時包含新功能和品質更新。

如果您已經習慣電腦作業系統與應用程式更新之間較長的週期，您可能會想了解：

  - 更新是否相容？

  - 我需要重新訓練使用者嗎？

  - 有哪些風險？

若要回答這些問題以及為何更頻繁地提供新功能，我們提供這種方法的一些優點

### <a name="feature-update-benefits"></a>功能更新的優點

First, we’ve moved away from the model of the past that would introduce huge waves of change around every three years to now incremental smaller changes with feature updates twice per year. Why? With technology trends moving so fast in addition to rapidly evolving security threats, this keeps experiences and protections current. Some of the security related updates for example can’t just be delivered by monthly security updates or antivirus signature files; they may be low-level changes platform, like virtualization-based security.

[Windows 即服務快速指南](https://docs.microsoft.com/windows/deployment/update/waas-quick-start)

[使用 Windows 10 安全性功能來降低威脅](https://docs.microsoft.com/windows/security/threat-protection/overview-of-threat-mitigations-in-windows-10%20%20)

### <a name="cumulative-update-model-benefits"></a>累計更新模型的優點

Second delivering quality and security updates as a cumulative update package corrects many of the issues of the past. It used to be that you might pick and choose sometimes from a dozen updates or more each month for both Windows and Office. As you can imagine, this creates a nearly impossible set of test matrices for support. Also, if you install a version of Windows or Office that is a year or more old, it might take hours or sometimes days to apply all updates delivered since that version was released.

With the cumulative model, you’re always one update away from being current and in doing so the number of monthly updates that you need to deploy is reduced. Each update builds upon updates from previous months and contains all of the fixes that you need to get current. Cumulative updates are especially helpful when PCs has been turned off for several months because they are in storage waiting to be reassigned to a different user.

### <a name="expanded-validation-of-updates"></a>擴充更新驗證

另一個優點是，在針對廣泛部署推出更新之前，我們會先透過 [Office](https://products.office.com/office-insider?tab=Windows-Desktop) 和 [Windows](https://insider.windows.com/) 的測試人員計畫發行組建，這可讓我們收集診斷資料和意見反應之後，再廣泛發行更新。 測試人員計畫現已對測試人員開放，因此您可事先了解更新。 在更新發行時，我們會從數百萬個設定之中收到診斷資料，因此當我們實際推出更新時，品質自然會更好

還有一件事，由於 Microsoft 365 Apps 企業版測試人員組建會反映每月通道更新，如果您使用 Office 的半年通道來提供 Windows 每年兩次的功能更新，您也可以使用半年企業通道 (預覽) 版本提早驗證這些組建。

### <a name="supporting-management-tools"></a>支援的管理工具

We've also thought through how to make the deployment of updates seamless to you. Configuration Manager (Current Branch) is updated frequently to support the roll-out of these updates to Windows and Office and any new capabilities.

[使用 Configuration Manager 來部署 Windows 10 更新](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-configuration-manager)

[使用 Configuration Manager 管理 Microsoft 365 Apps 企業版](https://docs.microsoft.com/mem/configmgr/sum/deploy-use/manage-office-365-proplus-updates)

## <a name="overview-of-windows-and-office-channels"></a>Windows 和 Office 通道的概觀

Windows 10 提供三個服務通道：

- [**Windows 測試人員計畫**](https://docs.microsoft.com/windows/deployment/update/waas-overview#windows-insider)，可供組織對下一次的功能更新所推出的功能進行測試並提供意見反應
- **半年通道**，每年兩次提供新的功能與功能更新版本
- **長期服務通道**，其設計僅供需要較長期服務選項的專門裝置使用

Microsoft 365 提供四個服務通道：

- [**Office 測試人員計畫**](https://products.office.com/office-insider)，可供組織對仍在開發的最新 Office 功能進行測試並提供意見反應
- **目前通道**，可在最新的 Office 功能可供使用時，立即提供給使用者。
- **半年企業通道**，每年只會提供兩次新功能
- **半年企業通道 (預覽)**，這是完整支援的 Office 組建，可讓試驗使用者和應用程式相容性測試者測試及驗證下一個半年企業通道

如需 Windows 和 Office 服務通道的詳細資訊，請檢閱下列文件：

- [Windows 即服務概觀](https://docs.microsoft.com/windows/deployment/update/waas-overview#servicing-channels)
- [Microsoft 365 應用程式更新通道概觀](https://docs.microsoft.com/DeployOffice/overview-update-channels#BKMK_SAC)

## <a name="phased-deployment-of-updates"></a>階段式更新部署

Now let’s shift gears to how you will roll out these updates. For any release, we recommend at least three deployment phases for IT – validation, piloting and broad production deployment. Once you’re up and running on Windows 10 and Microsoft 365 Apps for enterprise, you'll use monthly servicing to stay current with critical security and quality updates, then you’ll move to semi-annual servicing for new features.

### <a name="monthly-updating"></a>每月更新

The service model is designed so you can choose to limit the roll-out of new features to twice per year, and if needed you can even skip a semi-annual update and continue receiving quality and security updates. As mentioned, the cumulative nature of monthly updates means each will increase in size per month.

#### <a name="express-updates"></a>快速更新

Using a technology called "Express Updates" in Windows and Binary Delta Compression in Office, we can reduce the download size significantly. In both approaches, the update engines compare what’s on the PC and finds only the differentials needed to update what’s there.

[說明 Windows 10 品質更新和差異結尾更新](https://techcommunity.microsoft.com/t5/Windows-IT-Pro-Blog/Windows-10-quality-updates-explained-amp-the-end-of-delta/ba-p/214426)

商務用 Windows Update 及 Windows Server Update Services 已長期支援快速更新，但我們目前已將該支援擴展至 Microsoft Endpoint Configuration Manager (最新分支)，因此它也可以使用快速更新。

![](../media/step-7-windows-and-office-as-a-service-media/step-7-windows-and-office-as-a-service-media-3.png)

#### <a name="binary-delta-compression"></a>二進位差異壓縮

只有在您從最新版本的 Microsoft 365 Apps 企業版更新時，才會使用 Office 的二進位差異壓縮，因此要使用這個方法，您需要從先前的組建更新，且無法略過更新。

Windows and Office update channels can be managed via Configuration Manager using the standard approval and targeting process. Additionally, you can use policy settings in Office and Windows to enforce update channels used, as well as related settings.

### <a name="semi-annual-updates"></a>半年更新

以上為每月更新的考量事項，現在讓我們移至較大的半年更新。

如同「裝置和應用程式整備」中所說明，您可以使用部署程序轉輪步驟 1 中所設定的相同整備工具，開始進行這些較大更新的準備。

As for tooling, you can use policy settings with Windows Update for Business, software update management via Microsoft Endpoint Configuration Manager (Current Branch), Windows Server Update Services (WSUS), or update policies set by Microsoft Intune. If you are concerned about network bandwidth, see Step 2: Directory and Network Readiness, to learn about your options to reduce network traffic via Delivery Optimization and other peer to peer caching technologies.

![](../media/step-7-windows-and-office-as-a-service-media/step-7-windows-and-office-as-a-service-media-4.png)

[Windows 半年通道](https://docs.microsoft.com/windows/deployment/update/waas-overview#semi-annual-channel)

[Microsoft 365 Apps 企業版的半年企業通道](https://docs.microsoft.com/DeployOffice/overview-update-channels#BKMK_SAC)

#### <a name="upgrade-task-sequences"></a>升級工作順序

透過標準軟體更新管理常式安裝較大的功能更新是受支援的選項，但許多組織會選擇使用「升級工作順序」搭配 Microsoft Endpoint Configuration Manager (最新分支) 或 Microsoft Deployment Toolkit。

「工作順序」可讓您在安裝功能更新之前建立自訂檢查或工作，並可讓您在更新安裝自行完成後執行自訂工作，更新後的工作可能包括在更新期間視需要暫時暫停服務、驅動程式安裝和取代、應用程式升級或工作列與 Windows 10 [開始] 個人化設定。

![](../media/step-7-windows-and-office-as-a-service-media/step-7-windows-and-office-as-a-service-media-5.png)

If you’re already using task sequences to migrate your Windows 7 machines to Windows 10 and are well-versed with those tools, this is a great place to start and provides ultimate control. While you can use a single task sequence for the entire upgrade, it is quite common that organizations use two task sequences. One task sequence for making sure the machines are ready for the upgrade, that silently pre-stages all the required setup files on target computers, and one to do the actual upgrade. This approach ensures that your user productivity is less impacted.

[建立工作順序以在 Configuration Manager 中升級作業系統](https://docs.microsoft.com/mem/configmgr/osd/deploy-use/create-a-task-sequence-to-upgrade-an-operating-system)

#### <a name="semi-annual-channel-support-for-feature-updates"></a>功能更新的半年通道支援

[如 2018 年 9 月所宣布](https://www.microsoft.com/microsoft-365/blog/2018/09/06/helping-customers-shift-to-a-modern-desktop/)，半年通道更新的支援時間表將會使用下列模型。

  - 所有目前支援的 Windows 10 企業版和教育版功能更新，從版本 1607 開始，將會從原始發行日期起受到 30 個月的支援。

  - 指定目標為 9 月的所有未來功能更新，從版本 1809 開始，將會從發行日期起受到 30 個月的支援。

  - 指定目標為 3 月的未來功能更新，從版本 1903 開始，將會從發行日期起繼續受支援 18 個月。

  - Microsoft 365 Apps 企業版的半年更新會繼續受支援 18 個月

#### <a name="additional-setup-automation-options-outside-of-task-sequences"></a>工作順序以外的其他設定自動化選項

如果您未使用「升級工作順序」，您現在可以執行自訂動作，或在套用升級之前，在預先安裝階段 (在設定執行相容性檢查之前，或在預先認可階段) 的功能更新期間套用驅動程式檔案。

[Windows 10 設定 (版本 1803) 中的新增功能](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1803%23windows-setup)

## <a name="next-step"></a>下一步 

## <a name="step-8-user-communications-and-training"></a>[步驟 8：使用者的通訊和訓練](https://aka.ms/mdd8)

## <a name="previous-step"></a>上一步 

## <a name="step-6-os-deployment-and-feature-updates"></a>[步驟 6：作業系統部署與功能更新](https://aka.ms/mdd6)
