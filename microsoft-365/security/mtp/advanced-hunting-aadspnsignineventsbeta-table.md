---
title: Advanced 搜尋架構中的 AADSpnSignInEventsBeta 表格
description: 深入瞭解與 Azure Active Directory 服務主體及高級搜尋架構之 managed identity 登入事件表格相關的資訊
keywords: 高級搜尋，威脅搜尋，網路威脅搜尋，microsoft 威脅防護，microsoft 365，mtp，m365，search，query，遙測，schema reference，kusto，table，column，data type，description，，device，machine，使用者，帳戶，身分識別，AAD
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: 42acf24ce9b941fffb1ce0ed4b67216bd8c1de47
ms.sourcegitcommit: 4482c174e0e68e0fbbc7ad9ef6b0e78dc34ac85a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/08/2021
ms.locfileid: "49784296"
---
# <a name="aadspnsignineventsbeta"></a><span data-ttu-id="c28f1-104">AADSpnSignInEventsBeta</span><span class="sxs-lookup"><span data-stu-id="c28f1-104">AADSpnSignInEventsBeta</span></span>

<span data-ttu-id="c28f1-105">適用於：</span><span class="sxs-lookup"><span data-stu-id="c28f1-105">**Applies to:**</span></span>

- <span data-ttu-id="c28f1-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c28f1-106">Microsoft 365 Defender</span></span>

>[!IMPORTANT]
> <span data-ttu-id="c28f1-107">此 `AADSpnSignInEventsBeta` 表格目前在 Beta 中，並在短期內提供，可讓您透過 Azure Active Directory (AAD) 服務主體和受管理身分識別登入事件進行搜尋。</span><span class="sxs-lookup"><span data-stu-id="c28f1-107">The `AADSpnSignInEventsBeta` table is currently in beta and is being offered on a short-term basis to allow you to hunt through Azure Active Directory (AAD) service principal and managed identity sign-in events.</span></span> <span data-ttu-id="c28f1-108">我們最後會將所有登入架構資訊移至 `IdentityLogonEvents` 表格。</span><span class="sxs-lookup"><span data-stu-id="c28f1-108">We will eventually move all sign-in schema information to the `IdentityLogonEvents` table.</span></span><br><br>
> <span data-ttu-id="c28f1-109">可透過 Azure Security Center 的整合 Microsoft Defender for Endpoint 方案存取 Microsoft 365 Defender 的客戶，但沒有 Microsoft Defender for Office、Microsoft Defender 身分識別或 Microsoft Cloud App Security 的授權，將無法查看此架構。</span><span class="sxs-lookup"><span data-stu-id="c28f1-109">Customers who can access Microsoft 365 Defender through the Azure Security Center’s integrated Microsoft Defender for Endpoint solution, but do not have licenses for Microsoft Defender for Office, Microsoft Defender for Identity, or Microsoft Cloud App Security, will not be able to view this schema.</span></span> 



<span data-ttu-id="c28f1-110">[！附注] `AADSpnSignInEventsBeta` 高級搜尋架構中的表格包含 Azure Active Directory 服務主體和受管理身分識別登入的相關資訊。您可以在 [Azure Active Directory 登入活動報告-預覽](https://docs.microsoft.com/azure/active-directory/reports-monitoring/concept-all-sign-ins)中深入瞭解不同類型的登入。</span><span class="sxs-lookup"><span data-stu-id="c28f1-110">The `AADSpnSignInEventsBeta` table in the advanced hunting schema contains information about Azure Active Directory service principal and managed identity sign-ins. You can learn more about the different kinds of sign-ins in [Azure Active Directory sign-in activity reports - preview](https://docs.microsoft.com/azure/active-directory/reports-monitoring/concept-all-sign-ins).</span></span>

<span data-ttu-id="c28f1-111">使用這個參考來建立從表格取回之資訊的查詢。</span><span class="sxs-lookup"><span data-stu-id="c28f1-111">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="c28f1-112">如需進階搜捕結構描述中其他表格的資訊，請參閱 [進階搜捕參考](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-reference) (部分內容為機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="c28f1-112">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-reference).</span></span>





| <span data-ttu-id="c28f1-113">資料行名稱</span><span class="sxs-lookup"><span data-stu-id="c28f1-113">Column name</span></span>     | <span data-ttu-id="c28f1-114">資料類型</span><span class="sxs-lookup"><span data-stu-id="c28f1-114">Data type</span></span> | <span data-ttu-id="c28f1-115">描述</span><span class="sxs-lookup"><span data-stu-id="c28f1-115">Description</span></span>   |
| ----- | ----- | ---- |
| `Timestamp` | <span data-ttu-id="c28f1-116">datetime</span><span class="sxs-lookup"><span data-stu-id="c28f1-116">datetime</span></span>      | <span data-ttu-id="c28f1-117">記錄的產生日期和時間</span><span class="sxs-lookup"><span data-stu-id="c28f1-117">Date and time when the record was generated</span></span>                                                                                                     |
| `Application`          | <span data-ttu-id="c28f1-118">string</span><span class="sxs-lookup"><span data-stu-id="c28f1-118">string</span></span>        | <span data-ttu-id="c28f1-119">執行錄製動作的應用程式</span><span class="sxs-lookup"><span data-stu-id="c28f1-119">Application that performed the recorded action</span></span>                                                                                                   |
| `ApplicationId`        | <span data-ttu-id="c28f1-120">string</span><span class="sxs-lookup"><span data-stu-id="c28f1-120">string</span></span>        | <span data-ttu-id="c28f1-121">應用程式的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="c28f1-121">Unique identifier for the application</span></span>                                                                                                           |
| `IsManagedIdentity`    | <span data-ttu-id="c28f1-122">布林值</span><span class="sxs-lookup"><span data-stu-id="c28f1-122">boolean</span></span>       | <span data-ttu-id="c28f1-123">指出登入是否是由受管理身分識別所啟動</span><span class="sxs-lookup"><span data-stu-id="c28f1-123">Indicates whether the sign-in was initiated by a managed identity</span></span>                                                                               |
| `ErrorCode`            | <span data-ttu-id="c28f1-124">int</span><span class="sxs-lookup"><span data-stu-id="c28f1-124">int</span></span>        | <span data-ttu-id="c28f1-125">如果發生登入錯誤，則會包含錯誤代碼。</span><span class="sxs-lookup"><span data-stu-id="c28f1-125">Contains the error code if a sign-in error occurs.</span></span> <span data-ttu-id="c28f1-126">若要尋找特定錯誤碼的描述，請造訪 <https://aka.ms/AADsigninsErrorCodes> 。</span><span class="sxs-lookup"><span data-stu-id="c28f1-126">To find a description of a specific error code, visit <https://aka.ms/AADsigninsErrorCodes>.</span></span> |
| `CorrelationId`        | <span data-ttu-id="c28f1-127">string</span><span class="sxs-lookup"><span data-stu-id="c28f1-127">string</span></span>        | <span data-ttu-id="c28f1-128">登入事件的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="c28f1-128">Unique identifier of the sign-in event</span></span>                                                                                                          |
| `ServicePrincipalName` | <span data-ttu-id="c28f1-129">string</span><span class="sxs-lookup"><span data-stu-id="c28f1-129">string</span></span>        | <span data-ttu-id="c28f1-130">啟動登入的服務主體名稱</span><span class="sxs-lookup"><span data-stu-id="c28f1-130">Name of the service principal that initiated the sign-in</span></span>                                                                                        |
| `ServicePrincipalId`   | <span data-ttu-id="c28f1-131">string</span><span class="sxs-lookup"><span data-stu-id="c28f1-131">string</span></span>        | <span data-ttu-id="c28f1-132">啟動登入之服務主體的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="c28f1-132">Unique identifier of the service principal that initiated the sign-in</span></span>                                                                           |
| `ResourceDisplayName`  | <span data-ttu-id="c28f1-133">string</span><span class="sxs-lookup"><span data-stu-id="c28f1-133">string</span></span>        | <span data-ttu-id="c28f1-134">存取資源的顯示名稱</span><span class="sxs-lookup"><span data-stu-id="c28f1-134">Display name of the resource accessed</span></span>                                                                                                           |
| `ResourceId`           | <span data-ttu-id="c28f1-135">string</span><span class="sxs-lookup"><span data-stu-id="c28f1-135">string</span></span>        | <span data-ttu-id="c28f1-136">存取資源的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="c28f1-136">Unique identifier of the resource accessed</span></span>                                                                                                      |
| `ResourceTenantId`     | <span data-ttu-id="c28f1-137">string</span><span class="sxs-lookup"><span data-stu-id="c28f1-137">string</span></span>        | <span data-ttu-id="c28f1-138">存取資源租使用者的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="c28f1-138">Unique identifier of the tenant of the resource accessed</span></span>                                                                                        |
| `IPAddress`            | <span data-ttu-id="c28f1-139">string</span><span class="sxs-lookup"><span data-stu-id="c28f1-139">string</span></span>        | <span data-ttu-id="c28f1-140">指派給端點的 IP 位址，並在相關的網路通訊期間使用</span><span class="sxs-lookup"><span data-stu-id="c28f1-140">IP address assigned to the endpoint and used during related network communications</span></span>                                                              |
| `CountryCode`          | <span data-ttu-id="c28f1-141">string</span><span class="sxs-lookup"><span data-stu-id="c28f1-141">string</span></span>        | <span data-ttu-id="c28f1-142">兩個字母的代碼，指出用戶端 IP 位址為 geolocated 的國家/地區</span><span class="sxs-lookup"><span data-stu-id="c28f1-142">Two-letter code indicating the country where the client IP address is geolocated</span></span>                                                                |
| `State`                | <span data-ttu-id="c28f1-143">string</span><span class="sxs-lookup"><span data-stu-id="c28f1-143">string</span></span>        | <span data-ttu-id="c28f1-144">發生登入的狀態（若有的話）</span><span class="sxs-lookup"><span data-stu-id="c28f1-144">State where the sign-in occurred, if available</span></span>                                                                                                  |
| `City`                 | <span data-ttu-id="c28f1-145">string</span><span class="sxs-lookup"><span data-stu-id="c28f1-145">string</span></span>        | <span data-ttu-id="c28f1-146">帳戶使用者所在的城市</span><span class="sxs-lookup"><span data-stu-id="c28f1-146">City where the account user is located</span></span>                                                                                                          |
| `Latitude`             | <span data-ttu-id="c28f1-147">string</span><span class="sxs-lookup"><span data-stu-id="c28f1-147">string</span></span>        | <span data-ttu-id="c28f1-148">登入位置的北到南部座標</span><span class="sxs-lookup"><span data-stu-id="c28f1-148">The north to south coordinates of the sign-in location</span></span>                                                                                          |
| `Longitude`            | <span data-ttu-id="c28f1-149">string</span><span class="sxs-lookup"><span data-stu-id="c28f1-149">string</span></span>        | <span data-ttu-id="c28f1-150">登入位置的東對西座標</span><span class="sxs-lookup"><span data-stu-id="c28f1-150">The east to west coordinates of the sign-in location</span></span>                                                                                            |
| `RequestId`            | <span data-ttu-id="c28f1-151">string</span><span class="sxs-lookup"><span data-stu-id="c28f1-151">string</span></span>        | <span data-ttu-id="c28f1-152">要求的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="c28f1-152">Unique identifier of the request</span></span>                                                                                                                |
|`ReportId` | <span data-ttu-id="c28f1-153">string</span><span class="sxs-lookup"><span data-stu-id="c28f1-153">string</span></span> | <span data-ttu-id="c28f1-154">事件的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="c28f1-154">Unique identifier for the event</span></span> | 

 

## <a name="related-articles"></a><span data-ttu-id="c28f1-155">相關文章</span><span class="sxs-lookup"><span data-stu-id="c28f1-155">Related articles</span></span>

-   [<span data-ttu-id="c28f1-156">AADSignInEventsBeta</span><span class="sxs-lookup"><span data-stu-id="c28f1-156">AADSignInEventsBeta</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/advanced-hunting-aadsignineventsbeta-table)
-   [<span data-ttu-id="c28f1-157">進階搜捕概觀</span><span class="sxs-lookup"><span data-stu-id="c28f1-157">Advanced hunting overview</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)
-   [<span data-ttu-id="c28f1-158">了解查詢語言</span><span class="sxs-lookup"><span data-stu-id="c28f1-158">Learn the query language</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-query-language)
-   [<span data-ttu-id="c28f1-159">了解結構描述</span><span class="sxs-lookup"><span data-stu-id="c28f1-159">Understand the schema</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference)
