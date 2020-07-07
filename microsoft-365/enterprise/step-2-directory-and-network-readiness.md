---
title: 步驟 2 - 目錄和網路整備
f1.keywords:
- NOCSH
ms.author: jogruszc
author: JGruszczyk
manager: jemed
ms.date: 05/10/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: 了解如何在環境中評估目錄和網路整備。
ms.openlocfilehash: 78087b7e0c1cb7031954d3a9ac4188b59879db20
ms.sourcegitcommit: 584e2e9db8c541fe32624acdca5e12ee327fdb63
ms.contentlocale: zh-TW
ms.lasthandoff: 06/10/2020
ms.locfileid: "44679011"
---
# <a name="step-2-directory-and-network-readiness"></a>步驟 2：目錄和網路整備

Ensure your directory and the network are configured and ready to support to your shift to Windows 10 and Microsoft 365 Apps for enterprise. This will require Azure Active Directory Services to be in place for users, and your network must have the capacity to handle both its regular traffic and the movement of potentially vast amounts of data as PCs are upgraded, and users’ files, settings and applications are restored.

![](../media/step-2-directory-and-network-readiness-media/step-2-directory-and-network-readiness-media-1.png)

<table>
<thead>
<td><img src="../media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-5.png" alt="Step 2" height="144" width="144" /></td>
<td><p><strong>步驟 2：目錄和網路整備</strong></p>
<p>Cloud connected services in Microsoft 365 Apps for enterprise and new deployment options like Windows Autopilot require Azure Active Directory. Your network and connectivity are also important areas to plan when moving Windows images, apps, drivers and related files to your PCs. Learn how new tools and deployment options reduce and streamline network traffic.</p></td>
<td><a href="https://aka.ms/ddev2" target="_blank"><img src="../media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-15.png" alt="Step 2" height="130" width="231" /></a></td>
</thead>
</table>

>[!NOTE]
>目錄和網路整備是我們所建議部署程序轉輪中的第二個步驟，主要著重於 Azure Active Directory 及網路最佳化。 若要查看完整的桌面部署程序，請瀏覽[桌面部署中心](https://aka.ms/HowToShift)。
>

Directory and Network readiness is fundamental to ensuring a smooth OS and desktop deployment. As with any automated deployment, it is important to ensure your file shares can be reached, and your network will need to be able to support the transfer of very large files, possibly to hundreds or even thousands of PCs at a time.

With your shift to Windows 10 and Microsoft 365 Apps for enterprise you also now need to make sure that cloud-based identity is set up with Azure Active Directory. This is key not only to activating Microsoft 365 Apps for enterprise, it also allows you to take advantage of modern provisioning solutions like Windows Autopilot.

在本文中，我們將探索工具和選項，為您準備目錄服務，及使用者與裝置權限，準備好部署 Windows 10 及 Microsoft 365 Apps 企業版。

## <a name="adding-azure-active-directory"></a>新增 Azure Active Directory

如果貴組織已使用 Office 365、Exchange Online、Microsoft Intune 或其他 Microsoft 線上服務，好消息是，您已經在使用 Azure Active Directory。 如果是，您只需要確認您目標桌面部署的使用者是在 Azure Active Directory 中，並已指派授權。

如果您目前未使用 Azure Active Directory，則有[許多資源](https://docs.microsoft.com/azure/active-directory/)可協助您進行設定。 您也可能符合透過 Microsoft FastTrack 提供的個人化協助資格 (授權的一部分)。 您可以在[這裡](https://fasttrack.microsoft.com)進一步了解 Microsoft FastTrack。

一旦 Azure Active Directory 就位後，您的使用者可以登入並啟用其 Microsoft 365 Apps 企業版應用程式，且您可以使用 Microsoft Intune 或 Windows Autopilot 部署，以自動化部署應用程式和原則。

## <a name="network-readiness"></a>網路整備

規劃部署時，您必須考慮頻寬需求。 部署中有三個主要元件會影響您的網路 – 電腦映像處理、軟體更新及使用者個人化。 這可能表示每部電腦在初始移轉時超過 20 GB，而每部電腦每個月通常需要 1 GB (含) 以上來保持最新狀態。

首先，瀏覽這三個主要元件的需求：

### <a name="pc-imaging"></a>電腦影像

對於沒有自訂的 Windows 映像，您通常應該規劃每部電腦 3 GB，而對於具有應用程式的自訂映像，您可能需要允許 6 GB 或更多。 您可能也需要考慮驅動程式套件，這些套件可能為每部電腦數百個 MB (有時高達 1 GB)。

### <a name="software-updates"></a>軟體更新

您必須規劃軟體更新的網路頻寬。 Windows 10 和 Microsoft 365 Apps 企業版應用程式會使用每月和每半年提供更新的新服務模型。 如果是初次使用這個模式，您可以在[這裡](https://docs.microsoft.com/windows/deployment/update/waas-overview)深入了解其運作方式。

The new servicing model includes Feature Updates for Windows twice a year, Office Semi-Annual Enterprise Channel Updates, and monthly Quality Updates. Feature Updates are typically 2 – 4GB in size, and Office Semi-Annual Enterprise Channel updates are 300 – 400 MB per update. Then there are the monthly Quality Updates. These may range from a few hundred megabytes to over a gigabyte. This is because monthly updates are cumulative, so these increase in size over the servicing lifetime for each Windows 10 version. That said, there are tools that can help reduce the amount of data that must pass over the network to implement updates. We will cover this in more detail below.

### <a name="user-personalization"></a>使用者個人化

The third component to consider is user personalization. Here you need to plan network bandwidth to accommodate the restoring of user files, their settings, and their applications as part of the PC refresh or replacement process. Together, these items often exceed 20 GB per PC; for some users these may exceed 100 GB.

## <a name="limiting-bandwidth"></a>限制頻寬

One way to limit the impact of deployment-related traffic on the network is to throttle it using the BITS (Background Intelligent Transfer Service) setting on clients. BITS uses an Adaptive Bit Rate (ABR) to adjust bandwidth available for deployment purposes; it can be configured on clients using Group Policy.

[關於 BITS](https://docs.microsoft.com/windows/desktop/bits/about-bits) (英文)

如果您使用 Microsoft Endpoint Configuration Manager (最新分支)，也可以設定啟用 BITS 的發佈點，或啟用搭配 WDS 的多點傳送。

Throttling specific traffic means that normal network traffic is less impacted by PCs downloading updates and applications. But carving out a certain percentage of bandwidth for these tasks helps ensure productivity isn’t impacted by Windows or Office deployment and processes continue to run as needed, it can worsen deployment-related downtime, with users locked out of their PCs while a deployment runs.

幸好，有些新工具可讓您更輕鬆地管理大規模電腦部署的網路影響，包括 LEDBAT 最佳化頻寬使用，以及將部署網路流量從網路中央移開並移出到周邊網路的對等 (P2P) 選項

![](../media/step-2-directory-and-network-readiness-media/step-2-directory-and-network-readiness-media-3.png)

## <a name="scavenging-bandwidth"></a>清除頻寬

Windows Server 2019 與 Microsoft Endpoint Configuration Manager (最新分支) 支援的低額外延遲背景傳輸 (LEDBAT) 是針對最佳化 Windows 用戶端的網路流量所設計。

[Windows Server 2019 的前 10 大網路功能：\#9 LEDBAT – 延遲最佳化背景傳輸](https://blogs.technet.microsoft.com/networking/2018/07/25/ledbat/) (英文)

Unlike traditional throttling, LEDBAT can use all available network bandwidth as a background task, instantly yielding bandwidth when other traffic requests it. Unlike BITS there is no delay; everything is automated – no manual tuning or scheduling required, and everything is setup server side. This affords potentially massive performance gains.

![](../media/step-2-directory-and-network-readiness-media/step-2-directory-and-network-readiness-media-4.png)

## <a name="peer-to-peer-options"></a>對等選項

Peer-to-Peer options are increasingly being used in Windows 10 migrations, for PC imaging, software updates and user personalization. They are also valuable in facilitating build-to-build upgrades after your initial Windows 10 deployment. Here we will cover several examples to help move Windows 10 and Office-related traffic away from the center of the network, reducing the need for classic throttling approaches, and allowing PCs to find the update files they need on peers in their local network rather than downloading them from a distribution point or the internet.

**BranchCache** can help you download content in distributed environments without saturating the network. It comes in two options: Hosted Cache Mode, which lets you use local servers to cache content, and Distributed Cache Mode (a mode supported in Configuration Manager), which lets clients share already downloaded content with each other.

Configuration Manager 支援的**對等快取**用戶端也可利用對等快取。 這允許可在網路上可靠使用的電腦裝載內容散發的來源。 您不想對您所有的電腦啟用此功能 – 只鎖定以具有可靠網路連線的裝置 (例如桌上型、迷你機箱或直立式電腦) 作為主機。 對等快取甚至適用於在設定期間於 Windows PE 階段中執行的部署工作。

附註：BranchCache 和對等快取互補，而且可以在同一個環境中共同作業。

[BranchCache 與對等快取](https://blogs.technet.microsoft.com/swisspfe/2018/01/25/branch-cache-vs-peer-cache/) (英文)

**傳遞最佳化** 傳遞最佳化是另一種對等式快取技術，可為部署提供網路型控制項。 Windows 10 傳遞最佳化可更新內建 UWP 應用程式時，也可安裝來自 Microsoft Store 的應用程式，以及使用 Express Updates 進行軟體更新。 早期的 Windows 10 版本中已提供此功能，不過最近才與 Microsoft Endpoint Configuration Manager (最新分支) 整合。 從 Windows 10 版本 1803 起，新的設定選項讓您現在可以針對背景更新和前景作業 (例如從 Store 安裝應用程式) 獨立設定頻寬限制。 Windows 傳遞最佳化目前也在用戶端更新期間支援 Microsoft 365 Apps 企業版，您可在所有支援的用戶端更新管道取得。 我們即將在用戶端初始安裝期間支援 Windows 傳遞最佳化，敬請期待。  

![](../media/step-2-directory-and-network-readiness-media/step-2-directory-and-network-readiness-media-5.png)

**Microsoft 365 Apps 企業版的其他考量**

除了運用傳遞最佳化，以下三個項目會因 Microsoft 365 Apps 企業版部署而有助於減少網路負載。

**Binary Delta Compression** Microsoft 365 Apps for enterprise uses Binary Delta Compression to reduce bandwidth consumed by software updates when updating from the most recent release of Microsoft 365 Apps for enterprise to the next release. By only pulling the binary level changes from the previous release, the impact from month-over-month growth of cumulative updates is minimized. This has the potential of saving several hundred megabytes of data, per PC, each month. In order to use this capability though, you cannot skip releases. If you do, then the full cumulative update must be downloaded.

[下載 Microsoft 365 應用程式的更新](https://docs.microsoft.com/deployoffice/overview-update-process-microsoft-365-apps#download-the-updates-for-microsoft-365-apps)

**Outlook 資料檔** Outlook 通常會設定為在本機快取使用者的整個信箱，以供離線使用。 在任何 Windows 部署中，除了就地升級以外，使用者的 Outlook 資料檔都需要在升級後自行重建。 這是自動化程序，但是 Outlook 信箱限制通常設為最多 100 GB，而在本機重新快取所有使用者的整個信箱表示有大量資料轉送。 若要減少網路負載，您可考慮使用群組原則來降低「要離線保留的郵件」設定。 在 Microsoft 365 Apps 企業版或 Office 2016 中，Outlook 的預設值會設為 12 個月。 若要降低網路影響，請考慮將離線快取設定為最近 1 到 6 個月。 變更此設定並不會影響線上信箱的大小，仍可透過 Outlook 在線上搜尋整個信箱。

![](../media/step-2-directory-and-network-readiness-media/step-2-directory-and-network-readiness-media-6.png)

**隨選 OneDrive 檔案和已知資料夾移動** OneDrive 是在雲端中同步處理和保護電腦和其他裝置中使用者檔案的絕佳方式。 您可以利用「已知資料夾移動」，強制從使用者的 [桌面]、[文件] 和 [圖片] 資料夾進行檔案同步至 OneDrive，以便在登入新的裝置或重新安裝映像的電腦時取得這些檔案。 不過，由於保留在 [桌面]、[文件] 和 [圖片] 位置的檔案大小和數目，您會打算推出在您的電腦上啟用和強制執行 OneDrive 的原則。 其中一個選項是使用群組原則網路控制項來節流 OneDrive 同步服務所用的頻寬。

![](../media/step-2-directory-and-network-readiness-media/step-2-directory-and-network-readiness-media-7.png)

[設定已知的資料夾移動](https://techcommunity.microsoft.com/t5/Microsoft-OneDrive-Blog/Migrate-Your-Files-to-OneDrive-Easily-with-Known-Folder-Move/ba-p/207076) (英文)

[隨需 OneDrive 檔案](https://www.microsoft.com/microsoft-365/blog/2017/05/11/introducing-onedrive-files-on-demand-and-additional-features-making-it-easier-to-access-and-share-files/) (英文)

如果您還沒推行 OneDrive，從 Windows 7 轉移到 Windows 10 是啟用 OneDrive 且緊密整合 Microsoft 365 Apps 企業版的完美機會。 請考慮在進行您的應用程式和裝置整備工作時，開始這項推行。 在您開始透過網路移動 Windows 映像及部署應用程式之前，這會為檔案同步提供領先優勢。

## <a name="next-step"></a>下一步 

## <a name="step-3-office-and-lob-app-delivery"></a>[步驟 3：Office 和 LOB 應用程式傳遞](https://aka.ms/mdd3)

## <a name="previous-step"></a>上一步：

## <a name="step-1-device-and-app-readiness"></a>[步驟 1：裝置和應用程式整備](https://aka.ms/mdd1)

## <a name="feedback"></a>意見反應

We'd love to hear your thoughts. Choose the type you'd like to provide:

產品的意見反應登入以提供文件意見反應

Our new feedback system is built on GitHub Issues. Read about this change in our blog post.
