---
title: 使用合作協力廠商的 Windows PowerShell 管理 Microsoft 365 承租人
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- M365-subscription-management
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.assetid: f92d5116-5b66-4150-ad20-1452fc3dd712
description: 在本文中，您將瞭解如何使用 PowerShell 進行 Microsoft 365，以管理客戶租用。
ms.openlocfilehash: 14290f04159e3ba0ce46971d204b71d3bb1600d9
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "46688383"
---
# <a name="manage-microsoft-365-tenants-with-windows-powershell-for-delegated-access-permissions-dap-partners"></a><span data-ttu-id="857ab-103">使用委派存取許可權的 Windows PowerShell 管理 Microsoft 365 承租人 (結合) 夥伴</span><span class="sxs-lookup"><span data-stu-id="857ab-103">Manage Microsoft 365 tenants with Windows PowerShell for Delegated Access Permissions (DAP) partners</span></span>

<span data-ttu-id="857ab-104">*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*</span><span class="sxs-lookup"><span data-stu-id="857ab-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="857ab-105">Windows PowerShell 允許合作和雲端解決方案提供者 (CSP) 協力廠商可輕鬆管理及報告 Microsoft 365 系統管理中心中無法提供的客戶租使用者。</span><span class="sxs-lookup"><span data-stu-id="857ab-105">Windows PowerShell allows Syndication and Cloud Solution Provider (CSP) partners to easily administer and report on customer tenancy settings that are not available in the Microsoft 365 admin center.</span></span> <span data-ttu-id="857ab-106">請注意，合作夥伴系統管理員帳戶須有管理代表 (AOBO) 權限才能連接其客戶租用。</span><span class="sxs-lookup"><span data-stu-id="857ab-106">Note that Administer on Behalf Of (AOBO) permissions are required for the partner administrator account to connect to its customer tenancies.</span></span>
  
<span data-ttu-id="857ab-107">委派的存取權限 (DAP) 合作夥伴就是新聞訂閱方式和雲端解決方案提供者 (CSP) 合作夥伴。</span><span class="sxs-lookup"><span data-stu-id="857ab-107">Delegated Access Permission (DAP) partners are Syndication and Cloud Solution Providers (CSP) Partners.</span></span> <span data-ttu-id="857ab-108">他們通常是其他公司的網路或電信服務提供者。</span><span class="sxs-lookup"><span data-stu-id="857ab-108">They are frequently network or telecom providers to other companies.</span></span> <span data-ttu-id="857ab-109">他們會將 Microsoft 365 訂閱捆綁到其客戶的服務產品中。</span><span class="sxs-lookup"><span data-stu-id="857ab-109">They bundle Microsoft 365 subscriptions into their service offerings to their customers.</span></span> <span data-ttu-id="857ab-110">當他們銷售 Microsoft 365 訂閱時，系統會自動授與租用 AOBO) 許可權的 (管理，讓他們能管理及報告客戶租用。</span><span class="sxs-lookup"><span data-stu-id="857ab-110">When they sell a Microsoft 365 subscription, they are automatically granted Administer On Behalf Of (AOBO) permissions to the customer tenancies so they can administer and report on the customer tenancies.</span></span>
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="857ab-111">開始之前有哪些須知？</span><span class="sxs-lookup"><span data-stu-id="857ab-111">What do you need to know before you begin?</span></span>

<span data-ttu-id="857ab-112">本主題中的程式需要連接至[連線，才能與 PowerShell Microsoft 365](connect-to-microsoft-365-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="857ab-112">The procedures in this topic require you to connect to [Connect to Microsoft 365 with PowerShell](connect-to-microsoft-365-powershell.md).</span></span>
  
<span data-ttu-id="857ab-113">您也需要合作夥伴租用戶系統管理員認證。</span><span class="sxs-lookup"><span data-stu-id="857ab-113">You also need your partner tenant administrator credentials.</span></span>
  
## <a name="what-do-you-want-to-do"></a><span data-ttu-id="857ab-114">您要執行的工作</span><span class="sxs-lookup"><span data-stu-id="857ab-114">What do you want to do?</span></span>

### <a name="list-all-tenant-ids"></a><span data-ttu-id="857ab-115">列出所有租用戶識別碼</span><span class="sxs-lookup"><span data-stu-id="857ab-115">List all tenant IDs</span></span>

> [!NOTE]
> <span data-ttu-id="857ab-p103">如果您有擁有 500 個以上的租用戶，請使用  _-All_ 或 _-MaxResultsParameter_ 來設定 Cmdlet 語法的範圍。這適用於其他提供大量輸出的 Cmdlet (如 **Get-MsolUser** )。</span><span class="sxs-lookup"><span data-stu-id="857ab-p103">If you have more than 500 tenants, scope the cmdlet syntax with either  _-All_ or _-MaxResultsParameter_. This applies to other cmdlets that can give a large output, such as **Get-MsolUser**.</span></span>
  
<span data-ttu-id="857ab-118">若要列出所有可存取的客戶租用戶識別碼，請執行此命令。</span><span class="sxs-lookup"><span data-stu-id="857ab-118">To list all customer tenant Ids that you have access to, run this command.</span></span>
  
```
Get-MsolPartnerContract -All | Select-Object TenantId
```

<span data-ttu-id="857ab-119">這會顯示按照 **TenantId** 排列的所有客戶租用戶清單。</span><span class="sxs-lookup"><span data-stu-id="857ab-119">This will display a listing of all your customer tenants by **TenantId**.</span></span>

>[!Note]
><span data-ttu-id="857ab-120">PowerShell Core 不支援適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組和名稱有 **Msol** 的 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="857ab-120">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="857ab-121">若要繼續使用這些 Cmdlet，您必須從 Windows PowerShell 執行。</span><span class="sxs-lookup"><span data-stu-id="857ab-121">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>
>
  
### <a name="get-a-tenant-id-by-using-the-domain-name"></a><span data-ttu-id="857ab-122">使用網域名稱來取得租用戶識別碼</span><span class="sxs-lookup"><span data-stu-id="857ab-122">Get a tenant ID by using the domain name</span></span>

<span data-ttu-id="857ab-p105">若要依據網域名稱來取得特定客戶租用戶的 **TenantId** ，請執行此命令。將 _<domainname.onmicrosoft.com>_ 取代為所需的實際客戶租用戶網域名稱。</span><span class="sxs-lookup"><span data-stu-id="857ab-p105">To get the **TenantId** for a specific customer tenant by domain name, run this command. Replace _<domainname.onmicrosoft.com>_ with the actual domain name of the customer tenant that you want.</span></span>
  
```
Get-MsolPartnerContract -DomainName <domainname.onmicrosoft.com> | Select-Object TenantId
```

### <a name="list-all-domains-for-a-tenant"></a><span data-ttu-id="857ab-125">列出租用戶的所有網域</span><span class="sxs-lookup"><span data-stu-id="857ab-125">List all domains for a tenant</span></span>

<span data-ttu-id="857ab-p106">若要取得任一客戶租用戶的所有網域，請執行此命令。將 _<customer TenantId value>_ 取代為實際值。</span><span class="sxs-lookup"><span data-stu-id="857ab-p106">To get all domains for any one customer tenant, run this command. Replace  _<customer TenantId value>_ with the actual value.</span></span>
  
```
Get-MsolDomain -TenantId <customer TenantId value>
```

<span data-ttu-id="857ab-128">如果您已經註冊其他網域，這會傳回與客戶 **TenantId** 相關聯的所有網域。</span><span class="sxs-lookup"><span data-stu-id="857ab-128">If you have registered additional domains, this will return all domains associated with the customer **TenantId**.</span></span>
  
### <a name="get-a-mapping-of-all-tenants-and-registered-domains"></a><span data-ttu-id="857ab-129">取得所有租用戶和註冊網域的對應</span><span class="sxs-lookup"><span data-stu-id="857ab-129">Get a mapping of all tenants and registered domains</span></span>

<span data-ttu-id="857ab-130">Microsoft 365 命令的先前 PowerShell 會向您說明如何在承租人 IDs 或網域中檢索，但不能同時在兩者之間取得任何明確的對應。</span><span class="sxs-lookup"><span data-stu-id="857ab-130">The previous PowerShell for Microsoft 365 commands showed you how to retrieve either tenant IDs or domains but not both at the same time, and with no clear mapping between them all.</span></span> <span data-ttu-id="857ab-131">此命令會產生所有客戶租用戶識別碼和網域的清單。</span><span class="sxs-lookup"><span data-stu-id="857ab-131">This command generates a listing of all your customer tenant IDs and their domains.</span></span>
  
```
$Tenants = Get-MsolPartnerContract -All; $Tenants | foreach {$Domains = $_.TenantId; Get-MsolDomain -TenantId $Domains | fl @{Label="TenantId";Expression={$Domains}},name}
```

### <a name="get-all-users-for-a-tenant"></a><span data-ttu-id="857ab-132">取得租用戶的所有使用者</span><span class="sxs-lookup"><span data-stu-id="857ab-132">Get all users for a tenant</span></span>

<span data-ttu-id="857ab-p108">這會顯示特定租用戶之所有使用者的 **UserPrincipalName**、**DisplayName** 和 **isLicensed** 狀態。將 _<customer TenantId value>_ 取代為實際值。</span><span class="sxs-lookup"><span data-stu-id="857ab-p108">This will display the **UserPrincipalName**, the **DisplayName**, and the **isLicensed** status for all users for a particular tenant. Replace _<customer TenantId value>_ with the actual value.</span></span>
  
```
Get-MsolUser -TenantID <customer TenantId value>
```

### <a name="get-all-details-about-a-user"></a><span data-ttu-id="857ab-135">取得有關使用者的所有詳細資料</span><span class="sxs-lookup"><span data-stu-id="857ab-135">Get all details about a user</span></span>

<span data-ttu-id="857ab-p109">如果您想要查看特定使用者的所有內容，請執行此命令。將 _<customer TenantId value>_ 和 _<user principal name value>_ 取代為實際值。</span><span class="sxs-lookup"><span data-stu-id="857ab-p109">If you want to see all the properties of a particular user, run this command. Replace  _<customer TenantId value>_ and _<user principal name value>_ with the actual values.</span></span>
  
```
Get-MsolUser -TenantId <customer TenantId value> -UserPrincipalName <user principal name value>
```

### <a name="add-users-set-options-and-assign-licenses"></a><span data-ttu-id="857ab-138">新增使用者、設定選項及指派授權</span><span class="sxs-lookup"><span data-stu-id="857ab-138">Add users, set options, and assign licenses</span></span>

<span data-ttu-id="857ab-139">Microsoft 365 使用者的大量建立、設定及授權，對 Microsoft 365 使用 PowerShell 特別有效。</span><span class="sxs-lookup"><span data-stu-id="857ab-139">The bulk creation, configuration, and licensing of Microsoft 365 users is particularly efficient by using PowerShell for Microsoft 365.</span></span> <span data-ttu-id="857ab-140">在這兩個步驟的程式中，您會先以逗號分隔的值 (CSV) 檔案建立所有使用者的專案，然後使用 Microsoft 365 的 PowerShell 匯入該檔案。</span><span class="sxs-lookup"><span data-stu-id="857ab-140">In this two-step process, you first create entries for all the users you want to add in a comma-separated value (CSV) file and then import that file by using PowerShell for Microsoft 365.</span></span> 
  
#### <a name="create-a-csv-file"></a><span data-ttu-id="857ab-141">建立 CSV 檔案</span><span class="sxs-lookup"><span data-stu-id="857ab-141">Create a CSV file</span></span>

<span data-ttu-id="857ab-142">使用此格式來建立 CSV 檔案：</span><span class="sxs-lookup"><span data-stu-id="857ab-142">Create a CSV file by using this format:</span></span>
  
-  `UserPrincipalName,FirstName,LastName,DisplayName,Password,TenantId,UsageLocation,LicenseAssignment`
    
<span data-ttu-id="857ab-143">其中：</span><span class="sxs-lookup"><span data-stu-id="857ab-143">where:</span></span>
  
- <span data-ttu-id="857ab-p111">**UsageLocation** ：此項目的值是由兩個字母組成的使用者 ISO 國家/地區碼。您可以在 [ISO 線上瀏覽平台](https://go.microsoft.com/fwlink/p/?LinkId=532703)查詢國家/地區碼。例如，美國的代碼是 US，而巴西的代碼則是 BR。</span><span class="sxs-lookup"><span data-stu-id="857ab-p111">**UsageLocation**: The value for this is the two-letter ISO country/region code of the user. The country/region codes can be looked up at the[ISO Online Browsing Platform](https://go.microsoft.com/fwlink/p/?LinkId=532703). For example, the code for the United States is US, and the code for Brazil is BR.</span></span> 
    
- <span data-ttu-id="857ab-p112">**LicenseAssignment** ：此項目的值使用格式： `syndication-account:<PROVISIONING_ID>`. 例如，如果您要將 O365_Business_Premium 授權指派給客戶租用戶使用者， **LicenseAssignment** 值看起來會像： **syndication-account:O365_Business_Premium** 。在新聞訂閱方式合作夥伴入口網站中，您可以找到能以新聞訂閱方式或 CSP 合作夥伴身分存取的 PROVISIONING_ID。</span><span class="sxs-lookup"><span data-stu-id="857ab-p112">**LicenseAssignment**: The value for this uses this format: `syndication-account:<PROVISIONING_ID>`. For example, if you are assigning customer tenant users O365_Business_Premium licenses, the **LicenseAssignment** value looks like this: **syndication-account:O365_Business_Premium**. You will find the PROVISIONING_IDs in the Syndication Partner Portal that you have access to as a Syndication or CSP partner.</span></span>
    
#### <a name="import-the-csv-file-and-create-the-users"></a><span data-ttu-id="857ab-150">匯入 CSV 檔案及建立使用者</span><span class="sxs-lookup"><span data-stu-id="857ab-150">Import the CSV file and create the users</span></span>

<span data-ttu-id="857ab-p113">建立 CSV 檔案之後，請執行此命令以利用使用者在第一次登入時必須變更的不會到期密碼建立使用者帳戶，以及指派您指定的授權。請務必替代正確的 CSV 檔案名稱。</span><span class="sxs-lookup"><span data-stu-id="857ab-p113">After you have your CSV file created, run this command to create user accounts with non-expiring passwords that the user must change at first sign-in and that assigns the license you specify. Be sure to substitute the correct CSV file name.</span></span>
  
```
Import-Csv .\FILENAME.CSV | foreach {New-MsolUser -UserPrincipalName $_.UserPrincipalName -DisplayName $_.DisplayName -FirstName $_.FirstName -LastName $_.LastName -Password $_.Password -UsageLocation $_.UsageLocation -LicenseAssignment $_.LicenseAssignment -ForceChangePassword:$true -PasswordNeverExpires:$true -TenantId $_.TenantId}
```

## <a name="see-also"></a><span data-ttu-id="857ab-153">另請參閱</span><span class="sxs-lookup"><span data-stu-id="857ab-153">See also</span></span>

#### 

[<span data-ttu-id="857ab-154">合作夥伴說明</span><span class="sxs-lookup"><span data-stu-id="857ab-154">Help for partners</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=533477)

