---
title: 檢視您的應用程式
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
description: 檢視您的應用程式。
ms.openlocfilehash: 48a1a2140a3b59091796ca013a12eeefb8a284b9
ms.sourcegitcommit: 41c7f7bd5c808ee5ceca0f6efe13d4e67da0262b
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420063"
---
# <a name="view-your-apps"></a><span data-ttu-id="7e6eb-103">檢視您的應用程式</span><span class="sxs-lookup"><span data-stu-id="7e6eb-103">View your apps</span></span>

><span data-ttu-id="7e6eb-104">*[Microsoft 365 安全性與合規性的授權指引](https://aka.ms/ComplianceSD)。*</span><span class="sxs-lookup"><span data-stu-id="7e6eb-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="7e6eb-105">Microsoft 應用程式管理可讓您快速深入瞭解您租用戶中的 Microsoft 365 應用程式。</span><span class="sxs-lookup"><span data-stu-id="7e6eb-105">Microsoft app governance allows you to quickly gain deep insights into the Microsoft 365 apps in your tenant.</span></span> <span data-ttu-id="7e6eb-106">例如，您可以：</span><span class="sxs-lookup"><span data-stu-id="7e6eb-106">For example, you can see:</span></span>

- <span data-ttu-id="7e6eb-107">租用戶中啟用 OAuth 的應用程式清單，這些應用程式使用 Microsoft Graph API，以及相關的應用程式中繼資料和使用狀況資料。</span><span class="sxs-lookup"><span data-stu-id="7e6eb-107">A list of OAuth-enabled apps in the tenant that use the Microsoft Graph API, together with relevant app metadata and usage data.</span></span>
- <span data-ttu-id="7e6eb-108">選取清單中的應用程式，以包含更深入的深入解析和資訊的應用程式詳細資料。</span><span class="sxs-lookup"><span data-stu-id="7e6eb-108">App details with deeper insights and information by selecting an app in the list.</span></span>

## <a name="getting-a-list-of-all-the-apps-in-your-tenant"></a><span data-ttu-id="7e6eb-109">取得租用戶中所有應用程式的清單</span><span class="sxs-lookup"><span data-stu-id="7e6eb-109">Getting a list of all the apps in your tenant</span></span>

<span data-ttu-id="7e6eb-110">如需租用戶中的應用程式摘要，請前往 **Microsoft 365 合規性中心 > 應用程式保護與控管 > 應用程式**。</span><span class="sxs-lookup"><span data-stu-id="7e6eb-110">For a summary of apps in your tenant, go to **Microsoft 365 Compliance Center > App protection & governance > Apps**.</span></span>

![Microsoft 365 合規性中心的 MAPG 應用程式摘要頁面。](..\media\manage-app-protection-governance\mapg-cc-apps.png)

>[!Note]
> <span data-ttu-id="7e6eb-112">您的登入帳戶必須具有 [這些角色](app-governance-get-started.md#administrator-roles) 的其中一個，才能檢視任何應用程式控管資料。</span><span class="sxs-lookup"><span data-stu-id="7e6eb-112">Your sign-in account must have one of [these roles](app-governance-get-started.md#administrator-roles) to view any app governance data.</span></span>
>

<span data-ttu-id="7e6eb-113">您將看到應用程式清單和這項資訊：</span><span class="sxs-lookup"><span data-stu-id="7e6eb-113">You will see a list of apps and this information:</span></span>

- <span data-ttu-id="7e6eb-114">應用程式名稱</span><span class="sxs-lookup"><span data-stu-id="7e6eb-114">App Name</span></span>
- <span data-ttu-id="7e6eb-115">發行者</span><span class="sxs-lookup"><span data-stu-id="7e6eb-115">Publisher</span></span>
- <span data-ttu-id="7e6eb-116">應用程式認證</span><span class="sxs-lookup"><span data-stu-id="7e6eb-116">App certification</span></span>

  <span data-ttu-id="7e6eb-117">指出此應用程式是否與 Microsoft 技術相容、符合雲端應用程式安全性最佳做法，並受 Microsoft 支援。</span><span class="sxs-lookup"><span data-stu-id="7e6eb-117">Indicates whether the app is compatible with Microsoft technologies, compliant with cloud app security best practices, and supported by Microsoft.</span></span>

- <span data-ttu-id="7e6eb-118">上次修改日期</span><span class="sxs-lookup"><span data-stu-id="7e6eb-118">Last modified</span></span>

  <span data-ttu-id="7e6eb-119">顯示用戶端中已安裝應用程式控管的日期（如果該日期比上次修改應用程式的日期還要新）。</span><span class="sxs-lookup"><span data-stu-id="7e6eb-119">Shows the date app governance was installed in client if that date is more recent than the date the app was last modified.</span></span>

- <span data-ttu-id="7e6eb-120">安裝日期</span><span class="sxs-lookup"><span data-stu-id="7e6eb-120">Date installed</span></span>
- <span data-ttu-id="7e6eb-121">權限等級</span><span class="sxs-lookup"><span data-stu-id="7e6eb-121">Privilege level</span></span>
- <span data-ttu-id="7e6eb-122">使用者數目</span><span class="sxs-lookup"><span data-stu-id="7e6eb-122">Number of users</span></span>
- <span data-ttu-id="7e6eb-123">資料存取</span><span class="sxs-lookup"><span data-stu-id="7e6eb-123">Data access</span></span>

  <span data-ttu-id="7e6eb-124">此應用程式過去一天在租用戶中的資料上傳和下載總和以及前一天的變更。</span><span class="sxs-lookup"><span data-stu-id="7e6eb-124">The sum of the app’s data upload and download in the tenant over the last day, along with the change over the prior day.</span></span>

<span data-ttu-id="7e6eb-125">應用程式控管會根據預設 **應用程式名稱** 排序此份應用程式清單。</span><span class="sxs-lookup"><span data-stu-id="7e6eb-125">App governance sorts the app list by **App name** by default.</span></span> <span data-ttu-id="7e6eb-126">若要根據其他應用程屬性排序此清單，請選取屬性名稱。</span><span class="sxs-lookup"><span data-stu-id="7e6eb-126">To sort the list by another app attribute, select the attribute name.</span></span>

<span data-ttu-id="7e6eb-127">您也可以選取 **搜尋** 以根據名稱搜尋應用程式。</span><span class="sxs-lookup"><span data-stu-id="7e6eb-127">You can also select **Search** to search for an app by name.</span></span>

## <a name="getting-detailed-information-on-an-app"></a><span data-ttu-id="7e6eb-128">取得應用程式的詳細資訊</span><span class="sxs-lookup"><span data-stu-id="7e6eb-128">Getting detailed information on an app</span></span>

<span data-ttu-id="7e6eb-129">如需您租用戶中的特定應用程式詳細資訊，請前往 \*\*Microsoft 365 合規性中心 > 應用程式控管 > 應用程式頁面 > \*應用程式名稱\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7e6eb-129">For detailed information on a specific app in your tenant, go to \*\*Microsoft 365 Compliance Center > App governance > Apps page > \*app name\*\*\*.</span></span>

![Microsoft 365 合規性中心的應用程式控管應用程式詳細資料窗格](..\media\manage-app-protection-governance\mapg-cc-apps-app.png)

<span data-ttu-id="7e6eb-131">應用程式詳細資料窗格提供這些定位字元的其他資訊：</span><span class="sxs-lookup"><span data-stu-id="7e6eb-131">The app details pane provides additional information on these tabs:</span></span>

| <span data-ttu-id="7e6eb-132">索引標籤名稱</span><span class="sxs-lookup"><span data-stu-id="7e6eb-132">Tab name</span></span> | <span data-ttu-id="7e6eb-133">說明</span><span class="sxs-lookup"><span data-stu-id="7e6eb-133">Description</span></span> |
|:-------|:-----|
| <span data-ttu-id="7e6eb-134">詳細資料</span><span class="sxs-lookup"><span data-stu-id="7e6eb-134">Details</span></span> | <span data-ttu-id="7e6eb-135">查看應用程式上的其他資料，例如第一次同意的日期與應用程式識別碼。</span><span class="sxs-lookup"><span data-stu-id="7e6eb-135">See additional data on the app such as the date first consented and the App ID.</span></span> <span data-ttu-id="7e6eb-136">若要查看在 Azure AD 中註冊的應用程式屬性，請選取 **在 Azure AD 中選取**。</span><span class="sxs-lookup"><span data-stu-id="7e6eb-136">To see the properties of the app as registered in Azure AD, select **View app in Azure AD**.</span></span> |
| <span data-ttu-id="7e6eb-137">使用情況</span><span class="sxs-lookup"><span data-stu-id="7e6eb-137">Usage</span></span> | <span data-ttu-id="7e6eb-138">查看租用戶中由應用程式存取的資料、繪製資料使用量，以及顯示前 \<x> 名使用者與具有 [優先帳戶](/microsoft-365/admin/setup/priority-accounts) 的使用者。</span><span class="sxs-lookup"><span data-stu-id="7e6eb-138">See the data accessed by the app in the tenant, plot the data usage, and show usage by the top \<x> users and users with [priority accounts](/microsoft-365/admin/setup/priority-accounts).</span></span> |
| <span data-ttu-id="7e6eb-139">使用者</span><span class="sxs-lookup"><span data-stu-id="7e6eb-139">Users</span></span> | <span data-ttu-id="7e6eb-140">查看正在使用應用程式的使用者清單、無論他們是否為優先帳戶，以及下載和上傳的資料量。</span><span class="sxs-lookup"><span data-stu-id="7e6eb-140">See a list of users who are using the app, whether they are a priority account, and the amount of data downloaded and uploaded.</span></span> |
| <span data-ttu-id="7e6eb-141">權限</span><span class="sxs-lookup"><span data-stu-id="7e6eb-141">Permissions</span></span> | <span data-ttu-id="7e6eb-142">請參閱由應用程式授予及使用的權限摘要，以及特定權限的清單。</span><span class="sxs-lookup"><span data-stu-id="7e6eb-142">See a summary of the permissions granted to and used by the app and the list of specific permissions.</span></span> <span data-ttu-id="7e6eb-143">請參閱 [Microsoft Graph 權限參考](/graph/permissions-reference) 以取得詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="7e6eb-143">See the [Microsoft Graph permissions reference](/graph/permissions-reference) for more information.</span></span> |
|||

<span data-ttu-id="7e6eb-144">針對已啟用的應用程式，還有一個 **停用應用程式** 控制項以停用所選應用程式的使用，以及一個 **啟用應用程式** 控制項以啟用遭停用的應用程式。</span><span class="sxs-lookup"><span data-stu-id="7e6eb-144">For an enabled app, there is also a **Disable app** control to disable the use of the selected app and an **Enable app** control to enable the use of the disabled app.</span></span> <span data-ttu-id="7e6eb-145">這些動作需要這些 [系統管理員角色](app-governance-get-started.md#administrator-roles)：</span><span class="sxs-lookup"><span data-stu-id="7e6eb-145">These actions require these [administrator roles](app-governance-get-started.md#administrator-roles):</span></span>

- <span data-ttu-id="7e6eb-146">合規性系統管理員</span><span class="sxs-lookup"><span data-stu-id="7e6eb-146">Compliance Administrator</span></span>
- <span data-ttu-id="7e6eb-147">全域系統管理員</span><span class="sxs-lookup"><span data-stu-id="7e6eb-147">Global Administrator</span></span>
- <span data-ttu-id="7e6eb-148">安全性系統管理員</span><span class="sxs-lookup"><span data-stu-id="7e6eb-148">Security Administrator</span></span>
- <span data-ttu-id="7e6eb-149">安全性操作員</span><span class="sxs-lookup"><span data-stu-id="7e6eb-149">Security Operator</span></span>

## <a name="next-step"></a><span data-ttu-id="7e6eb-150">後續步驟</span><span class="sxs-lookup"><span data-stu-id="7e6eb-150">Next step</span></span>

<span data-ttu-id="7e6eb-151">[判斷您的整體應用程式合規性狀態](app-governance-visibility-insights-compliance-posture.md)。</span><span class="sxs-lookup"><span data-stu-id="7e6eb-151">[Determine your overall app compliance posture](app-governance-visibility-insights-compliance-posture.md).</span></span>
