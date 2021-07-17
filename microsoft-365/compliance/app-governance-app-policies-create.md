---
title: 建立應用程式原則
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: m365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: 建立應用程式原則。
ms.openlocfilehash: 66d8dda7c9cd768d6971e2b58dca4c9c5437e5bb
ms.sourcegitcommit: 2fd60871975d61e60d4827b36cd689021fd2a4c8
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/15/2021
ms.locfileid: "53438057"
---
# <a name="create-app-policies"></a><span data-ttu-id="dcf4f-103">建立應用程式原則</span><span class="sxs-lookup"><span data-stu-id="dcf4f-103">Create app policies</span></span>

><span data-ttu-id="dcf4f-104">*[Microsoft 365 安全性與合規性的授權指引](https://aka.ms/ComplianceSD)。*</span><span class="sxs-lookup"><span data-stu-id="dcf4f-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="dcf4f-105">除了偵測異常應用程式行為並產生警示的內建功能集外，Microsoft 應用程式控管中的應用程式原則也是一種您可以：</span><span class="sxs-lookup"><span data-stu-id="dcf4f-105">Along with a built-in set of capabilities to detect anomalous app behavior and generate alerts, app policies in Microsoft app governance are a way for you to:</span></span>

- <span data-ttu-id="dcf4f-106">指定應用程式控管可警示您應用程式行為的條件，以進行自動或手動補救。</span><span class="sxs-lookup"><span data-stu-id="dcf4f-106">Specify conditions by which app governance can alert you to app behavior for automatic or manual remediation.</span></span>
- <span data-ttu-id="dcf4f-107">為貴組織實作應用程式合規性原則。</span><span class="sxs-lookup"><span data-stu-id="dcf4f-107">Implement the app compliance policies for your organization.</span></span>

<span data-ttu-id="dcf4f-108">您可以從提供的範本建立可自訂的應用程式原則，也可以建立自己的自訂應用程式原則。</span><span class="sxs-lookup"><span data-stu-id="dcf4f-108">You can create app policies from provided templates that can be customized, or you can create your own custom app policy.</span></span>

<span data-ttu-id="dcf4f-109">若要建立新的應用程式原則，請前往 **[Microsoft 365 合規性中心] > [應用程式控管] > [概觀頁面] > [原則]**：</span><span class="sxs-lookup"><span data-stu-id="dcf4f-109">To create a new app policy, go to **Microsoft 365 Compliance Center > App governance > Overview page > Policies**:</span></span>

- <span data-ttu-id="dcf4f-110">若要使用針對應用程式使用量設計的範本，來建立新的應用程式原則，請選取 **[建立原則]** 下的 **[建立應用程式使用量原則]**。</span><span class="sxs-lookup"><span data-stu-id="dcf4f-110">To create a new app policy with templates designed for app usage, select **Create policy** under **Create an app usage policy**.</span></span>
- <span data-ttu-id="dcf4f-111">若要使用針對應用程式權限設計的範本，來建立新的應用程式原則，請選取 **[建立原則]** 下的 **[建立權限原則]**。</span><span class="sxs-lookup"><span data-stu-id="dcf4f-111">To create a new app policy with templates designed for app permissions, select **Create policy** under **Create a permissions policy**.</span></span>
- <span data-ttu-id="dcf4f-112">若要為應用程式認證或自訂原則建立新的應用程式，請選取 **[新建]**。</span><span class="sxs-lookup"><span data-stu-id="dcf4f-112">To create a new app policy for app certification or for a custom policy, select **Create new**.</span></span>

## <a name="app-policy-templates"></a><span data-ttu-id="dcf4f-113">應用程式原則範本</span><span class="sxs-lookup"><span data-stu-id="dcf4f-113">App policy templates</span></span>

<span data-ttu-id="dcf4f-114">若要根據應用程式原則範本建立新的應用程式原則，請在 **[選擇應用程式原則範本頁面]** 上，選取應用程式範本的類別、選取範本的名稱，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="dcf4f-114">To create a new app policy based on an app policy template, on the **Choose App policy template page**, select a category of app template, select the name of the template, and then select **Next**.</span></span>

<span data-ttu-id="dcf4f-115">應用程式控管有三種應用程式原則範本類別。</span><span class="sxs-lookup"><span data-stu-id="dcf4f-115">App governance has three categories of app policy templates.</span></span>

### <a name="app-users-and-data-access"></a><span data-ttu-id="dcf4f-116">應用程式使用者與資料存取</span><span class="sxs-lookup"><span data-stu-id="dcf4f-116">App users and data access</span></span>

<span data-ttu-id="dcf4f-117">應用程式控管包含這些範本，以產生應用程式使用量的警示。</span><span class="sxs-lookup"><span data-stu-id="dcf4f-117">App governance includes these templates to generate alerts for app usage.</span></span>

| <span data-ttu-id="dcf4f-118">範本名稱</span><span class="sxs-lookup"><span data-stu-id="dcf4f-118">Template name</span></span> | <span data-ttu-id="dcf4f-119">描述</span><span class="sxs-lookup"><span data-stu-id="dcf4f-119">Description</span></span> |
|:-------|:-----|
| <span data-ttu-id="dcf4f-120">具有大量資料存取權限的新應用程式</span><span class="sxs-lookup"><span data-stu-id="dcf4f-120">New app with a high volume of data access</span></span> | <span data-ttu-id="dcf4f-121">醒目提示任何存取大量資料的最近註冊之應用程式，以確保這些資料模式是預期的。</span><span class="sxs-lookup"><span data-stu-id="dcf4f-121">Highlights any recently registered apps with high volume data access to ensure those data patterns are expected.</span></span> <br><br> <span data-ttu-id="dcf4f-122">根據預設，此原則會標出過去 7 天內註冊且在這一期間具有超過 1 GB 資料存取的所有應用程式。</span><span class="sxs-lookup"><span data-stu-id="dcf4f-122">By default, this policy will flag all apps that have been registered in the last 7 days and that have had more than 1 GB in data access over that period.</span></span> <span data-ttu-id="dcf4f-123">此原則可以自訂更多條件和動作。</span><span class="sxs-lookup"><span data-stu-id="dcf4f-123">This policy can be customized with more conditions and actions.</span></span> |
|||

### <a name="app-permissions"></a><span data-ttu-id="dcf4f-124">應用程式權限</span><span class="sxs-lookup"><span data-stu-id="dcf4f-124">App Permissions</span></span>

<span data-ttu-id="dcf4f-125">應用程式控管包含這些範本，以產生應用程式權限的警示。</span><span class="sxs-lookup"><span data-stu-id="dcf4f-125">App governance includes these templates to generate alerts for app permissions.</span></span>

| <span data-ttu-id="dcf4f-126">範本名稱</span><span class="sxs-lookup"><span data-stu-id="dcf4f-126">Template name</span></span> | <span data-ttu-id="dcf4f-127">描述</span><span class="sxs-lookup"><span data-stu-id="dcf4f-127">Description</span></span> |
|:-------|:-----|
| <span data-ttu-id="dcf4f-128">權限過高的應用程式</span><span class="sxs-lookup"><span data-stu-id="dcf4f-128">Overprivileged apps</span></span> | <span data-ttu-id="dcf4f-129">醒目提示任何被授與高於其實際使用的權限的應用程式，以識別潛在的降低權限的機會。</span><span class="sxs-lookup"><span data-stu-id="dcf4f-129">Highlights any apps with more granted permissions than are being used by those apps to identify opportunities for potential permission reduction.</span></span> <br><br> <span data-ttu-id="dcf4f-130">根據預設，如果 90 天內未使用，此原則會標出標示為權限過高的所有應用程式。</span><span class="sxs-lookup"><span data-stu-id="dcf4f-130">By default, this policy will flag all apps that are marked as Overprivileged if not used for 90 days.</span></span> <span data-ttu-id="dcf4f-131">此時間間隔篩選可以自訂更多條件和動作。</span><span class="sxs-lookup"><span data-stu-id="dcf4f-131">This time period filter can be customized with more conditions and actions.</span></span> |
| <span data-ttu-id="dcf4f-132">具有高權限的新應用程式</span><span class="sxs-lookup"><span data-stu-id="dcf4f-132">New app with high-privilege permissions</span></span> | <span data-ttu-id="dcf4f-133">醒目提示所有具有高權限的新應用程式，以識別可能需要進一步調查的潛在高磁碟使用量應用程式。</span><span class="sxs-lookup"><span data-stu-id="dcf4f-133">Highlights all new apps with high privilege permissions to identify potential high-footprint apps that may need further investigation.</span></span> <br><br> <span data-ttu-id="dcf4f-134">根據預設，此原則會標幟在過去 7 天內註冊並具有高範圍權限的所有應用程式。</span><span class="sxs-lookup"><span data-stu-id="dcf4f-134">By default, this policy will flag all apps registered within the last 7 days that have high-scoped permissions.</span></span> |
|||

### <a name="app-certification"></a><span data-ttu-id="dcf4f-135">應用程式認證</span><span class="sxs-lookup"><span data-stu-id="dcf4f-135">App certification</span></span>

<span data-ttu-id="dcf4f-136">應用程式控管包含這些範本，以產生應用程式認證的警示。</span><span class="sxs-lookup"><span data-stu-id="dcf4f-136">App governance includes these templates to generate alerts for app certification.</span></span>

| <span data-ttu-id="dcf4f-137">範本名稱</span><span class="sxs-lookup"><span data-stu-id="dcf4f-137">Template name</span></span> | <span data-ttu-id="dcf4f-138">描述</span><span class="sxs-lookup"><span data-stu-id="dcf4f-138">Description</span></span> |
|:-------|:-----|
| <span data-ttu-id="dcf4f-139">新的未認證應用程式</span><span class="sxs-lookup"><span data-stu-id="dcf4f-139">New uncertified app</span></span> | <span data-ttu-id="dcf4f-140">醒目提示尚未經過應用程式認證程序的新應用程式，以確保在租用戶中預期它的存在。</span><span class="sxs-lookup"><span data-stu-id="dcf4f-140">Highlights new apps that haven't been through the app certification process to ensure that they are expected in the tenant.</span></span> <br><br> <span data-ttu-id="dcf4f-141">根據預設，此原則會標幟在過去 7 天內註冊並尚未認證的所有應用程式。</span><span class="sxs-lookup"><span data-stu-id="dcf4f-141">By default, this policy will flag all apps that were registered in the last 7 days and are uncertified.</span></span> |
|||

## <a name="custom-app-policies"></a><span data-ttu-id="dcf4f-142">自訂應用程式原則</span><span class="sxs-lookup"><span data-stu-id="dcf4f-142">Custom app policies</span></span>

<span data-ttu-id="dcf4f-143">當您需要執行尚未由其中一個內建範本完成的工作時，請使用自訂應用程式原則。</span><span class="sxs-lookup"><span data-stu-id="dcf4f-143">Use a custom app policy when you need to do something not already done by one of the built-in templates.</span></span>

<span data-ttu-id="dcf4f-144">若要建立新自訂應用程式原則，請先選取 **[原則]** 頁面中的 **[建立新的]**。</span><span class="sxs-lookup"><span data-stu-id="dcf4f-144">To create a new custom app policy, first select **Create new** on the **Policies** page.</span></span> <span data-ttu-id="dcf4f-145">在 **[選擇應用程式原則範本頁面]** 上，選取 **[自訂]** 類別、**[自訂原則]** 範本，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="dcf4f-145">On the **Choose App policy template page**, select the **Custom** category, the **Custom policy** template, and then select **Next**.</span></span>

<span data-ttu-id="dcf4f-146">在 **[名稱與訂閱]** 頁面上，設定下列項目：</span><span class="sxs-lookup"><span data-stu-id="dcf4f-146">On the **Name and description** page, configure the following:</span></span>

- <span data-ttu-id="dcf4f-147">原則名稱</span><span class="sxs-lookup"><span data-stu-id="dcf4f-147">Policy Name</span></span>

- <span data-ttu-id="dcf4f-148">原則描述</span><span class="sxs-lookup"><span data-stu-id="dcf4f-148">Policy Description</span></span>

- <span data-ttu-id="dcf4f-149">選取設定此原則所產生警示嚴重性之原則嚴重性。</span><span class="sxs-lookup"><span data-stu-id="dcf4f-149">Select the policy severity, which sets the severity of alerts generated by this policy.</span></span>

  - <span data-ttu-id="dcf4f-150">高</span><span class="sxs-lookup"><span data-stu-id="dcf4f-150">High</span></span>
  - <span data-ttu-id="dcf4f-151">中</span><span class="sxs-lookup"><span data-stu-id="dcf4f-151">Medium</span></span>
  - <span data-ttu-id="dcf4f-152">低</span><span class="sxs-lookup"><span data-stu-id="dcf4f-152">Low</span></span>

<span data-ttu-id="dcf4f-153">在 **[選擇原則設定和條件]** 頁面上，針對 **[選擇此原則適用的應用程式]**，選取：</span><span class="sxs-lookup"><span data-stu-id="dcf4f-153">On the **Choose Policy settings and conditions** page, for **Choose which apps this policy is applicable for**, select:</span></span>

- <span data-ttu-id="dcf4f-154">所有應用程式</span><span class="sxs-lookup"><span data-stu-id="dcf4f-154">All Apps</span></span>
- <span data-ttu-id="dcf4f-155">選擇特定應用程式</span><span class="sxs-lookup"><span data-stu-id="dcf4f-155">Choose specific apps</span></span>

  <span data-ttu-id="dcf4f-156">窗格可讓您選取一或多個應用程式。</span><span class="sxs-lookup"><span data-stu-id="dcf4f-156">A pane allows you to select one or more apps.</span></span>
  <span data-ttu-id="dcf4f-157">選取 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="dcf4f-157">Select **Add**.</span></span>

<span data-ttu-id="dcf4f-158">選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="dcf4f-158">Select **Next**.</span></span>

<span data-ttu-id="dcf4f-159">在 **[選擇原則設定和條件]** 頁面上，選取 **[設定原則的新條件]**，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="dcf4f-159">On the **Choose Policy settings and conditions** page, select **Set new conditions for policy**, and then select **Next**.</span></span>

<span data-ttu-id="dcf4f-160">**[建立規則]** 窗格可讓您選取新規則的條件。</span><span class="sxs-lookup"><span data-stu-id="dcf4f-160">The **Create rule** pane allows you to select conditions for a new rule.</span></span> <span data-ttu-id="dcf4f-161">選取 **[新增條件]**，然後從條件清單中選取，然後指定條件的值。</span><span class="sxs-lookup"><span data-stu-id="dcf4f-161">Select **Add condition** and select from the list of conditions, and then specify the value of the condition.</span></span> <span data-ttu-id="dcf4f-162">您可以新增多個條件。</span><span class="sxs-lookup"><span data-stu-id="dcf4f-162">You can add multiple conditions.</span></span>

<span data-ttu-id="dcf4f-163">以下是自訂應用程式原則的可用條件。</span><span class="sxs-lookup"><span data-stu-id="dcf4f-163">Here are the available conditions for a custom app policy.</span></span>

|<span data-ttu-id="dcf4f-164">條件</span><span class="sxs-lookup"><span data-stu-id="dcf4f-164">Condition</span></span> | <span data-ttu-id="dcf4f-165">已接受條件值</span><span class="sxs-lookup"><span data-stu-id="dcf4f-165">Condition values accepted</span></span> | <span data-ttu-id="dcf4f-166">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="dcf4f-166">More information</span></span> |
|:-------|:-----|:-------|
| <span data-ttu-id="dcf4f-167">應用程式註冊年齡</span><span class="sxs-lookup"><span data-stu-id="dcf4f-167">App registration age</span></span> | <span data-ttu-id="dcf4f-168">在過去 X 天內</span><span class="sxs-lookup"><span data-stu-id="dcf4f-168">Within last X days</span></span> |  |
| <span data-ttu-id="dcf4f-169">應用程式認證</span><span class="sxs-lookup"><span data-stu-id="dcf4f-169">App certification</span></span> | <span data-ttu-id="dcf4f-170">基本合規性、MCAS 合規性或 N/A</span><span class="sxs-lookup"><span data-stu-id="dcf4f-170">Basic compliance, MCAS Compliance, or N/A</span></span> | [<span data-ttu-id="dcf4f-171">Microsoft 365 認證</span><span class="sxs-lookup"><span data-stu-id="dcf4f-171">Microsoft 365 Certification</span></span>](https://docs.microsoft.com/microsoft-365-app-certification/docs/enterprise-app-certification-guide) |
| <span data-ttu-id="dcf4f-172">發行者驗證</span><span class="sxs-lookup"><span data-stu-id="dcf4f-172">Publisher verification</span></span> | <span data-ttu-id="dcf4f-173">是或否</span><span class="sxs-lookup"><span data-stu-id="dcf4f-173">Yes or No</span></span> | [<span data-ttu-id="dcf4f-174">發行者驗證</span><span class="sxs-lookup"><span data-stu-id="dcf4f-174">Publisher Verification</span></span>](https://docs.microsoft.com/azure/active-directory/develop/publisher-verification-overview) |
| <span data-ttu-id="dcf4f-175">應用程式權限</span><span class="sxs-lookup"><span data-stu-id="dcf4f-175">Application Permission</span></span> | <span data-ttu-id="dcf4f-176">從清單中選取一或多個 API 權限。</span><span class="sxs-lookup"><span data-stu-id="dcf4f-176">Select one or more API permission from list</span></span> | [<span data-ttu-id="dcf4f-177">Microsoft Graph 權限參考資料</span><span class="sxs-lookup"><span data-stu-id="dcf4f-177">Microsoft Graph permissions reference</span></span>](https://docs.microsoft.com/graph/permissions-reference) |
| <span data-ttu-id="dcf4f-178">委派的權限</span><span class="sxs-lookup"><span data-stu-id="dcf4f-178">Delegated Permission</span></span> | <span data-ttu-id="dcf4f-179">從清單中選取一或多個 API 權限。</span><span class="sxs-lookup"><span data-stu-id="dcf4f-179">Select one or more API permission from list</span></span> | [<span data-ttu-id="dcf4f-180">Microsoft Graph 權限參考資料</span><span class="sxs-lookup"><span data-stu-id="dcf4f-180">Microsoft Graph permissions reference</span></span>](https://docs.microsoft.com/graph/permissions-reference) |
| <span data-ttu-id="dcf4f-181">高權限</span><span class="sxs-lookup"><span data-stu-id="dcf4f-181">High privilege</span></span> | <span data-ttu-id="dcf4f-182">是或否</span><span class="sxs-lookup"><span data-stu-id="dcf4f-182">Yes or No</span></span> | <span data-ttu-id="dcf4f-183">這是根據 MCAS 使用之相同邏輯的內部職銜。</span><span class="sxs-lookup"><span data-stu-id="dcf4f-183">This is an internal designation based on the same logic used by MCAS.</span></span> |
| <span data-ttu-id="dcf4f-184">權限過高的應用程式</span><span class="sxs-lookup"><span data-stu-id="dcf4f-184">Overprivileged app</span></span> | <span data-ttu-id="dcf4f-185">是或否</span><span class="sxs-lookup"><span data-stu-id="dcf4f-185">Yes or No</span></span> | <span data-ttu-id="dcf4f-186">授與比這些應用程式使用權限更多的應用程式。</span><span class="sxs-lookup"><span data-stu-id="dcf4f-186">Apps with more granted permissions than are being used by those apps.</span></span> |
| <span data-ttu-id="dcf4f-187">應用程式資料存取</span><span class="sxs-lookup"><span data-stu-id="dcf4f-187">App data access</span></span> | <span data-ttu-id="dcf4f-188">每小時資料存取大於 X GB</span><span class="sxs-lookup"><span data-stu-id="dcf4f-188">Greater than X GB data access per hour</span></span> |  |
| <span data-ttu-id="dcf4f-189">應用程式資料存取趨勢</span><span class="sxs-lookup"><span data-stu-id="dcf4f-189">App data access trend</span></span> | <span data-ttu-id="dcf4f-190">過去 7 天的資料使用量增加 X%</span><span class="sxs-lookup"><span data-stu-id="dcf4f-190">X% increase in data usage in last 7 days</span></span> |  |
| <span data-ttu-id="dcf4f-191">應用程式 API 存取</span><span class="sxs-lookup"><span data-stu-id="dcf4f-191">App API Access</span></span> | <span data-ttu-id="dcf4f-192">每小時 API 呼叫大於 X</span><span class="sxs-lookup"><span data-stu-id="dcf4f-192">Greater than X API calls per hour</span></span> |  |
| <span data-ttu-id="dcf4f-193">應用程式 API 存取趨勢</span><span class="sxs-lookup"><span data-stu-id="dcf4f-193">App API Access trend</span></span> | <span data-ttu-id="dcf4f-194">過去 7 天的 API 呼叫增加 X%</span><span class="sxs-lookup"><span data-stu-id="dcf4f-194">X% increase in API Calls in last 7 days</span></span>     |  |
| <span data-ttu-id="dcf4f-195">使用者已同意</span><span class="sxs-lookup"><span data-stu-id="dcf4f-195">Users consented</span></span> | <span data-ttu-id="dcf4f-196">(大於或小於) X 已同意的使用者</span><span class="sxs-lookup"><span data-stu-id="dcf4f-196">(Greater than or Less than) X consented users</span></span> |  |
| <span data-ttu-id="dcf4f-197">已同意的優先使用者</span><span class="sxs-lookup"><span data-stu-id="dcf4f-197">Priority user consented</span></span> | <span data-ttu-id="dcf4f-198">是或否</span><span class="sxs-lookup"><span data-stu-id="dcf4f-198">Yes or No</span></span> | <span data-ttu-id="dcf4f-199">具有[優先帳戶](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts)的使用者。</span><span class="sxs-lookup"><span data-stu-id="dcf4f-199">A user with a [priority account](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts).</span></span> |
| <span data-ttu-id="dcf4f-200">應用程式同意者</span><span class="sxs-lookup"><span data-stu-id="dcf4f-200">App consented by</span></span> | <span data-ttu-id="dcf4f-201">從清單中選取使用者</span><span class="sxs-lookup"><span data-stu-id="dcf4f-201">Select user(s) from list</span></span> |  |
| <span data-ttu-id="dcf4f-202">同意使用者的角色</span><span class="sxs-lookup"><span data-stu-id="dcf4f-202">Consenting user’s role</span></span> | <span data-ttu-id="dcf4f-203">選取一或多個：Teams 系統管理員、目錄讀取者、安全性讀取者、合規性系統管理員、安全性系統管理員、服務台系統管理員、SharePoint 系統管理員、Exchange 系統管理員、全域讀取者、全域系統管理員、合規性資料系統管理員、使用者系統管理員、服務支援系統管理員</span><span class="sxs-lookup"><span data-stu-id="dcf4f-203">Select one or more: Teams Administrator, Directory Readers, Security Reader, Compliance Administrator, Security Administrator, Helpdesk Administrator, SharePoint Administrator, Exchange Administrator, Global Reader, Global Administrator, Compliance Data Administrator, User Administrator, Service Support Administrator</span></span> | <span data-ttu-id="dcf4f-204">已允許多個選取項目。</span><span class="sxs-lookup"><span data-stu-id="dcf4f-204">Multiple selections allowed.</span></span> <br><br> <span data-ttu-id="dcf4f-205">此清單中應提供具有受指派成員的任何 Azure AD 角色。</span><span class="sxs-lookup"><span data-stu-id="dcf4f-205">Any Azure AD role with assigned member should be made available in this list.</span></span> |
| <span data-ttu-id="dcf4f-206">已存取的工作負載</span><span class="sxs-lookup"><span data-stu-id="dcf4f-206">Workload accessed</span></span> | <span data-ttu-id="dcf4f-207">OneDrive 和/或 SharePoint 和/或 Exchange</span><span class="sxs-lookup"><span data-stu-id="dcf4f-207">OneDrive and/or SharePoint and/or Exchange</span></span> | <span data-ttu-id="dcf4f-208">已允許多個選取項目。</span><span class="sxs-lookup"><span data-stu-id="dcf4f-208">Multiple selections allowed.</span></span> |
| <span data-ttu-id="dcf4f-209">錯誤率</span><span class="sxs-lookup"><span data-stu-id="dcf4f-209">Error rate</span></span> | <span data-ttu-id="dcf4f-210">過去 7 天的錯誤率大於 X%，其中 X 是系統管理員定義的值</span><span class="sxs-lookup"><span data-stu-id="dcf4f-210">Error rate is greater than X% in the last 7 days, where X is an admin-defined value</span></span> |  |
||||

<!--
NOTE TO WRITER: Replace X in the above table with correct values.
-->

<span data-ttu-id="dcf4f-211">必須符合所有指定的條件，才能套用此應用程式原則。</span><span class="sxs-lookup"><span data-stu-id="dcf4f-211">All of the specified conditions must be met for this app policy to apply.</span></span>

<span data-ttu-id="dcf4f-212">當您完成指定條件時，請選取 **[儲存]**，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="dcf4f-212">When you are done specifying the conditions, select **Save**, and then select **Next**.</span></span>

<span data-ttu-id="dcf4f-213">在 **[定義原則動作]** 頁面上，如果您希望應用程式控管在根據此原則產生警示時停用應用程式，請選取 **[停用應用程式]**，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="dcf4f-213">On the **Define Policy Actions** page, select **Disable app** if you want app governance to disable the app when an alert based on this policy is generated, and then select **Next**.</span></span>

<span data-ttu-id="dcf4f-214">在 **[定義原則狀態]** 頁面，選取其中一個選項：</span><span class="sxs-lookup"><span data-stu-id="dcf4f-214">On the **Define Policy Status** page, select one of these options:</span></span>

- <span data-ttu-id="dcf4f-215">**[稽核模式]**：會評估原則，但不會發生已設定的動作。</span><span class="sxs-lookup"><span data-stu-id="dcf4f-215">**Audit mode**: Policies are evaluated but configured actions will not occur.</span></span> <span data-ttu-id="dcf4f-216">稽核模式原則會顯示在清單中的 **[稽核]** 狀態。</span><span class="sxs-lookup"><span data-stu-id="dcf4f-216">Audit mode policies appear with the status of **Audit** in the list of policies.</span></span>
- <span data-ttu-id="dcf4f-217">**[作用中]**：會評估原則，並會發生已設定的動作。</span><span class="sxs-lookup"><span data-stu-id="dcf4f-217">**Active**: Policies are evaluated and configured actions will occur.</span></span>
- <span data-ttu-id="dcf4f-218">**[非作用中]**：不會評估原則，且不會發生已設定的動作。</span><span class="sxs-lookup"><span data-stu-id="dcf4f-218">**Inactive**: Policies are not evaluated and configured actions will not occur.</span></span>

<!--
## Configure a user-based policy

## Create an app metadata-based policy

Publish metadata-based policies

## Configure access permissions
-->

## <a name="test-and-monitor-your-new-app-policy"></a><span data-ttu-id="dcf4f-219">測試並監視您的新應用程式原則</span><span class="sxs-lookup"><span data-stu-id="dcf4f-219">Test and monitor your new app policy</span></span>

<span data-ttu-id="dcf4f-220">現在您的應用程式原則已建立，您應該在 **[原則]** 頁面上監視它，以確保它在測試期間登錄預期的作用中警示數目和警示總數。</span><span class="sxs-lookup"><span data-stu-id="dcf4f-220">Now that your app policy is created, you should monitor it on the **Policies** page to ensure it is registering an expected number of active alerts and total alerts during testing.</span></span> 

![在 Microsoft 365 合規性中心中，具有醒目提示原則的 MAPG 原則摘要頁面。](..\media\manage-app-protection-governance\mapg-cc-policies-policy.png)

<span data-ttu-id="dcf4f-222">如果警示數目是意外的低值，請編輯應用程式原則的設定，確保您在設定其狀態之前已正確設定。</span><span class="sxs-lookup"><span data-stu-id="dcf4f-222">If the number of alerts is an unexpectedly low value, edit the settings of the app policy to ensure you've configured it correctly before setting its status.</span></span>

<span data-ttu-id="dcf4f-223">以下是建立新原則、進行測試，然後讓新原則成為作用中之程序範例：</span><span class="sxs-lookup"><span data-stu-id="dcf4f-223">Here is an example of a process for creating a new policy, testing it, and then making it active:</span></span>

1. <span data-ttu-id="dcf4f-224">建立新原則，將嚴重性、應用程式、條件和動作設定為初始值，且狀態設定為 **[稽核模式]**。</span><span class="sxs-lookup"><span data-stu-id="dcf4f-224">Create the new policy with severity, apps, conditions, and actions set to initial values and the status set to **Audit mode**.</span></span>
2. <span data-ttu-id="dcf4f-225">檢查預期的行為，例如已產生的警示。</span><span class="sxs-lookup"><span data-stu-id="dcf4f-225">Check for expected behavior, such as alerts generated.</span></span>
3. <span data-ttu-id="dcf4f-226">如果不是預期的行為，請根據需要編輯原則應用程式、條件和動作設定，並返回步驟 2。</span><span class="sxs-lookup"><span data-stu-id="dcf4f-226">If the behavior is not expected, edit the policy apps, conditions, and action settings as needed and go back to step 2.</span></span>
4. <span data-ttu-id="dcf4f-227">如果這是預期的行為，請編輯該原則，並將其狀態變更為 **[作用中]**。</span><span class="sxs-lookup"><span data-stu-id="dcf4f-227">If the behavior is expected, edit the policy and change its status to **Active**.</span></span>

![建立應用程式原則工作流程](../media/manage-app-protection-governance/mapg-create-new-policy-process.png)

## <a name="next-step"></a><span data-ttu-id="dcf4f-229">下一個步驟</span><span class="sxs-lookup"><span data-stu-id="dcf4f-229">Next step</span></span>

[<span data-ttu-id="dcf4f-230">管理您的應用程式原則。</span><span class="sxs-lookup"><span data-stu-id="dcf4f-230">Manage your app policies.</span></span>](app-governance-app-policies-manage.md)
