---
title: 進位搜尋架構中的 IdentityLogonEvents 資料表
description: 瞭解 Active Directory 在進一步搜尋架構的 IdentityLogonEvents 資料表中記錄的驗證事件
keywords: 進層搜尋、威脅搜尋、網路威脅搜尋、Microsoft 威脅防護、microsoft 365、mtp、m365、搜尋、查詢、遙測、架構參照、kusto、表格、欄、資料類型、描述、IdentityLogonEvents、Azure AD、Active Directory、Azure ATP、身分識別
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: 1df1295b3386b94e3737c53ac8226c719c8bfa08
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929919"
---
# <a name="identitylogonevents"></a><span data-ttu-id="cb505-104">IdentityLogonEvents</span><span class="sxs-lookup"><span data-stu-id="cb505-104">IdentityLogonEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="cb505-105">適用於：</span><span class="sxs-lookup"><span data-stu-id="cb505-105">**Applies to:**</span></span>
- <span data-ttu-id="cb505-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="cb505-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="cb505-107">進位搜尋架構中的表格包含由 Microsoft Defender 針對 Microsoft Cloud App Security 所取得之 Microsoft 線上服務所取得之身分識別與驗證活動所拍攝之內部部署 Active Directory 所進行之 `IdentityLogonEvents` 驗證活動的資訊。 [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="cb505-107">The `IdentityLogonEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about authentication activities made through your on-premises Active Directory captured by Microsoft Defender for Identity and authentication activities related to Microsoft online services captured by Microsoft Cloud App Security.</span></span> <span data-ttu-id="cb505-108">使用這個參考來建立從此表格取回之資訊的查詢。</span><span class="sxs-lookup"><span data-stu-id="cb505-108">Use this reference to construct queries that return information from this table.</span></span>

>[!TIP]
> <span data-ttu-id="cb505-109">有關事件種類及資料 (資料) 值的詳細資訊，請使用安全性中心內建的架構 `ActionType` 參照。 [](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center)</span><span class="sxs-lookup"><span data-stu-id="cb505-109">For detailed information about the events types (`ActionType` values) supported by a table, use the [built-in schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) available in the security center.</span></span>

>[!NOTE]
><span data-ttu-id="cb505-110">下表涵蓋 Azure Active Directory (AD) 由雲端 App 安全性所追蹤的登入活動，以及使用 ActiveSync 和其他舊版通訊協定所追蹤的特別互動式登入和驗證活動。</span><span class="sxs-lookup"><span data-stu-id="cb505-110">This table covers Azure Active Directory (AD) logon activities tracked by Cloud App Security, specifically interactive sign-ins and authentication activities using ActiveSync and other legacy protocols.</span></span> <span data-ttu-id="cb505-111">您可以在 Azure AD 稽核記錄中查看此表格中未提供的非互動標誌。</span><span class="sxs-lookup"><span data-stu-id="cb505-111">Non-interactive logons that are not available in this table can be viewed in the Azure AD audit log.</span></span> [<span data-ttu-id="cb505-112">深入瞭解將雲端 App 安全性與 Microsoft 365 連接</span><span class="sxs-lookup"><span data-stu-id="cb505-112">Learn more about connecting Cloud App Security to Microsoft 365</span></span>](https://docs.microsoft.com/cloud-app-security/connect-office-365-to-microsoft-cloud-app-security)

<span data-ttu-id="cb505-113">如需進階搜捕結構描述中其他表格的資訊，[請參閱進階搜捕參考](advanced-hunting-schema-tables.md) (部分內容為機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="cb505-113">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="cb505-114">欄名稱</span><span class="sxs-lookup"><span data-stu-id="cb505-114">Column name</span></span> | <span data-ttu-id="cb505-115">資料類型</span><span class="sxs-lookup"><span data-stu-id="cb505-115">Data type</span></span> | <span data-ttu-id="cb505-116">描述</span><span class="sxs-lookup"><span data-stu-id="cb505-116">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="cb505-117">datetime</span><span class="sxs-lookup"><span data-stu-id="cb505-117">datetime</span></span> | <span data-ttu-id="cb505-118">事件記錄的日期和時間</span><span class="sxs-lookup"><span data-stu-id="cb505-118">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="cb505-119">string</span><span class="sxs-lookup"><span data-stu-id="cb505-119">string</span></span> | <span data-ttu-id="cb505-120">觸發事件的活動類型。</span><span class="sxs-lookup"><span data-stu-id="cb505-120">Type of activity that triggered the event.</span></span> <span data-ttu-id="cb505-121">請參閱入口 [網站內架構參考以](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) 進一步查看詳細資料</span><span class="sxs-lookup"><span data-stu-id="cb505-121">See the [in-portal schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) for details</span></span> |
| `LogonType` | <span data-ttu-id="cb505-122">string</span><span class="sxs-lookup"><span data-stu-id="cb505-122">string</span></span> | <span data-ttu-id="cb505-123">登入會話的類型，特別是：</span><span class="sxs-lookup"><span data-stu-id="cb505-123">Type of logon session, specifically:</span></span><br><br> <span data-ttu-id="cb505-124">- **互動** - 使用者會使用本機鍵盤和螢幕與電腦進行實際互動</span><span class="sxs-lookup"><span data-stu-id="cb505-124">- **Interactive** - User physically interacts with the machine using the local keyboard and screen</span></span><br><br> <span data-ttu-id="cb505-125">- **遠端互動式 (RDP)** 標誌 - 使用者會使用遠端桌面、終端機服務、遠端協助或其他 RDP 用戶端，與電腦進行遠端互動</span><span class="sxs-lookup"><span data-stu-id="cb505-125">- **Remote interactive (RDP) logons** - User interacts with the machine remotely using Remote Desktop, Terminal Services, Remote Assistance, or other RDP clients</span></span><br><br> <span data-ttu-id="cb505-126">- **網路** - 當使用 PsExec 存取電腦時，或當電腦上的共用資源 ，例如印表機和共用資料夾存取時初始化的會話</span><span class="sxs-lookup"><span data-stu-id="cb505-126">- **Network** - Session initiated when the machine is accessed using PsExec or when shared resources on the machine, such as printers and shared folders, are accessed</span></span><br><br> <span data-ttu-id="cb505-127">- **批次** - 由排程任務啟動的會話</span><span class="sxs-lookup"><span data-stu-id="cb505-127">- **Batch** - Session initiated by scheduled tasks</span></span><br><br> <span data-ttu-id="cb505-128">- **服務** - 服務啟動時所啟動的會話</span><span class="sxs-lookup"><span data-stu-id="cb505-128">- **Service** - Session initiated by services as they start</span></span> |
| `Application` | <span data-ttu-id="cb505-129">string</span><span class="sxs-lookup"><span data-stu-id="cb505-129">string</span></span> | <span data-ttu-id="cb505-130">執行錄製動作的應用程式</span><span class="sxs-lookup"><span data-stu-id="cb505-130">Application that performed the recorded action</span></span> |
| `Protocol` | <span data-ttu-id="cb505-131">string</span><span class="sxs-lookup"><span data-stu-id="cb505-131">string</span></span> | <span data-ttu-id="cb505-132">已使用網路通訊協定</span><span class="sxs-lookup"><span data-stu-id="cb505-132">Network protocol used</span></span> |
| `FailureReason` | <span data-ttu-id="cb505-133">string</span><span class="sxs-lookup"><span data-stu-id="cb505-133">string</span></span> | <span data-ttu-id="cb505-134">說明錄製動作失敗原因的資訊</span><span class="sxs-lookup"><span data-stu-id="cb505-134">Information explaining why the recorded action failed</span></span> |
| `AccountName` | <span data-ttu-id="cb505-135">string</span><span class="sxs-lookup"><span data-stu-id="cb505-135">string</span></span> | <span data-ttu-id="cb505-136">帳戶的使用者名稱</span><span class="sxs-lookup"><span data-stu-id="cb505-136">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="cb505-137">string</span><span class="sxs-lookup"><span data-stu-id="cb505-137">string</span></span> | <span data-ttu-id="cb505-138">帳戶的網域</span><span class="sxs-lookup"><span data-stu-id="cb505-138">Domain of the account</span></span> |
| `AccountUpn` | <span data-ttu-id="cb505-139">string</span><span class="sxs-lookup"><span data-stu-id="cb505-139">string</span></span> | <span data-ttu-id="cb505-140">帳戶 (UPN) 使用者主體名稱</span><span class="sxs-lookup"><span data-stu-id="cb505-140">User principal name (UPN) of the account</span></span> |
| `AccountSid` | <span data-ttu-id="cb505-141">string</span><span class="sxs-lookup"><span data-stu-id="cb505-141">string</span></span> | <span data-ttu-id="cb505-142">帳戶 (安全性) SID 識別碼</span><span class="sxs-lookup"><span data-stu-id="cb505-142">Security Identifier (SID) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="cb505-143">string</span><span class="sxs-lookup"><span data-stu-id="cb505-143">string</span></span> | <span data-ttu-id="cb505-144">Azure AD 中帳戶的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="cb505-144">Unique identifier for the account in Azure AD</span></span> |
| `AccountDisplayName` | <span data-ttu-id="cb505-145">string</span><span class="sxs-lookup"><span data-stu-id="cb505-145">string</span></span> | <span data-ttu-id="cb505-146">顯示在通訊錄中的帳戶使用者名稱。</span><span class="sxs-lookup"><span data-stu-id="cb505-146">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="cb505-147">通常是指定或名字、中間名、姓氏或名字的組合。</span><span class="sxs-lookup"><span data-stu-id="cb505-147">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `DeviceName` | <span data-ttu-id="cb505-148">string</span><span class="sxs-lookup"><span data-stu-id="cb505-148">string</span></span> | <span data-ttu-id="cb505-149">裝置 FQDN (完整) 功能變數名稱</span><span class="sxs-lookup"><span data-stu-id="cb505-149">Fully qualified domain name (FQDN) of the device</span></span> |
| `DeviceType` | <span data-ttu-id="cb505-150">string</span><span class="sxs-lookup"><span data-stu-id="cb505-150">string</span></span> | <span data-ttu-id="cb505-151">裝置類型</span><span class="sxs-lookup"><span data-stu-id="cb505-151">Type of device</span></span> |
| `OSPlatform` | <span data-ttu-id="cb505-152">string</span><span class="sxs-lookup"><span data-stu-id="cb505-152">string</span></span> | <span data-ttu-id="cb505-153">電腦上執行的作業系統平台。</span><span class="sxs-lookup"><span data-stu-id="cb505-153">Platform of the operating system running on the machine.</span></span> <span data-ttu-id="cb505-154">這表示特定作業系統，包括相同家族內的變化，例如 Windows 10 和 Windows 7。</span><span class="sxs-lookup"><span data-stu-id="cb505-154">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `IPAddress` | <span data-ttu-id="cb505-155">字串</span><span class="sxs-lookup"><span data-stu-id="cb505-155">string</span></span> | <span data-ttu-id="cb505-156">指派給端點的 IP 位址，用於相關網路通訊期間</span><span class="sxs-lookup"><span data-stu-id="cb505-156">IP address assigned to the endpoint and used during related network communications</span></span> |
| `DestinationDeviceName` | <span data-ttu-id="cb505-157">string</span><span class="sxs-lookup"><span data-stu-id="cb505-157">string</span></span> | <span data-ttu-id="cb505-158">執行處理錄製動作之伺服器應用程式之裝置的名稱</span><span class="sxs-lookup"><span data-stu-id="cb505-158">Name of the device running the server application that processed the recorded action</span></span> |
| `DestinationIPAddress` | <span data-ttu-id="cb505-159">string</span><span class="sxs-lookup"><span data-stu-id="cb505-159">string</span></span> | <span data-ttu-id="cb505-160">執行處理錄製動作之伺服器應用程式的裝置 IP 位址</span><span class="sxs-lookup"><span data-stu-id="cb505-160">IP address of the device running the server application that processed the recorded action</span></span> |
| `TargetDeviceName` | <span data-ttu-id="cb505-161">string</span><span class="sxs-lookup"><span data-stu-id="cb505-161">string</span></span> | <span data-ttu-id="cb505-162">已記錄動作 (之) 之裝置之 FQDN 中完整功能變數名稱</span><span class="sxs-lookup"><span data-stu-id="cb505-162">Fully qualified domain name (FQDN) of the device that the recorded action was applied to</span></span> |
| `TargetAccountDisplayName` | <span data-ttu-id="cb505-163">string</span><span class="sxs-lookup"><span data-stu-id="cb505-163">string</span></span> | <span data-ttu-id="cb505-164">顯示所記錄動作所適用于之帳戶的名稱</span><span class="sxs-lookup"><span data-stu-id="cb505-164">Display name of the account that the recorded action was applied to</span></span> |
| `Location` | <span data-ttu-id="cb505-165">string</span><span class="sxs-lookup"><span data-stu-id="cb505-165">string</span></span> | <span data-ttu-id="cb505-166">與活動相關的城市、國家/地區或其他地理位置</span><span class="sxs-lookup"><span data-stu-id="cb505-166">City, country, or other geographic location associated with the event</span></span> |
| `Isp` | <span data-ttu-id="cb505-167">string</span><span class="sxs-lookup"><span data-stu-id="cb505-167">string</span></span> | <span data-ttu-id="cb505-168">與端點 IP 位址 (ISP) 網際網路服務提供者</span><span class="sxs-lookup"><span data-stu-id="cb505-168">Internet service provider (ISP) associated with the endpoint IP address</span></span> |
| `ReportId` | <span data-ttu-id="cb505-169">long</span><span class="sxs-lookup"><span data-stu-id="cb505-169">long</span></span> | <span data-ttu-id="cb505-170">事件的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="cb505-170">Unique identifier for the event</span></span> |
| `AdditionalFields` | <span data-ttu-id="cb505-171">string</span><span class="sxs-lookup"><span data-stu-id="cb505-171">string</span></span> | <span data-ttu-id="cb505-172">實體或事件的其他相關資訊</span><span class="sxs-lookup"><span data-stu-id="cb505-172">Additional information about the entity or event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="cb505-173">相關主題</span><span class="sxs-lookup"><span data-stu-id="cb505-173">Related topics</span></span>
- [<span data-ttu-id="cb505-174">進階搜捕概觀</span><span class="sxs-lookup"><span data-stu-id="cb505-174">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="cb505-175">了解查詢語言</span><span class="sxs-lookup"><span data-stu-id="cb505-175">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="cb505-176">使用共用查詢</span><span class="sxs-lookup"><span data-stu-id="cb505-176">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="cb505-177">跨裝置、電子郵件、應用程式和身分識別搜捕</span><span class="sxs-lookup"><span data-stu-id="cb505-177">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="cb505-178">了解結構描述</span><span class="sxs-lookup"><span data-stu-id="cb505-178">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="cb505-179">套用查詢最佳做法</span><span class="sxs-lookup"><span data-stu-id="cb505-179">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
