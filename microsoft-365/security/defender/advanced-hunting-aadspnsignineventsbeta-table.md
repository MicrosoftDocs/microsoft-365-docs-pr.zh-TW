---
title: Advanced 搜尋架構中的 AADSpnSignInEventsBeta 表格
description: 深入瞭解與高級搜尋架構的 Azure Active Directory 服務主體及受管理身分識別登入事件表格相關的資訊
keywords: 高級搜尋，威脅搜尋，網路威脅搜尋，Microsoft 365 Defender，Microsoft 365，m365，search，query，遙測，schema reference，kusto，table，column，data type，file，IP address，device，machine，使用者，帳戶，identity，AAD
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
ms.openlocfilehash: 6aa709fe4534bf049c6f8c097bc4bd85a9d6793b
ms.sourcegitcommit: 93eeaefc0d509c75e4c2210029155298ecca7583
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/09/2021
ms.locfileid: "53347904"
---
# <a name="aadspnsignineventsbeta"></a><span data-ttu-id="9e69e-104">AADSpnSignInEventsBeta</span><span class="sxs-lookup"><span data-stu-id="9e69e-104">AADSpnSignInEventsBeta</span></span>

<span data-ttu-id="9e69e-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="9e69e-105">**Applies to:**</span></span>

- <span data-ttu-id="9e69e-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9e69e-106">Microsoft 365 Defender</span></span>

>[!IMPORTANT]
> <span data-ttu-id="9e69e-107">`AADSpnSignInEventsBeta`資料表目前在 Beta 中，並在短期內提供，以供您尋找 Azure Active Directory (AAD) 服務主體和受管理身分識別登入事件。</span><span class="sxs-lookup"><span data-stu-id="9e69e-107">The `AADSpnSignInEventsBeta` table is currently in beta and is being offered on a short-term basis to allow you to hunt through Azure Active Directory (AAD) service principal and managed identity sign-in events.</span></span> <span data-ttu-id="9e69e-108">我們最後會將所有登入架構資訊移至 `IdentityLogonEvents` 表格。</span><span class="sxs-lookup"><span data-stu-id="9e69e-108">We will eventually move all sign-in schema information to the `IdentityLogonEvents` table.</span></span>



<span data-ttu-id="9e69e-109">[！附注] `AADSpnSignInEventsBeta` 高級搜尋架構中的表格包含 Azure Active Directory 服務主體和受管理身分識別登入的相關資訊。您可以在[Azure Active Directory 登入活動報告-預覽](/azure/active-directory/reports-monitoring/concept-all-sign-ins)中深入瞭解不同的登入類型。</span><span class="sxs-lookup"><span data-stu-id="9e69e-109">The `AADSpnSignInEventsBeta` table in the advanced hunting schema contains information about Azure Active Directory service principal and managed identity sign-ins. You can learn more about the different kinds of sign-ins in [Azure Active Directory sign-in activity reports - preview](/azure/active-directory/reports-monitoring/concept-all-sign-ins).</span></span>

<span data-ttu-id="9e69e-110">使用這個參考來建立從表格取回之資訊的查詢。</span><span class="sxs-lookup"><span data-stu-id="9e69e-110">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="9e69e-111">如需進階搜捕結構描述中其他表格的資訊，請參閱 [進階搜捕參考](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-reference) (部分內容為機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="9e69e-111">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-reference).</span></span>





| <span data-ttu-id="9e69e-112">資料行名稱</span><span class="sxs-lookup"><span data-stu-id="9e69e-112">Column name</span></span> | <span data-ttu-id="9e69e-113">資料類型</span><span class="sxs-lookup"><span data-stu-id="9e69e-113">Data type</span></span> | <span data-ttu-id="9e69e-114">描述</span><span class="sxs-lookup"><span data-stu-id="9e69e-114">Description</span></span> |
|-----|-----|-----|
| `Timestamp` | <span data-ttu-id="9e69e-115">datetime</span><span class="sxs-lookup"><span data-stu-id="9e69e-115">datetime</span></span> | <span data-ttu-id="9e69e-116">記錄的產生日期和時間</span><span class="sxs-lookup"><span data-stu-id="9e69e-116">Date and time when the record was generated</span></span> |
| `Application` | <span data-ttu-id="9e69e-117">string</span><span class="sxs-lookup"><span data-stu-id="9e69e-117">string</span></span> | <span data-ttu-id="9e69e-118">執行錄製動作的應用程式</span><span class="sxs-lookup"><span data-stu-id="9e69e-118">Application that performed the recorded action</span></span> |
| `ApplicationId` | <span data-ttu-id="9e69e-119">string</span><span class="sxs-lookup"><span data-stu-id="9e69e-119">string</span></span> | <span data-ttu-id="9e69e-120">應用程式的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="9e69e-120">Unique identifier for the application</span></span> |
| `IsManagedIdentity`    | <span data-ttu-id="9e69e-121">布林值</span><span class="sxs-lookup"><span data-stu-id="9e69e-121">boolean</span></span>       | <span data-ttu-id="9e69e-122">指出登入是否是由受管理身分識別所啟動</span><span class="sxs-lookup"><span data-stu-id="9e69e-122">Indicates whether the sign-in was initiated by a managed identity</span></span> |
| `ErrorCode`    | <span data-ttu-id="9e69e-123">int</span><span class="sxs-lookup"><span data-stu-id="9e69e-123">int</span></span> | <span data-ttu-id="9e69e-124">如果發生登入錯誤，則會包含錯誤代碼。</span><span class="sxs-lookup"><span data-stu-id="9e69e-124">Contains the error code if a sign-in error occurs.</span></span> <span data-ttu-id="9e69e-125">若要尋找特定錯誤碼的描述，請造訪 <https://aka.ms/AADsigninsErrorCodes> 。</span><span class="sxs-lookup"><span data-stu-id="9e69e-125">To find a description of a specific error code, visit <https://aka.ms/AADsigninsErrorCodes>.</span></span> |
| `CorrelationId`        | <span data-ttu-id="9e69e-126">string</span><span class="sxs-lookup"><span data-stu-id="9e69e-126">string</span></span>        | <span data-ttu-id="9e69e-127">登入事件的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="9e69e-127">Unique identifier of the sign-in event</span></span> |
| `ServicePrincipalName` | <span data-ttu-id="9e69e-128">string</span><span class="sxs-lookup"><span data-stu-id="9e69e-128">string</span></span>        | <span data-ttu-id="9e69e-129">啟動登入的服務主體名稱</span><span class="sxs-lookup"><span data-stu-id="9e69e-129">Name of the service principal that initiated the sign-in</span></span>  |
| `ServicePrincipalId`   | <span data-ttu-id="9e69e-130">string</span><span class="sxs-lookup"><span data-stu-id="9e69e-130">string</span></span>        | <span data-ttu-id="9e69e-131">啟動登入之服務主體的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="9e69e-131">Unique identifier of the service principal that initiated the sign-in</span></span>  |
| `ResourceDisplayName`  | <span data-ttu-id="9e69e-132">string</span><span class="sxs-lookup"><span data-stu-id="9e69e-132">string</span></span>        | <span data-ttu-id="9e69e-133">存取資源的顯示名稱</span><span class="sxs-lookup"><span data-stu-id="9e69e-133">Display name of the resource accessed</span></span>  |
| `ResourceId`           | <span data-ttu-id="9e69e-134">string</span><span class="sxs-lookup"><span data-stu-id="9e69e-134">string</span></span>        | <span data-ttu-id="9e69e-135">存取資源的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="9e69e-135">Unique identifier of the resource accessed</span></span>  |
| `ResourceTenantId`     | <span data-ttu-id="9e69e-136">string</span><span class="sxs-lookup"><span data-stu-id="9e69e-136">string</span></span>        | <span data-ttu-id="9e69e-137">存取資源租使用者的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="9e69e-137">Unique identifier of the tenant of the resource accessed</span></span> |
| `IPAddress`            | <span data-ttu-id="9e69e-138">string</span><span class="sxs-lookup"><span data-stu-id="9e69e-138">string</span></span>        | <span data-ttu-id="9e69e-139">指派給端點的 IP 位址，並在相關的網路通訊期間使用</span><span class="sxs-lookup"><span data-stu-id="9e69e-139">IP address assigned to the endpoint and used during related network communications</span></span>  |
| `Country`          | <span data-ttu-id="9e69e-140">string</span><span class="sxs-lookup"><span data-stu-id="9e69e-140">string</span></span>        | <span data-ttu-id="9e69e-141">兩個字母的代碼，指出用戶端 IP 位址為 geolocated 的國家/地區</span><span class="sxs-lookup"><span data-stu-id="9e69e-141">Two-letter code indicating the country where the client IP address is geolocated</span></span> |
| `State`                | <span data-ttu-id="9e69e-142">string</span><span class="sxs-lookup"><span data-stu-id="9e69e-142">string</span></span>        | <span data-ttu-id="9e69e-143">發生登入的狀態（若有的話）</span><span class="sxs-lookup"><span data-stu-id="9e69e-143">State where the sign-in occurred, if available</span></span> |
| `City`                 | <span data-ttu-id="9e69e-144">string</span><span class="sxs-lookup"><span data-stu-id="9e69e-144">string</span></span>        | <span data-ttu-id="9e69e-145">帳戶使用者所在的城市</span><span class="sxs-lookup"><span data-stu-id="9e69e-145">City where the account user is located</span></span>  |
| `Latitude`             | <span data-ttu-id="9e69e-146">string</span><span class="sxs-lookup"><span data-stu-id="9e69e-146">string</span></span>        | <span data-ttu-id="9e69e-147">登入位置的北到南部座標</span><span class="sxs-lookup"><span data-stu-id="9e69e-147">The north to south coordinates of the sign-in location</span></span> |
| `Longitude`            | <span data-ttu-id="9e69e-148">string</span><span class="sxs-lookup"><span data-stu-id="9e69e-148">string</span></span>        | <span data-ttu-id="9e69e-149">登入位置的東對西座標</span><span class="sxs-lookup"><span data-stu-id="9e69e-149">The east to west coordinates of the sign-in location</span></span> |
| `RequestId`            | <span data-ttu-id="9e69e-150">string</span><span class="sxs-lookup"><span data-stu-id="9e69e-150">string</span></span>        | <span data-ttu-id="9e69e-151">要求的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="9e69e-151">Unique identifier of the request</span></span> |
|`ReportId` | <span data-ttu-id="9e69e-152">string</span><span class="sxs-lookup"><span data-stu-id="9e69e-152">string</span></span> | <span data-ttu-id="9e69e-153">事件的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="9e69e-153">Unique identifier for the event</span></span> |

 

## <a name="related-articles"></a><span data-ttu-id="9e69e-154">相關文章</span><span class="sxs-lookup"><span data-stu-id="9e69e-154">Related articles</span></span>

-   [<span data-ttu-id="9e69e-155">AADSignInEventsBeta</span><span class="sxs-lookup"><span data-stu-id="9e69e-155">AADSignInEventsBeta</span></span>](./advanced-hunting-aadsignineventsbeta-table.md)
-   [<span data-ttu-id="9e69e-156">進階搜捕概觀</span><span class="sxs-lookup"><span data-stu-id="9e69e-156">Advanced hunting overview</span></span>](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)
-   [<span data-ttu-id="9e69e-157">了解查詢語言</span><span class="sxs-lookup"><span data-stu-id="9e69e-157">Learn the query language</span></span>](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-query-language)
-   [<span data-ttu-id="9e69e-158">了解結構描述</span><span class="sxs-lookup"><span data-stu-id="9e69e-158">Understand the schema</span></span>](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference)
