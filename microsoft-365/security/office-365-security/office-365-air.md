---
title: 自動調查及回應 Office 365 中的威脅
keywords: AIR, autoIR, ATP, 自動化, 調查, 回應, 修正, 威脅, 進階, 威脅, 保護
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
description: 開始使用 Office 365 進階威脅防護方案 2 中的自動化調查及回應功能
ms.openlocfilehash: 3f13b1de2747dcb6672f56989ff73cdf485e49b6
ms.sourcegitcommit: 8c244b38c43dd00c4ef0102f8bed02ab36639a6b
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/10/2019
ms.locfileid: "39967986"
---
# <a name="automatically-investigate-and-respond-to-threats-in-office-365"></a><span data-ttu-id="f318c-104">自動調查及回應 Office 365 中的威脅</span><span class="sxs-lookup"><span data-stu-id="f318c-104">Automatically investigate and respond to threats in Office 365</span></span>

## <a name="overview"></a><span data-ttu-id="f318c-105">概觀</span><span class="sxs-lookup"><span data-stu-id="f318c-105">Overview</span></span>

<span data-ttu-id="f318c-106">視您的訂閱而定，[Office 365 進階威脅防護](office-365-atp.md)可以包括自動化調查和回應 (AIR) 功能，可節省您的安全性作業小組時間和處理警示和威脅的精力。</span><span class="sxs-lookup"><span data-stu-id="f318c-106">Depending on your subscription, [Office 365 Advanced Threat Protection](office-365-atp.md) can include automated investigation and response (AIR) capabilities that can save your security operations team time and effort in dealing with alerts and threats.</span></span>

- <span data-ttu-id="f318c-107">若要開始使用 Office 365 中的自動化調查及回應功能，請使用本文章。</span><span class="sxs-lookup"><span data-stu-id="f318c-107">To get started using automated investigation and response capabilities in Office 365, use this article.</span></span> 
- <span data-ttu-id="f318c-108">若要取得其運作方式的概觀，請參閱 [Office 365 中的自動化調查及回應](automated-investigation-response-office.md)。</span><span class="sxs-lookup"><span data-stu-id="f318c-108">To get an overview of how it works, see [Automated investigation and response in Office 365](automated-investigation-response-office.md).</span></span>

> [!TIP]
> <span data-ttu-id="f318c-109">您有 Microsoft 365 E5 或 Microsoft 365 E3 以及身分識別與威脅防護產品？</span><span class="sxs-lookup"><span data-stu-id="f318c-109">Do you have Microsoft 365 E5 or Microsoft 365 E3 together with Identity & Threat Protection?</span></span> <span data-ttu-id="f318c-110">考量嘗試 [Microsoft 威脅防護中的自動化調查及回應 (AIR)](../mtp/mtp-autoir.md)</span><span class="sxs-lookup"><span data-stu-id="f318c-110">Consider trying [Automated investigation and response (AIR) in Microsoft Threat Protection](../mtp/mtp-autoir.md).</span></span>

<span data-ttu-id="f318c-111">使用自動化調查及回應功能，當觸發特定警示時，會起始一或多個安全性劇本，並且開始自動化調查程序。</span><span class="sxs-lookup"><span data-stu-id="f318c-111">With automated investigation and response capabilities, when certain alerts are triggered, one or more security playbooks initiate, and the automated investigation process begins.</span></span> <span data-ttu-id="f318c-112">在自動化調查程序期間及之後，您的安全性小組可以執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="f318c-112">During and after an automated investigation process, your security team can do the following:</span></span>

- <span data-ttu-id="f318c-113">[檢視調查的詳細資料](#view-details-of-an-investigation)</span><span class="sxs-lookup"><span data-stu-id="f318c-113">[](#view-details-of-an-investigation)View the details of an existing DLP policy</span></span>
- [<span data-ttu-id="f318c-114">根據調查的結果檢閱和核准動作</span><span class="sxs-lookup"><span data-stu-id="f318c-114">Review and approve actions as a result of an investigation</span></span>](#review-and-approve-actions) 
- [<span data-ttu-id="f318c-115">檢視與調查相關警示的詳細資料</span><span class="sxs-lookup"><span data-stu-id="f318c-115">View details about an alert related to an investigation</span></span>](#view-details-about-an-alert-related-to-an-investigation)

> [!IMPORTANT]
> <span data-ttu-id="f318c-116">若要執行本文所述的工作，您必須獲指派適當的權限。</span><span class="sxs-lookup"><span data-stu-id="f318c-116">To perform the tasks described in this article, you must have appropriate permissions assigned.</span></span> <span data-ttu-id="f318c-117">請參閱[使用 AIR 功能所需的權限](automated-investigation-response-office.md#required-permissions-to-use-air-capabilities)。</span><span class="sxs-lookup"><span data-stu-id="f318c-117">See [required permissions to use AIR capabilities](automated-investigation-response-office.md#required-permissions-to-use-air-capabilities).</span></span>

## <a name="view-details-of-an-investigation"></a><span data-ttu-id="f318c-118">檢視調查的詳細資料</span><span class="sxs-lookup"><span data-stu-id="f318c-118">View details of an investigation</span></span>

1. <span data-ttu-id="f318c-119">移至 [https://protection.office.com](https://protection.office.com) 並登入。</span><span class="sxs-lookup"><span data-stu-id="f318c-119">Go to [https://protection.office.com](https://protection.office.com) and sign in with an admin account.</span></span> <span data-ttu-id="f318c-120">這樣會帶您前往安全性與合規性中心。</span><span class="sxs-lookup"><span data-stu-id="f318c-120">This takes you to the the Security & Compliance Center.</span></span>

2. <span data-ttu-id="f318c-121">執行下列其中一項動作：</span><span class="sxs-lookup"><span data-stu-id="f318c-121">Do one of the following:</span></span>

    - <span data-ttu-id="f318c-122">移至 [威脅管理]\*\*\*\*  >  [儀表板]\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="f318c-122">Go to **Threat management** > **Dashboard**.</span></span> <span data-ttu-id="f318c-123">這樣會帶您前往[安全性儀表板](security-dashboard.md)。</span><span class="sxs-lookup"><span data-stu-id="f318c-123">This takes you to the [Security Dashboard](security-dashboard.md).</span></span> <span data-ttu-id="f318c-124">您的 AIR 小工具會顯示在[安全性儀表板](security-dashboard.md)上方。</span><span class="sxs-lookup"><span data-stu-id="f318c-124">Your AIR widgets appear across the top of the [Security Dashboard](security-dashboard.md).</span></span> <span data-ttu-id="f318c-125">選取小工具，例如**調查摘要**。</span><span class="sxs-lookup"><span data-stu-id="f318c-125">Select a widget, such as **Investigations summary**.</span></span>

    - <span data-ttu-id="f318c-126">移至 [威脅管理]\*\*\*\*  >  [調查]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f318c-126">Go to **Threat management** > **Investigations**.</span></span> 

    <span data-ttu-id="f318c-127">這兩種方法都會帶您前往調查清單。</span><span class="sxs-lookup"><span data-stu-id="f318c-127">Either method takes you to a list of investigations.</span></span>

    ![AIR 的主要調查頁面](../media/air-maininvestigationpage.png) 

3. <span data-ttu-id="f318c-129">在調查清單中，選取 [識別碼]\*\*\*\* 欄中的項目。</span><span class="sxs-lookup"><span data-stu-id="f318c-129">In the list of investigations, select an item in the **ID** column.</span></span> <span data-ttu-id="f318c-130">這樣會開啟調查詳細資料頁面，從檢視中的調查圖形開始。</span><span class="sxs-lookup"><span data-stu-id="f318c-130">This opens investigation details page, starting with the investigation graph in view.</span></span>

    ![AIR 調查圖形頁面](../media/air-investigationgraphpage.png)

4. <span data-ttu-id="f318c-132">使用各個索引標籤深入了解調查。</span><span class="sxs-lookup"><span data-stu-id="f318c-132">Use the various tabs to learn more about the investigation.</span></span>

## <a name="review-and-approve-actions"></a><span data-ttu-id="f318c-133">檢閱和核准動作</span><span class="sxs-lookup"><span data-stu-id="f318c-133">Review and approve actions</span></span>

<span data-ttu-id="f318c-134">在 Office 365 中，自動化調查通常會導致一或多個建議的動作。</span><span class="sxs-lookup"><span data-stu-id="f318c-134">In Office 365, automated investigations typically result in one or more recommended actions.</span></span> <span data-ttu-id="f318c-135">不過，在安全性操作小組核准之前，不會採取任何動作。</span><span class="sxs-lookup"><span data-stu-id="f318c-135">However, no actions are taken until they are approved by your security operations team.</span></span> <span data-ttu-id="f318c-136">使用下列程序來檢閱和核准動作。</span><span class="sxs-lookup"><span data-stu-id="f318c-136">Use the following procedure to review and approve actions.</span></span>

1. <span data-ttu-id="f318c-137">移至 [https://protection.office.com](https://protection.office.com) 並登入。</span><span class="sxs-lookup"><span data-stu-id="f318c-137">Go to [https://protection.office.com](https://protection.office.com) and sign in with an admin account.</span></span> 

2. <span data-ttu-id="f318c-138">移至 [威脅管理]\*\*\*\*  >  [調查]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f318c-138">Go to **Threat management** > **Investigations**.</span></span>

3. <span data-ttu-id="f318c-139">在調查清單中，選取 [識別碼]\*\*\*\* 欄中的項目。</span><span class="sxs-lookup"><span data-stu-id="f318c-139">In the list of investigations, select an item in the **ID** column.</span></span> 

3. <span data-ttu-id="f318c-140">在調查詳細資料檢視上，選取 [動作]\*\*\*\* 索引標籤。以下列出等候核准的任何動作。</span><span class="sxs-lookup"><span data-stu-id="f318c-140">On the investigation details view, select the **Actions** tab. Any actions that are pending approval are listed here.</span></span>

4. <span data-ttu-id="f318c-141">選取清單中的項目。</span><span class="sxs-lookup"><span data-stu-id="f318c-141">Click an item in the list.</span></span>

5. <span data-ttu-id="f318c-142">選取 [核准]\*\*\*\* 以採取建議的動作 (或選取 [拒絕]\*\*\*\* 關閉調查而不採取動作)。</span><span class="sxs-lookup"><span data-stu-id="f318c-142">Select **Approve** to take the recommended action (or **Reject** to close the investigation without taking action).</span></span>

## <a name="view-details-about-an-alert-related-to-an-investigation"></a><span data-ttu-id="f318c-143">檢視與調查相關警示的詳細資料</span><span class="sxs-lookup"><span data-stu-id="f318c-143">View details about an alert related to an investigation</span></span>

<span data-ttu-id="f318c-144">某些類型的警示會在 Office 365 中觸發自動化調查。</span><span class="sxs-lookup"><span data-stu-id="f318c-144">Certain kinds of alerts trigger automated investigation in Office 365.</span></span> <span data-ttu-id="f318c-145">若要深入了解，請參閱[警示](automated-investigation-response-office.md#alerts)。</span><span class="sxs-lookup"><span data-stu-id="f318c-145">To learn more, see [Click-to-Run](automated-investigation-response-office.md#alerts).</span></span> <span data-ttu-id="f318c-146">使用下列程序來檢視與自動化調查相關聯警示的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="f318c-146">Use the following procedure to view details about an alert that is associated with an automated investigation.</span></span>

1. <span data-ttu-id="f318c-147">移至 [https://protection.office.com](https://protection.office.com) 並登入。</span><span class="sxs-lookup"><span data-stu-id="f318c-147">Go to [https://protection.office.com](https://protection.office.com) and sign in with an admin account.</span></span> <span data-ttu-id="f318c-148">這樣會帶您前往安全性與合規性中心。</span><span class="sxs-lookup"><span data-stu-id="f318c-148">This takes you to the the Security & Compliance Center.</span></span>

2. <span data-ttu-id="f318c-149">移至 [威脅管理]\*\*\*\*  >  [調查]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f318c-149">Go to **Threat management** > **Investigations**.</span></span>

3. <span data-ttu-id="f318c-150">在調查清單中，選取 [識別碼]\*\*\*\* 欄中的項目。</span><span class="sxs-lookup"><span data-stu-id="f318c-150">In the list of investigations, select an item in the **ID** column.</span></span> 

4. <span data-ttu-id="f318c-151">開啟調查詳細資料時，選取 [警示]\*\*\*\* 索引標籤。觸發調查的任何警示都會列在此處。</span><span class="sxs-lookup"><span data-stu-id="f318c-151">With details of an investigation open, select the **Alerts** tab. Any alerts that triggered the investigation are listed here.</span></span>

5. <span data-ttu-id="f318c-152">選取清單中的項目。</span><span class="sxs-lookup"><span data-stu-id="f318c-152">Click an item in the list.</span></span> <span data-ttu-id="f318c-153">隨即開啟一個飛出視窗，其中包含警示的詳細資料以及其他資訊和動作的連結。</span><span class="sxs-lookup"><span data-stu-id="f318c-153">A flyout opens, with details about the alert and links to additional information and actions.</span></span>

6. <span data-ttu-id="f318c-154">檢閱飛出視窗中的資訊，並視特定警示採取動作，例如**解決**、**隱藏**，或**通知使用者**。</span><span class="sxs-lookup"><span data-stu-id="f318c-154">Review the information on the flyout, and, depending on the particular alert, take an action, such as **Resolve**, **Suppress**, or **Notify users**.</span></span> 

    - <span data-ttu-id="f318c-155">**解決**等同於關閉警示</span><span class="sxs-lookup"><span data-stu-id="f318c-155">**Resolve** is equivalent to closing an alert</span></span>
    
    - <span data-ttu-id="f318c-156">**隱藏**會導致原則在指定時段不觸發警示</span><span class="sxs-lookup"><span data-stu-id="f318c-156">**Suppress** causes a policy to not trigger alerts for a specified period of time</span></span>
    
    - <span data-ttu-id="f318c-157">**通知使用者**會啟動電子郵件，並且已輸入使用者的電子郵件地址，讓您的安全性操作小組輸入要給這些使用者的訊息。</span><span class="sxs-lookup"><span data-stu-id="f318c-157">**Notify users** starts an email with users' email addresses already entered, and enables your security operations team to type a message to those users.</span></span> <span data-ttu-id="f318c-158">(這類似於使用[威脅總管](threat-explorer.md)將訊息傳送給收件者。)</span><span class="sxs-lookup"><span data-stu-id="f318c-158">(This is similar to sending a message to recipients using [Threat Explorer](threat-explorer.md).)</span></span>  

## <a name="use-the-office-365-management-activity-api-for-custom-or-third-party-reporting-solutions"></a><span data-ttu-id="f318c-159">針對自訂或第三方報告解決方案使用 Office 365 管理活動 API</span><span class="sxs-lookup"><span data-stu-id="f318c-159">Use the Office 365 Management Activity API for custom or third-party reporting solutions</span></span>

<span data-ttu-id="f318c-160">如果貴組織使用自訂或第三方報告解決方案，您可以使用 Office 365 管理活動 API 來檢視該解決方案中自動化調查的資訊。</span><span class="sxs-lookup"><span data-stu-id="f318c-160">If your organization is using a custom or third-party reporting solution, you can view information about automated investigations in that solution by using the Office 365 Management Activity API.</span></span>

<span data-ttu-id="f318c-161">使用下列資源進行設定：</span><span class="sxs-lookup"><span data-stu-id="f318c-161">Use the following resources to set this up:</span></span>

|<span data-ttu-id="f318c-162">資源</span><span class="sxs-lookup"><span data-stu-id="f318c-162">Resource</span></span>  |<span data-ttu-id="f318c-163">描述</span><span class="sxs-lookup"><span data-stu-id="f318c-163">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="f318c-164">[Office 365 Management API 概觀](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview) (英文)</span><span class="sxs-lookup"><span data-stu-id="f318c-164">See [Office 365 Management APIs overview](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview).</span></span>     |<span data-ttu-id="f318c-165">Office 365 管理活動 API 提供 Office 365 和 Azure Active Directory 活動記錄中各種使用者、系統管理員、系統和原則動作及事件的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="f318c-165">The Office 365 Management Activity API (preview) provides information about policy actions and events from Office 365 and Azure Active Directory activity logs, for use in security and compliance monitoring and reporting solutions.</span></span>         |
|<span data-ttu-id="f318c-166">[開始使用 Office 365 管理 API](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis) (英文)</span><span class="sxs-lookup"><span data-stu-id="f318c-166">To get started, see [Get started with Office 365 Management APIs](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis).</span></span>     |<span data-ttu-id="f318c-167">Office 365 管理 API 使用 Azure AD 來為您的應用程式提供驗證服務，以存取 Office 365 資料。</span><span class="sxs-lookup"><span data-stu-id="f318c-167">The Office 365 Management API uses Azure AD to provide authentication services for your application to access Office 365 data.</span></span> <span data-ttu-id="f318c-168">請依照本文中的步驟進行設定。</span><span class="sxs-lookup"><span data-stu-id="f318c-168">Follow the steps in this article to set this up.</span></span>          |
|<span data-ttu-id="f318c-169">[Office 365 管理活動 API 參考](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference) (英文)</span><span class="sxs-lookup"><span data-stu-id="f318c-169">[Office 365 Management Activity API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)</span></span>     |<span data-ttu-id="f318c-170">您可以使用 Office 365 管理活動 API，從 Office 365 和 Azure AD 活動記錄中擷取使用者、系統管理員、系統和原則動作及事件的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="f318c-170">You can use the Office 365 Management Activity API to retrieve information about user, admin, system, and policy actions and events from Office 365 and Azure AD activity logs.</span></span> <span data-ttu-id="f318c-171">請閱讀本文以深入了解其運作方式。</span><span class="sxs-lookup"><span data-stu-id="f318c-171">Read this article to learn more about how this works.</span></span>        |
|<span data-ttu-id="f318c-172">[Office 365 管理活動 API 架構](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema) (英文)</span><span class="sxs-lookup"><span data-stu-id="f318c-172">[Office 365 Management Activity API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema)</span></span>     |<span data-ttu-id="f318c-173">取得[常見架構](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) (英文) 和 [Office 365 ATP 和威脅調查和回應架構](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) (英文) 的概觀，以深入了解 Office 365 管理活動 API 中可用的特定類型資料。</span><span class="sxs-lookup"><span data-stu-id="f318c-173">Get an overview of the [Common schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) and the [Office 365 ATP and threat investigation and response schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) to learn about specific kinds of data available through the Office 365 Management Activity API.</span></span>         |

## <a name="next-steps"></a><span data-ttu-id="f318c-174">後續步驟</span><span class="sxs-lookup"><span data-stu-id="f318c-174">Next steps</span></span>

- [<span data-ttu-id="f318c-175">了解如何取得 AIR 及查看所需權限</span><span class="sxs-lookup"><span data-stu-id="f318c-175">Find out how to get AIR and see required permissions</span></span>](automated-investigation-response-office.md#how-to-get-air)
- [<span data-ttu-id="f318c-176">深入了解警示</span><span class="sxs-lookup"><span data-stu-id="f318c-176">Learn more about alerts</span></span>](../../compliance/alert-policies.md)
- [<span data-ttu-id="f318c-177">手動尋找並調查在 Office 365 中傳送的惡意電子郵件</span><span class="sxs-lookup"><span data-stu-id="f318c-177">Manually find and investigate malicious email that was delivered in Office 365</span></span>](investigate-malicious-email-that-was-delivered.md)
- <span data-ttu-id="f318c-178">[了解 Microsoft Defender ATP 中的 AIR](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations) (部分機器翻譯)</span><span class="sxs-lookup"><span data-stu-id="f318c-178">[Learn about AIR in Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)</span></span>
- [<span data-ttu-id="f318c-179">造訪 Microsoft 365 藍圖，查看即將推出的功能</span><span class="sxs-lookup"><span data-stu-id="f318c-179">Visit the Microsoft 365 Roadmap to see what's coming soon and rolling out</span></span>](https://www.microsoft.com/microsoft-365/roadmap?filters=)