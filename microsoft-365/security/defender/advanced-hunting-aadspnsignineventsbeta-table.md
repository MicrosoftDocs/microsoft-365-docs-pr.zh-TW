---
title: Advanced 搜尋架構中的 AADSpnSignInEventsBeta 表格
description: 深入瞭解與高級搜尋架構的 Azure Active Directory 服務主體及受管理身分識別登入事件表格相關的資訊
keywords: 高級搜尋，威脅搜尋，網路威脅搜尋，Microsoft 365 Defender，Microsoft 365，m365，search，query，遙測，schema reference，kusto，table，column，data type，file，IP address，device，machine，使用者，account，identity，AAD
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: f74972bcd5d0ddaab58d82b72a55991fda44e3b1
ms.sourcegitcommit: 9541d5e6720a06327dc785e3ad7e8fb11246fd72
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2021
ms.locfileid: "52583541"
---
# <a name="aadspnsignineventsbeta"></a><span data-ttu-id="eb5a3-104">AADSpnSignInEventsBeta</span><span class="sxs-lookup"><span data-stu-id="eb5a3-104">AADSpnSignInEventsBeta</span></span>

<span data-ttu-id="eb5a3-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="eb5a3-105">**Applies to:**</span></span>

- <span data-ttu-id="eb5a3-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="eb5a3-106">Microsoft 365 Defender</span></span>

>[!IMPORTANT]
> <span data-ttu-id="eb5a3-107">`AADSpnSignInEventsBeta`資料表目前在 Beta 中，並在短期內提供，以供您尋找 Azure Active Directory (AAD) 服務主體和受管理身分識別登入事件。</span><span class="sxs-lookup"><span data-stu-id="eb5a3-107">The `AADSpnSignInEventsBeta` table is currently in beta and is being offered on a short-term basis to allow you to hunt through Azure Active Directory (AAD) service principal and managed identity sign-in events.</span></span> <span data-ttu-id="eb5a3-108">我們最後會將所有登入架構資訊移至 `IdentityLogonEvents` 表格。</span><span class="sxs-lookup"><span data-stu-id="eb5a3-108">We will eventually move all sign-in schema information to the `IdentityLogonEvents` table.</span></span>



<span data-ttu-id="eb5a3-109">[！附注] `AADSpnSignInEventsBeta` 高級搜尋架構中的表格包含 Azure Active Directory 服務主體和受管理身分識別登入的相關資訊。您可以在[Azure Active Directory 登入活動報告-預覽](/azure/active-directory/reports-monitoring/concept-all-sign-ins)中深入瞭解不同的登入類型。</span><span class="sxs-lookup"><span data-stu-id="eb5a3-109">The `AADSpnSignInEventsBeta` table in the advanced hunting schema contains information about Azure Active Directory service principal and managed identity sign-ins. You can learn more about the different kinds of sign-ins in [Azure Active Directory sign-in activity reports - preview](/azure/active-directory/reports-monitoring/concept-all-sign-ins).</span></span>

<span data-ttu-id="eb5a3-110">使用這個參考來建立從表格取回之資訊的查詢。</span><span class="sxs-lookup"><span data-stu-id="eb5a3-110">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="eb5a3-111">如需進階搜捕結構描述中其他表格的資訊，請參閱 [進階搜捕參考](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-reference) (部分內容為機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="eb5a3-111">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-reference).</span></span>





| <span data-ttu-id="eb5a3-112">資料行名稱</span><span class="sxs-lookup"><span data-stu-id="eb5a3-112">Column name</span></span>     | <span data-ttu-id="eb5a3-113">資料類型</span><span class="sxs-lookup"><span data-stu-id="eb5a3-113">Data type</span></span> | <span data-ttu-id="eb5a3-114">描述</span><span class="sxs-lookup"><span data-stu-id="eb5a3-114">Description</span></span>   |
| ----- | ----- | ---- |
| `Timestamp` | <span data-ttu-id="eb5a3-115">datetime</span><span class="sxs-lookup"><span data-stu-id="eb5a3-115">datetime</span></span>      | <span data-ttu-id="eb5a3-116">記錄的產生日期和時間</span><span class="sxs-lookup"><span data-stu-id="eb5a3-116">Date and time when the record was generated</span></span>                                                                                                     |
| `Application`          | <span data-ttu-id="eb5a3-117">string</span><span class="sxs-lookup"><span data-stu-id="eb5a3-117">string</span></span>        | <span data-ttu-id="eb5a3-118">執行錄製動作的應用程式</span><span class="sxs-lookup"><span data-stu-id="eb5a3-118">Application that performed the recorded action</span></span>                                                                                                   |
| `ApplicationId`        | <span data-ttu-id="eb5a3-119">string</span><span class="sxs-lookup"><span data-stu-id="eb5a3-119">string</span></span>        | <span data-ttu-id="eb5a3-120">應用程式的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="eb5a3-120">Unique identifier for the application</span></span>                                                                                                           |
| `IsManagedIdentity`    | <span data-ttu-id="eb5a3-121">布林值</span><span class="sxs-lookup"><span data-stu-id="eb5a3-121">boolean</span></span>       | <span data-ttu-id="eb5a3-122">指出登入是否是由受管理身分識別所啟動</span><span class="sxs-lookup"><span data-stu-id="eb5a3-122">Indicates whether the sign-in was initiated by a managed identity</span></span>                                                                               |
| `ErrorCode`            | <span data-ttu-id="eb5a3-123">int</span><span class="sxs-lookup"><span data-stu-id="eb5a3-123">int</span></span>        | <span data-ttu-id="eb5a3-124">如果發生登入錯誤，則會包含錯誤代碼。</span><span class="sxs-lookup"><span data-stu-id="eb5a3-124">Contains the error code if a sign-in error occurs.</span></span> <span data-ttu-id="eb5a3-125">若要尋找特定錯誤碼的描述，請造訪 <https://aka.ms/AADsigninsErrorCodes> 。</span><span class="sxs-lookup"><span data-stu-id="eb5a3-125">To find a description of a specific error code, visit <https://aka.ms/AADsigninsErrorCodes>.</span></span> |
| `CorrelationId`        | <span data-ttu-id="eb5a3-126">string</span><span class="sxs-lookup"><span data-stu-id="eb5a3-126">string</span></span>        | <span data-ttu-id="eb5a3-127">登入事件的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="eb5a3-127">Unique identifier of the sign-in event</span></span>                                                                                                          |
| `ServicePrincipalName` | <span data-ttu-id="eb5a3-128">string</span><span class="sxs-lookup"><span data-stu-id="eb5a3-128">string</span></span>        | <span data-ttu-id="eb5a3-129">啟動登入的服務主體名稱</span><span class="sxs-lookup"><span data-stu-id="eb5a3-129">Name of the service principal that initiated the sign-in</span></span>                                                                                        |
| `ServicePrincipalId`   | <span data-ttu-id="eb5a3-130">string</span><span class="sxs-lookup"><span data-stu-id="eb5a3-130">string</span></span>        | <span data-ttu-id="eb5a3-131">啟動登入之服務主體的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="eb5a3-131">Unique identifier of the service principal that initiated the sign-in</span></span>                                                                           |
| `ResourceDisplayName`  | <span data-ttu-id="eb5a3-132">string</span><span class="sxs-lookup"><span data-stu-id="eb5a3-132">string</span></span>        | <span data-ttu-id="eb5a3-133">存取資源的顯示名稱</span><span class="sxs-lookup"><span data-stu-id="eb5a3-133">Display name of the resource accessed</span></span>                                                                                                           |
| `ResourceId`           | <span data-ttu-id="eb5a3-134">string</span><span class="sxs-lookup"><span data-stu-id="eb5a3-134">string</span></span>        | <span data-ttu-id="eb5a3-135">存取資源的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="eb5a3-135">Unique identifier of the resource accessed</span></span>                                                                                                      |
| `ResourceTenantId`     | <span data-ttu-id="eb5a3-136">string</span><span class="sxs-lookup"><span data-stu-id="eb5a3-136">string</span></span>        | <span data-ttu-id="eb5a3-137">存取資源租使用者的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="eb5a3-137">Unique identifier of the tenant of the resource accessed</span></span>                                                                                        |
| `IPAddress`            | <span data-ttu-id="eb5a3-138">string</span><span class="sxs-lookup"><span data-stu-id="eb5a3-138">string</span></span>        | <span data-ttu-id="eb5a3-139">指派給端點的 IP 位址，並在相關的網路通訊期間使用</span><span class="sxs-lookup"><span data-stu-id="eb5a3-139">IP address assigned to the endpoint and used during related network communications</span></span>                                                              |
| `Country`          | <span data-ttu-id="eb5a3-140">string</span><span class="sxs-lookup"><span data-stu-id="eb5a3-140">string</span></span>        | <span data-ttu-id="eb5a3-141">兩個字母的代碼，指出用戶端 IP 位址為 geolocated 的國家/地區</span><span class="sxs-lookup"><span data-stu-id="eb5a3-141">Two-letter code indicating the country where the client IP address is geolocated</span></span>                                                                |
| `State`                | <span data-ttu-id="eb5a3-142">string</span><span class="sxs-lookup"><span data-stu-id="eb5a3-142">string</span></span>        | <span data-ttu-id="eb5a3-143">發生登入的狀態（若有的話）</span><span class="sxs-lookup"><span data-stu-id="eb5a3-143">State where the sign-in occurred, if available</span></span>                                                                                                  |
| `City`                 | <span data-ttu-id="eb5a3-144">string</span><span class="sxs-lookup"><span data-stu-id="eb5a3-144">string</span></span>        | <span data-ttu-id="eb5a3-145">帳戶使用者所在的城市</span><span class="sxs-lookup"><span data-stu-id="eb5a3-145">City where the account user is located</span></span>                                                                                                          |
| `Latitude`             | <span data-ttu-id="eb5a3-146">string</span><span class="sxs-lookup"><span data-stu-id="eb5a3-146">string</span></span>        | <span data-ttu-id="eb5a3-147">登入位置的北到南部座標</span><span class="sxs-lookup"><span data-stu-id="eb5a3-147">The north to south coordinates of the sign-in location</span></span>                                                                                          |
| `Longitude`            | <span data-ttu-id="eb5a3-148">string</span><span class="sxs-lookup"><span data-stu-id="eb5a3-148">string</span></span>        | <span data-ttu-id="eb5a3-149">登入位置的東對西座標</span><span class="sxs-lookup"><span data-stu-id="eb5a3-149">The east to west coordinates of the sign-in location</span></span>                                                                                            |
| `RequestId`            | <span data-ttu-id="eb5a3-150">string</span><span class="sxs-lookup"><span data-stu-id="eb5a3-150">string</span></span>        | <span data-ttu-id="eb5a3-151">要求的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="eb5a3-151">Unique identifier of the request</span></span>                                                                                                                |
|`ReportId` | <span data-ttu-id="eb5a3-152">string</span><span class="sxs-lookup"><span data-stu-id="eb5a3-152">string</span></span> | <span data-ttu-id="eb5a3-153">事件的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="eb5a3-153">Unique identifier for the event</span></span> | 

 

## <a name="related-articles"></a><span data-ttu-id="eb5a3-154">相關文章</span><span class="sxs-lookup"><span data-stu-id="eb5a3-154">Related articles</span></span>

-   [<span data-ttu-id="eb5a3-155">AADSignInEventsBeta</span><span class="sxs-lookup"><span data-stu-id="eb5a3-155">AADSignInEventsBeta</span></span>](./advanced-hunting-aadsignineventsbeta-table.md)
-   [<span data-ttu-id="eb5a3-156">進階搜捕概觀</span><span class="sxs-lookup"><span data-stu-id="eb5a3-156">Advanced hunting overview</span></span>](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)
-   [<span data-ttu-id="eb5a3-157">了解查詢語言</span><span class="sxs-lookup"><span data-stu-id="eb5a3-157">Learn the query language</span></span>](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-query-language)
-   [<span data-ttu-id="eb5a3-158">了解結構描述</span><span class="sxs-lookup"><span data-stu-id="eb5a3-158">Understand the schema</span></span>](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference)