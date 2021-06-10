---
title: 使用集中式部署 PowerShell Cmdlet 來管理增益集
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 1/24/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
- MED150
- MBS150
- BCS160
f1.keywords:
- NOCSH
ms.assetid: 94f4e86d-b8e5-42dd-b558-e6092f830ec9
ms.custom:
- seo-marvel-apr2020
description: 使用集中式部署 PowerShell Cmdlet，協助您部署及管理 Microsoft 365 組織的 Office 增益集。
ms.openlocfilehash: 7872deedfcfe058f0a4ac63c489bbed139699d18
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924669"
---
# <a name="use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins"></a><span data-ttu-id="dde17-103">使用集中式部署 PowerShell Cmdlet 來管理增益集</span><span class="sxs-lookup"><span data-stu-id="dde17-103">Use the Centralized Deployment PowerShell cmdlets to manage add-ins</span></span>

<span data-ttu-id="dde17-104">作為全域管理員 Microsoft 365，您可以透過 [集中式部署] 功能將 Office 增益集部署給使用者 (請參閱[在系統管理中心部署 Office 增益集](../admin/manage/manage-deployment-of-add-ins.md)) 。</span><span class="sxs-lookup"><span data-stu-id="dde17-104">As a Microsoft 365 global admin, you can deploy Office add-ins to users via the Centralized Deployment feature (see [Deploy Office Add-ins in the admin center](../admin/manage/manage-deployment-of-add-ins.md)).</span></span> <span data-ttu-id="dde17-105">除了透過 Microsoft 365 系統管理中心部署 Office 增益集之外，您也可以使用 Microsoft PowerShell。</span><span class="sxs-lookup"><span data-stu-id="dde17-105">In addition to deploying Office add-ins via the Microsoft 365 admin center, you can also use Microsoft PowerShell.</span></span> <span data-ttu-id="dde17-106">[針對 Windows PowerShell 安裝 O365 集中式 Add-In 部署模組](https://www.powershellgallery.com/packages/O365CentralizedAddInDeployment)。</span><span class="sxs-lookup"><span data-stu-id="dde17-106">Install the [O365 Centralized Add-In Deployment Module for Windows PowerShell](https://www.powershellgallery.com/packages/O365CentralizedAddInDeployment).</span></span> 

<span data-ttu-id="dde17-107">下載該模組之後，請開啟一個一般 Windows PowerShell 視窗，並執行下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="dde17-107">After you download the module, open a regular Windows PowerShell window and run the following cmdlet:</span></span>

```powershell
 Import-Module -Name O365CentralizedAddInDeployment
```
    
## <a name="connect-using-your-admin-credentials"></a><span data-ttu-id="dde17-108">使用您的系統管理員認證連線</span><span class="sxs-lookup"><span data-stu-id="dde17-108">Connect using your admin credentials</span></span>

<span data-ttu-id="dde17-109">在您可以使用集中式部署 Cmdlet 之前，您必須先登入。</span><span class="sxs-lookup"><span data-stu-id="dde17-109">Before you can use the Centralized Deployment cmdlets, you need to sign in.</span></span>
  
1. <span data-ttu-id="dde17-110">開始 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="dde17-110">Start PowerShell.</span></span>
    
2. <span data-ttu-id="dde17-111">使用您公司的系統管理員認證連線 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="dde17-111">Connect to PowerShell by using your company admin credentials.</span></span> <span data-ttu-id="dde17-112">執行下列 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="dde17-112">Run the following cmdlet.</span></span>
    
  ```powershell
  Connect-OrganizationAddInService
  ```

3. <span data-ttu-id="dde17-113">在 [**輸入認證**] 頁面中，輸入您的 Microsoft 365 全域系統管理員認證。</span><span class="sxs-lookup"><span data-stu-id="dde17-113">In the **Enter Credentials** page, enter your Microsoft 365 global admin credentials.</span></span> <span data-ttu-id="dde17-114">或者，您也可以直接在 Cmdlet 中輸入認證。</span><span class="sxs-lookup"><span data-stu-id="dde17-114">Alternately, you can enter your credentials directly into the cmdlet.</span></span> 
    
    <span data-ttu-id="dde17-115">執行下列 Cmdlet，將您的公司系統管理員認證指定為 PSCredential 物件。</span><span class="sxs-lookup"><span data-stu-id="dde17-115">Run the following cmdlet specifying your company admin credentials as a PSCredential object.</span></span>
    
  ```powershell
  $secpasswd = ConvertTo-SecureString "MyPassword" -AsPlainText -Force
  $mycredentials = New-Object System.Management.Automation.PSCredential ("serviceaccount@contoso.com", $secpasswd)
  Connect-OrganizationAddInService -Credential $mycredentials
  ```

> [!NOTE]
> <span data-ttu-id="dde17-116">如需使用 PowerShell 的詳細資訊，請參閱[連線 Microsoft 365 搭配 PowerShell](./connect-to-microsoft-365-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="dde17-116">For more information about using PowerShell, see [Connect to Microsoft 365 with PowerShell](./connect-to-microsoft-365-powershell.md).</span></span> 
  
## <a name="upload-an-add-in-manifest"></a><span data-ttu-id="dde17-117">Upload 增益集資訊清單</span><span class="sxs-lookup"><span data-stu-id="dde17-117">Upload an add-in manifest</span></span>

<span data-ttu-id="dde17-118">執行 **新的 OrganizationAdd** Cmdlet，從路徑（可以是檔案位置或 URL）上傳增益集資訊清單。</span><span class="sxs-lookup"><span data-stu-id="dde17-118">Run the **New-OrganizationAdd-In** cmdlet to upload an add-in manifest from a path, which can be either a file location or URL.</span></span> <span data-ttu-id="dde17-119">下列範例會顯示  _ManifestPath_ 參數值的檔案位置。</span><span class="sxs-lookup"><span data-stu-id="dde17-119">The following example shows a file location for the value of the  _ManifestPath_ parameter.</span></span> 
  
```powershell
New-OrganizationAddIn -ManifestPath 'C:\Users\Me\Desktop\taskpane.xml' -Locale 'en-US'
```

<span data-ttu-id="dde17-120">您也可以執行 **新的 OrganizationAdd** Cmdlet，以上傳增益集，並使用  _Members_ 參數直接將其指派給使用者或群組，如下列範例所示。</span><span class="sxs-lookup"><span data-stu-id="dde17-120">You can also run the **New-OrganizationAdd-In** cmdlet to upload an add-in and assign it to users or groups directly by using the  _Members_ parameter, as shown in the following example.</span></span> <span data-ttu-id="dde17-121">以逗號分隔成員的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="dde17-121">Separate the email addresses of members with a comma.</span></span> 
  
```powershell
New-OrganizationAddIn -ManifestPath 'C:\Users\Me\Desktop\taskpane.xml' -Locale 'en-US' -Members  'KathyBonner@contoso.com', 'MaxHargrave@contoso.com'
```

## <a name="upload-an-add-in-from-the-office-store"></a><span data-ttu-id="dde17-122">從 Office 存放區 Upload 增益集</span><span class="sxs-lookup"><span data-stu-id="dde17-122">Upload an add-in from the Office Store</span></span>

<span data-ttu-id="dde17-123">執行 **OrganizationAddIn** Cmdlet，以從 Office 儲存區上傳資訊清單。</span><span class="sxs-lookup"><span data-stu-id="dde17-123">Run the **New-OrganizationAddIn** cmdlet to upload a manifest from the Office Store.</span></span>
  
<span data-ttu-id="dde17-124">在下列範例中， **OrganizationAddIn** Cmdlet 會為美國位置和內容市場的增益集指定 AssetId。</span><span class="sxs-lookup"><span data-stu-id="dde17-124">In the following example, the **New-OrganizationAddIn** cmdlet specifies the AssetId for an add-in for a United States location and content market.</span></span>
  
```powershell
New-OrganizationAddIn -AssetId 'WA104099688' -Locale 'en-US' -ContentMarket 'en-US'
```

<span data-ttu-id="dde17-125">若要決定 _AssetId_ 參數的值，您可以從增益集的 Office 儲存區網頁 URL 進行複製。</span><span class="sxs-lookup"><span data-stu-id="dde17-125">To determine the value for the  _AssetId_ parameter, you can copy it from the URL of the Office Store webpage for the add-in.</span></span> <span data-ttu-id="dde17-126">AssetIds 永遠以 "WA" 開頭，後面接數位。</span><span class="sxs-lookup"><span data-stu-id="dde17-126">AssetIds always begin with "WA" followed by a number.</span></span> <span data-ttu-id="dde17-127">例如，在上一個範例中，WA104099688 的 AssetId 值來源為增益集的 Office 儲存區網頁 URL： [https://store.office.com/en-001/app.aspx?assetid=WA104099688](https://store.office.com/en-001/app.aspx?assetid=WA104099688) 。</span><span class="sxs-lookup"><span data-stu-id="dde17-127">For example, in the previous example, the source for the AssetId value of WA104099688 is the Office Store webpage URL for the add-in: [https://store.office.com/en-001/app.aspx?assetid=WA104099688](https://store.office.com/en-001/app.aspx?assetid=WA104099688).</span></span>
  
<span data-ttu-id="dde17-128">_Locale_ 參數和 _ContentMarket_ 參數的值相同，並指出您嘗試安裝增益集的國家/地區。</span><span class="sxs-lookup"><span data-stu-id="dde17-128">The values for the  _Locale_ parameter and the  _ContentMarket_ parameter are identical and indicate the country/region you're trying to install the add-in from.</span></span> <span data-ttu-id="dde17-129">格式為 en-US，fr-FR。</span><span class="sxs-lookup"><span data-stu-id="dde17-129">The format is en-US, fr-FR.</span></span> <span data-ttu-id="dde17-130">等等。</span><span class="sxs-lookup"><span data-stu-id="dde17-130">and so forth.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="dde17-131">從 Office 儲存區上傳的增益集將會在 Office 存放區上的最新更新可用幾天內自動更新。</span><span class="sxs-lookup"><span data-stu-id="dde17-131">Add-ins uploaded from the Office Store will update automatically within a few days of the latest update being available on the Office Store.</span></span> 
  
## <a name="get-details-of-an-add-in"></a><span data-ttu-id="dde17-132">取得增益集的詳細資料</span><span class="sxs-lookup"><span data-stu-id="dde17-132">Get details of an add-in</span></span>

<span data-ttu-id="dde17-133">執行 **OrganizationAddIn 指令程式** （如下所示），以取得上傳至租使用者的所有增益集的詳細資料，包括增益集的產品識別碼。</span><span class="sxs-lookup"><span data-stu-id="dde17-133">Run the **Get-OrganizationAddIn** cmdlet as shown below to get details of all add-ins uploaded to the tenant, included an add-in's product ID.</span></span>
  
```powershell
Get-OrganizationAddIn
```

<span data-ttu-id="dde17-134">使用 _ProductId_ 參數的值來執行 **OrganizationAddIn 指令程式**，以指定您要從中取得詳細資料的增益集。</span><span class="sxs-lookup"><span data-stu-id="dde17-134">Run the **Get-OrganizationAddIn** cmdlet with a value for the  _ProductId_ parameter to specify which add-in you want to retrieve details for.</span></span> 
  
```powershell
Get-OrganizationAddIn -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122
```

<span data-ttu-id="dde17-135">若要取得所有增益集的完整詳細資料以及所指派的使用者和群組，請將 **OrganizationAddIn** 指令程式的輸出輸送至 Format-List Cmdlet，如下列範例所示。</span><span class="sxs-lookup"><span data-stu-id="dde17-135">To get full details of all the add-ins plus the assigned users and groups, pipe the output of the **Get-OrganizationAddIn** cmdlet to the Format-List cmdlet, as shown in the following example.</span></span>
  
```powershell
foreach($G in (Get-organizationAddIn)){Get-OrganizationAddIn -ProductId $G.ProductId | Format-List}
```

## <a name="turn-on-or-turn-off-an-add-in"></a><span data-ttu-id="dde17-136">開啟或關閉增益集</span><span class="sxs-lookup"><span data-stu-id="dde17-136">Turn on or turn off an add-in</span></span>

<span data-ttu-id="dde17-137">若要關閉增益集，讓指派給它的使用者和群組不再具有存取權，請使用 _ProductId_ 參數和 _Enabled_ 參數設定為，以執行 **OrganizationAddIn 指令程式**， `$false` 如下列範例所示。</span><span class="sxs-lookup"><span data-stu-id="dde17-137">To turn off an add-in so users and groups that are assigned to it will no longer have access, run the **Set-OrganizationAddIn** cmdlet with the  _ProductId_ parameter and the  _Enabled_ parameter set to  `$false`, as shown in the following example.</span></span>
  
```powershell
Set-OrganizationAddIn -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -Enabled $false
```

<span data-ttu-id="dde17-138">若要將增益集重新開啟，請執行與  _Enabled_ 參數設定為相同的 Cmdlet  `$true` 。</span><span class="sxs-lookup"><span data-stu-id="dde17-138">To turn an add-in back on, run the same cmdlet with the  _Enabled_ parameter set to  `$true`.</span></span>
  
```powershell
Set-OrganizationAddIn -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -Enabled $true
```

## <a name="add-or-remove-users-from-an-add-in"></a><span data-ttu-id="dde17-139">新增或移除增益集中的使用者</span><span class="sxs-lookup"><span data-stu-id="dde17-139">Add or remove users from an add-in</span></span>

<span data-ttu-id="dde17-140">若要將使用者和群組新增至特定增益集，請使用 _ProductId_、 _add_ 和 _Members_ 參數執行 **OrganizationAddInAssignments** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="dde17-140">To add users and groups to a specific add-in, run the **Set-OrganizationAddInAssignments** cmdlet with the  _ProductId_,  _Add_, and  _Members_ parameters.</span></span> <span data-ttu-id="dde17-141">以逗號分隔成員的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="dde17-141">Separate the email addresses of members with a comma.</span></span> 
  
```powershell
Set-OrganizationAddInAssignments -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -Add -Members 'KathyBonner@contoso.com','sales@contoso.com'
```

<span data-ttu-id="dde17-142">若要移除使用者和群組，請使用  _移除_ 參數來執行相同的 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="dde17-142">To remove users and groups, run the same cmdlet using the  _Remove_ parameter.</span></span> 
  
```powershell
Set-OrganizationAddInAssignments -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -Remove -Members 'KathyBonner@contoso.com','sales@contoso.com'
```

<span data-ttu-id="dde17-143">若要將增益集指派給租使用者上的所有使用者，請使用  _AssignToEveryone_ 參數設定為，以執行相同的 Cmdlet  `$true` 。</span><span class="sxs-lookup"><span data-stu-id="dde17-143">To assign an add-in to all users on the tenant, run the same cmdlet using the  _AssignToEveryone_ parameter with the value set to  `$true`.</span></span>
  
```powershell
Set-OrganizationAddInAssignments -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -AssignToEveryone $true
```

<span data-ttu-id="dde17-144">若要將增益集指派給所有人，並回復至先前指派的使用者和群組，您可以執行相同的指令程式，並將 AssignToEveryone 參數的值設為，以關閉參數 `$false` 。</span><span class="sxs-lookup"><span data-stu-id="dde17-144">To not assign an add-in to everyone and revert to the previously assigned users and groups, you can run the same cmdlet and turn off the  _AssignToEveryone_ parameter by setting its value to  `$false`.</span></span>
  
```powershell
Set-OrganizationAddInAssignments -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -AssignToEveryone $false
```

## <a name="update-an-add-in"></a><span data-ttu-id="dde17-145">更新增益集</span><span class="sxs-lookup"><span data-stu-id="dde17-145">Update an add-in</span></span>

<span data-ttu-id="dde17-146">若要從資訊清單更新增益集，請使用 _ProductId_、 _ManifestPath_ 及 _Locale_ 參數執行 **OrganizationAddIn 指令程式**，如下列範例所示。</span><span class="sxs-lookup"><span data-stu-id="dde17-146">To update an add-in from a manifest, run the **Set-OrganizationAddIn** cmdlet with the  _ProductId_,  _ManifestPath_, and  _Locale_ parameters, as shown in the following example.</span></span> 
  
```powershell
Set-OrganizationAddIn -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -ManifestPath 'C:\Users\Me\Desktop\taskpane.xml' -Locale 'en-US'
```

> [!NOTE]
> <span data-ttu-id="dde17-147">從 Office 儲存區上傳的增益集將會在 Office 存放區上的最新更新可用幾天內自動更新。</span><span class="sxs-lookup"><span data-stu-id="dde17-147">Add-ins uploaded from the Office Store will update automatically within a few days of the latest update being available on the Office Store.</span></span> 
  
## <a name="delete-an-add-in"></a><span data-ttu-id="dde17-148">刪除增益集</span><span class="sxs-lookup"><span data-stu-id="dde17-148">Delete an add-in</span></span>

<span data-ttu-id="dde17-149">若要刪除增益集，請使用 _ProductId_ 參數執行 **Remove-OrganizationAddIn** Cmdlet，如下列範例所示。</span><span class="sxs-lookup"><span data-stu-id="dde17-149">To delete an add-in, run the **Remove-OrganizationAddIn** cmdlet with the  _ProductId_ parameter, as shown in the following example.</span></span> 
  
```powershell
Remove-OrganizationAddIn -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122
```

<!--
## Customize Microsoft Store add-ins for your organization

You must customize the add-in before you deploy it to your organization. Add-ins older than version 1.1 are not supported by this feature. 

We recommend that you deploy a customized add-in  to yourself first to make sure it works as expected before you deploy it to your entire organization.

Note also the following restrictions:
- All URLs must be absolute (include http or https) and valid.
- *DisplayName* must not exceed 125 characters 
- *DisplayName*, *Resources* and *AppDomains* must not include the following characters: 
 
    - \<
    -  \>
    -  ;
    -  =   

If you want to customize an add-in that has been deployed, you have to uninstall it in the admin center, and see [remove an add-in from local cache](#remove-an-add-in-from-local-cache) for steps to remove it from each computer it has been deployed to.

To customize an add-in, run the **Set –OrganizationAddInOverrides** cmdlet with the *ProductId* as a parameter, followed by the tag you want to overwrite and the new value. To find out how to get the *ProductId* see [get details of an add-in](#get-details-of-an-add-in) in this article. For example:

```powershell
 Set-OrganizationAddInOverrides -ProductId 5b31b349-2c41-4f94-b720-6ee40349d391 -IconUrl "https://site.com/img.jpg" 
```
To customize multiple tags for an add-in, add those tags to the commandline:

```powershell
Set-OrganizationAddInOverrides -ProductId 5b31b349-2c41-4f94-b720-6ee40349d391 -Hosts h1, 2 -DisplayName "New DocuSign W" -IconUrl "https://site.com/img.jpg" 
```

> [!IMPORTANT]
> You must apply multiple customized tags to one add-in as one command. If you customize tags one by one, only the last customization will be applied. Additionally, if you customize a tag by mistake, you must remove all customizations and start over.

### Tags you can customize

| Tag                  | Description          |
| :------------------- | :------------------- |
| \<IconURL>   </br>| The URL of the image used as the add-in’s icon (in admin center). </br> |
| \<DisplayName>| The title of the add-in  (in admin center).|
| \<Hosts>| List of apps that will support the add-in.|
| \<SourceLocation> | The source URL that the add-in will connect to.| 
| \<AppDomains> | A list of domains that the add-in can connect with. | 
| \<SupportURL>| The URL users can use to access help and support. | 
| \<Resources>  | This tag contains a number of elements including titles, tooltips, and icons of different sizes.| 
|
### Customize Resources tag

Any element in the <Resources> tag of the manifest can be customized dynamically. You first need to check the manifest to find the element id to which you want to assign a new value. The <Resources> tag looks like this:

```
<Resources>  
    <bt:Images> 
          <bt:Image id=”img16icon” DefaultValue=”https://site.com/img.jpg” 
    </bt:Images> 
</Resources> 
``` 
In this case, the element id for the image is “img16icon” and the value associated with it is “http:<i></i>//site.<i></i>com/img.jpg.”

Once you have identified the elements you want to customize, use the following command in Powershell to assign new values to the elements:

```powershell
Set-OrganizationAddInOverrides -Resources @{“ElementID” = “New Value”; “NextElementID” = “Next New Value”} 
```

You can customize as many elements with the command as you need to.

### Remove customization from an add-in

The only option currently available for deleting customizations is to delete all of them at once:

```powershell
Remove-OrganizationAddInOverrides -ProductId 5b31b349-2c41-4f94-b720-6ee40349d391 
```

### View add-in customizations

To view a list of applied customizations, run the **Get-OrganizationAddInOverrides** cmdlet. If **Get-OrganizationAddInOverrides** is run without a *ProductId* then a list of all add-ins with applied overrides are returned.  

```powershell
Get-OrganizationAddInOverrides 
```
If ProductId is specified, then a list of overrides applied to that add-in is returned. 

```powershell
Get-OrganizationAddInOverrides -ProductId 5b31b349-2c41-4f94-b720-6ee40349d391 
```

### Remove an add-in from local cache

If an add-in has been deployed, it has to be removed from the cache in each computer before it can be customized. To remive an add-in from cache:

1. Navigate to the “Users” folder in C:\ 
1. Go to your user folder
1. Navigate to AppData\Local\Microsoft\Office and select the folder associated with your version of Office
1. In the *Wef* folder delete the *Manifests* folder.

-->

## <a name="get-detailed-help-for-each-cmdlet"></a><span data-ttu-id="dde17-150">取得每個 Cmdlet 的詳細資訊</span><span class="sxs-lookup"><span data-stu-id="dde17-150">Get detailed help for each cmdlet</span></span>

<span data-ttu-id="dde17-151">您可以使用 Get-help 指令程式，查看每個 Cmdlet 的詳細說明。</span><span class="sxs-lookup"><span data-stu-id="dde17-151">You can look at detailed help for each cmdlet by using the Get-help cmdlet.</span></span> <span data-ttu-id="dde17-152">例如，下列 Cmdlet 提供 Remove-OrganizationAddIn Cmdlet 的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="dde17-152">For example, the following cmdlet provides detailed information about the Remove-OrganizationAddIn cmdlet.</span></span>
  
```powershell
Get-help Remove-OrganizationAddIn -Full
```