---
title: 使用 PowerShell 管理商務用 Skype Online 原則
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- NOCSH
ms.custom: ''
ms.assetid: ff93a341-6f0f-4f06-9690-726052e1be64
description: 摘要：使用 PowerShell，使用原則來管理商務用 Skype Online 使用者帳戶屬性。
ms.openlocfilehash: ca945bc05e76525b4b2df6fb0b982a8468d87810
ms.sourcegitcommit: babbba2b5bf69fd3facde2905ec024b753dcd1b3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/06/2021
ms.locfileid: "50515049"
---
# <a name="manage-skype-for-business-online-policies-with-powershell"></a><span data-ttu-id="3062f-103">使用 PowerShell 管理商務用 Skype Online 原則</span><span class="sxs-lookup"><span data-stu-id="3062f-103">Manage Skype for Business Online policies with PowerShell</span></span>

<span data-ttu-id="3062f-104">*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*</span><span class="sxs-lookup"><span data-stu-id="3062f-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="3062f-105">若要管理商務用 Skype Online 之使用者帳戶的許多屬性，您必須使用 Microsoft 365 的 PowerShell，將其指定為原則的屬性。</span><span class="sxs-lookup"><span data-stu-id="3062f-105">To manage many properties of user account for Skype for Business Online, you must specify them as properties of policies with PowerShell for Microsoft 365.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="3062f-106">開始之前</span><span class="sxs-lookup"><span data-stu-id="3062f-106">Before you begin</span></span>

<span data-ttu-id="3062f-107">使用下列指示設定執行命令 (略過已完成的步驟) ：</span><span class="sxs-lookup"><span data-stu-id="3062f-107">Use these instructions to get set up to run the commands (skip the steps you have already completed):</span></span>

  > [!Note]
  > <span data-ttu-id="3062f-108">商務用 Skype Online 連接器目前是最新 Teams PowerShell 模組的一部分。</span><span class="sxs-lookup"><span data-stu-id="3062f-108">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span> <span data-ttu-id="3062f-109">如果您使用的是最新的 Teams PowerShell 公開發行版本，則不需要安裝商務用 Skype Online 連接器。</span><span class="sxs-lookup"><span data-stu-id="3062f-109">If you're using the latest Teams PowerShell public release, you don't need to install the Skype for Business Online Connector.</span></span>

1. <span data-ttu-id="3062f-110">安裝 [團隊 PowerShell 模組](https://docs.microsoft.com/microsoftteams/teams-powershell-install)。</span><span class="sxs-lookup"><span data-stu-id="3062f-110">Install the [Teams PowerShell module](https://docs.microsoft.com/microsoftteams/teams-powershell-install).</span></span>
    
2. <span data-ttu-id="3062f-111">開啟 Windows PowerShell 命令提示字元，然後執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="3062f-111">Open a Windows PowerShell command prompt and run the following commands:</span></span> 

   ```powershell
   Import-Module MicrosoftTeams
   $userCredential = Get-Credential
   Connect-MicrosoftTeams -Credential $userCredential
   ```

   <span data-ttu-id="3062f-112">出現提示時，請輸入您的商務用 Skype Online 系統管理員帳戶名稱和密碼。</span><span class="sxs-lookup"><span data-stu-id="3062f-112">When prompted, enter your Skype for Business Online administrator account name and password.</span></span>
    
## <a name="manage-user-account-policies"></a><span data-ttu-id="3062f-113">管理使用者帳戶原則</span><span class="sxs-lookup"><span data-stu-id="3062f-113">Manage user account policies</span></span>

<span data-ttu-id="3062f-114">許多商務用 Skype Online 使用者帳戶屬性是使用原則進行設定。</span><span class="sxs-lookup"><span data-stu-id="3062f-114">Many Skype for Business Online user account properties are configured by using policies.</span></span> <span data-ttu-id="3062f-115">原則只是可套用至一或多個使用者的設定集合。</span><span class="sxs-lookup"><span data-stu-id="3062f-115">Policies are simply collections of settings that can be applied to one or more users.</span></span> <span data-ttu-id="3062f-116">若要查看原則的設定方式，您可以對 FederationAndPICDefault 原則執行此範例命令：</span><span class="sxs-lookup"><span data-stu-id="3062f-116">To take a look at how the a policy has been configured, you can run this example command for the FederationAndPICDefault policy:</span></span>
  
```powershell
Get-CsExternalAccessPolicy -Identity "FederationAndPICDefault"
```

<span data-ttu-id="3062f-117">反過來，您應該會收到類似以下的內容：</span><span class="sxs-lookup"><span data-stu-id="3062f-117">In turn, you should get back something similar to this:</span></span>
  
```powershell
Identity                          : Tag:FederationAndPICDefault
Description                       :
EnableFederationAccess            : True
EnableXmppAccess                  : False
EnablePublicCloudAccess           : True
EnablePublicCloudAudioVideoAccess : True
EnableOutsideAccess               : True
```

<span data-ttu-id="3062f-118">在此範例中，此原則中的值會決定在與同盟使用者通訊時，可使用或無法執行的動作。</span><span class="sxs-lookup"><span data-stu-id="3062f-118">In this example, the values within this policy determine what a use can or cannot do when it comes to communicating with federated users.</span></span> <span data-ttu-id="3062f-119">例如，EnableOutsideAccess 屬性必須設定為 True，使用者才能夠與組織外部的人員進行通訊。</span><span class="sxs-lookup"><span data-stu-id="3062f-119">For example, the EnableOutsideAccess property must be set to True for a user to be able to communicate with people outside the organization.</span></span> <span data-ttu-id="3062f-120">請注意，此屬性不會出現在 Microsoft 365 系統管理中心中。</span><span class="sxs-lookup"><span data-stu-id="3062f-120">Note that this property does not appear in the Microsoft 365 admin center.</span></span> <span data-ttu-id="3062f-121">相反地，此屬性會根據您所做的其他選擇，自動設定為 True 或 False。</span><span class="sxs-lookup"><span data-stu-id="3062f-121">Instead, the property is automatically set to True or False based on the other selections that you make.</span></span> <span data-ttu-id="3062f-122">其他兩個感興趣的屬性如下：</span><span class="sxs-lookup"><span data-stu-id="3062f-122">The other two properties of interest are:</span></span>
  
- <span data-ttu-id="3062f-123">**EnableFederationAccess** 指出使用者是否可以與同盟網域的使用者進行通訊。</span><span class="sxs-lookup"><span data-stu-id="3062f-123">**EnableFederationAccess** indicates whether the user can communicate with people from federated domains.</span></span>
    
- <span data-ttu-id="3062f-124">**EnablePublicCloudAccess** 指出使用者是否可以與 Windows Live 使用者進行通訊。</span><span class="sxs-lookup"><span data-stu-id="3062f-124">**EnablePublicCloudAccess** indicates whether the user can communicate with Windows Live users.</span></span>
    
<span data-ttu-id="3062f-125">因此，您不會直接變更使用者帳戶上的同盟相關屬性 (例如 **Set-CsUser EnableFederationAccess $True**) 。</span><span class="sxs-lookup"><span data-stu-id="3062f-125">Therefore, you don't directly change federation-related properties on user accounts (for example, **Set-CsUser -EnableFederationAccess $True**).</span></span> <span data-ttu-id="3062f-126">相反地，您會指派具有所需屬性值預先設定的外部存取原則。</span><span class="sxs-lookup"><span data-stu-id="3062f-126">Instead, you assign an account an external access policy that has the desired property values preconfigured.</span></span> <span data-ttu-id="3062f-127">若要讓使用者能夠與同盟使用者和 Windows Live 使用者進行通訊，則必須將該使用者帳戶指派給允許通訊類型的原則。</span><span class="sxs-lookup"><span data-stu-id="3062f-127">If we want a user to be able to communicate with federated users and with Windows Live users, that user account must be assigned a policy that allows those types of communication.</span></span>
  
<span data-ttu-id="3062f-128">如果您想要知道某人是否可以與組織外部的使用者進行通訊，您必須：</span><span class="sxs-lookup"><span data-stu-id="3062f-128">If you want to know whether or not someone can communicate with users from outside the organization, you have to:</span></span>
  
- <span data-ttu-id="3062f-129">判斷已指派哪個外部存取原則給該使用者。</span><span class="sxs-lookup"><span data-stu-id="3062f-129">Determine which external access policy has been assigned to that user.</span></span>
    
- <span data-ttu-id="3062f-130">判斷該原則允許或不允許哪些功能。</span><span class="sxs-lookup"><span data-stu-id="3062f-130">Determine which capabilities are or are not allowed by that policy.</span></span>
    
<span data-ttu-id="3062f-131">例如，您可以使用下列命令來執行這項操作：</span><span class="sxs-lookup"><span data-stu-id="3062f-131">For example, you can do that by using this command:</span></span>
  
```powershell
Get-CsOnlineUser -Identity "Alex Darrow" | ForEach {Get-CsExternalAccessPolicy -Identity $_.ExternalAccessPolicy}
```

<span data-ttu-id="3062f-132">這個命令會尋找指派給使用者的原則，然後尋找該原則中啟用或停用的功能。</span><span class="sxs-lookup"><span data-stu-id="3062f-132">This command finds the policy assigned to the user, then finds the capabilities enabled or disabled within that policy.</span></span>
  
<span data-ttu-id="3062f-133">若要使用 PowerShell 管理商務用 Skype Online 原則，請參閱下列的 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="3062f-133">To manage Skype for Business Online policies with PowerShell, see the cmdlets for:</span></span>

- <span data-ttu-id="3062f-134">[用戶端原則](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#client-policy-cmdlets)</span><span class="sxs-lookup"><span data-stu-id="3062f-134">[Client policy](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#client-policy-cmdlets)</span></span>
- <span data-ttu-id="3062f-135">[會議原則](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#conferencing-policy-cmdlets)</span><span class="sxs-lookup"><span data-stu-id="3062f-135">[Conferencing policy](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#conferencing-policy-cmdlets)</span></span>
- <span data-ttu-id="3062f-136">[行動原則](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#mobile-policy-cmdlets)</span><span class="sxs-lookup"><span data-stu-id="3062f-136">[Mobile policy](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#mobile-policy-cmdlets)</span></span>
- <span data-ttu-id="3062f-137">[線上語音信箱原則](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#online-voicemail-policy-cmdlets)</span><span class="sxs-lookup"><span data-stu-id="3062f-137">[Online Voicemail policy](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#online-voicemail-policy-cmdlets)</span></span>
- <span data-ttu-id="3062f-138">[語音路由原則](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#voice-routing-policy-cmdlets)</span><span class="sxs-lookup"><span data-stu-id="3062f-138">[Voice Routing policy](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#voice-routing-policy-cmdlets)</span></span>


> [!NOTE]
> <span data-ttu-id="3062f-139">商務用 Skype Online 撥號對應表是除了名稱以外的每個原則中的原則。</span><span class="sxs-lookup"><span data-stu-id="3062f-139">A Skype for Business Online dial plan is a policy in every respect except the name.</span></span> <span data-ttu-id="3062f-140">已選擇名稱「撥號對應表」，而不是 "撥號原則"，以便提供與 Office 通訊伺服器及 Exchange 的回溯相容性。</span><span class="sxs-lookup"><span data-stu-id="3062f-140">The name "dial plan" was chosen instead of, say, "dialing policy" in order to provide backward compatibility with Office Communications Server and with Exchange.</span></span> 
  
<span data-ttu-id="3062f-141">例如，若要查看所有可供使用的語音原則，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="3062f-141">For example, to look at all the voice policies available for your use, run this command:</span></span>
  
```powershell
Get-CsVoicePolicy
```

> [!NOTE]
> <span data-ttu-id="3062f-142">這會傳回所有可用的語音原則清單。</span><span class="sxs-lookup"><span data-stu-id="3062f-142">That returns a list of all the voice policies available to you.</span></span> <span data-ttu-id="3062f-143">不過，請記住，並非所有原則都可以指派給所有使用者。</span><span class="sxs-lookup"><span data-stu-id="3062f-143">Keep in mind, however, that not all policies can be assigned to all users.</span></span> <span data-ttu-id="3062f-144">這是因為授權和地理位置的各種限制。</span><span class="sxs-lookup"><span data-stu-id="3062f-144">This is due to various restrictions involving licensing and geographic location.</span></span> <span data-ttu-id="3062f-145"> (所謂的「[使用位置](https://msdn.microsoft.com/library/azure/dn194136.aspx)」。) 如果您想知道可指派給特定使用者的外部存取原則及會議原則，請使用類似下列的命令：</span><span class="sxs-lookup"><span data-stu-id="3062f-145">(The so-called "[usage location](https://msdn.microsoft.com/library/azure/dn194136.aspx).") If you want to know the external access policies and the conferencing policies that can be assigned to a particular user, use commands similar to these:</span></span> 

```powershell
Get-CsConferencingPolicy -ApplicableTo "Alex Darrow"
Get-CsExternalAccessPolicy -ApplicableTo "Alex Darrow"
```

<span data-ttu-id="3062f-p107">[ApplicableTo] 參數會對可指派給特定使用者 (例如，Alex Darrow) 的原則限制傳回的資料。根據授權及使用位置的限制，這可能代表所有可用原則的子集。</span><span class="sxs-lookup"><span data-stu-id="3062f-p107">The ApplicableTo parameter limits the returned data to policies that can be assigned to the specified user (for example, Alex Darrow). Depending on licensing and usage location restrictions, that might represent a subset of all the available policies.</span></span> 
  
<span data-ttu-id="3062f-148">在某些情況下，原則的屬性不會與 Microsoft 365 搭配使用，而有些則只能由 Microsoft 支援人員管理。</span><span class="sxs-lookup"><span data-stu-id="3062f-148">In some cases, properties of policies are not used with Microsoft 365, while others can only be managed by Microsoft support personnel.</span></span> 
  
<span data-ttu-id="3062f-149">透過商務用 Skype Online，使用者必須以某種類型的原則來管理。</span><span class="sxs-lookup"><span data-stu-id="3062f-149">With Skype for Business Online, users must be managed by a policy of some kind.</span></span> <span data-ttu-id="3062f-150">如果有效的原則相關屬性為空白，這表示有問題的使用者是由全域原則所管理，這是自動套用至使用者的原則，除非使用者特別指派每個使用者原則。</span><span class="sxs-lookup"><span data-stu-id="3062f-150">If a valid policy-related property is blank, that means that the user in question is being managed by a global policy, which is a policy that is automatically applied to a user unless he or she is specifically assigned a per-user policy.</span></span> <span data-ttu-id="3062f-151">因為我們沒有看到針對使用者帳戶所列出的用戶端原則，所以它是由全域原則所管理。</span><span class="sxs-lookup"><span data-stu-id="3062f-151">Because we don't see a client policy listed for a user account, it is managed by the global policy.</span></span> <span data-ttu-id="3062f-152">您可以使用下列命令來判斷全域用戶端原則：</span><span class="sxs-lookup"><span data-stu-id="3062f-152">You can determine the global client policy with this command:</span></span>
  
```powershell
Get-CsClientPolicy -Identity "Global"
```

## <a name="see-also"></a><span data-ttu-id="3062f-153">另請參閱</span><span class="sxs-lookup"><span data-stu-id="3062f-153">See also</span></span>

[<span data-ttu-id="3062f-154">使用 PowerShell 管理商務用 Skype Online</span><span class="sxs-lookup"><span data-stu-id="3062f-154">Manage Skype for Business Online with PowerShell</span></span>](manage-skype-for-business-online-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="3062f-155">使用 PowerShell 管理 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3062f-155">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="3062f-156">開始使用適用於 Microsoft 365 的 PowerShell</span><span class="sxs-lookup"><span data-stu-id="3062f-156">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)

