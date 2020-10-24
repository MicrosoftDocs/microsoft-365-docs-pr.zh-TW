---
title: 使用 PowerShell 來查看 Microsoft 365 使用者帳戶
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- LIL_Placement
- PowerShell
- Ent_Office_Other
- seo-marvel-apr2020
ms.assetid: bb12f49d-a85d-4f3b-ada2-5c4e33977b10
description: 瞭解如何使用 PowerShell 以不同方式來查看、列出或顯示 Microsoft 365 使用者帳戶。
ms.openlocfilehash: 312e9fb983c4d1f4de8bc74586c88f1e669eb90a
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754069"
---
# <a name="view-microsoft-365-user-accounts-with-powershell"></a><span data-ttu-id="20496-103">使用 PowerShell 來查看 Microsoft 365 使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="20496-103">View Microsoft 365 user accounts with PowerShell</span></span>

<span data-ttu-id="20496-104">*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*</span><span class="sxs-lookup"><span data-stu-id="20496-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="20496-105">您可以使用 Microsoft 365 系統管理中心來查看您的 Microsoft 365 租使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="20496-105">You can use the Microsoft 365 admin center to view the accounts for your Microsoft 365 tenant.</span></span> <span data-ttu-id="20496-106">PowerShell Microsoft 365 可啟用此功能，但也提供其他功能。</span><span class="sxs-lookup"><span data-stu-id="20496-106">PowerShell for Microsoft 365 enables this but also provides additional functionality.</span></span>
  
## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="20496-107">針對 Graph 模組，請使用 Azure Active Directory PowerShell</span><span class="sxs-lookup"><span data-stu-id="20496-107">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="20496-108">首先，連線 [至您的 Microsoft 365 租使用者](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)。</span><span class="sxs-lookup"><span data-stu-id="20496-108">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
  
### <a name="view-all-accounts"></a><span data-ttu-id="20496-109">查看所有帳戶</span><span class="sxs-lookup"><span data-stu-id="20496-109">View all accounts</span></span>

<span data-ttu-id="20496-110">若要顯示完整的使用者帳戶清單，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="20496-110">To display the full list of user accounts, run this command:</span></span>
  
```powershell
Get-AzureADUser
```

<span data-ttu-id="20496-111">您應該會收到類似以下的資訊：</span><span class="sxs-lookup"><span data-stu-id="20496-111">You should get information similar to this:</span></span>
  
```powershell
ObjectId                             DisplayName                                           UserPrincipalName
--------                             -----------                                           -----------------
032fc1fc-b5a2-46f1-8635-3d7dcb52c48d Adele Vance                                           AdeleV@litwareinc.OnMicr...
bd1e6af1-41e7-4f77-a2ac-5b209950135c Global Administrator                                  admin@litwareinc.onmicro...
ec37a4d6-232e-4eb7-82a5-1613490642a5 Alex Wilber                                           AlexW@litwareinc.OnMicro...
be4bdddd-c790-424c-9f96-a0cf609b7815 Allan Deyoung                                         AllanD@litwareinc.OnMicr...
598ab87b-76f0-4bf9-9538-bd46b10f4438 Christie Cline                                        ChristieC@litwareinc.OnM...
40722671-e520-4a5f-97d4-0bc9e9b2dc0f Debra Berger                                          DebraB@litwareinc.OnMicr...
```

### <a name="view-a-specific-account"></a><span data-ttu-id="20496-112">查看特定帳戶</span><span class="sxs-lookup"><span data-stu-id="20496-112">View a specific account</span></span>

<span data-ttu-id="20496-113">若要顯示特定的使用者帳戶，請執行下列命令。</span><span class="sxs-lookup"><span data-stu-id="20496-113">To display a specific user account, run the following command.</span></span> <span data-ttu-id="20496-114">填寫使用者帳戶的登入帳戶名稱，也稱為使用者主要名稱 (UPN) 。</span><span class="sxs-lookup"><span data-stu-id="20496-114">Fill in the sign-in account name of the user account, which is also known as the user principal name (UPN).</span></span> <span data-ttu-id="20496-115">移除 "<" 和 ">" 字元。</span><span class="sxs-lookup"><span data-stu-id="20496-115">Remove the "<" and ">" characters.</span></span>
  
```powershell
Get-AzureADUser -ObjectID <sign-in name of the user account>
```

<span data-ttu-id="20496-116">以下為範例：</span><span class="sxs-lookup"><span data-stu-id="20496-116">Here's an example:</span></span>
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com
```

### <a name="view-additional-property-values-for-a-specific-account"></a><span data-ttu-id="20496-117">查看特定帳戶的其他屬性值</span><span class="sxs-lookup"><span data-stu-id="20496-117">View additional property values for a specific account</span></span>

<span data-ttu-id="20496-118">根據預設， **AzureADUser** Cmdlet 只會顯示帳戶的 *ObjectID*、 *DisplayName*及 *UserPrincipalName* 屬性。</span><span class="sxs-lookup"><span data-stu-id="20496-118">By default, the **Get-AzureADUser** cmdlet only displays the *ObjectID*, *DisplayName*, and *UserPrincipalName* properties of accounts.</span></span>

<span data-ttu-id="20496-119">若要更選擇要顯示的內容，請搭配使用 **Select** Cmdlet 搭配 **AzureADUser 指令程式** 。</span><span class="sxs-lookup"><span data-stu-id="20496-119">To be more selective about the properties to display, use the **Select** cmdlet in combination with the **Get-AzureADUser** cmdlet.</span></span> <span data-ttu-id="20496-120">若要組合這兩個 Cmdlet，請使用 "管道" 字元 ( "|") ，它會通知 Azure Active Directory PowerShell 以取得一個命令的結果，並將其傳送至下一個命令。</span><span class="sxs-lookup"><span data-stu-id="20496-120">To combine the two cmdlets, use the "pipe" character ("|"), which tells Azure Active Directory PowerShell for Graph to take the results of one command and send it to the next command.</span></span> <span data-ttu-id="20496-121">以下是一個範例命令，會顯示每個使用者帳戶的 *DisplayName*、 *部門*和 *UsageLocation* ：</span><span class="sxs-lookup"><span data-stu-id="20496-121">Here's an example command that displays the *DisplayName*, *Department*, and *UsageLocation* for every user account:</span></span>
  
```powershell
Get-AzureADUser | Select DisplayName,Department,UsageLocation
```

<span data-ttu-id="20496-122">這個命令會指示 PowerShell：</span><span class="sxs-lookup"><span data-stu-id="20496-122">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="20496-123"> (**AzureADUser**) 取得使用者帳戶上的所有資訊，並將其傳送至下一個命令 (**|**) 。</span><span class="sxs-lookup"><span data-stu-id="20496-123">Get all the information on the user accounts (**Get-AzureADUser**) and send it to the next command (**|**).</span></span>
    
1.  <span data-ttu-id="20496-124">只顯示使用者帳戶名稱、部門和使用位置， (**選取 DisplayName、部門、UsageLocation**) 。</span><span class="sxs-lookup"><span data-stu-id="20496-124">Display only the user account name, department, and usage location (**Select DisplayName, Department, UsageLocation**).</span></span>
  
<span data-ttu-id="20496-125">若要查看特定使用者帳戶的所有屬性，請使用 **Select** Cmdlet 及萬用字元 ( \* ) 。</span><span class="sxs-lookup"><span data-stu-id="20496-125">To see all the properties for a specific user account, use the **Select** cmdlet and the wildcard character (\*).</span></span> <span data-ttu-id="20496-126">以下為範例：</span><span class="sxs-lookup"><span data-stu-id="20496-126">Here's an example:</span></span>
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com | Select *
```

<span data-ttu-id="20496-127">在另一個範例中，執行下列命令以檢查特定使用者帳戶的啟用狀態：</span><span class="sxs-lookup"><span data-stu-id="20496-127">As another example, run the following command to check the enabled status of a specific user account:</span></span>
  
```powershell
Get-AzureADUser -ObjectID <sign-in name of the user account> | Select DisplayName,UserPrincipalName,AccountEnabled
```

### <a name="view-account-synchronization-status"></a><span data-ttu-id="20496-128">查看帳戶同步處理狀態</span><span class="sxs-lookup"><span data-stu-id="20496-128">View account synchronization status</span></span>

<span data-ttu-id="20496-129">使用者帳戶有兩個來源：</span><span class="sxs-lookup"><span data-stu-id="20496-129">User accounts have two sources:</span></span> 

- <span data-ttu-id="20496-130">Windows Server Active Directory (AD) ，也就是從內部部署 AD 同步處理至雲端的帳戶。</span><span class="sxs-lookup"><span data-stu-id="20496-130">Windows Server Active Directory (AD), which are accounts that sync from on-premises AD to the cloud.</span></span>

- <span data-ttu-id="20496-131">Azure Active Directory (Azure AD) 直接在雲端中建立的 AD 帳戶。</span><span class="sxs-lookup"><span data-stu-id="20496-131">Azure Active Directory (Azure AD) AD accounts, which are created directly in the cloud.</span></span>


<span data-ttu-id="20496-132">下列命令會指示 PowerShell 取得屬性 *DirSyncEnabled* 設定為 *True*的所有使用者。</span><span class="sxs-lookup"><span data-stu-id="20496-132">The following command instructs PowerShell to get all users who have the attribute *DirSyncEnabled* set to *True*.</span></span> <span data-ttu-id="20496-133">您可以使用它來尋找與內部部署 AD 同步處理的帳戶。</span><span class="sxs-lookup"><span data-stu-id="20496-133">You can use it to find accounts that are synchronizing from on-premise AD.</span></span>

```powershell
Get-AzureADUser | Where {$_.DirSyncEnabled -eq $true}
```

<span data-ttu-id="20496-134">下列命令會指示 PowerShell 取得屬性 *DirSyncEnabled* 設定為 *False*的所有使用者。</span><span class="sxs-lookup"><span data-stu-id="20496-134">The following command instructs PowerShell to get all users who have the attribute *DirSyncEnabled* set to *False*.</span></span> <span data-ttu-id="20496-135">您可以使用它來尋找僅雲端帳戶。</span><span class="sxs-lookup"><span data-stu-id="20496-135">You can use it to find cloud-only accounts.</span></span>

```powershell
Get-AzureADUser | Where {$_.DirSyncEnabled -ne $false}
```

### <a name="view-accounts-based-on-a-common-property"></a><span data-ttu-id="20496-136">根據共同屬性來查看帳戶</span><span class="sxs-lookup"><span data-stu-id="20496-136">View accounts based on a common property</span></span>

<span data-ttu-id="20496-137">若要更選擇要顯示的帳戶清單，您可以使用 **Where** Cmdlet 搭配 **AzureADUser** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="20496-137">To be more selective about the list of accounts to display, you can use the **Where** cmdlet in combination with the **Get-AzureADUser** cmdlet.</span></span> <span data-ttu-id="20496-138">若要組合這兩個 Cmdlet，請使用 "管道" 字元 ( "|") ，它會通知 Azure Active Directory PowerShell 以取得一個命令的結果，並將其傳送至下一個命令。</span><span class="sxs-lookup"><span data-stu-id="20496-138">To combine the two cmdlets, use the "pipe" character ("|"), which tells Azure Active Directory PowerShell for Graph to take the results of one command and send it to the next command.</span></span> <span data-ttu-id="20496-139">以下範例命令只會顯示具有未指定使用位置的使用者帳戶：</span><span class="sxs-lookup"><span data-stu-id="20496-139">Here's an example command that displays only those user accounts that have an unspecified usage location:</span></span>
  
```powershell
Get-AzureADUser | Where {$_.UsageLocation -eq $Null}
```

<span data-ttu-id="20496-140">此命令會指導 Azure Active Directory PowerShell 的圖形：</span><span class="sxs-lookup"><span data-stu-id="20496-140">This command instructs Azure Active Directory PowerShell for Graph to:</span></span>
  
1. <span data-ttu-id="20496-141"> (**AzureADUser**) 取得使用者帳戶上的所有資訊，並將其傳送至下一個命令 (**|**) 。</span><span class="sxs-lookup"><span data-stu-id="20496-141">Get all the information on the user accounts (**Get-AzureADUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="20496-142">尋找所有未指定使用位置的使用者帳戶， (**其中 {$ \_ 。UsageLocation-eq $Null}**) 。</span><span class="sxs-lookup"><span data-stu-id="20496-142">Find all the user accounts that have an unspecified usage location (**Where {$\_.UsageLocation -eq $Null}**).</span></span> <span data-ttu-id="20496-143">在大括弧內，此命令會指示 PowerShell 只找出 UsageLocation 使用者帳戶屬性 (的帳戶集\*\* $ \_ 。\*\* 未指定 UsageLocation)  (**-eq $Null**) 。</span><span class="sxs-lookup"><span data-stu-id="20496-143">Inside the braces, the command instructs PowerShell to only find the set of accounts for which the UsageLocation user account property (**$\_.UsageLocation**) is not specified (**-eq $Null**).</span></span>
    
<span data-ttu-id="20496-144">**UsageLocation**屬性只是與使用者帳戶相關聯的眾多屬性之一。</span><span class="sxs-lookup"><span data-stu-id="20496-144">The **UsageLocation** property is only one of many properties associated with a user account.</span></span> <span data-ttu-id="20496-145">若要顯示特定使用者帳戶的所有屬性，請使用 **Select** Cmdlet 及萬用字元 ( \* ) 。</span><span class="sxs-lookup"><span data-stu-id="20496-145">To display all the properties for a specific user account, use the **Select** cmdlet and the wildcard character (\*).</span></span> <span data-ttu-id="20496-146">以下為範例：</span><span class="sxs-lookup"><span data-stu-id="20496-146">Here's an example:</span></span>
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com | Select *
```

<span data-ttu-id="20496-147">例如，「 **城市** 」是使用者帳戶屬性的名稱。</span><span class="sxs-lookup"><span data-stu-id="20496-147">For example, **City** is the name of a user account property.</span></span> <span data-ttu-id="20496-148">您可以使用下列命令列出居住在倫敦的所有使用者帳戶：</span><span class="sxs-lookup"><span data-stu-id="20496-148">You can use the following command to list all accounts of users who live in London:</span></span>
  
```powershell
Get-AzureADUser | Where {$_.City -eq "London"}
```

> [!TIP]
>  <span data-ttu-id="20496-149">在這些範例中， **where** Cmdlet 的語法是 **{$ \_ 。**</span><span class="sxs-lookup"><span data-stu-id="20496-149">The syntax for the **Where** cmdlet in these examples is **Where {$\_.**</span></span> <span data-ttu-id="20496-150">[user account property name][比較運算子]值 **}**。 > [comparison 運算子] 是 **-eq** for equals，- **ne** 代表不等於，- **lt** 代表小於， **-gt** 代表大於，其他。</span><span class="sxs-lookup"><span data-stu-id="20496-150">[user account property name] [comparison operator] [value] **}**.> [comparison operator] is **-eq** for equals, **-ne** for not equals, **-lt** for less than, **-gt** for greater than, and others.</span></span>  <span data-ttu-id="20496-151">[value] 通常是一個字串， (字母、數位及其他字元的順序) 、數值或未指定的 **$Null** 。</span><span class="sxs-lookup"><span data-stu-id="20496-151">[value] is typically a string (a sequence of letters, numbers, and other characters), a numerical value, or **$Null** for unspecified.</span></span> <span data-ttu-id="20496-152">如需詳細資訊，請參閱 [Where](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/where-object?view=powershell-7)。</span><span class="sxs-lookup"><span data-stu-id="20496-152">For more information, see [Where](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/where-object?view=powershell-7).</span></span>
  

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="20496-153">使用適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組。</span><span class="sxs-lookup"><span data-stu-id="20496-153">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="20496-154">首先，連線 [至您的 Microsoft 365 租使用者](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)。</span><span class="sxs-lookup"><span data-stu-id="20496-154">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

### <a name="view-all-accounts"></a><span data-ttu-id="20496-155">查看所有帳戶</span><span class="sxs-lookup"><span data-stu-id="20496-155">View all accounts</span></span>

<span data-ttu-id="20496-156">若要顯示完整的使用者帳戶清單，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="20496-156">To display the full list of user accounts, run this command:</span></span>
  
```powershell
Get-MsolUser
```

>[!Note]
><span data-ttu-id="20496-157">PowerShell 核心不支援 Windows PowerShell 模組的 Microsoft Azure Active Directory 模組，以及其名稱中含有 *Msol* 的 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="20496-157">PowerShell Core doesn't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with *Msol* in their name.</span></span> <span data-ttu-id="20496-158">從 Windows PowerShell 執行這些 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="20496-158">Run these cmdlets from Windows PowerShell.</span></span>
>

<span data-ttu-id="20496-159">您應該會收到類似以下的資訊：</span><span class="sxs-lookup"><span data-stu-id="20496-159">You should get information similar to this:</span></span>
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BonnieK@litwareinc.onmicrosoft.com    Bonnie Kearney        True
FabriceC@litwareinc.onmicrosoft.com   Fabrice Canel         True
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False 
AnneWlitwareinc.onmicrosoft.com       Anne Wallace          True
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False
```

<span data-ttu-id="20496-160">**Get-MsolUser**指令程式也有一組參數，用來篩選顯示的使用者帳戶集。</span><span class="sxs-lookup"><span data-stu-id="20496-160">The **Get-MsolUser** cmdlet also has a set of parameters to filter the set of user accounts displayed.</span></span> <span data-ttu-id="20496-161">例如，針對未經許可的使用者清單 (已新增至 Microsoft 365 的使用者，但是尚未獲得授權使用任何服務) ，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="20496-161">For example, for the list of unlicensed users (users who have been added to Microsoft 365 but haven't yet been licensed to use any of the services), run this command:</span></span>
  
```powershell
Get-MsolUser -UnlicensedUsersOnly
```

<span data-ttu-id="20496-162">您應該會收到類似以下的資訊：</span><span class="sxs-lookup"><span data-stu-id="20496-162">You should get information similar to this:</span></span>
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False
```

<span data-ttu-id="20496-163">如需其他參數以篩選顯示的使用者帳戶集合的詳細資訊，請參閱 [Get-MsolUser](https://docs.microsoft.com/previous-versions/azure/dn194133(v=azure.100))。</span><span class="sxs-lookup"><span data-stu-id="20496-163">For information about additional parameters to filter the set of user accounts that are displayed, see [Get-MsolUser](https://docs.microsoft.com/previous-versions/azure/dn194133(v=azure.100)).</span></span>
  
### <a name="view-a-specific-account"></a><span data-ttu-id="20496-164">查看特定帳戶</span><span class="sxs-lookup"><span data-stu-id="20496-164">View a specific account</span></span>

<span data-ttu-id="20496-165">若要顯示特定的使用者帳戶，請執行下列命令。</span><span class="sxs-lookup"><span data-stu-id="20496-165">To display a specific user account, run the following command.</span></span> <span data-ttu-id="20496-166">填寫使用者帳戶的登入名稱，也稱為使用者主要名稱 (UPN) 。</span><span class="sxs-lookup"><span data-stu-id="20496-166">Fill in the sign-in name of the user account, which is also known as the user principal name (UPN).</span></span> <span data-ttu-id="20496-167">移除 "<" 和 ">" 字元。</span><span class="sxs-lookup"><span data-stu-id="20496-167">Remove the "<" and ">" characters.</span></span>
  
```powershell
Get-MsolUser -UserPrincipalName <sign-in name of the user account>
```

### <a name="view-accounts-based-on-a-common-property"></a><span data-ttu-id="20496-168">根據共同屬性來查看帳戶</span><span class="sxs-lookup"><span data-stu-id="20496-168">View accounts based on a common property</span></span>

<span data-ttu-id="20496-169">若要更選擇要顯示的帳戶清單，您可以使用 **Where** Cmdlet 與 **Get-MsolUser** Cmdlet 結合使用。</span><span class="sxs-lookup"><span data-stu-id="20496-169">To be more selective about the list of accounts to display, you can use the **Where** cmdlet in combination with the **Get-MsolUser** cmdlet.</span></span> <span data-ttu-id="20496-170">若要組合這兩個 Cmdlet，請使用 "管道" 字元 ( "|") ，告知 PowerShell 取得一個命令的結果，並將它傳送至下一個命令。</span><span class="sxs-lookup"><span data-stu-id="20496-170">To combine the two cmdlets, use the "pipe" character ("|"), which tells PowerShell to take the results of one command and send it to the next command.</span></span> <span data-ttu-id="20496-171">以下範例只會顯示具有未指定使用位置的使用者帳戶：</span><span class="sxs-lookup"><span data-stu-id="20496-171">Here's an example that displays only those user accounts that have an unspecified usage location:</span></span>
  
```powershell
Get-MsolUser | Where {$_.UsageLocation -eq $Null}
```

<span data-ttu-id="20496-172">這個命令會指示 PowerShell：</span><span class="sxs-lookup"><span data-stu-id="20496-172">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="20496-173">**Get-MsolUser**) 取得使用者帳戶 (的所有資訊，並將其傳送至下一個命令 (**|**) 。</span><span class="sxs-lookup"><span data-stu-id="20496-173">Get all the information on the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="20496-174">尋找所有未指定使用位置的使用者帳戶， (**其中 {$ \_ 。UsageLocation-eq $Null}**) 。</span><span class="sxs-lookup"><span data-stu-id="20496-174">Find all user accounts that have an unspecified usage location (**Where {$\_.UsageLocation -eq $Null}**).</span></span> <span data-ttu-id="20496-175">在大括弧內，此命令會指示 PowerShell 只尋找 UsageLocation 使用者帳戶屬性 (的帳戶集\*\* $ \_ 。\*\* 未指定 UsageLocation)  (**-eq $Null**) 。</span><span class="sxs-lookup"><span data-stu-id="20496-175">Inside the braces, the command instructs PowerShell to find only the set of accounts for which the UsageLocation user account property (**$\_.UsageLocation**) is not specified (**-eq $Null**).</span></span>
    
<span data-ttu-id="20496-176">您應該會收到類似以下的資訊：</span><span class="sxs-lookup"><span data-stu-id="20496-176">You should get information similar to this:</span></span>
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False 
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False

```

<span data-ttu-id="20496-177">*UsageLocation*屬性只是與使用者帳戶相關聯的眾多屬性之一。</span><span class="sxs-lookup"><span data-stu-id="20496-177">The *UsageLocation* property is only one of many properties associated with a user account.</span></span> <span data-ttu-id="20496-178">若要查看使用者帳戶的所有屬性，請使用 **Select** Cmdlet 及萬用字元 ( \* ) 以顯示特定使用者帳戶的所有屬性。</span><span class="sxs-lookup"><span data-stu-id="20496-178">To see all of the properties for user accounts, use the **Select** cmdlet and the wildcard character (\*) to display them all for a specific user account.</span></span> <span data-ttu-id="20496-179">以下為範例：</span><span class="sxs-lookup"><span data-stu-id="20496-179">Here's an example:</span></span>
  
```powershell
Get-MsolUser -UserPrincipalName BelindaN@litwareinc.onmicosoft.com | Select *
```

<span data-ttu-id="20496-180">例如，「 *城市* 」是使用者帳戶屬性的名稱。</span><span class="sxs-lookup"><span data-stu-id="20496-180">For example, *City* is the name of a user account property.</span></span> <span data-ttu-id="20496-181">您可以使用下列命令來列出居住在倫敦的使用者的所有使用者帳戶：</span><span class="sxs-lookup"><span data-stu-id="20496-181">You can use the following command to list all of the user accounts for users who live in London:</span></span>
  
```powershell
Get-MsolUser | Where {$_.City -eq "London"}
```

> [!TIP]
>  <span data-ttu-id="20496-182">在這些範例中， **where** Cmdlet 的語法是 **{$ \_ 。**</span><span class="sxs-lookup"><span data-stu-id="20496-182">The syntax for the **Where** cmdlet in these examples is **Where {$\_.**</span></span> <span data-ttu-id="20496-183">[user account property name][比較運算子]值 **}**.</span><span class="sxs-lookup"><span data-stu-id="20496-183">[user account property name] [comparison operator] [value] **}**.</span></span>  <span data-ttu-id="20496-184">[比較運算子] 的 **-eq** 代表 equals，- **ne** 代表不等於， **-lt** 代表小於， **-gt** 代表大於，其他。</span><span class="sxs-lookup"><span data-stu-id="20496-184">[comparison operator] is **-eq** for equals, **-ne** for not equals, **-lt** for less than, **-gt** for greater than, and others.</span></span>  <span data-ttu-id="20496-185">[value] 通常是一個字串， (字母、數位及其他字元的順序) 、數值或未指定的 **$Null** 。</span><span class="sxs-lookup"><span data-stu-id="20496-185">[value] is typically a string (a sequence of letters, numbers, and other characters), a numerical value, or **$Null** for unspecified.</span></span> <span data-ttu-id="20496-186">如需詳細資訊，請參閱 [Where](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/where-object?view=powershell-7)。</span><span class="sxs-lookup"><span data-stu-id="20496-186">For more information, see [Where](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/where-object?view=powershell-7).</span></span>
  
<span data-ttu-id="20496-187">若要檢查使用者帳戶的封鎖狀態，請使用下列命令：</span><span class="sxs-lookup"><span data-stu-id="20496-187">To check the blocked status of a user account, use the following command:</span></span>
  
```powershell
Get-MsolUser -UserPrincipalName <UPN of user account> | Select DisplayName,BlockCredential
```

### <a name="view-additional-property-values-for-accounts"></a><span data-ttu-id="20496-188">查看帳戶的其他屬性值</span><span class="sxs-lookup"><span data-stu-id="20496-188">View additional property values for accounts</span></span>

<span data-ttu-id="20496-189">根據預設， **Get-MsolUser** Cmdlet 會顯示使用者帳戶的三個屬性：</span><span class="sxs-lookup"><span data-stu-id="20496-189">By default, the **Get-MsolUser** cmdlet displays these three properties of user accounts:</span></span>
  
- <span data-ttu-id="20496-190">UserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="20496-190">UserPrincipalName</span></span>
    
- <span data-ttu-id="20496-191">DisplayName</span><span class="sxs-lookup"><span data-stu-id="20496-191">DisplayName</span></span>
    
- <span data-ttu-id="20496-192">Islicensed 內容</span><span class="sxs-lookup"><span data-stu-id="20496-192">isLicensed</span></span>
    
<span data-ttu-id="20496-193">如果您需要其他屬性，例如使用者在其中運作的部門，以及他們使用 Microsoft 365 服務的國家/地區，您可以同時執行 **Get-MsolUser** 與 **Select** 資訊清單，以指定使用者帳戶屬性的清單。</span><span class="sxs-lookup"><span data-stu-id="20496-193">If you need additional properties, such as the department where the user works and the country/region where they use Microsoft 365 services, you can run **Get-MsolUser** in combination with the **Select** cmdlet to specify the list of user account properties.</span></span> <span data-ttu-id="20496-194">以下為範例：</span><span class="sxs-lookup"><span data-stu-id="20496-194">Here's an example:</span></span>
  
```powershell
Get-MsolUser | Select DisplayName, Department, UsageLocation
```

<span data-ttu-id="20496-195">這個命令會指示 PowerShell：</span><span class="sxs-lookup"><span data-stu-id="20496-195">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="20496-196">取得 (**Get-MsolUser**) 的使用者帳戶資訊，並將其傳送至下一個命令 (**|**) 。</span><span class="sxs-lookup"><span data-stu-id="20496-196">Get all the information about the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="20496-197">只顯示使用者帳戶名稱、部門和使用位置， (**選取 DisplayName、部門、UsageLocation**) 。</span><span class="sxs-lookup"><span data-stu-id="20496-197">Display only the user account name, department, and usage location (**Select DisplayName, Department, UsageLocation**).</span></span>
    
<span data-ttu-id="20496-198">您應該會收到類似以下的資訊：</span><span class="sxs-lookup"><span data-stu-id="20496-198">You should get information similar to this:</span></span>
  
```powershell
DisplayName             Department                       UsageLocation
-----------             ----------                       -------------
Bonnie Kearney          Sales & Marketing                    US
Fabrice Canel           Legal                                US
Brian Johnson
Anne Wallace            Executive Management                 US
Alex Darrow             Sales & Marketing                    US
Scott Wallace           Operations
```

<span data-ttu-id="20496-199">**Select** Cmdlet 可讓您選擇要顯示的屬性。</span><span class="sxs-lookup"><span data-stu-id="20496-199">The **Select** cmdlet lets you choose what properties to display.</span></span> <span data-ttu-id="20496-200">若要顯示特定使用者帳戶的所有屬性，請使用通配字元 ( \* ) 。</span><span class="sxs-lookup"><span data-stu-id="20496-200">To display all the properties for a specific user account, use the wildcard character (\*).</span></span> <span data-ttu-id="20496-201">以下為範例：</span><span class="sxs-lookup"><span data-stu-id="20496-201">Here's an example:</span></span>
  
```powershell
Get-MsolUser -UserPrincipalName BelindaN@litwareinc.onmicosoft.com | Select *
```

<span data-ttu-id="20496-202">若要更選擇要顯示的帳戶清單，您也可以使用 **Where** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="20496-202">To be more selective about the list of accounts to display, you can also use the **Where** cmdlet.</span></span> <span data-ttu-id="20496-203">以下範例命令只會顯示具有未指定使用位置的使用者帳戶：</span><span class="sxs-lookup"><span data-stu-id="20496-203">Here's an example command that displays only those user accounts that have an unspecified usage location:</span></span>
  
```powershell
Get-MsolUser | Where {$_.UsageLocation -eq $Null} | Select DisplayName, Department, UsageLocation
```

<span data-ttu-id="20496-204">這個命令會指示 PowerShell：</span><span class="sxs-lookup"><span data-stu-id="20496-204">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="20496-205">取得 (**Get-MsolUser**) 的使用者帳戶資訊，並將其傳送至下一個命令 (**|**) 。</span><span class="sxs-lookup"><span data-stu-id="20496-205">Get all the information about the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="20496-206">尋找所有未指定使用位置的使用者帳戶， (**其中 {$ \_ 。UsageLocation-eq $Null}**) ，並將產生的資訊傳送至下一個命令 (**|**) 。</span><span class="sxs-lookup"><span data-stu-id="20496-206">Find all user accounts that have an unspecified usage location (**Where {$\_.UsageLocation -eq $Null}**), and send the resulting information to the next command (**|**).</span></span> <span data-ttu-id="20496-207">在大括弧內，此命令會指示 PowerShell 只找出 UsageLocation 使用者帳戶屬性 (的帳戶集\*\* $ \_ 。\*\* 未指定 UsageLocation)  (**-eq $Null**) 。</span><span class="sxs-lookup"><span data-stu-id="20496-207">Inside the braces, the command instructs PowerShell to only find the set of accounts for which the UsageLocation user account property (**$\_.UsageLocation**) is not specified (**-eq $Null**).</span></span>
    
1. <span data-ttu-id="20496-208">只顯示使用者帳戶名稱、部門和使用位置， (**選取 DisplayName、部門、UsageLocation**) 。</span><span class="sxs-lookup"><span data-stu-id="20496-208">Display only the user account name, department, and usage location (**Select DisplayName, Department, UsageLocation**).</span></span>
    
<span data-ttu-id="20496-209">您應該會收到類似以下的資訊：</span><span class="sxs-lookup"><span data-stu-id="20496-209">You should get information similar to this:</span></span>
  
```powershell
DisplayName              Department                      UsageLocation
-----------              ----------                      -------------
Brian Johnson 
Scott Wallace            Operations
```

<span data-ttu-id="20496-210">如果您是使用目錄同步處理來建立及管理 Microsoft 365 使用者，您可以顯示已計畫 Microsoft 365 使用者的本機帳戶。</span><span class="sxs-lookup"><span data-stu-id="20496-210">If you're using directory synchronization to create and manage your Microsoft 365 users, you can display the local account from which a Microsoft 365 user has been projected.</span></span> <span data-ttu-id="20496-211">下列範例假設：</span><span class="sxs-lookup"><span data-stu-id="20496-211">The following example assumes that:</span></span>

- <span data-ttu-id="20496-212">Azure AD Connect 設定為使用 ObjectGUID 的預設來源錨點。</span><span class="sxs-lookup"><span data-stu-id="20496-212">Azure AD Connect is configured to use the default source anchor of ObjectGUID.</span></span> <span data-ttu-id="20496-213"> (如需設定來源錨點的詳細資訊，請參閱 [AZURE AD Connect：設計概念](https://docs.microsoft.com/azure/active-directory/hybrid/plan-connect-design-concepts)) 。</span><span class="sxs-lookup"><span data-stu-id="20496-213">(For more information about configuring a source anchor, see [Azure AD Connect: Design concepts](https://docs.microsoft.com/azure/active-directory/hybrid/plan-connect-design-concepts)).</span></span>
- <span data-ttu-id="20496-214">已安裝 PowerShell 的 Active Directory 網域服務模組 (請參閱 [RSAT tools](https://www.microsoft.com/en-gb/download/details.aspx?id=45520)) 。</span><span class="sxs-lookup"><span data-stu-id="20496-214">The Active Directory Domain Services module for PowerShell has been installed (see [RSAT tools](https://www.microsoft.com/en-gb/download/details.aspx?id=45520)).</span></span>

```powershell
Get-ADUser ([guid][System.Convert]::FromBase64String((Get-MsolUser -UserPrincipalName <UPN of user account>).ImmutableID)).guid
```

## <a name="see-also"></a><span data-ttu-id="20496-215">請參閱</span><span class="sxs-lookup"><span data-stu-id="20496-215">See also</span></span>

[<span data-ttu-id="20496-216">以 PowerShell 管理 Microsoft 365 使用者帳戶、授權和群組</span><span class="sxs-lookup"><span data-stu-id="20496-216">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="20496-217">使用 PowerShell 管理 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="20496-217">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="20496-218">開始使用適用於 Microsoft 365 的 PowerShell</span><span class="sxs-lookup"><span data-stu-id="20496-218">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
