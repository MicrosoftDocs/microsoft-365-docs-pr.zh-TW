---
title: 開啟或關閉 Office 365 稽核記錄搜尋
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: e893b19a-660c-41f2-9074-d3631c95a014
description: 您可以在安全&合规性中心中打开审核日志搜索功能。 如果你改变主意，你可以随时关闭。 关闭审核日志搜索后，管理员无法搜索 Office 365 审核日志以查找组织中的用户和管理员活动。
ms.openlocfilehash: c5e1106617aa4828ec2db5afcc44ac55e91f2383
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37078146"
---
# <a name="turn-office-365-audit-log-search-on-or-off"></a><span data-ttu-id="1b63b-105">開啟或關閉 Office 365 稽核記錄搜尋</span><span class="sxs-lookup"><span data-stu-id="1b63b-105">Turn Office 365 audit log search on or off</span></span>

<span data-ttu-id="1b63b-106">您（或其他管理员）必须先打开审核日志记录，然后才能开始搜索 Office 365 审核日志。</span><span class="sxs-lookup"><span data-stu-id="1b63b-106">You (or another admin) must turn on audit logging before you can start searching the Office 365 audit log.</span></span> <span data-ttu-id="1b63b-107">启用安全&合规性中心的审核日志搜索后，组织的用户和管理活动将记录在审核日志中，并保留 90 天。</span><span class="sxs-lookup"><span data-stu-id="1b63b-107">When audit log search in the Security & Compliance Center is turned on, user and admin activity from your organization is recorded in the audit log and retained for 90 days.</span></span> <span data-ttu-id="1b63b-108">但是，您的组织可能不希望记录和保留审核日志数据。</span><span class="sxs-lookup"><span data-stu-id="1b63b-108">However, your organization might not want to record and retain audit log data.</span></span> <span data-ttu-id="1b63b-109">或者，您可能正在使用第三方安全信息和事件管理 （SIEM） 应用程序来访问您的审核数据。</span><span class="sxs-lookup"><span data-stu-id="1b63b-109">Or you might be using a third-party security information and event management (SIEM) application to access your auditing data.</span></span> <span data-ttu-id="1b63b-110">在这些情况下，全局管理员可以在 Office 365 中关闭审核日志搜索。</span><span class="sxs-lookup"><span data-stu-id="1b63b-110">In those cases, a global admin can turn off audit log search in Office 365.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="1b63b-111">開始之前</span><span class="sxs-lookup"><span data-stu-id="1b63b-111">Before you begin</span></span>

- <span data-ttu-id="1b63b-112">您必须在 Exchange Online 中分配审核日志角色，才能在 Office 365 组织中打开或关闭审核日志搜索。</span><span class="sxs-lookup"><span data-stu-id="1b63b-112">You have to be assigned the Audit Logs role in Exchange Online to turn audit log search on or off in your Office 365 organization.</span></span> <span data-ttu-id="1b63b-113">默认情况下，此角色分配给 Exchange 管理中心"**权限"** 页上的"合规性管理和组织管理"角色组。</span><span class="sxs-lookup"><span data-stu-id="1b63b-113">By default, this role is assigned to the Compliance Management and Organization Management role groups on the **Permissions** page in the Exchange admin center.</span></span> <span data-ttu-id="1b63b-114">Office 365 中的全局管理员是 Exchange 联机中的组织管理角色组的成员。</span><span class="sxs-lookup"><span data-stu-id="1b63b-114">Global admins in Office 365 are members of the Organization Management role group in Exchange Online.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="1b63b-115">必须在 Exchange Online 中为用户分配权限才能打开或关闭审核日志搜索。</span><span class="sxs-lookup"><span data-stu-id="1b63b-115">Users have to be assigned permissions in Exchange Online to turn audit log search on or off.</span></span> <span data-ttu-id="1b63b-116">如果向用户分配了"安全&合规性中心""**权限"** 页上的"审核日志"角色，则用户将无法打开或关闭审核日志搜索。</span><span class="sxs-lookup"><span data-stu-id="1b63b-116">If you assign users the Audit Logs role on the **Permissions** page in the Security & Compliance Center, they won't be able to turn audit log search on or off.</span></span> <span data-ttu-id="1b63b-117">这是因为基础 cmdlet 是交换联机 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="1b63b-117">This is because the underlying cmdlet is an Exchange Online cmdlet.</span></span> 
  
- <span data-ttu-id="1b63b-118">如果在 Office 365 中关闭审核日志搜索，您将无法使用 Office 365 管理活动 API 访问组织的审核数据。</span><span class="sxs-lookup"><span data-stu-id="1b63b-118">If you turn off audit log search in Office 365, you won't be able to use the Office 365 Management Activity API to access auditing data for your organization.</span></span> <span data-ttu-id="1b63b-119">按照本文中的步骤关闭审核日志搜索意味着当您使用安全&合规性中心搜索审核日志时，或者当您在 Exchange 在线 PowerShell 中运行**搜索统一审核日志**cmdlet 时，将不会返回任何结果.</span><span class="sxs-lookup"><span data-stu-id="1b63b-119">Turning off audit log search by following the steps in this article means that no results will be returned when you search the audit log using the Security & Compliance Center or when you run the **Search-UnifiedAuditLog** cmdlet in Exchange Online PowerShell.</span></span> <span data-ttu-id="1b63b-120">这也意味着您的审核日志无法通过 Office 365 管理活动 API 提供。</span><span class="sxs-lookup"><span data-stu-id="1b63b-120">This also means that your audit logs won't be available through the Office 365 Management Activity API.</span></span>  
    
- <span data-ttu-id="1b63b-121">有关搜索 Office 365 审核日志的分步说明，请参阅[在安全&合规性中心中搜索审核日志。](search-the-audit-log-in-security-and-compliance.md)</span><span class="sxs-lookup"><span data-stu-id="1b63b-121">For step-by-step instructions on searching the Office 365 audit log, see [Search the audit log in the Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span></span>
    
## <a name="turn-on-audit-log-search"></a><span data-ttu-id="1b63b-122">打开审核日志搜索</span><span class="sxs-lookup"><span data-stu-id="1b63b-122">Turn on audit log search</span></span>

<span data-ttu-id="1b63b-123">您可以使用安全&合规性中心或 PowerShell 在 Office 365 中打开审核日志搜索。</span><span class="sxs-lookup"><span data-stu-id="1b63b-123">You can use the Security & Compliance Center or PowerShell to turn on audit log search in Office 365.</span></span> <span data-ttu-id="1b63b-124">在打开审核日志搜索后，可能需要几个小时才能在搜索审核日志时返回结果。</span><span class="sxs-lookup"><span data-stu-id="1b63b-124">It might take several hours after you turn on audit log search before you can return results when you search the audit log.</span></span> <span data-ttu-id="1b63b-125">您必须在 Exchange 联机中分配审核日志角色才能打开审核日志搜索。</span><span class="sxs-lookup"><span data-stu-id="1b63b-125">You have to be assigned the Audit Logs role in Exchange Online to turn on audit log search.</span></span>
  
### <a name="use-the-security--compliance-center-to-turn-on-audit-log-search"></a><span data-ttu-id="1b63b-126">使用安全&合规性中心打开审核日志搜索</span><span class="sxs-lookup"><span data-stu-id="1b63b-126">Use the Security & Compliance Center to turn on audit log search</span></span>

1. <span data-ttu-id="1b63b-127">在安全&合规性中心，转到**搜索**\>**审核日志搜索**。</span><span class="sxs-lookup"><span data-stu-id="1b63b-127">In the Security & Compliance Center, go to **Search** \> **Audit log search**.</span></span>
    
2. <span data-ttu-id="1b63b-128">**单击"开始录制用户和管理活动"。**</span><span class="sxs-lookup"><span data-stu-id="1b63b-128">Click **Start recording user and admin activities**.</span></span>
    
    ![单击"开始记录用户和管理活动"以打开审核](media/39a9d35f-88d0-4bbe-a962-0be2f838e2bf.png)
  
    <span data-ttu-id="1b63b-130">将显示一个对话框，指出组织中的用户和管理员活动将记录到 Office 365 审核日志中，并可在报表中查看。</span><span class="sxs-lookup"><span data-stu-id="1b63b-130">A dialog box is displayed saying that user and admin activity in your organization will be recorded to the Office 365 audit log and available to view in a report.</span></span> 
    
3. <span data-ttu-id="1b63b-131">按一下 [開啟]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1b63b-131">Click **Turn on**.</span></span>
    
    <span data-ttu-id="1b63b-132">将显示一条消息，指出审核日志正在准备中，您可以在准备完成后的几个小时内运行搜索。</span><span class="sxs-lookup"><span data-stu-id="1b63b-132">A message is displayed that says the audit log is being prepared and that you can run a search in a couple of hours after the preparation is complete.</span></span>
    
### <a name="use-powershell-to-turn-on-audit-log-search"></a><span data-ttu-id="1b63b-133">使用 PowerShell 打开审核日志搜索</span><span class="sxs-lookup"><span data-stu-id="1b63b-133">Use PowerShell to turn on audit log search</span></span>

1. [<span data-ttu-id="1b63b-134">連線到 Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="1b63b-134">Connect to Exchange Online PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=396554)
    
2. <span data-ttu-id="1b63b-135">运行以下 PowerShell 命令以在 Office 365 中打开审核日志搜索。</span><span class="sxs-lookup"><span data-stu-id="1b63b-135">Run the following PowerShell command to turn on audit log search in Office 365.</span></span>
    
    ```
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $true
    ```

    <span data-ttu-id="1b63b-136">将显示一条消息，指出更改最多可能需要 60 分钟才能生效。</span><span class="sxs-lookup"><span data-stu-id="1b63b-136">A message is displayed saying that it might take up to 60 minutes for the change to take effect.</span></span>
  
## <a name="turn-off-audit-log-search"></a><span data-ttu-id="1b63b-137">关闭审核日志搜索</span><span class="sxs-lookup"><span data-stu-id="1b63b-137">Turn off audit log search</span></span>

<span data-ttu-id="1b63b-138">您必须使用连接到 Exchange 在线组织的远程 PowerShell 来关闭审核日志搜索。</span><span class="sxs-lookup"><span data-stu-id="1b63b-138">You have to use remote PowerShell connected to your Exchange Online organization to turn off audit log search.</span></span> <span data-ttu-id="1b63b-139">与打开审核日志搜索类似，您必须在 Exchange Online 中分配审核日志角色才能关闭审核日志搜索。</span><span class="sxs-lookup"><span data-stu-id="1b63b-139">Similar to turning on audit log search, you have to be assigned the Audit Logs role in Exchange Online to turn off audit log search.</span></span>
  
1. [<span data-ttu-id="1b63b-140">連線到 Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="1b63b-140">Connect to Exchange Online PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=396554)
    
2. <span data-ttu-id="1b63b-141">运行以下 PowerShell 命令以在 Office 365 中关闭审核日志搜索。</span><span class="sxs-lookup"><span data-stu-id="1b63b-141">Run the following PowerShell command to turn off audit log search in Office 365.</span></span>
    
    ```
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $false
    ```

3. <span data-ttu-id="1b63b-142">一段时间后，验证审核日志搜索是否关闭（禁用）。</span><span class="sxs-lookup"><span data-stu-id="1b63b-142">After a while, verify that audit log search is turned off (disabled).</span></span> <span data-ttu-id="1b63b-143">方法有兩種：</span><span class="sxs-lookup"><span data-stu-id="1b63b-143">There are two ways to do this:</span></span>
    
    - <span data-ttu-id="1b63b-144">在 PowerShell 中，运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="1b63b-144">In PowerShell, run the following command:</span></span>

        ```
        Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
        ```

        <span data-ttu-id="1b63b-145">"`False`_统一审核登录启用"_ 属性的值指示已关闭审核日志搜索。</span><span class="sxs-lookup"><span data-stu-id="1b63b-145">The value of  `False` for the  _UnifiedAuditLogIngestionEnabled_ property indicates that audit log search is turned off.</span></span> 
    
    - <span data-ttu-id="1b63b-146">在安全&合规性中心，**转到"搜索**\>**审核日志搜索"，** 然后单击"**搜索"。**</span><span class="sxs-lookup"><span data-stu-id="1b63b-146">In the Security & Compliance Center, go to **Search** \> **Audit log search**, and then click **Search**.</span></span>
    
      <span data-ttu-id="1b63b-147">将显示一条消息，指出审核日志搜索未打开。</span><span class="sxs-lookup"><span data-stu-id="1b63b-147">A message is displayed saying that audit log search isn't turned on.</span></span> 
    
      ![如果关闭审核，将显示一条消息](media/dca53da6-1cbe-4fa3-9860-f0d674de9538.png)
