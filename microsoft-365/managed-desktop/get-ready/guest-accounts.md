---
title: 來賓帳戶的先決條件
description: 來賓帳戶的設定指導方針及其調整方式
keywords: Microsoft 受管理的電腦, Microsoft 365, 服務, 文件
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: d29b9d6bdc30d981b273d95925ba740bc92304c4
ms.sourcegitcommit: 5377b00703b6f559092afe44fb61462e97968a60
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/27/2021
ms.locfileid: "52694242"
---
# <a name="prerequisites-for-guest-accounts"></a><span data-ttu-id="45218-104">來賓帳戶的先決條件</span><span class="sxs-lookup"><span data-stu-id="45218-104">Prerequisites for guest accounts</span></span>

<span data-ttu-id="45218-105">Microsoft 受管理的電腦需要在您的 Azure AD 組織中具備下列設定，以供來賓帳戶存取使用。</span><span class="sxs-lookup"><span data-stu-id="45218-105">Microsoft Managed Desktop requires the following settings in your Azure AD organization for guest account access.</span></span> <span data-ttu-id="45218-106">您可以在 [外部身分識別 **/外部協同作業設定**] 底下的 [Azure 入口網站](https://portal.azure.com)調整這些設定：</span><span class="sxs-lookup"><span data-stu-id="45218-106">You can adjust these settings at the [Azure portal](https://portal.azure.com) under **External Identities / External collaboration settings**:</span></span>

-   <span data-ttu-id="45218-107">若要將 **來賓邀請限制** 設定為 **成員使用者，並將指派給特定系統管理員角色的使用者，可邀請來賓使用者（包括具有成員許可權的來賓**）</span><span class="sxs-lookup"><span data-stu-id="45218-107">For **Guest invite restrictions** set to **Member users and users assigned to specific admin roles can invite guest users including guests with member permissions**</span></span>
-   <span data-ttu-id="45218-108">針對共同作業 **限制**，選擇下列其中一個選項：</span><span class="sxs-lookup"><span data-stu-id="45218-108">For **Collaboration restrictions**, choose any of these options:</span></span>
    -   <span data-ttu-id="45218-109">如果您選取 [ **允許將邀請傳送至任何網域 (最包含)**]，則不需要其他設定。</span><span class="sxs-lookup"><span data-stu-id="45218-109">If you select **Allow invitations to be sent to any domain (most inclusive)**, no other configuration required.</span></span>
    -   <span data-ttu-id="45218-110">如果您選取 **[拒絕指定的網域邀請**]，請確定 Microsoft.com 未列在目標網域中。</span><span class="sxs-lookup"><span data-stu-id="45218-110">If you select **Deny invitations to the specified domains**, make sure that Microsoft.com isn’t listed in the target domains.</span></span>
    -   <span data-ttu-id="45218-111">如果您選取 **[只對指定的網域允許邀請] (最嚴格的)**，請 *確定 Microsoft.com 列* 在目標網域中。</span><span class="sxs-lookup"><span data-stu-id="45218-111">If you select **Allow invitations only to the specified domains (most restrictive)**, make sure that Microsoft.com *is* listed in the target domains.</span></span>

<span data-ttu-id="45218-112">如果您設定的限制與這些設定互動，請務必排除 Azure Active Directory 新式的 **Workplace Service 帳戶**。</span><span class="sxs-lookup"><span data-stu-id="45218-112">If you set restrictions that interact with these settings, make sure to exclude the Azure Active Directory **Modern Workplace Service Accounts**.</span></span> <span data-ttu-id="45218-113">例如，如果您有一個條件式存取原則，可防止來賓帳戶存取 Intune 入口網站，請從這個原則中排除 **新式的 Workplace Service 帳戶** 群組。</span><span class="sxs-lookup"><span data-stu-id="45218-113">For example, if you have a conditional access policy that prevents guest accounts from accessing the Intune portal, exclude the **Modern Workplace Service Accounts** group from this policy.</span></span>

## <a name="steps-to-get-ready"></a><span data-ttu-id="45218-114">準備就緒的步驟</span><span class="sxs-lookup"><span data-stu-id="45218-114">Steps to get ready</span></span>

1. <span data-ttu-id="45218-115">檢閱 [Microsoft 受管理的電腦的先決條件](prerequisites.md)。</span><span class="sxs-lookup"><span data-stu-id="45218-115">Review [prerequisites for Microsoft Managed Desktop](prerequisites.md).</span></span>
2. <span data-ttu-id="45218-116">使用[整備評估工具](readiness-assessment-tool.md)。</span><span class="sxs-lookup"><span data-stu-id="45218-116">Use [readiness assessment tools](readiness-assessment-tool.md).</span></span>
3. <span data-ttu-id="45218-117"> (本文[的來賓帳戶先決條件](guest-accounts.md)) </span><span class="sxs-lookup"><span data-stu-id="45218-117">[Prerequisites for guest accounts](guest-accounts.md) (This article)</span></span>
4. [<span data-ttu-id="45218-118">Microsoft 受管理的電腦的網路設定</span><span class="sxs-lookup"><span data-stu-id="45218-118">Network configuration for Microsoft Managed Desktop</span></span>](network.md)
5. [<span data-ttu-id="45218-119">為 Microsoft 受管理的電腦準備認證和網路設定檔</span><span class="sxs-lookup"><span data-stu-id="45218-119">Prepare certificates and network profiles for Microsoft Managed Desktop</span></span>](certs-wifi-lan.md)
6. [<span data-ttu-id="45218-120">為 Microsoft 受管理的電腦準備內部部署資源存取</span><span class="sxs-lookup"><span data-stu-id="45218-120">Prepare on-premises resources access for Microsoft Managed Desktop</span></span>](authentication.md)
7. [<span data-ttu-id="45218-121">Microsoft 受管理的電腦中的應用程式</span><span class="sxs-lookup"><span data-stu-id="45218-121">Apps in Microsoft Managed Desktop</span></span>](apps.md)
8. [<span data-ttu-id="45218-122">為 Microsoft 受管理的電腦準備對應磁碟機</span><span class="sxs-lookup"><span data-stu-id="45218-122">Prepare mapped drives for Microsoft Managed Desktop</span></span>](mapped-drives.md)
9. [<span data-ttu-id="45218-123">為 Microsoft 受管理的電腦準備列印資源</span><span class="sxs-lookup"><span data-stu-id="45218-123">Prepare printing resources for Microsoft Managed Desktop</span></span>](printing.md)
