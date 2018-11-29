---
title: 步驟 1 - 裝置和應用程式整備
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
description: 了解如何在環境中評估裝置和應用程式整備。
ms.openlocfilehash: a9fa85ea37de06399aa2264b09c61e588edc2107
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/28/2018
ms.locfileid: "26866767"
---
# <a name="step-1-device-and-app-readiness"></a>步驟 1：裝置和應用程式整備

從清查您的裝置和應用程式開始您的桌面部署專案，設定前進的優先順序，測試優先的應用程式和裝置，然後針對需要進行修復以準備部署。

![](media/step-1-device-and-app-readiness-media/step-1-device-and-app-readiness-media-1.png)

<table>
<thead>
<td><img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-3.png" alt="Step 1" height="130" width="130" /></td>
<td><p><strong>步驟 1：裝置和應用程式整備</strong></p>
<p>從清查您的裝置和應用程式開始您的桌面部署專案，設定前進的優先順序，測試優先的應用程式和裝置，然後針對需要進行修復以準備部署。</p></td>
<td><a href="https://aka.ms/ddev1" target="_blank"><img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-14.png" alt="Step 1" height="120" width="213" /></a></td>
</thead>
</table>

>[!NOTE]
>裝置和應用程式整備是我們所建議部署程序轉輪中的第一個步驟，方法是涵蓋應用程式與硬體相容性的整體層面。若要查看完整的桌面部署程序，請瀏覽[現代化電腦的部署中心](https://aka.ms/HowToShift) (英文)。
>

在過去，升級使用者桌面的主要障礙是應用程式和硬體相容性。在您規劃要移轉至 Windows 10 和 Office 365 專業增強版方面有一個好消息，就是近 10 年內撰寫的任何應用程式都能在 Windows 10 上執行，貴組織在回溯到 Office 2010 的 Office 版本上所使用的任何 COM 增益集和 VBA 巨集，都能持續在最新版本的 Office 上運作，不需要修改。

也就是說，根據貴組織的大小和年份，確認應用程式和硬體的相容性很可能還是建議的 8 階段部署程序中的基本初始步驟。

我們會在本文中引導您進行第一個階段 – 裝置和應用程式整備 – 使用新的 Windows Analytics Upgrade Readiness 工具，這是一個可透過您的 Windows 授權使用的智慧型雲端式解決方案。

如果您目前尚未針對環境設定 Windows Analytics，或是想要註冊試用，請移至 [Windows Analytics 頁面](http://www.aka.ms/windowsanalytics)並開始使用。

## <a name="recommended-tool-windows-analytics-upgrade-readiness"></a>建議的工具：Windows Analytics Upgrade Readiness

Windows Analytics Upgrade Readiness 提供許多優於傳統桌面管理系統的優點，是我們極力推薦的工具。它沒有代理程式，而是會引導您進行需要執行的作業，並且它會利用透過升級數百萬部取用者電腦所收集而來的應用程式和驅動程式相容性資訊，給予您詳細的評估，識別可能會阻止您升級的相容性問題，且提供具有 Microsoft 已知建議修正的連結。

若要設定 Window Analytics Upgrade Readiness，首先您需要設定 Azure 訂用帳戶並且將 Azure Log Analytics 工作區納入其中。一旦您讓 Windows Analytics Upgrade Readiness 服務執行，就可以透過「群組原則」設定來註冊任何網際網路連線 Windows 7 SP1 或更新的裝置。就是這麼簡單。不需要部署任何代理程式，Windows Analytics Upgrade Readiness 的視覺化工作流程會從試驗到生產環境部署引導您。如果您想要的話，可以從 Windows Analytics Upgrade Readiness 將資料匯出至軟體部署工具 (例如 System Center Configuration Manager)，直接將電腦設為目標，並且在它們準備好進行部署時建置集合。

## <a name="device-and-app-readiness-process"></a>裝置和應用程式整備程序

裝置和應用程式整備有四個步驟：1. 清查，2. 設定優先順序，3. 測試，4. 修復。讓我們依序看看每個步驟。

### <a name="1-inventory"></a>1\. 清查

Windows Analytics Upgrade Readiness 服務會使用無代理程式的程序，來清查整個桌面的電腦、應用程式和 Office 增益集。

![](media/step-1-device-and-app-readiness-media/step-1-device-and-app-readiness-media-3.png)

它也會提供經常造訪網際網路網站、應用程式和內部網路位置，以協助您稍後進行相容性測試。

![](media/step-1-device-and-app-readiness-media/step-1-device-and-app-readiness-media-4.png)

### <a name="2-prioritize"></a>2\. 設定優先順序

清查之後，Windows Analytics Upgrade Readiness 會協助您識別貴組織中最常使用的應用程式和硬體並設定優先順序，以及盡可能解除鎖定多部電腦以進行部署時要注意哪些地方，

![](media/step-1-device-and-app-readiness-media/step-1-device-and-app-readiness-media-5.png)

同時提供指引，協助您評估在下一個步驟「測試」期間解決問題時所需的更新。

### <a name="3-testing"></a>3\. 測試

您會發現大部分已清查的應用程式、驅動程式和增益集都以現狀運作。針對 Windows Analytics Upgrade Readiness 評估為有問題的項目，它為您提供已知資訊，包括在哪裡尋找版本更新來解決相容性問題。並非將時間和資源都耗費在解決非關鍵、鬆散部署應用程式和舊版裝置中的複雜問題，您可以選擇與使用者合作來淘汰及取代這些項目。

您也可以使用 Windows Analytics Upgrade Readiness 來評估瀏覽器型相容性問題，識別使用者存取的網站和 Web 應用程式中，仍然使用 ActiveX 控制項、瀏覽器協助程式物件、VBScript 或 Microsoft Edge 瀏覽器已不再支援的舊版技術的項目。您的使用者針對這些網站仍然需要使用 Internet Explorer 11，而您可以使用 Enterprise Mode Site List Manager，將它們新增至[企業模式網站清單](https://docs.microsoft.com/zh-TW/microsoft-edge/deploy/emie-to-improve-compatibility) (機器翻譯)。

此外，為了協助您移至 Office 365 專業增強版，您可能想要使用[適用於 Office 的整備工具組](https://docs.microsoft.com/zh-TW/deployoffice/use-the-readiness-toolkit-to-assess-application-compatibility-for-office-365-pro)，測試您的增益集與 Microsoft Visual Basic for Applications (VBA) 巨集的相容性。

![](media/step-1-device-and-app-readiness-media/step-1-device-and-app-readiness-media-6.png)

### <a name="4-remediation"></a>4\. 修復

裝置和應用程式整備的最後一個階段是「修復」。您在這裡想要收集必要的軟體或驅動程式套件，您要在部署程序中，使用這些項目來取代或更新舊版。

![](media/step-1-device-and-app-readiness-media/step-1-device-and-app-readiness-media-7.png)

執行問題修復清單時，您會發現越來越多電腦變成「準備好進行部署」。這表示驅動程式和電腦上的應用程式都已記錄為與您目標部署的 Windows 10 版本相容。

## <a name="continued-use-of-telemetry-tools"></a>繼續使用遙測工具

Windows Analytics Upgrade Readiness 不只是協助您移轉至 Windows 10 和 Office 365 專業增強版的工具。一旦您讓桌面在 Windows 10 和 Office 365 上執行，就可以使用它來協助維護部署及管理半年功能更新，讓您保持在最新版本。

## <a name="next-step"></a>下一步 

## <a name="step-2-directory-and-network-readinesshttpsakamsmdd2"></a>[步驟 2：目錄和網路整備](https://aka.ms/mdd2)