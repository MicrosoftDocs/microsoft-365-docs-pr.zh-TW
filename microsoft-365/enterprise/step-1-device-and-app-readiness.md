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
# <a name="step-1-device-and-app-readiness"></a><span data-ttu-id="49646-103">步驟 1：裝置和應用程式整備</span><span class="sxs-lookup"><span data-stu-id="49646-103">Step 1: Device and App Readiness</span></span>

<span data-ttu-id="49646-104">從清查您的裝置和應用程式開始您的桌面部署專案，設定前進的優先順序，測試優先的應用程式和裝置，然後針對需要進行修復以準備部署。</span><span class="sxs-lookup"><span data-stu-id="49646-104">Begin your desktop deployment project with an inventory of your devices and apps, prioritize what you to move forward, test prioritized apps and devices, then remediate what’s needed to get ready for deployment.</span></span>

![](media/step-1-device-and-app-readiness-media/step-1-device-and-app-readiness-media-1.png)

<table>
<thead>
<td><img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-3.png" alt="Step 1" height="130" width="130" /></td>
<td><p><span data-ttu-id="49646-105"><strong>步驟 1：裝置和應用程式整備</strong></span><span class="sxs-lookup"><span data-stu-id="49646-105"><strong>Step 1: Device and App Readiness</strong></span></span></p>
<p><span data-ttu-id="49646-106">從清查您的裝置和應用程式開始您的桌面部署專案，設定前進的優先順序，測試優先的應用程式和裝置，然後針對需要進行修復以準備部署。</span><span class="sxs-lookup"><span data-stu-id="49646-106">Begin your desktop deployment project with an inventory of your devices and apps, prioritize what you to move forward, test prioritized apps and devices, then remediate what’s needed to get ready for deployment.</span></span></p></td>
<td><a href="https://aka.ms/ddev1" target="_blank"><img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-14.png" alt="Step 1" height="120" width="213" /></a></td>
</thead>
</table>

>[!NOTE]
><span data-ttu-id="49646-p101">裝置和應用程式整備是我們所建議部署程序轉輪中的第一個步驟，方法是涵蓋應用程式與硬體相容性的整體層面。若要查看完整的桌面部署程序，請瀏覽[現代化電腦的部署中心](https://aka.ms/HowToShift) (英文)。</span><span class="sxs-lookup"><span data-stu-id="49646-p101">Device and App Readiness is the first step in our recommended deployment process wheel by covering the holistic aspects of application and hardware compatibility. To see the full desktop deployment process, visit the [Modern Desktop Deployment Center](https://aka.ms/HowToShift).</span></span>
>

<span data-ttu-id="49646-p102">在過去，升級使用者桌面的主要障礙是應用程式和硬體相容性。在您規劃要移轉至 Windows 10 和 Office 365 專業增強版方面有一個好消息，就是近 10 年內撰寫的任何應用程式都能在 Windows 10 上執行，貴組織在回溯到 Office 2010 的 Office 版本上所使用的任何 COM 增益集和 VBA 巨集，都能持續在最新版本的 Office 上運作，不需要修改。</span><span class="sxs-lookup"><span data-stu-id="49646-p102">In the past, a major hurdle to upgrading the users’ desktops is application and hardware compatibility. The good news as you plan your shift to Windows 10 and Office 365 ProPlus, is just about any application written in the last 10 years will run on Windows 10, and any COM add-ins and VBA macros your organization used on versions of Office dating back to Office 2010, will continue to work on the latest versions of Office, without modification.</span></span>

<span data-ttu-id="49646-111">也就是說，根據貴組織的大小和年份，確認應用程式和硬體的相容性很可能還是建議的 8 階段部署程序中的基本初始步驟。</span><span class="sxs-lookup"><span data-stu-id="49646-111">That said, depending on the size and age of your organization, verifying application and hardware compatibility is likely still an essential initial step in our recommended 8-phase deployment process.</span></span>

<span data-ttu-id="49646-112">我們會在本文中引導您進行第一個階段 – 裝置和應用程式整備 – 使用新的 Windows Analytics Upgrade Readiness 工具，這是一個可透過您的 Windows 授權使用的智慧型雲端式解決方案。</span><span class="sxs-lookup"><span data-stu-id="49646-112">In this article we take you through that first phase – Device and App Readiness – using the new Windows Analytics Upgrade Readiness tool, an intelligent cloud-based solution available with your Windows license.</span></span>

<span data-ttu-id="49646-113">如果您目前尚未針對環境設定 Windows Analytics，或是想要註冊試用，請移至 [Windows Analytics 頁面](http://www.aka.ms/windowsanalytics)並開始使用。</span><span class="sxs-lookup"><span data-stu-id="49646-113">If you don’t currently have Windows Analytics set up for your environment or would like to sign up for a trial, go the [Windows Analytics page](http://www.aka.ms/windowsanalytics) and get started.</span></span>

## <a name="recommended-tool-windows-analytics-upgrade-readiness"></a><span data-ttu-id="49646-114">建議的工具：Windows Analytics Upgrade Readiness</span><span class="sxs-lookup"><span data-stu-id="49646-114">Recommended Tool: Windows Analytics Upgrade Readiness</span></span>

<span data-ttu-id="49646-p103">Windows Analytics Upgrade Readiness 提供許多優於傳統桌面管理系統的優點，是我們極力推薦的工具。它沒有代理程式，而是會引導您進行需要執行的作業，並且它會利用透過升級數百萬部取用者電腦所收集而來的應用程式和驅動程式相容性資訊，給予您詳細的評估，識別可能會阻止您升級的相容性問題，且提供具有 Microsoft 已知建議修正的連結。</span><span class="sxs-lookup"><span data-stu-id="49646-p103">Windows Analytics Upgrade Readiness offers many advantages over traditional desktop management systems and is our recommended tool. It is agentless; it guides you through what needs to be done; and, it makes use of application and driver compatibility information gathered through the upgrade of hundreds of millions of consumer PCs, to give you a detailed assessment, identifying compatibility issues that might block your upgrade, with links to suggested fixes known to Microsoft.</span></span>

<span data-ttu-id="49646-p104">若要設定 Window Analytics Upgrade Readiness，首先您需要設定 Azure 訂用帳戶並且將 Azure Log Analytics 工作區納入其中。一旦您讓 Windows Analytics Upgrade Readiness 服務執行，就可以透過「群組原則」設定來註冊任何網際網路連線 Windows 7 SP1 或更新的裝置。就是這麼簡單。不需要部署任何代理程式，Windows Analytics Upgrade Readiness 的視覺化工作流程會從試驗到生產環境部署引導您。如果您想要的話，可以從 Windows Analytics Upgrade Readiness 將資料匯出至軟體部署工具 (例如 System Center Configuration Manager)，直接將電腦設為目標，並且在它們準備好進行部署時建置集合。</span><span class="sxs-lookup"><span data-stu-id="49646-p104">To set up Window Analytics Upgrade Readiness you’ll first need to set up an Azure subscription and include an Azure Log Analytics workspace to that. Once you have the Windows Analytics Upgrade Readiness service running, you can then enroll any Internet-connected Windows 7 SP1 or newer device via Group Policy settings. It’s that simple. There are no agents to deploy, and Windows Analytics Upgrade Readiness’s visual workflow guides you from pilot to production deployment. If you wish, you can export data from Windows Analytics Upgrade Readiness to software deployment tools such as System Center Configuration Manager, to target PCs directly and build collections as they become ready for deployment.</span></span>

## <a name="device-and-app-readiness-process"></a><span data-ttu-id="49646-122">裝置和應用程式整備程序</span><span class="sxs-lookup"><span data-stu-id="49646-122">Device and App Readiness Process</span></span>

<span data-ttu-id="49646-p105">裝置和應用程式整備有四個步驟：1. 清查，2. 設定優先順序，3. 測試，4. 修復。讓我們依序看看每個步驟。</span><span class="sxs-lookup"><span data-stu-id="49646-p105">Device and App Readiness compromises four steps: 1. Inventory, 2. Prioritize, 3. Test, 4. Remediate. Let’s look at each of these in turn.</span></span>

### <a name="1-inventory"></a><span data-ttu-id="49646-p106">1\. 清查</span><span class="sxs-lookup"><span data-stu-id="49646-p106">1\. Inventory</span></span>

<span data-ttu-id="49646-131">Windows Analytics Upgrade Readiness 服務會使用無代理程式的程序，來清查整個桌面的電腦、應用程式和 Office 增益集。</span><span class="sxs-lookup"><span data-stu-id="49646-131">Windows Analytics Upgrade Readiness service uses an agent-less process to inventory the computers, applications and Office add-ins across your desktop estate.</span></span>

![](media/step-1-device-and-app-readiness-media/step-1-device-and-app-readiness-media-3.png)

<span data-ttu-id="49646-132">它也會提供經常造訪網際網路網站、應用程式和內部網路位置，以協助您稍後進行相容性測試。</span><span class="sxs-lookup"><span data-stu-id="49646-132">It also provides reports on highly visited Internet sites, apps and Intranet locations to help you with compatibility testing later.</span></span>

![](media/step-1-device-and-app-readiness-media/step-1-device-and-app-readiness-media-4.png)

### <a name="2-prioritize"></a><span data-ttu-id="49646-p107">2\. 設定優先順序</span><span class="sxs-lookup"><span data-stu-id="49646-p107">2\. Prioritize</span></span>

<span data-ttu-id="49646-135">清查之後，Windows Analytics Upgrade Readiness 會協助您識別貴組織中最常使用的應用程式和硬體並設定優先順序，以及盡可能解除鎖定多部電腦以進行部署時要注意哪些地方，</span><span class="sxs-lookup"><span data-stu-id="49646-135">With inventory taken, Windows Analytics Upgrade Readiness helps you to identify and prioritize the most common apps and hardware used in your organization, and what to focus on to unblock as many PCs as possible for deployment,</span></span>

![](media/step-1-device-and-app-readiness-media/step-1-device-and-app-readiness-media-5.png)

<span data-ttu-id="49646-136">同時提供指引，協助您評估在下一個步驟「測試」期間解決問題時所需的更新。</span><span class="sxs-lookup"><span data-stu-id="49646-136">also providing guidance to help you assess the updates are necessary to resolve issues during the next step: testing.</span></span>

### <a name="3-testing"></a><span data-ttu-id="49646-p108">3\. 測試</span><span class="sxs-lookup"><span data-stu-id="49646-p108">3\. Testing</span></span>

<span data-ttu-id="49646-p109">您會發現大部分已清查的應用程式、驅動程式和增益集都以現狀運作。針對 Windows Analytics Upgrade Readiness 評估為有問題的項目，它為您提供已知資訊，包括在哪裡尋找版本更新來解決相容性問題。並非將時間和資源都耗費在解決非關鍵、鬆散部署應用程式和舊版裝置中的複雜問題，您可以選擇與使用者合作來淘汰及取代這些項目。</span><span class="sxs-lookup"><span data-stu-id="49646-p109">You will find that most of the applications, drivers, and add-ins inventoried, will work as-is. For items Windows Analytics Upgrade Readiness assesses to have issues, it provides you with known information, including where to find version updates to resolve compatibility problems. Rather than devoting time and resource resolving complex issues in non-critical, sparsely deployed applications and older devices, you may choose instead to work with users to retire and replace these items.</span></span>

<span data-ttu-id="49646-p110">您也可以使用 Windows Analytics Upgrade Readiness 來評估瀏覽器型相容性問題，識別使用者存取的網站和 Web 應用程式中，仍然使用 ActiveX 控制項、瀏覽器協助程式物件、VBScript 或 Microsoft Edge 瀏覽器已不再支援的舊版技術的項目。您的使用者針對這些網站仍然需要使用 Internet Explorer 11，而您可以使用 Enterprise Mode Site List Manager，將它們新增至[企業模式網站清單](https://docs.microsoft.com/zh-TW/microsoft-edge/deploy/emie-to-improve-compatibility) (機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="49646-p110">You can use Windows Analytics Upgrade Readiness to assess browser-based compatibility issues too, identifying websites and web apps accessed by users still using ActiveX controls, Browser Helper Objects, VBScript, or other legacy technology not supported by the Microsoft Edge browser. Your users will still need to use Internet Explorer 11 for these sites, and you can add them to the [Enterprise Mode site list](https://docs.microsoft.com/zh-TW/microsoft-edge/deploy/emie-to-improve-compatibility), using the Enterprise Mode Site List Manager.</span></span>

<span data-ttu-id="49646-144">此外，為了協助您移至 Office 365 專業增強版，您可能想要使用[適用於 Office 的整備工具組](https://docs.microsoft.com/zh-TW/deployoffice/use-the-readiness-toolkit-to-assess-application-compatibility-for-office-365-pro)，測試您的增益集與 Microsoft Visual Basic for Applications (VBA) 巨集的相容性。</span><span class="sxs-lookup"><span data-stu-id="49646-144">Additionally, to assist in your move to Office 365 ProPlus, you may wish to make use of the [Readiness Toolkit for Office](https://docs.microsoft.com/zh-TW/deployoffice/use-the-readiness-toolkit-to-assess-application-compatibility-for-office-365-pro) to test the compatibility of your add-ins and Microsoft Visual Basic for Applications (VBA) macros.</span></span>

![](media/step-1-device-and-app-readiness-media/step-1-device-and-app-readiness-media-6.png)

### <a name="4-remediation"></a><span data-ttu-id="49646-p111">4\. 修復</span><span class="sxs-lookup"><span data-stu-id="49646-p111">4\. Remediation</span></span>

<span data-ttu-id="49646-p112">裝置和應用程式整備的最後一個階段是「修復」。您在這裡想要收集必要的軟體或驅動程式套件，您要在部署程序中，使用這些項目來取代或更新舊版。</span><span class="sxs-lookup"><span data-stu-id="49646-p112">As the final phase of device and app readiness is to ‘remediate’. Here you’ll want to collect the required software or driver packages; you are going to use these to supersede or update older versions as part of the deployment process.</span></span>

![](media/step-1-device-and-app-readiness-media/step-1-device-and-app-readiness-media-7.png)

<span data-ttu-id="49646-p113">執行問題修復清單時，您會發現越來越多電腦變成「準備好進行部署」。這表示驅動程式和電腦上的應用程式都已記錄為與您目標部署的 Windows 10 版本相容。</span><span class="sxs-lookup"><span data-stu-id="49646-p113">As you work through the list remediating issues, you’ll see that more and more PCs become “Ready for Deployment”. This means that both the drivers and apps on the PCs are noted as compatible with the version of Windows 10 you are targeting for deployment.</span></span>

## <a name="continued-use-of-telemetry-tools"></a><span data-ttu-id="49646-151">繼續使用遙測工具</span><span class="sxs-lookup"><span data-stu-id="49646-151">Continued use of telemetry tools</span></span>

<span data-ttu-id="49646-p114">Windows Analytics Upgrade Readiness 不只是協助您移轉至 Windows 10 和 Office 365 專業增強版的工具。一旦您讓桌面在 Windows 10 和 Office 365 上執行，就可以使用它來協助維護部署及管理半年功能更新，讓您保持在最新版本。</span><span class="sxs-lookup"><span data-stu-id="49646-p114">Windows Analytics Upgrade Readiness isn’t just a tool to help you shift to Windows 10 and Office 365 ProPlus. Once you have desktops running on Windows 10 and Office 365 you can use it to help maintain your deployment and manage semi-annual Feature Updates so that you can stay current.</span></span>

## <a name="next-step"></a><span data-ttu-id="49646-154">下一步</span><span class="sxs-lookup"><span data-stu-id="49646-154">Next Step</span></span> 

## <a name="step-2-directory-and-network-readinesshttpsakamsmdd2"></a>[<span data-ttu-id="49646-155">步驟 2：目錄和網路整備</span><span class="sxs-lookup"><span data-stu-id="49646-155">Step 2: Directory and Network Readiness</span></span>](https://aka.ms/mdd2)