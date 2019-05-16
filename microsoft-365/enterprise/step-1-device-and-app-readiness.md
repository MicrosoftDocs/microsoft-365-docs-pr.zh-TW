---
title: 步驟 1 - 裝置和應用程式整備
ms.author: jogruszc
author: JGruszczyk
manager: jemed
ms.date: 09/14/2018
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: 了解如何在環境中評估裝置和應用程式整備。
ms.openlocfilehash: 2059904bf7c0f89876c2142d83212ce75542c505
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/15/2019
ms.locfileid: "34073153"
---
# <a name="step-1-device-and-app-readiness"></a><span data-ttu-id="8f86d-103">步驟 1：裝置和應用程式整備</span><span class="sxs-lookup"><span data-stu-id="8f86d-103">Step 1: Device and App Readiness</span></span>

![](media/step-1-device-and-app-readiness-media/step-1-device-and-app-readiness-media-1.png)

<table>
<thead>
<td><img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-3.png" alt="Step 1" height="130" width="130" /></td>
<td><p><span data-ttu-id="8f86d-104"><strong>步驟 1：裝置和應用程式整備</strong></span><span class="sxs-lookup"><span data-stu-id="8f86d-104"><strong>Step 1: Device and App Readiness</strong></span></span></p>
<p><span data-ttu-id="8f86d-105">從清查您的裝置和應用程式開始您的桌面部署專案，設定前進的優先順序，測試優先的應用程式和裝置，然後針對需要進行修復以準備部署。</span><span class="sxs-lookup"><span data-stu-id="8f86d-105">Begin your desktop deployment project with an inventory of your devices and apps, prioritize what you need to move forward, test prioritized apps and devices, then remediate what’s needed to get ready for deployment.</span></span></p></td>
<td><a href="https://aka.ms/ddev1" target="_blank"><img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-14.png" alt="Step 1" height="120" width="213" /></a></td>
</thead>
</table>

>[!NOTE]
><span data-ttu-id="8f86d-106">裝置和應用程式整備是我們所建議部署程序轉輪中的第一個步驟，方法是涵蓋應用程式與硬體相容性的整體層面。</span><span class="sxs-lookup"><span data-stu-id="8f86d-106">Device and App Readiness is the first step in our recommended deployment process wheel by covering the holistic aspects of application and hardware compatibility.</span></span> <span data-ttu-id="8f86d-107">若要查看完整的桌面部署程序，請瀏覽[桌面部署中心](https://aka.ms/HowToShift)。</span><span class="sxs-lookup"><span data-stu-id="8f86d-107">To see the full desktop deployment process, visit the [Desktop Deployment Center](https://aka.ms/HowToShift).</span></span>
>

<span data-ttu-id="8f86d-p102">在過去，升級使用者桌面的主要障礙是應用程式和硬體相容性。在您規劃要移轉至 Windows 10 和 Office 365 專業增強版方面有一個好消息，就是近 10 年內撰寫的任何應用程式都能在 Windows 10 上執行，貴組織在回溯到 Office 2010 的 Office 版本上所使用的任何 COM 增益集和 VBA 巨集，都能持續在最新版本的 Office 上運作，不需要修改。</span><span class="sxs-lookup"><span data-stu-id="8f86d-p102">In the past, a major hurdle to upgrading the users’ desktops is application and hardware compatibility. The good news as you plan your shift to Windows 10 and Office 365 ProPlus, is just about any application written in the last 10 years will run on Windows 10, and any COM add-ins and VBA macros your organization used on versions of Office dating back to Office 2010, will continue to work on the latest versions of Office, without modification.</span></span>

<span data-ttu-id="8f86d-110">也就是說，根據貴組織的大小和年份，確認應用程式和硬體的相容性很可能還是建議的 8 階段部署程序中的基本初始步驟。</span><span class="sxs-lookup"><span data-stu-id="8f86d-110">That said, depending on the size and age of your organization, verifying application and hardware compatibility is likely still an essential initial step in our recommended 8-phase deployment process.</span></span>

<span data-ttu-id="8f86d-111">我們會在本文中引導您進行第一個階段 – 裝置和應用程式整備 – 使用 Microsoft 整備評估工具 (包括新的 Windows Analytics 更新整備小幫手工具)，這是一個可透過您的 Windows 授權使用的智慧型雲端式解決方案。</span><span class="sxs-lookup"><span data-stu-id="8f86d-111">In this article we take you through that first phase – Device and App Readiness – using Microsoft readiness assessment tools including the new Windows Analytics Upgrade Readiness tool, an intelligent cloud-based solution available with your Windows license.</span></span>

## <a name="windows-10-compatibility-scan"></a><span data-ttu-id="8f86d-112">Windows 10 相容性掃描</span><span class="sxs-lookup"><span data-stu-id="8f86d-112">Windows 10 Compatibility Scan</span></span>

<span data-ttu-id="8f86d-113">部署 Windows 10 之前，Microsoft 建議您檢查執行 Windows 7 或 8/8.1 的現有裝置整備度。</span><span class="sxs-lookup"><span data-stu-id="8f86d-113">Before deploying Windows 10 Microsoft recommends checking the readiness of your existing devices running Windows 7 or 8/8.1.</span></span> <span data-ttu-id="8f86d-114">Windows 10 安裝媒體支援可供 setup.exe 執行升級的命令列參數，但只會檢查相容性，而不會實際執行升級。</span><span class="sxs-lookup"><span data-stu-id="8f86d-114">Windows 10 installation media supports a command line switch for the setup.exe to run the upgrade but only check for compatibility, not actually perform the upgrade.</span></span> <span data-ttu-id="8f86d-115">ScanOnly 可當作指令碼批次檔案執行或可整合至 System Center Configuration Manager 工作序列 (包括直接從網路執行 ScanOnly 的功能)，讓 Windows 10 安裝媒體不會向下串流至本機裝置。</span><span class="sxs-lookup"><span data-stu-id="8f86d-115">ScanOnly can be run as a scripted batch file or integrated into a System Center Configuration Manager task sequence, including the ability to run the ScanOnly directly from the network so the Windows 10 installation media isn't streamed down to the local device.</span></span> <span data-ttu-id="8f86d-116">ScanOnly 完成時，系統會經由 Setup.EXE 所產生記錄檔中的傳回碼來傳回結果。</span><span class="sxs-lookup"><span data-stu-id="8f86d-116">When ScanOnly completes the results are returned via return codes in log files generated by Setup.EXE.</span></span>   

<span data-ttu-id="8f86d-117">以無訊息方式完成相容性掃描的範例 ScanOnly 命令列，看起來如下所示：</span><span class="sxs-lookup"><span data-stu-id="8f86d-117">A sample ScanOnly command line that completes the compatibility scan silently would look like the below:</span></span>

    Setup.EXE /Auto Upgrade /Quiet /NoReboot /Compat ScanOnly

<span data-ttu-id="8f86d-118">如需 ScanOnly 和其他 Windows 安裝程式命令參數的詳細資訊，請檢閱 [Windows 安裝程式命令列選項](https://aka.ms/setupswitches)。</span><span class="sxs-lookup"><span data-stu-id="8f86d-118">For more information on ScanOnly and other Windows setup command switches please review the [Windows Setup Commmand-line Options](https://aka.ms/setupswitches).</span></span>

## <a name="recommended-tool-windows-analytics-upgrade-readiness"></a><span data-ttu-id="8f86d-119">建議的工具：Windows Analytics Upgrade Readiness</span><span class="sxs-lookup"><span data-stu-id="8f86d-119">Recommended Tool: Windows Analytics Upgrade Readiness</span></span>

<span data-ttu-id="8f86d-120">Windows Analytics 更新整備小幫手是我們建議使用的工具，其提供比傳統桌面管理系統還要多的優點。</span><span class="sxs-lookup"><span data-stu-id="8f86d-120">Windows Analytics Upgrade Readiness offers many advantages over traditional desktop management systems and is our recommended tool.</span></span> <span data-ttu-id="8f86d-121">這項工具無代理程式，可引導您使用透過升級數億台消費者電腦所蒐集的應用程式和驅動程式相容性資訊。</span><span class="sxs-lookup"><span data-stu-id="8f86d-121">It is agentless and guides you through what needs to be done making use of application and driver compatibility information gathered through the upgrade of hundreds of millions of consumer PCs.</span></span> <span data-ttu-id="8f86d-122">此資訊提供給您詳細的評估、找出可能封鎖升級的相容性問題，並輔以 Microsoft 已知建議修正程式的連結。</span><span class="sxs-lookup"><span data-stu-id="8f86d-122">This information gives you a detailed assessment, identifying compatibility issues that might block your upgrade, supported with links to suggested fixes known to Microsoft.</span></span>

<span data-ttu-id="8f86d-123">若要設定 Windows Analytics 更新整備小幫手，您必須先設定 Azure 訂用帳戶並包含其 Azure 記錄分析工作區。</span><span class="sxs-lookup"><span data-stu-id="8f86d-123">To set up Window Analytics Upgrade Readiness you’ll first need to set up an Azure subscription and include an Azure Log Analytics workspace to that.</span></span> <span data-ttu-id="8f86d-124">執行 Windows Analytics 更新整備小幫手服務後，您可以接著透過群組原則設定，註冊任何連上網際網路的 Windows 7 SP1 或更新裝置 - 就是這麼簡單。</span><span class="sxs-lookup"><span data-stu-id="8f86d-124">Once you have the Windows Analytics Upgrade Readiness service running, you can then enroll any Internet-connected Windows 7 SP1 or newer device via Group Policy settings - it’s that simple.</span></span> <span data-ttu-id="8f86d-125">沒有要部署的代理程式，而 Windows Analytics 更新整備小幫手的視覺化工作流程會引導您進行試驗以至生產部署。</span><span class="sxs-lookup"><span data-stu-id="8f86d-125">There are no agents to deploy, and Windows Analytics Upgrade Readiness’s visual workflow guides you from pilot to production deployment.</span></span> <span data-ttu-id="8f86d-126">如有需要，您可以將資料從 Windows Analytics 更新整備小幫手匯出至 System Center Configuration Manager 之類的軟體部署工具、直接匯出至目標電腦，並且在資料準備好進行部署時建立集合。</span><span class="sxs-lookup"><span data-stu-id="8f86d-126">If you wish, you can export data from Windows Analytics Upgrade Readiness to software deployment tools such as System Center Configuration Manager, to target PCs directly and build collections as they become ready for deployment.</span></span>

<span data-ttu-id="8f86d-127">如果您目前尚未針對環境設定 Windows Analytics，或是想要註冊試用，請移至 [Windows Analytics 頁面](http://www.aka.ms/windowsanalytics)並開始使用。</span><span class="sxs-lookup"><span data-stu-id="8f86d-127">If you don’t currently have Windows Analytics set up for your environment or would like to sign up for a trial, go the [Windows Analytics page](http://www.aka.ms/windowsanalytics) and get started.</span></span>

## <a name="device-and-app-readiness-process"></a><span data-ttu-id="8f86d-128">裝置和應用程式整備程序</span><span class="sxs-lookup"><span data-stu-id="8f86d-128">Device and App Readiness Process</span></span>

<span data-ttu-id="8f86d-129">裝置和應用程式整備包含四個步驟：1.</span><span class="sxs-lookup"><span data-stu-id="8f86d-129">Device and App Readiness is comprised of four steps: 1.</span></span> <span data-ttu-id="8f86d-130">清查，2.</span><span class="sxs-lookup"><span data-stu-id="8f86d-130">Inventory, 2.</span></span> <span data-ttu-id="8f86d-131">設定優先順序，3.</span><span class="sxs-lookup"><span data-stu-id="8f86d-131">Prioritize, 3.</span></span> <span data-ttu-id="8f86d-132">測試，4.</span><span class="sxs-lookup"><span data-stu-id="8f86d-132">Test, 4.</span></span> <span data-ttu-id="8f86d-133">修復。</span><span class="sxs-lookup"><span data-stu-id="8f86d-133">Remediate.</span></span> <span data-ttu-id="8f86d-134">讓我們依序查看每個步驟。</span><span class="sxs-lookup"><span data-stu-id="8f86d-134">Let’s look at each of these in turn.</span></span>

### <a name="1-inventory"></a><span data-ttu-id="8f86d-135">1\.</span><span class="sxs-lookup"><span data-stu-id="8f86d-135">1\.</span></span> <span data-ttu-id="8f86d-136">清查</span><span class="sxs-lookup"><span data-stu-id="8f86d-136">Inventory</span></span>

<span data-ttu-id="8f86d-137">Windows Analytics 更新整備小幫手服務會使用無代理程式的程序，來清查整個桌面的電腦、應用程式和 Office 增益集。</span><span class="sxs-lookup"><span data-stu-id="8f86d-137">Windows Analytics Upgrade Readiness service uses an agent-less process to inventory the computers, applications, and Office add-ins across your desktop estate.</span></span>

![](media/step-1-device-and-app-readiness-media/step-1-device-and-app-readiness-media-3.png)

<span data-ttu-id="8f86d-138">它也會提供經常造訪網際網路網站、應用程式和內部網路位置，以協助您稍後進行相容性測試。</span><span class="sxs-lookup"><span data-stu-id="8f86d-138">It also provides reports on highly visited Internet sites, apps, and Intranet locations to help you with compatibility testing later.</span></span>

![](media/step-1-device-and-app-readiness-media/step-1-device-and-app-readiness-media-4.png)

### <a name="2-prioritize"></a><span data-ttu-id="8f86d-139">2\.</span><span class="sxs-lookup"><span data-stu-id="8f86d-139">2\.</span></span> <span data-ttu-id="8f86d-140">設定優先順序</span><span class="sxs-lookup"><span data-stu-id="8f86d-140">Prioritize</span></span>

<span data-ttu-id="8f86d-141">清查之後，Windows Analytics 更新整備小幫手會協助您識別貴組織中最常使用的應用程式和硬體並設定優先順序，以及盡可能解除鎖定多部電腦以進行部署時要注意哪些地方，</span><span class="sxs-lookup"><span data-stu-id="8f86d-141">With inventory taken, Windows Analytics Upgrade Readiness helps you to identify and prioritize the most common apps and hardware used in your organization, as well as what to focus on to unblock as many PCs as possible for deployment.</span></span>

![](media/step-1-device-and-app-readiness-media/step-1-device-and-app-readiness-media-5.png)

<span data-ttu-id="8f86d-142">同時提供指引，協助您評估在下一個步驟「測試」期間解決問題時所需的更新。</span><span class="sxs-lookup"><span data-stu-id="8f86d-142">It also provides guidance to help you assess the updates necessary to resolve issues during the next step: testing.</span></span>

### <a name="3-testing"></a><span data-ttu-id="8f86d-143">3\.</span><span class="sxs-lookup"><span data-stu-id="8f86d-143">3\.</span></span> <span data-ttu-id="8f86d-144">測試</span><span class="sxs-lookup"><span data-stu-id="8f86d-144">Testing</span></span>

<span data-ttu-id="8f86d-145">您會發現大部分已清查的應用程式、驅動程式和增益集都以現狀運作。</span><span class="sxs-lookup"><span data-stu-id="8f86d-145">You will find that most of the applications, drivers, and add-ins inventoried will work as-is.</span></span> <span data-ttu-id="8f86d-146">針對 Windows Analytics 更新整備小幫手評估為有問題的項目，它為您提供已知資訊，包括在哪裡尋找版本更新來解決相容性問題。</span><span class="sxs-lookup"><span data-stu-id="8f86d-146">For items Windows Analytics Upgrade Readiness assesses to have issues, it provides you with known information including where to find version updates to resolve compatibility problems.</span></span> <span data-ttu-id="8f86d-147">並非將時間和資源都耗費在解決非關鍵、鬆散部署應用程式和舊版裝置中的複雜問題，您可以選擇與使用者合作來淘汰及取代這些項目。</span><span class="sxs-lookup"><span data-stu-id="8f86d-147">Rather than devoting time and resource resolving complex issues in non-critical, sparsely deployed applications and older devices, you may choose instead to work with users to retire and replace these items.</span></span>

<span data-ttu-id="8f86d-p111">您也可以使用 Windows Analytics Upgrade Readiness 來評估瀏覽器型相容性問題，識別使用者存取的網站和 Web 應用程式中，仍然使用 ActiveX 控制項、瀏覽器協助程式物件、VBScript 或 Microsoft Edge 瀏覽器已不再支援的舊版技術的項目。您的使用者針對這些網站仍然需要使用 Internet Explorer 11，而您可以使用 Enterprise Mode Site List Manager，將它們新增至[企業模式網站清單](https://docs.microsoft.com/zh-TW/microsoft-edge/deploy/emie-to-improve-compatibility) (機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="8f86d-p111">You can use Windows Analytics Upgrade Readiness to assess browser-based compatibility issues too, identifying websites and web apps accessed by users still using ActiveX controls, Browser Helper Objects, VBScript, or other legacy technology not supported by the Microsoft Edge browser. Your users will still need to use Internet Explorer 11 for these sites, and you can add them to the [Enterprise Mode site list](https://docs.microsoft.com/en-us/microsoft-edge/deploy/emie-to-improve-compatibility), using the Enterprise Mode Site List Manager.</span></span>

<span data-ttu-id="8f86d-150">此外，為了協助您移至 Office 365 專業增強版，您可能想要使用[適用於 Office 的整備工具組](https://docs.microsoft.com/zh-TW/deployoffice/use-the-readiness-toolkit-to-assess-application-compatibility-for-office-365-pro)，測試您的增益集與 Microsoft Visual Basic for Applications (VBA) 巨集的相容性。</span><span class="sxs-lookup"><span data-stu-id="8f86d-150">Additionally, to assist in your move to Office 365 ProPlus, you may wish to make use of the [Readiness Toolkit for Office](https://docs.microsoft.com/en-us/deployoffice/use-the-readiness-toolkit-to-assess-application-compatibility-for-office-365-pro) to test the compatibility of your add-ins and Microsoft Visual Basic for Applications (VBA) macros.</span></span>

![](media/step-1-device-and-app-readiness-media/step-1-device-and-app-readiness-media-6.png)

### <a name="4-remediation"></a><span data-ttu-id="8f86d-p112">4\. 修復</span><span class="sxs-lookup"><span data-stu-id="8f86d-p112">4\. Remediation</span></span>

<span data-ttu-id="8f86d-153">裝置和應用程式整備的最後一個階段是「修復」。</span><span class="sxs-lookup"><span data-stu-id="8f86d-153">The final phase of device and app readiness is to ‘remediate’.</span></span> <span data-ttu-id="8f86d-154">您在這裡想要收集必要的軟體或驅動程式套件，您要在部署程序中，使用這些項目來取代或更新舊版。</span><span class="sxs-lookup"><span data-stu-id="8f86d-154">Here you’ll want to collect the required software or driver packages; you are going to use these to supersede or update older versions as part of the deployment process.</span></span>

![](media/step-1-device-and-app-readiness-media/step-1-device-and-app-readiness-media-7.png)

<span data-ttu-id="8f86d-p114">執行問題修復清單時，您會發現越來越多電腦變成「準備好進行部署」。這表示驅動程式和電腦上的應用程式都已記錄為與您目標部署的 Windows 10 版本相容。</span><span class="sxs-lookup"><span data-stu-id="8f86d-p114">As you work through the list remediating issues, you’ll see that more and more PCs become “Ready for Deployment”. This means that both the drivers and apps on the PCs are noted as compatible with the version of Windows 10 you are targeting for deployment.</span></span>

### <a name="configuration-manager-software-inventory-for-application-prioritization"></a><span data-ttu-id="8f86d-157">適用於設定應用程式優先順序的 Configuration Manager 軟體清查</span><span class="sxs-lookup"><span data-stu-id="8f86d-157">Configuration Manager Software Inventory for Application Prioritization</span></span>

<span data-ttu-id="8f86d-158">使用雲端式分析解決方案進行裝置和應用程式整備時，Configuration Manager 軟體清查是替代方法。</span><span class="sxs-lookup"><span data-stu-id="8f86d-158">Configuration Manager software inventory is an alternative to using cloud-based analytics solutions for device and app readiness.</span></span> <span data-ttu-id="8f86d-159">您可以使用安裝計數並深入了解特定電腦，以協助設定相容性測試和驗證的優先順序，並透過套件將應用程式套件設定為與 Windows 10 相容。</span><span class="sxs-lookup"><span data-stu-id="8f86d-159">You can use installation counts and drill into specific computers to help prioritize compatibility testing and validation and set application packages as compatible with Windows 10 via package settings.</span></span> <span data-ttu-id="8f86d-160">雖然此選項並未提供比較已知相容性資訊與 Microsoft 分析服務的功能，但可成為有效的解決方法，其以一小組已排定優先順序的應用程式為目標進行手動測試。</span><span class="sxs-lookup"><span data-stu-id="8f86d-160">While this option does not offer the ability to compare known compatibility information with Microsoft’s analytics services, it can be an effective solution to target a smaller set of prioritized apps for manual testing.</span></span> 

<span data-ttu-id="8f86d-161">如需詳細資訊，請參閱 [System Center Configuration Manager 中的軟體清查簡介](https://docs.microsoft.com/zh-TW/sccm/core/clients/manage/inventory/introduction-to-software-inventory)，以及 [System Center Configuration Manager 中的套件和程式](https://docs.microsoft.com/zh-TW/sccm/apps/deploy-use/packages-and-programs)中應用程式套件的設定平台需求。</span><span class="sxs-lookup"><span data-stu-id="8f86d-161">For more information, see [Introduction to software inventory in System Center Configuration Manager](https://docs.microsoft.com/en-us/sccm/core/clients/manage/inventory/introduction-to-software-inventory) and setting platform requirements in application packages in [Packages and programs in System Center Configuration Manager](https://docs.microsoft.com/en-us/sccm/apps/deploy-use/packages-and-programs).</span></span>


## <a name="desktop-app-assure"></a><span data-ttu-id="8f86d-162">電腦 App 保證</span><span class="sxs-lookup"><span data-stu-id="8f86d-162">Desktop App Assure</span></span>

<span data-ttu-id="8f86d-163">協助達到 Windows 10 和 Office 365 專業增強版應用程式相容性的另一個工具是透過 FastTrack Center 提供的[電腦 App 保證](https://aka.ms/desktopappassure)程式。</span><span class="sxs-lookup"><span data-stu-id="8f86d-163">Another tool to help with Windows 10 and Office 365 ProPlus app compatibility is the [Desktop App Assure](https://aka.ms/desktopappassure) program available through the FastTrack Center.</span></span> <span data-ttu-id="8f86d-164">在有效應用程式發生問題時，Microsoft 工程師可以透過「電腦 App 保證」免費與您合作，協助修復應用程式不相容性問題。</span><span class="sxs-lookup"><span data-stu-id="8f86d-164">Through Desktop App Assure in the event of valid application issues a Microsoft engineer with work with you at no additional cost to help remediate the application incompatibility.</span></span>

## <a name="continued-use-of-diagnostic-data-tools"></a><span data-ttu-id="8f86d-165">繼續使用診斷資料工具</span><span class="sxs-lookup"><span data-stu-id="8f86d-165">Continued Use of Diagnostic Data Tools</span></span>

<span data-ttu-id="8f86d-p117">Windows Analytics Upgrade Readiness 不只是協助您移轉至 Windows 10 和 Office 365 專業增強版的工具。一旦您讓桌面在 Windows 10 和 Office 365 上執行，就可以使用它來協助維護部署及管理半年功能更新，讓您保持在最新版本。</span><span class="sxs-lookup"><span data-stu-id="8f86d-p117">Windows Analytics Upgrade Readiness isn’t just a tool to help you shift to Windows 10 and Office 365 ProPlus. Once you have desktops running on Windows 10 and Office 365 you can use it to help maintain your deployment and manage semi-annual Feature Updates so that you can stay current.</span></span>

## <a name="next-step"></a><span data-ttu-id="8f86d-168">下一步</span><span class="sxs-lookup"><span data-stu-id="8f86d-168">Next Step</span></span> 

## <a name="step-2-directory-and-network-readinesshttpsakamsmdd2"></a>[<span data-ttu-id="8f86d-169">步驟 2：目錄和網路整備</span><span class="sxs-lookup"><span data-stu-id="8f86d-169">Step 2: Directory and Network Readiness</span></span>](https://aka.ms/mdd2)