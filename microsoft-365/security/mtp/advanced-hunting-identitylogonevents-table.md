---
title: Advanced 搜尋架構中的 IdentityLogonEvents 表格
description: 深入瞭解在高級搜尋架構的 IdentityLogonEvents 資料表中，由 Active Directory 記錄的驗證事件
keywords: 高級搜尋，威脅搜尋，網路威脅搜尋，microsoft 威脅防護，microsoft 365，mtp，m365，搜尋，查詢，遙測，架構參考，kusto，表格，欄，資料類型，描述，IdentityLogonEvents，Azure AD，Active Directory，Azure ATP，身分識別
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 212189c89f354b186072bb109f119cf048680d08
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/13/2020
ms.locfileid: "48431084"
---
# <a name="identitylogonevents"></a><span data-ttu-id="be192-104">IdentityLogonEvents</span><span class="sxs-lookup"><span data-stu-id="be192-104">IdentityLogonEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="be192-105">適用於：\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="be192-105">**Applies to:**</span></span>
- <span data-ttu-id="be192-106">Microsoft 威脅防護</span><span class="sxs-lookup"><span data-stu-id="be192-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="be192-107">[！附注] `IdentityLogonEvents` [高級搜尋](advanced-hunting-overview.md) 架構中的表格包含透過 Azure ATP 和驗證活動（透過 Microsoft Cloud App Security 所捕獲的 microsoft online 服務所捕獲）進行驗證的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="be192-107">The `IdentityLogonEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about authentication activities made through your on-premises Active Directory captured by Azure ATP and authentication activities related to Microsoft online services captured by Microsoft Cloud App Security.</span></span> <span data-ttu-id="be192-108">使用這個參考來建立從此表格取回之資訊的查詢。</span><span class="sxs-lookup"><span data-stu-id="be192-108">Use this reference to construct queries that return information from this table.</span></span>

>[!TIP]
> <span data-ttu-id="be192-109">如需有關資料表所支援之事件種類 () 值的詳細資訊 `ActionType` ，請使用安全性中心內的 [內建架構參照](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) 。</span><span class="sxs-lookup"><span data-stu-id="be192-109">For detailed information about the events types (`ActionType` values) supported by a table, use the [built-in schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) available in the security center.</span></span>

>[!NOTE]
><span data-ttu-id="be192-110">下表涵蓋 Cloud App Security （特別是互動式登入及驗證活動）所追蹤的 Azure Active Directory (AD) 登入活動 ActiveSync 和其他舊版通訊協定。</span><span class="sxs-lookup"><span data-stu-id="be192-110">This table covers Azure Active Directory (AD) logon activities tracked by Cloud App Security, specifically interactive sign-ins and authentication activities using ActiveSync and other legacy protocols.</span></span> <span data-ttu-id="be192-111">您可以在 Azure AD 審核記錄中查看無法在此表格中使用的非互動式登入。</span><span class="sxs-lookup"><span data-stu-id="be192-111">Non-interactive logons that are not available in this table can be viewed in the Azure AD audit log.</span></span> [<span data-ttu-id="be192-112">深入瞭解將雲端 App 安全性連接至 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="be192-112">Learn more about connecting Cloud App Security to Microsoft 365</span></span>](https://docs.microsoft.com/cloud-app-security/connect-office-365-to-microsoft-cloud-app-security)

<span data-ttu-id="be192-113">如需進階搜捕結構描述中其他表格的資訊，[請參閱進階搜捕參考](advanced-hunting-schema-tables.md) (部分內容為機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="be192-113">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="be192-114">欄名稱</span><span class="sxs-lookup"><span data-stu-id="be192-114">Column name</span></span> | <span data-ttu-id="be192-115">資料類型</span><span class="sxs-lookup"><span data-stu-id="be192-115">Data type</span></span> | <span data-ttu-id="be192-116">描述</span><span class="sxs-lookup"><span data-stu-id="be192-116">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="be192-117">datetime</span><span class="sxs-lookup"><span data-stu-id="be192-117">datetime</span></span> | <span data-ttu-id="be192-118">事件記錄的日期和時間</span><span class="sxs-lookup"><span data-stu-id="be192-118">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="be192-119">string</span><span class="sxs-lookup"><span data-stu-id="be192-119">string</span></span> | <span data-ttu-id="be192-120">觸發事件的活動類型。</span><span class="sxs-lookup"><span data-stu-id="be192-120">Type of activity that triggered the event.</span></span> <span data-ttu-id="be192-121">如需詳細資訊，請參閱[入口網站內架構參考](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center)</span><span class="sxs-lookup"><span data-stu-id="be192-121">See the [in-portal schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) for details</span></span> |
| `LogonType` | <span data-ttu-id="be192-122">string</span><span class="sxs-lookup"><span data-stu-id="be192-122">string</span></span> | <span data-ttu-id="be192-123">登入會話的類型，特別：</span><span class="sxs-lookup"><span data-stu-id="be192-123">Type of logon session, specifically:</span></span><br><br> <span data-ttu-id="be192-124">- **互動式** 使用者會使用本機鍵盤和畫面，以實際方式與機器互動</span><span class="sxs-lookup"><span data-stu-id="be192-124">- **Interactive** - User physically interacts with the machine using the local keyboard and screen</span></span><br><br> <span data-ttu-id="be192-125">- \*\*遠端互動 (RDP) \*\* 登入-使用者利用遠端桌面、終端機服務、遠端協助或其他 RDP 用戶端從遠端與機器互動</span><span class="sxs-lookup"><span data-stu-id="be192-125">- **Remote interactive (RDP) logons** - User interacts with the machine remotely using Remote Desktop, Terminal Services, Remote Assistance, or other RDP clients</span></span><br><br> <span data-ttu-id="be192-126">- 使用 PsExec 存取機器時，或在機器上共用資源（如印表機和共用資料夾）存取時，所啟動的**網路**會話</span><span class="sxs-lookup"><span data-stu-id="be192-126">- **Network** - Session initiated when the machine is accessed using PsExec or when shared resources on the machine, such as printers and shared folders, are accessed</span></span><br><br> <span data-ttu-id="be192-127">- 由排程任務所啟動的**批次**會話</span><span class="sxs-lookup"><span data-stu-id="be192-127">- **Batch** - Session initiated by scheduled tasks</span></span><br><br> <span data-ttu-id="be192-128">- **服務** -啟動時由服務啟動的會話</span><span class="sxs-lookup"><span data-stu-id="be192-128">- **Service** - Session initiated by services as they start</span></span> |
| `Application` | <span data-ttu-id="be192-129">string</span><span class="sxs-lookup"><span data-stu-id="be192-129">string</span></span> | <span data-ttu-id="be192-130">執行錄製動作的應用程式</span><span class="sxs-lookup"><span data-stu-id="be192-130">Application that performed the recorded action</span></span> |
| `Protocol` | <span data-ttu-id="be192-131">string</span><span class="sxs-lookup"><span data-stu-id="be192-131">string</span></span> | <span data-ttu-id="be192-132">使用的網路通訊協定</span><span class="sxs-lookup"><span data-stu-id="be192-132">Network protocol used</span></span> |
| `FailureReason` | <span data-ttu-id="be192-133">string</span><span class="sxs-lookup"><span data-stu-id="be192-133">string</span></span> | <span data-ttu-id="be192-134">說明錄製的動作失敗原因的資訊</span><span class="sxs-lookup"><span data-stu-id="be192-134">Information explaining why the recorded action failed</span></span> |
| `AccountName` | <span data-ttu-id="be192-135">string</span><span class="sxs-lookup"><span data-stu-id="be192-135">string</span></span> | <span data-ttu-id="be192-136">帳戶的使用者名稱</span><span class="sxs-lookup"><span data-stu-id="be192-136">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="be192-137">string</span><span class="sxs-lookup"><span data-stu-id="be192-137">string</span></span> | <span data-ttu-id="be192-138">帳戶的網域</span><span class="sxs-lookup"><span data-stu-id="be192-138">Domain of the account</span></span> |
| `AccountUpn` | <span data-ttu-id="be192-139">string</span><span class="sxs-lookup"><span data-stu-id="be192-139">string</span></span> | <span data-ttu-id="be192-140">帳戶的使用者主要名稱 (UPN) </span><span class="sxs-lookup"><span data-stu-id="be192-140">User principal name (UPN) of the account</span></span> |
| `AccountSid` | <span data-ttu-id="be192-141">string</span><span class="sxs-lookup"><span data-stu-id="be192-141">string</span></span> | <span data-ttu-id="be192-142">帳戶的安全性識別碼 (SID) </span><span class="sxs-lookup"><span data-stu-id="be192-142">Security Identifier (SID) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="be192-143">string</span><span class="sxs-lookup"><span data-stu-id="be192-143">string</span></span> | <span data-ttu-id="be192-144">Azure AD 中帳戶的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="be192-144">Unique identifier for the account in Azure AD</span></span> |
| `AccountDisplayName` | <span data-ttu-id="be192-145">string</span><span class="sxs-lookup"><span data-stu-id="be192-145">string</span></span> | <span data-ttu-id="be192-146">顯示在通訊錄中之帳戶使用者的名稱。</span><span class="sxs-lookup"><span data-stu-id="be192-146">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="be192-147">通常是指定的名稱或名字、中間初始名稱或姓氏的組合。</span><span class="sxs-lookup"><span data-stu-id="be192-147">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `DeviceName` | <span data-ttu-id="be192-148">string</span><span class="sxs-lookup"><span data-stu-id="be192-148">string</span></span> | <span data-ttu-id="be192-149">裝置的完整功能變數名稱 (FQDN) </span><span class="sxs-lookup"><span data-stu-id="be192-149">Fully qualified domain name (FQDN) of the device</span></span> |
| `DeviceType` | <span data-ttu-id="be192-150">string</span><span class="sxs-lookup"><span data-stu-id="be192-150">string</span></span> | <span data-ttu-id="be192-151">裝置類型</span><span class="sxs-lookup"><span data-stu-id="be192-151">Type of device</span></span> |
| `OSPlatform` | <span data-ttu-id="be192-152">string</span><span class="sxs-lookup"><span data-stu-id="be192-152">string</span></span> | <span data-ttu-id="be192-153">電腦上執行的作業系統平台。</span><span class="sxs-lookup"><span data-stu-id="be192-153">Platform of the operating system running on the machine.</span></span> <span data-ttu-id="be192-154">這表示特定作業系統，包括相同家族內的變化，例如 Windows 10 和 Windows 7。</span><span class="sxs-lookup"><span data-stu-id="be192-154">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `IPAddress` | <span data-ttu-id="be192-155">字串</span><span class="sxs-lookup"><span data-stu-id="be192-155">string</span></span> | <span data-ttu-id="be192-156">指派給端點的 IP 位址，並在相關的網路通訊期間使用</span><span class="sxs-lookup"><span data-stu-id="be192-156">IP address assigned to the endpoint and used during related network communications</span></span> |
| `DestinationDeviceName` | <span data-ttu-id="be192-157">string</span><span class="sxs-lookup"><span data-stu-id="be192-157">string</span></span> | <span data-ttu-id="be192-158">執行伺服器應用程式（處理錄製的動作）的裝置名稱</span><span class="sxs-lookup"><span data-stu-id="be192-158">Name of the device running the server application that processed the recorded action</span></span> |
| `DestinationIPAddress` | <span data-ttu-id="be192-159">string</span><span class="sxs-lookup"><span data-stu-id="be192-159">string</span></span> | <span data-ttu-id="be192-160">執行伺服器應用程式（處理錄製的動作）的裝置的 IP 位址</span><span class="sxs-lookup"><span data-stu-id="be192-160">IP address of the device running the server application that processed the recorded action</span></span> |
| `TargetDeviceName` | <span data-ttu-id="be192-161">string</span><span class="sxs-lookup"><span data-stu-id="be192-161">string</span></span> | <span data-ttu-id="be192-162">套用錄製動作之裝置的完整功能變數名稱 (FQDN) </span><span class="sxs-lookup"><span data-stu-id="be192-162">Fully qualified domain name (FQDN) of the device that the recorded action was applied to</span></span> |
| `TargetAccountDisplayName` | <span data-ttu-id="be192-163">string</span><span class="sxs-lookup"><span data-stu-id="be192-163">string</span></span> | <span data-ttu-id="be192-164">套用錄製的動作所套用之帳戶的顯示名稱</span><span class="sxs-lookup"><span data-stu-id="be192-164">Display name of the account that the recorded action was applied to</span></span> |
| `Location` | <span data-ttu-id="be192-165">string</span><span class="sxs-lookup"><span data-stu-id="be192-165">string</span></span> | <span data-ttu-id="be192-166">與事件關聯的城市、國家或其他地理位置</span><span class="sxs-lookup"><span data-stu-id="be192-166">City, country, or other geographic location associated with the event</span></span> |
| `Isp` | <span data-ttu-id="be192-167">string</span><span class="sxs-lookup"><span data-stu-id="be192-167">string</span></span> | <span data-ttu-id="be192-168">網際網路服務提供者 (與端點 IP 位址相關聯的 ISP) </span><span class="sxs-lookup"><span data-stu-id="be192-168">Internet service provider (ISP) associated with the endpoint IP address</span></span> |
| `ReportId` | <span data-ttu-id="be192-169">long</span><span class="sxs-lookup"><span data-stu-id="be192-169">long</span></span> | <span data-ttu-id="be192-170">事件的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="be192-170">Unique identifier for the event</span></span> |
| `AdditionalFields` | <span data-ttu-id="be192-171">string</span><span class="sxs-lookup"><span data-stu-id="be192-171">string</span></span> | <span data-ttu-id="be192-172">實體或事件的其他資訊</span><span class="sxs-lookup"><span data-stu-id="be192-172">Additional information about the entity or event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="be192-173">相關主題</span><span class="sxs-lookup"><span data-stu-id="be192-173">Related topics</span></span>
- [<span data-ttu-id="be192-174">進階搜捕概觀</span><span class="sxs-lookup"><span data-stu-id="be192-174">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="be192-175">了解查詢語言</span><span class="sxs-lookup"><span data-stu-id="be192-175">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="be192-176">使用共用查詢</span><span class="sxs-lookup"><span data-stu-id="be192-176">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="be192-177">搜捕裝置、電子郵件、應用程式和身分識別</span><span class="sxs-lookup"><span data-stu-id="be192-177">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="be192-178">了解結構描述</span><span class="sxs-lookup"><span data-stu-id="be192-178">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="be192-179">套用查詢最佳做法</span><span class="sxs-lookup"><span data-stu-id="be192-179">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
