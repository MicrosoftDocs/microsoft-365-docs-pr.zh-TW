---
title: Microsoft 受管理的桌上型電腦的組態設定
description: 在 Microsoft 受管理的桌上型電腦的組態設定的資訊
keywords: Microsoft 受管理的桌上型電腦、 Microsoft 365、 服務、 文件、 設定、 可設定的設定
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 2/14/2019
ms.openlocfilehash: 64560a1eb597072dd99c1538b0131e3cd807899c
ms.sourcegitcommit: 1942a860d1b65e1f8062564ec4703b953e0c2fd7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/20/2019
ms.locfileid: "30122243"
---
# <a name="configurable-settings---microsoft-managed-desktop"></a><span data-ttu-id="c67d3-104">可設定-Microsoft 受管理的桌上型電腦</span><span class="sxs-lookup"><span data-stu-id="c67d3-104">Configurable settings - Microsoft Managed Desktop</span></span>

<span data-ttu-id="c67d3-p101">Microsoft 受管理的桌上型電腦部署設定及原則可套用至所有由 Microsoft 受管理的桌上型電腦管理的裝置。如需詳細資訊，請參閱[裝置設定](../service-description/device-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="c67d3-p101">Microsoft Managed Desktop deploys settings and policies that are applied to all devices managed by Microsoft Managed Desktop. For more information, see [Device configuration](../service-description/device-policies.md).</span></span>

<span data-ttu-id="c67d3-p102">Microsoft 受管理的桌上型電腦中的組態設定將 IT 系統管理員提供一種方式來自訂和部署對其組織及商務需求都是唯一的設定。這些設定是除了裝置組態設定及管理 Microsoft 受管理的桌上型電腦的原則。</span><span class="sxs-lookup"><span data-stu-id="c67d3-p102">Configurable settings in Microsoft Managed Desktop give IT admins a way to customize and deploy settings that are unique to their organization and business needs. These settings are in addition to device configuration settings and policies that are managed by Microsoft Managed Desktop.</span></span>  

<span data-ttu-id="c67d3-p103">可設定的設定變更是在雲端中進行並套用您 Microsoft 受管理的桌上型電腦中的裝置已定義的部署鈴響。此程序會類似於 Microsoft 受管理的桌上型電腦管理變更裝置 configuruation 設定和原則定義及管理服務的方式。藉由使用 Microsoft 受管理的桌上型電腦使用進行部署變更的相同程序，您繼續使用現代 IT 管理作法往前移，您的組織。</span><span class="sxs-lookup"><span data-stu-id="c67d3-p103">Configurable setting changes are made in the cloud and applied to your Microsoft Managed Desktop devices in defined deployment rings. This process is similar to how Microsoft Managed Desktop manages changes to device configuruation settings and policies that are defined and managed by the service. By using the same process that Microsoft Managed Desktop uses for deploying changes,you continue to move your organization forward, using modern IT management practices.</span></span>

## <a name="when-to-use-configurable-settings"></a><span data-ttu-id="c67d3-112">何時使用組態設定？</span><span class="sxs-lookup"><span data-stu-id="c67d3-112">When to use configurable settings?</span></span>

<span data-ttu-id="c67d3-113">有一些時間來使用組態設定。</span><span class="sxs-lookup"><span data-stu-id="c67d3-113">There are a few times to use configurable settings.</span></span> 

<span data-ttu-id="c67d3-p104">**佈建程序**– Microsoft 受管理的桌上型電腦建議您在您開始 Microsoft 受管理的桌上型電腦服務時自訂組態設定，或當您開始大量的裝置 （20 或多個）。設定類別來設定 Microsoft 受管理的桌上型電腦管理入口網站。您已 onboarded 以及可以存取系統入口網站之後，您可以決定您要自訂您的組織、 進行的變更的部署階段及再部署變更的設定類別。</span><span class="sxs-lookup"><span data-stu-id="c67d3-p104">**Onboarding process** – Microsoft Managed Desktop recommends that you customize configurable settings when you onboard to Microsoft Managed Desktop service, or when you onboard a large number of devices (20 or more). Setting categories are configured in Microsoft Managed Desktop admin portal. After you’ve onboarded and have access to the admin portal, you can decide which setting categories you want to customize for your organization, make the changes, stage a deployment, and then deploy your changes.</span></span>

<span data-ttu-id="c67d3-p105">**維持設定**-定期檢閱您的設定並進行所需的更新。您可能需要變更以支援您的企業中的變更。</span><span class="sxs-lookup"><span data-stu-id="c67d3-p105">**Maintain settings** - Review your settings regularly and make needed updates. You might need to make changes to support a change in your business.</span></span>   

## <a name="setting-categories"></a><span data-ttu-id="c67d3-119">設定類別</span><span class="sxs-lookup"><span data-stu-id="c67d3-119">Setting categories</span></span>

<span data-ttu-id="c67d3-120">這些是您可以自訂的組態設定類別：</span><span class="sxs-lookup"><span data-stu-id="c67d3-120">These are the configurable settings categories that you can customize:</span></span>
- <span data-ttu-id="c67d3-121">[桌面背景圖片](config-setting-ref.md#desktop-background-picture)– 自訂 Microsoft 受管理的桌上型電腦裝置桌面背景圖片。</span><span class="sxs-lookup"><span data-stu-id="c67d3-121">[Desktop background picture](config-setting-ref.md#desktop-background-picture) – Customize the desktop background picture for Microsoft Managed Desktop devices.</span></span> 
- <span data-ttu-id="c67d3-p106">[瀏覽器啟動頁面](config-setting-ref.md#browser-start-pages)– 來搭配 Microsoft Edge 新增起始頁面。請參閱起始畫面的瀏覽器</span><span class="sxs-lookup"><span data-stu-id="c67d3-p106">[Browser start pages](config-setting-ref.md#browser-start-pages) – Add start pages to use with Microsoft Edge. See Browser start page</span></span>
- <span data-ttu-id="c67d3-p107">[企業模式網站清單](config-setting-ref.md#enterprise-mode-site-list-location)– 新增網站，以及其相容性模式。在清單上的網站會啟動 Internet Explorer 中。</span><span class="sxs-lookup"><span data-stu-id="c67d3-p107">[Enterprise mode site list](config-setting-ref.md#enterprise-mode-site-list-location) – Add sites, and their compatibility mode. Sites on the list will start in Internet Explorer.</span></span> 
- <span data-ttu-id="c67d3-126">[信任的網站](config-setting-ref.md#trusted-sites)-新增受信任的網站以及每個網站的設定安全性區域。</span><span class="sxs-lookup"><span data-stu-id="c67d3-126">[Trusted sites](config-setting-ref.md#trusted-sites) – Add trusted sites and set security zones for each site.</span></span> 
- <span data-ttu-id="c67d3-127">[Proxy 網站例外](config-setting-ref.md#proxy)– 設定 proxy 伺服器位址和連接埠號碼，並新增 proxy 網站例外狀況。</span><span class="sxs-lookup"><span data-stu-id="c67d3-127">[Proxy site exceptions](config-setting-ref.md#proxy) – Set up your proxy server address number and port number, and add proxy site exceptions.</span></span>

<span data-ttu-id="c67d3-p108">可以自訂及部署在其上每個設定類別。可以同時將變更部署到多個設定類別，不過，您可以僅部署一次一個變更到設定類別。</span><span class="sxs-lookup"><span data-stu-id="c67d3-p108">Each setting category can be customized and deployed on its own. You can deploy changes to multiple setting categories at the same time, however, you can only deploy one change at a time to a setting category.</span></span>

<span data-ttu-id="c67d3-130">例如：</span><span class="sxs-lookup"><span data-stu-id="c67d3-130">For example:</span></span>
- <span data-ttu-id="c67d3-131">您可對桌面背景圖片和受信任的站台，他們自己的部署，同時為每個部署的變更。</span><span class="sxs-lookup"><span data-stu-id="c67d3-131">You can deploy changes to desktop background picture and trusted sites, each as their own deployment, at the same time.</span></span> 
- <span data-ttu-id="c67d3-p109">您不能部署至瀏覽器開始頁面的兩個部署在同一時間。最新的部署將會停止仍正在進行中的舊版部署。</span><span class="sxs-lookup"><span data-stu-id="c67d3-p109">You can’t deploy two deployments to browser start pages at the same time. The most recent deployment will stop earlier deployments that are still in progress.</span></span>

## <a name="configurable-setting-process"></a><span data-ttu-id="c67d3-134">可設定的設定程序</span><span class="sxs-lookup"><span data-stu-id="c67d3-134">Configurable setting process</span></span>

<span data-ttu-id="c67d3-135">整體程序如下所示。</span><span class="sxs-lookup"><span data-stu-id="c67d3-135">The overall process looks like this.</span></span> 

<span data-ttu-id="c67d3-p110">**步驟 1-規劃**-了解可設定的設定並決定您要為組織設定的設定類別。規劃您的使用者通訊符合您的內部變更管理程序。例如，若要新增瀏覽器開始頁面，可讓您知道它們將擁有一組新的開始頁面在瀏覽器中部署之後的使用者。</span><span class="sxs-lookup"><span data-stu-id="c67d3-p110">**Step 1 - Plan** - Learn about configurable settings and decide which setting categories you want to configure for your organization. Plan communication to your users that meets your internal change management processes. For example, if you're adding browser start pages, let your users know that they'll have a new set of start pages in their browser after the deployment.</span></span>  

<span data-ttu-id="c67d3-p111">**步驟 2-設定和分段執行部署**-對 Microsoft 受管理的桌上型電腦管理入口網站中的組態設定進行變更。讓他們準備好部署階段所做的變更。請記得讓使用者知道的變更和所做的變更將會如何變更其裝置使用體驗。</span><span class="sxs-lookup"><span data-stu-id="c67d3-p111">**Step 2 - Configure and stage deployment** - Make changes to configurable settings in Microsoft Managed Desktop admin portal. Stage the changes so they’re ready to deploy. Remember to let your users know about the changes, and how the changes will change their device experience.</span></span>   

<span data-ttu-id="c67d3-p112">您設定和分段執行 Microsoft 受管理的桌上型電腦管理入口網站中的變更。如需詳細資訊，請參閱 ＜ [Customize 組態設定](config-setting-ref.md)。</span><span class="sxs-lookup"><span data-stu-id="c67d3-p112">You configure and stage changes in the Microsoft Managed Desktop admin portal. For more information, see [Customize configurable settings](config-setting-ref.md).</span></span> 

<span data-ttu-id="c67d3-p113">**步驟 3-通訊的變更**通訊使用者即將產生之變更的相關資訊。針對每個部署中，完成您變更管理程序的一部分的通訊。您應該清楚地影響使用者的運作方式，或就會看到其裝置上的任何變更。</span><span class="sxs-lookup"><span data-stu-id="c67d3-p113">**Step 3 - Communicate changes** Communicate information about upcoming changes to your users. For each deployment, complete the communication that is part of your change management processes. You should clearly communicate any change that impacts how a user works, or what they will see on their devices.</span></span>

<span data-ttu-id="c67d3-p114">**步驟 4-部署變更**-部署您的變更，開頭測試響鈴。測試響鈴可讓您驗證及疑難排解較少的裝置鈴響中任何問題再部署至較大的裝置群組的變更。如果您執行發生任何問題，您可以將回復變更、 更新設定和分段執行新的部署。Microsoft 受管理的桌上型電腦建議您遵循結構化的方法和部署至鈴響順序如下： 測試、 第一個、 快速且然後廣泛。</span><span class="sxs-lookup"><span data-stu-id="c67d3-p114">**Step 4 - Deploy changes** – Deploy your changes, starting with the Test ring. The Test ring allows you to validate and troubleshoot any issues in a ring with fewer devices, before deploying changes to larger groups of devices. If you run into any issues, you can revert the change, update the setting, and stage a new deployment. Microsoft Managed Desktop recommends that you follow the structured approach and deploy to rings in this order: Test, First, Fast, and then Broad.</span></span>   

<span data-ttu-id="c67d3-p115">使用 Microsoft 受管理的桌上型電腦管理入口網站管理所有組態設定。如需詳細資訊，請參閱 ＜ [Deploy 變更](config-setting-deploy.md)。</span><span class="sxs-lookup"><span data-stu-id="c67d3-p115">All configurable settings are managed using the Microsoft Managed Desktop admin portal. For more information, see [Deploy changes](config-setting-deploy.md).</span></span> 

<span data-ttu-id="c67d3-p116">**步驟 5-追蹤修訂**– 上部署狀態追蹤正在進行變更。每項設定，您可以：</span><span class="sxs-lookup"><span data-stu-id="c67d3-p116">**Step 5 - Track changes** – Track the progress for your changes on Deployment status. For each setting, you can:</span></span>
- <span data-ttu-id="c67d3-p117">**追蹤進度**– 追蹤狀態之後部署變更。狀態會變更為 [**進行中**，然後再可以是**Complete**、 」 或 「**失敗**。如果部署失敗，支援要求自動開啟調查問題 Microsoft 受管理的桌上型電腦作業。</span><span class="sxs-lookup"><span data-stu-id="c67d3-p117">**Track progress** – Track status after you deploy the change. The status will change to **In progress**, and then either **Complete**, or **Failed**. If a deployment fails, a support request is automatically opened for Microsoft Managed Desktop Operations to investigate the issue.</span></span>  
- <span data-ttu-id="c67d3-158">**請參閱部署版本**– 分別部署變更具有版本號碼。</span><span class="sxs-lookup"><span data-stu-id="c67d3-158">**See version deployed** – Each deployed change has a version number.</span></span>
- <span data-ttu-id="c67d3-p118">**還原變更**– 回復變更會停止目前的部署，並回復至已部署至所有鈴響的最後一個變更所有鈴響。您會回復為上次正確設定值。</span><span class="sxs-lookup"><span data-stu-id="c67d3-p118">**Revert changes** – Reverting a change stops the current deployment, and reverts all rings to the last changes that was deployed to all rings. You are rolling back to the last-known-good setting value.</span></span>
- <span data-ttu-id="c67d3-161">**驗證變更**-部署完成之後，驗證您如預期般已套用變更。</span><span class="sxs-lookup"><span data-stu-id="c67d3-161">**Validate changes** - After the deployment is complete, validate the changes were applied as you expected.</span></span>  

<span data-ttu-id="c67d3-162">如果部署失敗，或無法回復變更 Microsoft 受管理的桌上型電腦作業[開啟支援要求](admin-support.md)。</span><span class="sxs-lookup"><span data-stu-id="c67d3-162">If a deployment has failed, or you can't revert a change, [open a support request](admin-support.md) with Microsoft Managed Desktop Operations.</span></span> 

<span data-ttu-id="c67d3-163">如需詳細資訊，請參閱 ＜ [Deploy 和追蹤可設定的設定](config-setting-deploy.md)。</span><span class="sxs-lookup"><span data-stu-id="c67d3-163">For more information, see [Deploy and track configurable settings](config-setting-deploy.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="c67d3-164">其他資源</span><span class="sxs-lookup"><span data-stu-id="c67d3-164">Additional resources</span></span>
- [<span data-ttu-id="c67d3-165">可設定的設定參考 （英文)</span><span class="sxs-lookup"><span data-stu-id="c67d3-165">Configurable settings reference</span></span>](config-setting-ref.md) 
- [<span data-ttu-id="c67d3-166">部署組態設定</span><span class="sxs-lookup"><span data-stu-id="c67d3-166">Deploy configurable settings</span></span>](config-setting-deploy.md) 
