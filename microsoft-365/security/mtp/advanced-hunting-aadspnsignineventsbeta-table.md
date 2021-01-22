---
title: 進位搜尋架構中的 AADSpnSignInEventsBeta 資料表
description: 瞭解與 Azure Active Directory 服務主體及進位搜尋架構的受管理身分識別登錄事件資料表相關聯的資訊
keywords: 進一步搜尋、威脅搜尋、網路威脅搜尋、Microsoft 威脅防護、microsoft 365、mtp、m365、搜尋、查詢、遙測、架構參考、kusto、資料表、資料行、資料類型、描述、警示資訊、警示、實體、證據、檔案、IP 位址、裝置、電腦、使用者、帳戶、身分識別、AAD
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 172c400df3adea70a2e2d2e37547fa39e0d3b9cf
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928615"
---
# <a name="aadspnsignineventsbeta"></a><span data-ttu-id="0d772-104">AADSpnSignInEventsBeta</span><span class="sxs-lookup"><span data-stu-id="0d772-104">AADSpnSignInEventsBeta</span></span>

<span data-ttu-id="0d772-105">適用於：</span><span class="sxs-lookup"><span data-stu-id="0d772-105">**Applies to:**</span></span>

- <span data-ttu-id="0d772-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0d772-106">Microsoft 365 Defender</span></span>

>[!IMPORTANT]
> <span data-ttu-id="0d772-107">資料表目前為 Beta 版，目前提供短期版本，讓您搜尋 `AADSpnSignInEventsBeta` Azure Active Directory (AAD) 服務主體及受管理的身分識別登錄事件。</span><span class="sxs-lookup"><span data-stu-id="0d772-107">The `AADSpnSignInEventsBeta` table is currently in beta and is being offered on a short-term basis to allow you to hunt through Azure Active Directory (AAD) service principal and managed identity sign-in events.</span></span> <span data-ttu-id="0d772-108">我們最終會移動所有登錄架構資訊至 `IdentityLogonEvents` 資料表。</span><span class="sxs-lookup"><span data-stu-id="0d772-108">We will eventually move all sign-in schema information to the `IdentityLogonEvents` table.</span></span><br><br>
> <span data-ttu-id="0d772-109">可透過 Azure 資訊安全中心整合的 Microsoft Defender 端點解決方案存取 Microsoft 365 Defender，但沒有 Microsoft Defender for Office、Microsoft Defender for Identity 或 Microsoft Cloud App 安全性授權的客戶，將無法查看此架構。</span><span class="sxs-lookup"><span data-stu-id="0d772-109">Customers who can access Microsoft 365 Defender through the Azure Security Center’s integrated Microsoft Defender for Endpoint solution, but do not have licenses for Microsoft Defender for Office, Microsoft Defender for Identity, or Microsoft Cloud App Security, will not be able to view this schema.</span></span> 



<span data-ttu-id="0d772-110">進 `AADSpnSignInEventsBeta` 位搜尋架構中的資料表包含有關 Azure Active Directory 服務主體及受管理身分識別登錄的資訊。您可以在 [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/reports-monitoring/concept-all-sign-ins)的登錄活動報告中深入瞭解不同類型的登錄 - 預覽。</span><span class="sxs-lookup"><span data-stu-id="0d772-110">The `AADSpnSignInEventsBeta` table in the advanced hunting schema contains information about Azure Active Directory service principal and managed identity sign-ins. You can learn more about the different kinds of sign-ins in [Azure Active Directory sign-in activity reports - preview](https://docs.microsoft.com/azure/active-directory/reports-monitoring/concept-all-sign-ins).</span></span>

<span data-ttu-id="0d772-111">使用這個參考來建立從表格取回之資訊的查詢。</span><span class="sxs-lookup"><span data-stu-id="0d772-111">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="0d772-112">如需進階搜捕結構描述中其他表格的資訊，請參閱 [進階搜捕參考](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-reference) (部分內容為機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="0d772-112">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-reference).</span></span>





| <span data-ttu-id="0d772-113">資料行名稱</span><span class="sxs-lookup"><span data-stu-id="0d772-113">Column name</span></span>     | <span data-ttu-id="0d772-114">資料類型</span><span class="sxs-lookup"><span data-stu-id="0d772-114">Data type</span></span> | <span data-ttu-id="0d772-115">描述</span><span class="sxs-lookup"><span data-stu-id="0d772-115">Description</span></span>   |
| ----- | ----- | ---- |
| `Timestamp` | <span data-ttu-id="0d772-116">datetime</span><span class="sxs-lookup"><span data-stu-id="0d772-116">datetime</span></span>      | <span data-ttu-id="0d772-117">記錄的產生日期和時間</span><span class="sxs-lookup"><span data-stu-id="0d772-117">Date and time when the record was generated</span></span>                                                                                                     |
| `Application`          | <span data-ttu-id="0d772-118">string</span><span class="sxs-lookup"><span data-stu-id="0d772-118">string</span></span>        | <span data-ttu-id="0d772-119">執行錄製動作的應用程式</span><span class="sxs-lookup"><span data-stu-id="0d772-119">Application that performed the recorded action</span></span>                                                                                                   |
| `ApplicationId`        | <span data-ttu-id="0d772-120">string</span><span class="sxs-lookup"><span data-stu-id="0d772-120">string</span></span>        | <span data-ttu-id="0d772-121">應用程式的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="0d772-121">Unique identifier for the application</span></span>                                                                                                           |
| `IsManagedIdentity`    | <span data-ttu-id="0d772-122">布林值</span><span class="sxs-lookup"><span data-stu-id="0d772-122">boolean</span></span>       | <span data-ttu-id="0d772-123">指出該登錄是否由受管理的身分識別初始化</span><span class="sxs-lookup"><span data-stu-id="0d772-123">Indicates whether the sign-in was initiated by a managed identity</span></span>                                                                               |
| `ErrorCode`            | <span data-ttu-id="0d772-124">int</span><span class="sxs-lookup"><span data-stu-id="0d772-124">int</span></span>        | <span data-ttu-id="0d772-125">發生登錄錯誤時，包含錯誤碼。</span><span class="sxs-lookup"><span data-stu-id="0d772-125">Contains the error code if a sign-in error occurs.</span></span> <span data-ttu-id="0d772-126">若要尋找特定錯誤碼的描述，請流覽 <https://aka.ms/AADsigninsErrorCodes> 。</span><span class="sxs-lookup"><span data-stu-id="0d772-126">To find a description of a specific error code, visit <https://aka.ms/AADsigninsErrorCodes>.</span></span> |
| `CorrelationId`        | <span data-ttu-id="0d772-127">string</span><span class="sxs-lookup"><span data-stu-id="0d772-127">string</span></span>        | <span data-ttu-id="0d772-128">此登錄事件的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="0d772-128">Unique identifier of the sign-in event</span></span>                                                                                                          |
| `ServicePrincipalName` | <span data-ttu-id="0d772-129">string</span><span class="sxs-lookup"><span data-stu-id="0d772-129">string</span></span>        | <span data-ttu-id="0d772-130">初始化該登錄的服務主體名稱</span><span class="sxs-lookup"><span data-stu-id="0d772-130">Name of the service principal that initiated the sign-in</span></span>                                                                                        |
| `ServicePrincipalId`   | <span data-ttu-id="0d772-131">string</span><span class="sxs-lookup"><span data-stu-id="0d772-131">string</span></span>        | <span data-ttu-id="0d772-132">初始化登錄的服務主體的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="0d772-132">Unique identifier of the service principal that initiated the sign-in</span></span>                                                                           |
| `ResourceDisplayName`  | <span data-ttu-id="0d772-133">string</span><span class="sxs-lookup"><span data-stu-id="0d772-133">string</span></span>        | <span data-ttu-id="0d772-134">顯示已存取資源的名稱</span><span class="sxs-lookup"><span data-stu-id="0d772-134">Display name of the resource accessed</span></span>                                                                                                           |
| `ResourceId`           | <span data-ttu-id="0d772-135">string</span><span class="sxs-lookup"><span data-stu-id="0d772-135">string</span></span>        | <span data-ttu-id="0d772-136">已存取資源的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="0d772-136">Unique identifier of the resource accessed</span></span>                                                                                                      |
| `ResourceTenantId`     | <span data-ttu-id="0d772-137">string</span><span class="sxs-lookup"><span data-stu-id="0d772-137">string</span></span>        | <span data-ttu-id="0d772-138">存取資源之租使用者的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="0d772-138">Unique identifier of the tenant of the resource accessed</span></span>                                                                                        |
| `IPAddress`            | <span data-ttu-id="0d772-139">string</span><span class="sxs-lookup"><span data-stu-id="0d772-139">string</span></span>        | <span data-ttu-id="0d772-140">指派給端點的 IP 位址，用於相關網路通訊期間</span><span class="sxs-lookup"><span data-stu-id="0d772-140">IP address assigned to the endpoint and used during related network communications</span></span>                                                              |
| `CountryCode`          | <span data-ttu-id="0d772-141">string</span><span class="sxs-lookup"><span data-stu-id="0d772-141">string</span></span>        | <span data-ttu-id="0d772-142">兩個字母的代碼，指出用戶端 IP 位址已異地定位的國家/地區</span><span class="sxs-lookup"><span data-stu-id="0d772-142">Two-letter code indicating the country where the client IP address is geolocated</span></span>                                                                |
| `State`                | <span data-ttu-id="0d772-143">string</span><span class="sxs-lookup"><span data-stu-id="0d772-143">string</span></span>        | <span data-ttu-id="0d772-144">發生此登錄的州/省 （如果可用）</span><span class="sxs-lookup"><span data-stu-id="0d772-144">State where the sign-in occurred, if available</span></span>                                                                                                  |
| `City`                 | <span data-ttu-id="0d772-145">string</span><span class="sxs-lookup"><span data-stu-id="0d772-145">string</span></span>        | <span data-ttu-id="0d772-146">帳戶使用者所在的城市</span><span class="sxs-lookup"><span data-stu-id="0d772-146">City where the account user is located</span></span>                                                                                                          |
| `Latitude`             | <span data-ttu-id="0d772-147">string</span><span class="sxs-lookup"><span data-stu-id="0d772-147">string</span></span>        | <span data-ttu-id="0d772-148">簽署位置的北到南座標</span><span class="sxs-lookup"><span data-stu-id="0d772-148">The north to south coordinates of the sign-in location</span></span>                                                                                          |
| `Longitude`            | <span data-ttu-id="0d772-149">string</span><span class="sxs-lookup"><span data-stu-id="0d772-149">string</span></span>        | <span data-ttu-id="0d772-150">簽署位置的東部至西座標</span><span class="sxs-lookup"><span data-stu-id="0d772-150">The east to west coordinates of the sign-in location</span></span>                                                                                            |
| `RequestId`            | <span data-ttu-id="0d772-151">string</span><span class="sxs-lookup"><span data-stu-id="0d772-151">string</span></span>        | <span data-ttu-id="0d772-152">要求的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="0d772-152">Unique identifier of the request</span></span>                                                                                                                |
|`ReportId` | <span data-ttu-id="0d772-153">string</span><span class="sxs-lookup"><span data-stu-id="0d772-153">string</span></span> | <span data-ttu-id="0d772-154">事件的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="0d772-154">Unique identifier for the event</span></span> | 

 

## <a name="related-articles"></a><span data-ttu-id="0d772-155">相關文章</span><span class="sxs-lookup"><span data-stu-id="0d772-155">Related articles</span></span>

-   [<span data-ttu-id="0d772-156">AADSignInEventsBeta</span><span class="sxs-lookup"><span data-stu-id="0d772-156">AADSignInEventsBeta</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/advanced-hunting-aadsignineventsbeta-table)
-   [<span data-ttu-id="0d772-157">進階搜捕概觀</span><span class="sxs-lookup"><span data-stu-id="0d772-157">Advanced hunting overview</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)
-   [<span data-ttu-id="0d772-158">了解查詢語言</span><span class="sxs-lookup"><span data-stu-id="0d772-158">Learn the query language</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-query-language)
-   [<span data-ttu-id="0d772-159">了解結構描述</span><span class="sxs-lookup"><span data-stu-id="0d772-159">Understand the schema</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference)

