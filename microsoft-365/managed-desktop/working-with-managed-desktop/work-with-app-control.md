---
title: 使用應用程式控制
description: ''
keywords: Microsoft 受管理的電腦, Microsoft 365, 服務, 文件
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
audience: ITpro
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 31cc897fe28f557a65cba9c99e5dcecbf7c2b0e5
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917637"
---
# <a name="work-with-app-control"></a><span data-ttu-id="38f9b-103">使用應用程式控制</span><span class="sxs-lookup"><span data-stu-id="38f9b-103">Work with app control</span></span>

<span data-ttu-id="38f9b-104">在您的環境中部署應用程式控制後，您和 Microsoft 受管理的桌面作業都有持續的責任。</span><span class="sxs-lookup"><span data-stu-id="38f9b-104">Once app control has been deployed in your environment, both you and Microsoft Managed Desktop Operations have ongoing responsibilities.</span></span> <span data-ttu-id="38f9b-105">例如，您可能想要在環境中新增新的應用程式，或新增 (或移除) 信任的簽署者。</span><span class="sxs-lookup"><span data-stu-id="38f9b-105">For example, you might want to add a new app in the environment or add (or remove) a trusted signer.</span></span> <span data-ttu-id="38f9b-106">若要改善安全性，在您將所有應用程式發行給使用者之前，應先進行代碼簽署。</span><span class="sxs-lookup"><span data-stu-id="38f9b-106">To improve security, all apps should be code-signed before you release them to users.</span></span> <span data-ttu-id="38f9b-107">應用程式的發行者詳細資料會包含有關簽署者的資訊。</span><span class="sxs-lookup"><span data-stu-id="38f9b-107">An app's publisher details includes information about the signer.</span></span>


## <a name="add-a-new-app"></a><span data-ttu-id="38f9b-108">新增應用程式</span><span class="sxs-lookup"><span data-stu-id="38f9b-108">Add a new app</span></span>

<span data-ttu-id="38f9b-109">若要新增應用程式，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="38f9b-109">To add a new app, follow these steps:</span></span>

1. <span data-ttu-id="38f9b-110">將 app 新增至 [Microsoft Intune](/mem/intune/apps/apps-win32-app-management)。</span><span class="sxs-lookup"><span data-stu-id="38f9b-110">Add the app to [Microsoft Intune](/mem/intune/apps/apps-win32-app-management).</span></span>
2. <span data-ttu-id="38f9b-111">將 app 部署到測試環中的任何裝置。</span><span class="sxs-lookup"><span data-stu-id="38f9b-111">Deploy the app to any device in the Test ring.</span></span> 
3. <span data-ttu-id="38f9b-112">根據標準商務程式測試您的應用程式。</span><span class="sxs-lookup"><span data-stu-id="38f9b-112">Test your app according to your standard business processes.</span></span> 
4. <span data-ttu-id="38f9b-113">在 [ **應用程式和服務 Logs\Microsoft\Windows\AppLocker**] 底下，檢查事件檢視器，尋找任何 **8003** 或 **8006** 事件。</span><span class="sxs-lookup"><span data-stu-id="38f9b-113">Check Event Viewer under **Application and Services Logs\Microsoft\Windows\AppLocker**, looking for any **8003** or **8006** events.</span></span> <span data-ttu-id="38f9b-114">這些事件表示應用程式會遭到封鎖。</span><span class="sxs-lookup"><span data-stu-id="38f9b-114">These events indicate that the app would be blocked.</span></span> <span data-ttu-id="38f9b-115">如需所有應用程式鎖定事件及其意義的詳細資訊，請參閱 [Using 事件檢視器 With AppLocker](/windows/security/threat-protection/windows-defender-application-control/applocker/using-event-viewer-with-applocker)。</span><span class="sxs-lookup"><span data-stu-id="38f9b-115">For more information about all App Locker events and their meanings, see [Using Event Viewer with AppLocker](/windows/security/threat-protection/windows-defender-application-control/applocker/using-event-viewer-with-applocker).</span></span>
5. <span data-ttu-id="38f9b-116">如果您發現以上任何事件，請使用 Microsoft 受管理的桌面作業開啟簽署者要求。</span><span class="sxs-lookup"><span data-stu-id="38f9b-116">If you find any of these events, open a signer request with Microsoft Managed Desktop Operations.</span></span>

## <a name="add-or-remove-a-trusted-signer"></a><span data-ttu-id="38f9b-117">新增 (或移除) 信任的簽署者</span><span class="sxs-lookup"><span data-stu-id="38f9b-117">Add (or remove) a trusted signer</span></span>

<span data-ttu-id="38f9b-118">當您開啟簽章要求時，您必須先提供一些重要的 publisher 詳細資料。</span><span class="sxs-lookup"><span data-stu-id="38f9b-118">When you open a signer request, you'll need to provide some important publisher details first.</span></span> <span data-ttu-id="38f9b-119">請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="38f9b-119">Then follow these steps:</span></span>

1. <span data-ttu-id="38f9b-120">[收集發行者的詳細資料](#gather-publisher-details)。</span><span class="sxs-lookup"><span data-stu-id="38f9b-120">[Gather publisher details](#gather-publisher-details).</span></span>
2. <span data-ttu-id="38f9b-121">使用 Microsoft Managed Desktop Operations 開啟票證以要求籤署者規則，並包含下列詳細資料：</span><span class="sxs-lookup"><span data-stu-id="38f9b-121">Open a ticket with Microsoft Managed Desktop Operations to request the signer rule and include following details:</span></span>  
    - <span data-ttu-id="38f9b-122">應用程式名稱</span><span class="sxs-lookup"><span data-stu-id="38f9b-122">Application name</span></span> 
    - <span data-ttu-id="38f9b-123">應用程式版本</span><span class="sxs-lookup"><span data-stu-id="38f9b-123">Application version</span></span> 
    - <span data-ttu-id="38f9b-124">描述</span><span class="sxs-lookup"><span data-stu-id="38f9b-124">Description</span></span> 
    - <span data-ttu-id="38f9b-125">變更類型 ( "add" 或 "remove" ) </span><span class="sxs-lookup"><span data-stu-id="38f9b-125">Change type ("add" or "remove")</span></span>  
    - <span data-ttu-id="38f9b-126">發行者詳細資料 (例如： "O = <publisher name> ，L = <location> ，S = State，C = Country" ) </span><span class="sxs-lookup"><span data-stu-id="38f9b-126">Publisher details (for example: “O=<publisher name>,L=<location>,S=State,C=Country”)</span></span> 

> [!NOTE]
> <span data-ttu-id="38f9b-127">若要移除應用程式的信任，請遵循相同的步驟，但設定要 *移除* 的 **變更類型**。</span><span class="sxs-lookup"><span data-stu-id="38f9b-127">To remove trust for an app, follow the same steps, but set **Change type** to *remove*.</span></span>

<span data-ttu-id="38f9b-128">作業會逐步將原則部署到遵循此排程的部署群組：</span><span class="sxs-lookup"><span data-stu-id="38f9b-128">Operations will progressively deploy policies to deployment groups following this schedule:</span></span>


|<span data-ttu-id="38f9b-129">部署群組</span><span class="sxs-lookup"><span data-stu-id="38f9b-129">Deployment group</span></span>  |<span data-ttu-id="38f9b-130">原則類型</span><span class="sxs-lookup"><span data-stu-id="38f9b-130">Policy type</span></span>  |<span data-ttu-id="38f9b-131">時程</span><span class="sxs-lookup"><span data-stu-id="38f9b-131">Timing</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="38f9b-132">測試</span><span class="sxs-lookup"><span data-stu-id="38f9b-132">Test</span></span>     |  <span data-ttu-id="38f9b-133">稽核</span><span class="sxs-lookup"><span data-stu-id="38f9b-133">Audit</span></span>       |  <span data-ttu-id="38f9b-134">Day 0</span><span class="sxs-lookup"><span data-stu-id="38f9b-134">Day 0</span></span>       |
|<span data-ttu-id="38f9b-135">名字</span><span class="sxs-lookup"><span data-stu-id="38f9b-135">First</span></span>     | <span data-ttu-id="38f9b-136">Enforced</span><span class="sxs-lookup"><span data-stu-id="38f9b-136">Enforced</span></span>        | <span data-ttu-id="38f9b-137">第 1 天</span><span class="sxs-lookup"><span data-stu-id="38f9b-137">Day 1</span></span>        |
|<span data-ttu-id="38f9b-138">快速</span><span class="sxs-lookup"><span data-stu-id="38f9b-138">Fast</span></span>     | <span data-ttu-id="38f9b-139">Enforced</span><span class="sxs-lookup"><span data-stu-id="38f9b-139">Enforced</span></span>        |  <span data-ttu-id="38f9b-140">第 2 天</span><span class="sxs-lookup"><span data-stu-id="38f9b-140">Day 2</span></span>       |
|<span data-ttu-id="38f9b-141">廣泛</span><span class="sxs-lookup"><span data-stu-id="38f9b-141">Broad</span></span>     | <span data-ttu-id="38f9b-142">Enforced</span><span class="sxs-lookup"><span data-stu-id="38f9b-142">Enforced</span></span>        |  <span data-ttu-id="38f9b-143">第 3 天</span><span class="sxs-lookup"><span data-stu-id="38f9b-143">Day 3</span></span>       |


<span data-ttu-id="38f9b-144">您可以在首次部署期間隨時暫停或回退部署。</span><span class="sxs-lookup"><span data-stu-id="38f9b-144">You can pause or roll back the deployment at any time during the rollout.</span></span> <span data-ttu-id="38f9b-145">若要這麼做，請使用 Operations 開啟另一個服務要求。</span><span class="sxs-lookup"><span data-stu-id="38f9b-145">To do this, open another service request with Operations.</span></span>

> [!NOTE]
> <span data-ttu-id="38f9b-146">如果您暫停簽章規則的發行，該規則必須在另一個首展開始之前還原或完成。</span><span class="sxs-lookup"><span data-stu-id="38f9b-146">If you pause the release of a signer rule, that rule must be either rolled back or completed before another rollout can start.</span></span>

## <a name="gather-publisher-details"></a><span data-ttu-id="38f9b-147">收集發行者詳細資料</span><span class="sxs-lookup"><span data-stu-id="38f9b-147">Gather publisher details</span></span>

<span data-ttu-id="38f9b-148">若要存取應用程式的發行者資料，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="38f9b-148">To access the publisher data for an app, follow these steps:</span></span>

1. <span data-ttu-id="38f9b-149">在已套用稽核模式原則的測試環中，尋找 Microsoft 受管理的桌面裝置。</span><span class="sxs-lookup"><span data-stu-id="38f9b-149">Find a Microsoft Managed Desktop device in the Test ring that has an Audit Mode policy applied.</span></span> 
2. <span data-ttu-id="38f9b-150">嘗試在裝置上安裝應用程式。</span><span class="sxs-lookup"><span data-stu-id="38f9b-150">Attempt to install the app on the device.</span></span>
3. <span data-ttu-id="38f9b-151">開啟該裝置上的事件檢視器。</span><span class="sxs-lookup"><span data-stu-id="38f9b-151">Open Event Viewer on that device.</span></span> 
4. <span data-ttu-id="38f9b-152">在事件檢視器中，流覽至 [ **應用程式和服務 Logs\Microsoft\Windows**]，然後選取 **AppLocker**。</span><span class="sxs-lookup"><span data-stu-id="38f9b-152">In Event Viewer, navigate to **Application and Services Logs\Microsoft\Windows**, and then select **AppLocker**.</span></span> 
5. <span data-ttu-id="38f9b-153">尋找任何 **8003** 或 **8006** 事件，然後複製事件中的資訊：</span><span class="sxs-lookup"><span data-stu-id="38f9b-153">Find any **8003** or **8006** event, and then copy information from the event:</span></span> 
    - <span data-ttu-id="38f9b-154">應用程式名稱</span><span class="sxs-lookup"><span data-stu-id="38f9b-154">Application name</span></span> 
    - <span data-ttu-id="38f9b-155">應用程式版本</span><span class="sxs-lookup"><span data-stu-id="38f9b-155">Application version</span></span> 
    - <span data-ttu-id="38f9b-156">描述</span><span class="sxs-lookup"><span data-stu-id="38f9b-156">Description</span></span> 
    - <span data-ttu-id="38f9b-157">發行者詳細資料 (例如： "O = <publisher name> ，L = <location> ，S = State，C = Country" ) </span><span class="sxs-lookup"><span data-stu-id="38f9b-157">Publisher details (for example: “O=<publisher name>, L=<location>, S=State, C=Country”)</span></span>