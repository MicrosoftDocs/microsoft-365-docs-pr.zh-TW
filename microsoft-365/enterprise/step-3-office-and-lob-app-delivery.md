---
title: 步驟 3 - Office 和 LOB 應用程式傳遞
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
description: 了解如何傳遞 Office 和 LOB 應用程式。
ms.openlocfilehash: 2bae1f159f7c8ae947d4afddfe1e608cdd8bc85b
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/28/2018
ms.locfileid: "26866773"
---
# <a name="step-3-office-and-lob-app-delivery"></a><span data-ttu-id="ca9f1-103">步驟 3：Office 和 LOB 應用程式傳遞</span><span class="sxs-lookup"><span data-stu-id="ca9f1-103">Step 3: Office and LOB App Delivery</span></span>

<span data-ttu-id="ca9f1-p101">現在您已準備好提供 Office 和企業營運應用程式。有許多方法可以使用，包括一些有趣的新選項。請花一些時間來了解，並選出符合目前需求的最佳方法。</span><span class="sxs-lookup"><span data-stu-id="ca9f1-p101">You are now ready to deliver Office and your Line of Business Apps. There are a number of ways to do this, including some exciting new options. Take some time to review and chose the best methods for your current needs.</span></span>

![](media/step-3-office-and-lob-app-delivery-media/step-3-office-and-lob-app-delivery-media-1.png)

<table>
<thead>
<td><img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-6.png" alt="Step 3" height="130" width="130" /></td>
<td><p><span data-ttu-id="ca9f1-107"><strong>步驟 3：Office 和 LOB 應用程式傳遞</strong></span><span class="sxs-lookup"><span data-stu-id="ca9f1-107"><strong>Step 3: Office and LOB App Delivery</strong></span></span></p>
<p><span data-ttu-id="ca9f1-p102">請確定您的應用程式已封裝並且準備好進行自動化安裝。了解隨選即用封裝與 Office 365 專業增強版如何給予您設定、傳遞及將 Office 應用程式保持在最新狀態的新選項。</span><span class="sxs-lookup"><span data-stu-id="ca9f1-p102">Ensure your apps are packaged and ready for automated installation. Learn how Click-to-Run packaging with Office 365 ProPlus gives you new options to configure, deliver and keep your Office apps up-to-date.</span></span></p></td>
<td><a href="https://aka.ms/ddev3" target="_blank"><img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-16.png" alt="Step 3" height="120" width="213" /></a></td>
</thead>
</table>

>[!NOTE]
><span data-ttu-id="ca9f1-p103">Office 和 LOB 應用程式傳遞是我們所建議部署程序轉輪中的第三個步驟，涵蓋安裝及管理 Office 及 LOB 的多個選項。若要成功進行部署，請勿略過前兩個步驟。若要查看完整的桌面部署程序，請瀏覽[現代化電腦的部署中心](https://aka.ms/HowToShift) (英文)。</span><span class="sxs-lookup"><span data-stu-id="ca9f1-p103">Office and LOB App Delivery is the third step in our recommended deployment process wheel covering the options to install and manage Office and LOB. For successful deployment do not skip the first two steps.  To see the full desktop deployment process, visit the [Modern Desktop Deployment Center](https://aka.ms/HowToShift).</span></span>
>

<span data-ttu-id="ca9f1-p104">某些應用程式僅適用於 32 位元或 64 位元編譯版本其中一個，而其他包括 Office 365 專業增強版則同時是 32 位元和 64 位元原生編譯程式碼，而您要做的其中一項最大決策就是決定要部署哪個版本。若要利用新裝置上其他運算能力及 RAM，建議您使用 64 位元版本，但在開始前，您必須先找出可能會產生的任何增益集或檔案相關的相容性問題。在繼續之前，可能需要您再次瀏覽步驟 1 裝置和應用程式整備。</span><span class="sxs-lookup"><span data-stu-id="ca9f1-p104">While some applications are only available as either a 32-bit or 64-bit compiled version, others, including Office 365 ProPlus, both as 32-bit and 64-bit native compiled code, and one of biggest decisions you will make is which version to deploy. To take advantage of additional compute power and RAM on new devices, you will want to use the 64-bit version, but before you do you will need to figure out any add-in or file-related compatibility challenges you may have. This may require you to revisit Step 1 Device and App Readiness before you continue.</span></span>

<span data-ttu-id="ca9f1-p105">如果沒有任何問題，建議您將所有應用程式部署為 64 位元版本，包括 Microsoft Office。64 位元原生編譯應用程式可提供最佳效能，是承受未來考驗的最佳選擇。</span><span class="sxs-lookup"><span data-stu-id="ca9f1-p105">If nothing is blocking you, we recommend you deploy 64-bit versions of all apps, including Microsoft Office. 64-bit native compiled apps offer the best performance and is the most future-proof choice.</span></span>

<span data-ttu-id="ca9f1-118">在 Windows 上安裝應用程式有許多方法與模型，讓我們來看看您的傳遞選項。</span><span class="sxs-lookup"><span data-stu-id="ca9f1-118">There are many methods and models for installing apps on Windows, so let’s look at your delivery options.</span></span>

[<span data-ttu-id="ca9f1-119">Windows 10 應用程式管理</span><span class="sxs-lookup"><span data-stu-id="ca9f1-119">Windows 10 application management</span></span>](https://docs.microsoft.com/zh-TW/windows/application-management/)

## <a name="msi-based-deployments"></a><span data-ttu-id="ca9f1-120">MSI 型部署</span><span class="sxs-lookup"><span data-stu-id="ca9f1-120">MSI-based Deployments</span></span>

<span data-ttu-id="ca9f1-p106">針對企業營運應用程式，您可能使用 MSI 型套件或可執行檔，並將應用程式安裝為 OS 部署工作順序的一部分。Windows 10 仍會繼續使用這些套件</span><span class="sxs-lookup"><span data-stu-id="ca9f1-p106">For your line of business apps, you’ll probably use MSI-based packages or executables, and install apps as part of an OS deployment task sequence. Windows 10 continues to work with these packages</span></span>

<span data-ttu-id="ca9f1-p107">System Center Configuration Manager 和 Microsoft Intune 等軟體部署工具也經過最佳化以提供 MSI 封裝的應用程式。在 Windows 10 上驗證應用程式之後，即可將 System Center Configuration Manager (最新分支) 用於應用程式傳遞。如果使用 Microsoft Intune 的公司入口網站，您可以延伸選擇，將獲得 IT 批准組織可用的應用程式包含最新的應用程式，且使用者可自行選取所需項目。</span><span class="sxs-lookup"><span data-stu-id="ca9f1-p107">Software deployment tools like System Center Configuration Manager and Microsoft Intune are also optimized to deliver MSI-packaged apps. Once you have validated your apps on Windows 10, you can use System Center Configuration Manager (current branch) for app delivery. If you use the Company Portal in Microsoft Intune you can extend the choice of IT sanctioned apps available to your organization to include the latest applications, and users to self-select what they need.</span></span>

![](media/step-3-office-and-lob-app-delivery-media/step-3-office-and-lob-app-delivery-media-3.png)

## <a name="pc-imaging"></a><span data-ttu-id="ca9f1-126">電腦影像</span><span class="sxs-lookup"><span data-stu-id="ca9f1-126">PC Imaging</span></span>

<span data-ttu-id="ca9f1-p108">應用程式傳遞的另一個常見方法是電腦影像。在此情況下，應用程式安裝會透過工作順序或在範本電腦上以手動方式進行，然後會擷取系統映像並預先安裝必要的應用程式。以影像方式建立及擷取可以在佈建新電腦時節省時間，但請記得，映像內的作業系統和應用程式會快速過期。在 Windows 10 和 Office 365 專業增強版中的累計更新模型可協助解決這個問題，但無法完全消除。這也是為什麼我們建議您使用精簡映像的方式，您的應用程式會在部署時間從映像外部進行安裝。</span><span class="sxs-lookup"><span data-stu-id="ca9f1-p108">Another popular method of app delivery is PC imaging. In this case, applications are either installed via task sequence or manually on a sample PC, then a system image is captured with the required applications pre-installed. The imaging approach to build and capture can save time when provisioning new PCs but remember Operating systems and apps within the image can become stale quickly. The Cumulative Update model in Windows 10 and Office 365 ProPlus help with this problem, but doesn’t eliminate it completely. This is why we recommend a thin image approach, where your applications are installed from outside the image at deploy time.</span></span>

![](media/step-3-office-and-lob-app-delivery-media/step-3-office-and-lob-app-delivery-media-4.png)

<span data-ttu-id="ca9f1-p109">如果您想在映像中包含 Office 365 專業增強版，請記住，這會使用使用者型啟用，而無法由系統管理員預先啟用。使用 Office 部署工具在影像裝置上預先安裝 Office，並跳過使用者登入。使用者可以登入，受指派啟用，並充分利用其他運用首次登入的功能。</span><span class="sxs-lookup"><span data-stu-id="ca9f1-p109">If you do want to include Office 365 ProPlus in your image, remember that this uses a user-based activation; it cannot be pre-activated by the system admin. Use the Office Deployment Tool to pre-install Office on the device you are imaging and skip the user sign-in. Users can sign-in, be assigned the activation and take advantage of other capabilities that leverage sign-in on first use.</span></span>

<span data-ttu-id="ca9f1-134">[建立安裝作業系統的工作順序](https://docs.microsoft.com/zh-TW/sccm/osd/deploy-use/create-a-task-sequence-to-install-an-operating-system) (英文)</span><span class="sxs-lookup"><span data-stu-id="ca9f1-134">[Create a Task Sequence to Install an Operating System](https://docs.microsoft.com/zh-TW/sccm/osd/deploy-use/create-a-task-sequence-to-install-an-operating-system)</span></span>

## <a name="click-to-run"></a><span data-ttu-id="ca9f1-135">隨選即用</span><span class="sxs-lookup"><span data-stu-id="ca9f1-135">Click-to-Run</span></span> 

<span data-ttu-id="ca9f1-p110">Office 365 專業增強版使用隨選即用來安裝，隨選即用取代了 Windows 即將推出的 Office 2019 每個版本中的 MSI 型封裝。它會帶來許多好處，包括更快速的安裝、更快且更有效率的更新以及更簡潔的解除安裝</span><span class="sxs-lookup"><span data-stu-id="ca9f1-p110">Office 365 ProPlus is installed using Click-to-Run, and Click-to-Run replaces MSI-based packaging in every version of the upcoming Office 2019 release for Windows. It brings with it a number of advantages, including faster installations, faster and more efficient updating, and cleaner uninstallation</span></span>

<span data-ttu-id="ca9f1-p111">透過隨選即用提供的程式會在您電腦上的虛擬應用程式環境中執行，因此能與其他應用程式共存，而不發生衝突；這些程式也會如 MSI 型套件佔去約一半的磁碟空間。因為隨選即用支援程式串流，透過串流最常使用的功能，使用者就可以在幾分鐘內開始使用 Office 應用程式，而不需先等候 Office 完整安裝。這不只對於初始部署很重要，這表示更新可以順暢地在背景中串流，將對使用者的影響降至最低。</span><span class="sxs-lookup"><span data-stu-id="ca9f1-p111">Programs delivered via Click-to-Run execute in a virtual application environment on your computer and so co-exist with other applications without conflict; they also take about half the disk space they would as an MSI-based package. And because Click-to-Run supports program streaming, by streaming the most commonly used features first, users can start using Office applications in just a few minutes, rather than waiting for Office to install fully first. This is important not just for the initial deployment, it means updates can be streamed seamlessly in the background with minimal impact on users.</span></span>

<span data-ttu-id="ca9f1-p112">如果您使用 System Center Configuration Manager，您仍然可以使用它來廣泛部署 Office 365 專業增強版。System Center Configuration Manager (最新分支) 擁有更新的 Office 自訂工具的原生支援，隨選即用在安裝時間的套件自訂，以及安裝後軟體更新管理的原生支援。</span><span class="sxs-lookup"><span data-stu-id="ca9f1-p112">If you use System Center Configuration Manager, you can still use it for broad deployment of Office 365 ProPlus. System Center Configuration Manager (current branch) has native support for the updated Office Customization Tool, package customization for Click-to-Run at install time, and native support for software update management post installation.</span></span>

<span data-ttu-id="ca9f1-143">[Office 365 專業增強版部署指南](https://docs.microsoft.com/zh-TW/deployoffice/deployment-guide-for-office-365-proplus) (英文)</span><span class="sxs-lookup"><span data-stu-id="ca9f1-143">[Deployment Guide for Office 365 ProPlus](https://docs.microsoft.com/zh-TW/deployoffice/deployment-guide-for-office-365-proplus)</span></span>

[<span data-ttu-id="ca9f1-144">升級至 Office 365 專業增強版時，移除 Office 現有的 MSI 版本</span><span class="sxs-lookup"><span data-stu-id="ca9f1-144">Remove existing MSI versions of Office when upgrading to Office 365 ProPlus</span></span>](https://docs.microsoft.com/zh-TW/deployoffice/upgrade-from-msi-version)

[<span data-ttu-id="ca9f1-145">使用 Configuration Manager 管理 Office 365 ProPlus</span><span class="sxs-lookup"><span data-stu-id="ca9f1-145">Manage Office 365 ProPlus with Configuration Manager</span></span>](https://docs.microsoft.com/zh-TW/sccm/sum/deploy-use/manage-office-365-proplus-updates)

[<span data-ttu-id="ca9f1-146">使用 Microsoft Intune 將 Office 365 應用程式指派給 Windows 10 裝置</span><span class="sxs-lookup"><span data-stu-id="ca9f1-146">Assign Office 365 apps to Windows 10 devices with Microsoft Intune</span></span>](https://docs.microsoft.com/zh-TW/intune/apps-add-office365)

## <a name="browser-based-apps"></a><span data-ttu-id="ca9f1-147">瀏覽器型應用程式</span><span class="sxs-lookup"><span data-stu-id="ca9f1-147">Browser-based Apps</span></span>

<span data-ttu-id="ca9f1-p113">有幾個項目需考慮，以確認您的瀏覽器型應用程式可以繼續正常運作。如果您有特定的網站和應用程式與 Microsoft Edge 有相容性問題，您可以使用企業模式網站清單，以便使用 Internet Explorer 11 時網站會自動開啟。</span><span class="sxs-lookup"><span data-stu-id="ca9f1-p113">There are a few things to consider in order to make sure that your browser-based applications continue to work as expected. If you have specific web sites and apps that you know have compatibility problems with Microsoft Edge, you can use the Enterprise Mode site list so that the web sites will automatically open using Internet Explorer 11.</span></span>

<span data-ttu-id="ca9f1-p114">此外，如果您知道您的內部網路網站使用 Microsoft Edge 無法正常運作，則可以設定所有內部網路網站自動使用 Internet Explorer 11 開啟。此程序會使用 XML 檔案來控制 IE11 是否用於每個網站，並使用群組原則來強制執行設定。</span><span class="sxs-lookup"><span data-stu-id="ca9f1-p114">Additionally, if you know that your intranet sites aren't going to work properly with Microsoft Edge, you can set all intranet sites to open using Internet Explorer 11 automatically. This process uses an XML file to govern whether IE11 is used for each site, using Group Policy to enforce settings.</span></span>

<span data-ttu-id="ca9f1-p115">到目前為止，我們探討了已知的部署方法。但還有兩種應用程式部署的新方法您可能可以考慮。</span><span class="sxs-lookup"><span data-stu-id="ca9f1-p115">So far, we have covered well known deployment methods. But there are two new approaches to app deployment you may wish to consider.</span></span>

[<span data-ttu-id="ca9f1-154">什麼是企業模式</span><span class="sxs-lookup"><span data-stu-id="ca9f1-154">What is Enterprise Mode</span></span>](https://docs.microsoft.com/zh-TW/internet-explorer/ie11-deploy-guide/what-is-enterprise-mode#what-is-enterprise-mode)

## <a name="microsoft-store-for-business"></a><span data-ttu-id="ca9f1-155">商務用 Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="ca9f1-155">Microsoft Store for Business</span></span> 

<span data-ttu-id="ca9f1-p116">商務用 Microsoft Store 提供彈性的方式來大規模探索、取得、管理和發佈免費與付費應用程式到 Windows 10 裝置。身為 IT 系統管理員，您可以將精選 Microsoft Store 應用程式以及您的自訂應用程式，發佈到您自己的私人存放區，並視需要指派及重複使用授權。使用者僅能導向至這個存放區，因此只能尋找和安裝核准的應用程式。</span><span class="sxs-lookup"><span data-stu-id="ca9f1-p116">Microsoft Store for Business provides a flexible way discover, acquire, manage, and distribute free and paid apps to Windows 10 devices at scale. As an IT admin, you can publish selected Microsoft Store apps, along with your custom own apps, to your own private store, and assign and re-use licenses as needed. Your users are directed to this store only, and so can only find and install approved apps.</span></span>

<span data-ttu-id="ca9f1-p117">Microsoft Store 應用程式可原生內建為 UWP 應用程式，或者您可以使用 Desktop Bridge 為 Store 重新封裝現有的應用程式，並新增適用於 Windows 10 的新式體驗。除了您用來推出 Windows 10 體驗的程式碼，應用程式會維持不變，並繼續以完全信任使用者模式執行。</span><span class="sxs-lookup"><span data-stu-id="ca9f1-p117">Store apps can be natively built as UWP apps or you can use the Desktop Bridge to repackage your existing apps for the Store and add modern experiences for Windows 10. Aside from the code that you use to light up Windows 10 experiences, your app remains unchanged and continues to run in full-trust user mode.</span></span>

## <a name="msix-containerization"></a><span data-ttu-id="ca9f1-161">MSIX 容器化</span><span class="sxs-lookup"><span data-stu-id="ca9f1-161">MSIX Containerization</span></span>

<span data-ttu-id="ca9f1-p118">應用程式封裝的新選項是 MSIX。MSIX 使用 Windows 提供的容器化技術，結合隨選即用、UWP 和 MSI 封裝的最佳層面。具備工具可將現有的安裝程式如 EXE、MSI、APPV 和 APPX 直接移轉到 MSIX，MSIX 容器化為許多目前使用中的安裝技術提供統一的路徑。目前的 Windows 版本中包含 MSIX 支援：執行 Windows 10 RS5 或更新版本的任何裝置，包含要安裝及執行 MSIX 封裝應用程式所需的所有項目。Windows 10 會動態整合收到的 MSIX 容器，同時讓應用程式與作業系統保持分離。</span><span class="sxs-lookup"><span data-stu-id="ca9f1-p118">A new option for application packaging is MSIX. MSIX uses the containerization technology available in Windows, bringing together the best aspects of Click-to-Run, UWP and MSI packaging. With tools to migrate existing installers like EXE, MSI, APPV and APPX directly to MSIX we see MSIX Containerization provides a unifed path for the many installation technologies in use today. MSIX support is included in current versions of Windows: any device running Windows 10 RS5 or newer, includes everything you need to install and run MSIX packaged apps. Windows 10 dynamically integrates MSIX containers it receives, while keeping the applications separate from the operating system.</span></span>

<span data-ttu-id="ca9f1-p119">容器化表示可以完全解除安裝和移除套件，與現在許多可能會在系統上留下項目的 MSI 和 EXE 型套件不同。這也表示您只需要標準使用者認證即可安裝應用程式，而不需要擁有系統管理員認證才能安裝 MSIX 容器。MSIX 容器的更新也更有效率。更新發行時，使用區塊層級差異表示只會套用新的二進位檔，減少更新承載，可耗用較少的網路頻寬更快速地進行部署。</span><span class="sxs-lookup"><span data-stu-id="ca9f1-p119">Containerization means clean uninstall and removal of packages, unlike a lot of MSI and EXE-based packages today that may leave items on the system. It also means only needing Standard User credentials to install applications – you do not have to have Administrator credentials to install MSIX containers. MSIX containers are more efficient to update too. When an update is published, use of block level differentials means only net new binaries are applied, reducing the update payload, for faster deployments consuming less network bandwidth.</span></span>

<span data-ttu-id="ca9f1-171">您可以透過 [MSIX 技術社群網站](https://techcommunity.microsoft.com/t5/MSIX/ct-p/MSIX)找到更多 MSIX 相關資訊</span><span class="sxs-lookup"><span data-stu-id="ca9f1-171">You can find more information on MSIX via the [MSIX Tech Community site](https://techcommunity.microsoft.com/t5/MSIX/ct-p/MSIX)</span></span>

## <a name="next-step"></a><span data-ttu-id="ca9f1-172">下一步</span><span class="sxs-lookup"><span data-stu-id="ca9f1-172">Next Step</span></span>

## <a name="step-4-user-files-and-settingshttpsakamsmdd4"></a><span data-ttu-id="ca9f1-173">[步驟 4：使用者檔案和設定](https://aka.ms/mdd4) (英文)</span><span class="sxs-lookup"><span data-stu-id="ca9f1-173">[Step 4: User Files and Settings](https://aka.ms/mdd4)</span></span>

## <a name="previous-step"></a><span data-ttu-id="ca9f1-174">上一步</span><span class="sxs-lookup"><span data-stu-id="ca9f1-174">Previous Step</span></span>

## <a name="step-2-directory-and-network-readinesshttpsakamsmdd2"></a>[<span data-ttu-id="ca9f1-175">步驟 2：目錄和網路整備</span><span class="sxs-lookup"><span data-stu-id="ca9f1-175">Step 2: Directory and Network Readiness</span></span>](https://aka.ms/mdd2) 