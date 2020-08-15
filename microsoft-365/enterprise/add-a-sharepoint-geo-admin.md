---
title: 新增或移除地理位置系統管理員
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.collection: SPO_Content
localization_priority: Normal
f1.keywords:
- NOCSH
description: 需要為每個地理位置設定個別的系統管理員嗎？ 了解如何在 Microsoft 365 多地理位置中新增或移除地理位置系統管理員。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9a3d916bfec2c53850f923fb5322298e9ff440ca
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "46688831"
---
# <a name="add-or-remove-a-geo-administrator-in-microsoft-365-multi-geo"></a><span data-ttu-id="fae5f-104">在 Microsoft 365 多地理位置中新增或移除地理位置系統管理員</span><span class="sxs-lookup"><span data-stu-id="fae5f-104">Add or remove a geo administrator in Microsoft 365 Multi-Geo</span></span>

<span data-ttu-id="fae5f-105">您可以為租用戶中的每個地理位置設定個別的系統管理員。</span><span class="sxs-lookup"><span data-stu-id="fae5f-105">You can configure separate administrators for each geo location that you have in your tenant.</span></span> <span data-ttu-id="fae5f-106">這些系統管理員將能存取專為其地理位置設定的 Sharepoint 和 OneDrive 設定。</span><span class="sxs-lookup"><span data-stu-id="fae5f-106">These administrators will have access to the SharePoint Online and OneDrive settings that are specific to their geo location.</span></span>

<span data-ttu-id="fae5f-107">某些服務 - 例如詞彙儲存庫- 可從中心位置進行管理並會複製到衛星位置。</span><span class="sxs-lookup"><span data-stu-id="fae5f-107">Some services - such as the term store - are administered from the central location and replicated to satellite locations.</span></span> <span data-ttu-id="fae5f-108">中央位置的地理位置系統管理員可以存取這些服務，而衛星位置的地理位置系統管理員則無法存取。</span><span class="sxs-lookup"><span data-stu-id="fae5f-108">The geo admin for the central location has access to these, whereas geo admins for satellite locations don't.</span></span>

<span data-ttu-id="fae5f-109">全域系統管理員和 SharePoint Online 系統管理員可以繼續存取中心位置和所有衛星位置的設定。</span><span class="sxs-lookup"><span data-stu-id="fae5f-109">Global administrators and SharePoint Online administrators continue to have access to settings in the central location and all satellite locations.</span></span>

## <a name="configuring-geo-administrators"></a><span data-ttu-id="fae5f-110">設定地理位置系統管理員</span><span class="sxs-lookup"><span data-stu-id="fae5f-110">Configuring geo administrators</span></span>

<span data-ttu-id="fae5f-111">設定地理位置系統管理員需要 SharePoint Online PowerShell 模組。</span><span class="sxs-lookup"><span data-stu-id="fae5f-111">Configuring geo admins requires SharePoint Online PowerShell module.</span></span>

<span data-ttu-id="fae5f-112">使用 [Connect-SPOService](https://docs.microsoft.com/powershell/module/sharepoint-online/Connect-SPOService) 連線到您想新增地理位置系統管理員之地理位置的系統管理中心。(例如，Connect-SPOService  https://ContosoEUR-admin.sharepoint.com.)</span><span class="sxs-lookup"><span data-stu-id="fae5f-112">Use [Connect-SPOService](https://docs.microsoft.com/powershell/module/sharepoint-online/Connect-SPOService) to connect to the admin center of the geo location where you want to add the geo admin. (For example, Connect-SPOService  https://ContosoEUR-admin.sharepoint.com.)</span></span>

<span data-ttu-id="fae5f-113">若要檢視某位置的現有地理位置系統管理員，請執行 `Get-SPOGeoAdministrator`</span><span class="sxs-lookup"><span data-stu-id="fae5f-113">To view the existing geo admins of a location, run `Get-SPOGeoAdministrator`</span></span>

### <a name="adding-a-user-as-a-geo-admin"></a><span data-ttu-id="fae5f-114">將使用者新增為地理位置系統管理員</span><span class="sxs-lookup"><span data-stu-id="fae5f-114">Adding a user as a geo admin</span></span>

<span data-ttu-id="fae5f-115">若要將使用者新增為地理位置系統管理員，請執行 `Add-SPOGeoAdministrator -UserPrincipalName <UPN>`</span><span class="sxs-lookup"><span data-stu-id="fae5f-115">To add a user as a geo admin, run `Add-SPOGeoAdministrator -UserPrincipalName <UPN>`</span></span>

<span data-ttu-id="fae5f-116">若要在某位置將使用者的地理位置系統管理員身份移除，請執行 `Remove-SPOGeoAdministrator -UserPrincipalName <UPN>`</span><span class="sxs-lookup"><span data-stu-id="fae5f-116">To remove a user as a Geo Admin of a location, run  `Remove-SPOGeoAdministrator -UserPrincipalName <UPN>`</span></span>

### <a name="adding-a-group-as-a-geo-admin"></a><span data-ttu-id="fae5f-117">將群組新增為地理位置系統管理員</span><span class="sxs-lookup"><span data-stu-id="fae5f-117">Adding a group as a geo admin</span></span>

<span data-ttu-id="fae5f-118">您可以新增安全性群組或擁有郵件功能的安全性群組作為地理位置系統管理員。(不支援通訊群組與 Microsoft 365 群組。)</span><span class="sxs-lookup"><span data-stu-id="fae5f-118">You can add a security group or a mail-enabled security group as a geo admin. (Distribution groups and Microsoft 365 Groups are not supported.)</span></span>

<span data-ttu-id="fae5f-119">若要新增群組為地理位置系統管理員，請執行 `Add-SPOGeoAdministrator -GroupAlias <alias>`</span><span class="sxs-lookup"><span data-stu-id="fae5f-119">To add a group as a geo administrator, run `Add-SPOGeoAdministrator -GroupAlias <alias>`</span></span>

<span data-ttu-id="fae5f-120">若要移除群組的地理位置系統管理員身份，請執行 `Remove-SPOGeoAdministrator -GroupAlias <alias>`</span><span class="sxs-lookup"><span data-stu-id="fae5f-120">To remove a group as a geo administrator, run `Remove-SPOGeoAdministrator -GroupAlias <alias>`</span></span>

<span data-ttu-id="fae5f-121">請注意，並非所有安全性群組都有群組別名。</span><span class="sxs-lookup"><span data-stu-id="fae5f-121">Note that not all security groups have a group alias.</span></span> <span data-ttu-id="fae5f-122">如果您要新增的安全性群組並沒有別名，請執行 [Get-MsolGroup](https://docs.microsoft.com/powershell/module/msonline/get-msolgroup) 擷取群組清單、找出安全性群組 ObjectID，然後再執行：</span><span class="sxs-lookup"><span data-stu-id="fae5f-122">If you want to add a security group that does not have an alias, run [Get-MsolGroup](https://docs.microsoft.com/powershell/module/msonline/get-msolgroup) to retrieve a list of groups, find your security group's ObjectID, and then run:</span></span>

`Add-SPOGeoAdministrator -ObjectID <ObjectID>`

<span data-ttu-id="fae5f-123">若要使用 ObjectID 移除群組，請執行 `Remove-SPOGeoAdministrator -ObjectID <ObjectID>`</span><span class="sxs-lookup"><span data-stu-id="fae5f-123">To remove a group by using the ObjectID, run `Remove-SPOGeoAdministrator -ObjectID <ObjectID>`</span></span>

## <a name="related-topics"></a><span data-ttu-id="fae5f-124">相關主題</span><span class="sxs-lookup"><span data-stu-id="fae5f-124">Related topics</span></span>

[<span data-ttu-id="fae5f-125">Add-SPOGeoAdministrator</span><span class="sxs-lookup"><span data-stu-id="fae5f-125">Add-SPOGeoAdministrator</span></span>](https://docs.microsoft.com/powershell/module/sharepoint-online/add-spogeoadministrator)

[<span data-ttu-id="fae5f-126">Add-SPOGeoAdministrator</span><span class="sxs-lookup"><span data-stu-id="fae5f-126">Get-SPOGeoAdministrator</span></span>](https://docs.microsoft.com/powershell/module/sharepoint-online/get-spogeoadministrator)

[<span data-ttu-id="fae5f-127">Remove-SPOGeoAdministrator</span><span class="sxs-lookup"><span data-stu-id="fae5f-127">Remove-SPOGeoAdministrator</span></span>](https://docs.microsoft.com/powershell/module/sharepoint-online/remove-spogeoadministrator)

[<span data-ttu-id="fae5f-128">為安全性群組設定別名 (MailNickName)</span><span class="sxs-lookup"><span data-stu-id="fae5f-128">Set an alias (MailNickName) for a security group</span></span>](https://docs.microsoft.com/powershell/module/azuread/set-azureadgroup)