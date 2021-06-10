---
title: 關閉基本行動與安全性
f1.keywords: NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
description: 移除群組或原則，以關閉基本行動性和安全性。
ms.openlocfilehash: 1d81aed01193fb2ba821ebc055958ac6cd8ac382
ms.sourcegitcommit: 72795ec56a7c4db863dcaaff5e9f7c41c653fda8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/26/2021
ms.locfileid: "52023866"
---
# <a name="turn-off-basic-mobility-and-security"></a><span data-ttu-id="5d0ab-103">關閉基本行動與安全性</span><span class="sxs-lookup"><span data-stu-id="5d0ab-103">Turn off Basic Mobility and Security</span></span>

<span data-ttu-id="5d0ab-104">若要有效關閉基本行動性和安全性，請從裝置管理原則移除安全性群組定義的人員群組，或自行移除原則。</span><span class="sxs-lookup"><span data-stu-id="5d0ab-104">To effectively turn off Basic Mobility and Security, you remove groups of people defined by security groups from the device management policies, or remove the policies themselves.</span></span>

- <span data-ttu-id="5d0ab-105">從您已建立的裝置原則中移除使用者安全性群組，以移除使用者群組。</span><span class="sxs-lookup"><span data-stu-id="5d0ab-105">Remove groups of users by removing user security groups from the device policies you've created.</span></span>

- <span data-ttu-id="5d0ab-106">移除所有基本行動及安全性裝置原則，以停用所有使用者的基本行動性和安全性。</span><span class="sxs-lookup"><span data-stu-id="5d0ab-106">Disable Basic Mobility and Security for everyone by removing all Basic Mobility and Security device policies.</span></span>

<span data-ttu-id="5d0ab-107">這些選項會移除組織中裝置的基本行動性和安全性強制執行。</span><span class="sxs-lookup"><span data-stu-id="5d0ab-107">These options remove Basic Mobility and Security enforcement for devices in your organization.</span></span> <span data-ttu-id="5d0ab-108">不幸的是，在您設定後，您無法直接 "取消「取消」「基本行動性」和「安全性」。</span><span class="sxs-lookup"><span data-stu-id="5d0ab-108">Unfortunately, you can't simply "unprovision" Basic Mobility and Security after you've set it up.</span></span> 

>[!IMPORTANT]
><span data-ttu-id="5d0ab-109">當您移除原則中的使用者安全性群組或自行移除原則時，請注意使用者裝置的影響。</span><span class="sxs-lookup"><span data-stu-id="5d0ab-109">Be aware of the impact on users' devices when you remove user security groups from policies or remove the policies themselves.</span></span> <span data-ttu-id="5d0ab-110">例如，電子郵件設定檔及快取的電子郵件可能會被移除，視裝置而定。</span><span class="sxs-lookup"><span data-stu-id="5d0ab-110">For example, email profiles and cached emails might be removed, depending on the device.</span></span> <span data-ttu-id="5d0ab-111">如需詳細資訊，請參閱  [當您刪除原則或移除原則中的使用者時，會發生什麼事？](../../admin/basic-mobility-security/create-device-security-policies.md)</span><span class="sxs-lookup"><span data-stu-id="5d0ab-111">For more info, see  [What happens when you delete a policy or remove a user from the policy?](../../admin/basic-mobility-security/create-device-security-policies.md)</span></span>

## <a name="remove-user-security-groups-from-basic-mobility-and-security-device-policies"></a><span data-ttu-id="5d0ab-112">從基本行動及安全性裝置原則中移除使用者安全性群組</span><span class="sxs-lookup"><span data-stu-id="5d0ab-112">Remove user security groups from Basic Mobility and Security device policies</span></span>

1. <span data-ttu-id="5d0ab-113">在您的瀏覽器類型：中  [https://protection.office.com/devicev2](https://protection.office.com/devicev2) 。</span><span class="sxs-lookup"><span data-stu-id="5d0ab-113">In your browser type: [https://protection.office.com/devicev2](https://protection.office.com/devicev2).</span></span>

2. <span data-ttu-id="5d0ab-114">選取裝置原則，然後選取 [ **編輯原則**]。</span><span class="sxs-lookup"><span data-stu-id="5d0ab-114">Select a device policy, and select **Edit policy**.</span></span> 

3. <span data-ttu-id="5d0ab-115">在 [  **部署**]   頁面上，選取 [ **移除**]。</span><span class="sxs-lookup"><span data-stu-id="5d0ab-115">On the  **Deployment**  page, select **Remove**.</span></span>

4. <span data-ttu-id="5d0ab-116">在 [  **群組**] 下，選取安全性群組。</span><span class="sxs-lookup"><span data-stu-id="5d0ab-116">Under  **Groups**, select a security group.</span></span>

5. <span data-ttu-id="5d0ab-117">選取 [  **移除**]，然後選取 [ **儲存**]。</span><span class="sxs-lookup"><span data-stu-id="5d0ab-117">Select  **Remove**, and select **Save**.</span></span>

## <a name="remove-basic-mobility-and-security-device-policies"></a><span data-ttu-id="5d0ab-118">移除基本行動及安全性裝置原則</span><span class="sxs-lookup"><span data-stu-id="5d0ab-118">Remove Basic Mobility and Security device policies</span></span>

1.  <span data-ttu-id="5d0ab-119">在您的瀏覽器類型：中  [https://protection.office.com/devicev2](https://protection.office.com/devicev2) 。</span><span class="sxs-lookup"><span data-stu-id="5d0ab-119">In your browser type: [https://protection.office.com/devicev2](https://protection.office.com/devicev2).</span></span> 

2.  <span data-ttu-id="5d0ab-120">選取裝置原則，然後選取 [  **刪除原則**]。</span><span class="sxs-lookup"><span data-stu-id="5d0ab-120">Select a device policy, and then select  **Delete policy**.</span></span>
    
3.  <span data-ttu-id="5d0ab-121">在警告對話方塊中，選取 **[是]**。</span><span class="sxs-lookup"><span data-stu-id="5d0ab-121">In the Warning dialog box, select **Yes**.</span></span>

>[!NOTE]
><span data-ttu-id="5d0ab-122">如需更多步驟以解除封鎖裝置如果組織裝置仍處於封鎖狀態，請參閱博客文章[移除適用於 Office 365 的行動裝置管理中的存取控制](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Removing-Access-Control-from-Mobile-Device-Management-for-Office/ba-p/279934)。</span><span class="sxs-lookup"><span data-stu-id="5d0ab-122">For more steps to unblock devices if your organization devices are still in a blocked state,  see the blog post [Removing Access Control from Mobile Device Management for Office 365](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Removing-Access-Control-from-Mobile-Device-Management-for-Office/ba-p/279934).</span></span>
