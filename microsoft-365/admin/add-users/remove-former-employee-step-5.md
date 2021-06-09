---
title: 步驟 5-清除並封鎖離職員工的行動裝置
f1.keywords:
- NOCSH
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
- SPO_Content
ms.custom:
- MSStore_Link
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: 請遵循下列步驟來封鎖離職員工的行動裝置存取。
ms.openlocfilehash: 1ce12b06b6a0a74615ff8ac43b8f333456a469bb
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/06/2021
ms.locfileid: "52244195"
---
# <a name="step-5---wipe-and-block-a-former-employees-mobile-device"></a><span data-ttu-id="e70cd-103">步驟 5-清除並封鎖離職員工的行動裝置</span><span class="sxs-lookup"><span data-stu-id="e70cd-103">Step 5 - Wipe and block a former employee's mobile device</span></span>

<span data-ttu-id="e70cd-104">如果您的離職員工有組織電話，您可以使用 Exchange 系統管理中心來清除並封鎖該裝置，以便從裝置移除所有組織資料，而且該資料就無法再連接至 Office 365。</span><span class="sxs-lookup"><span data-stu-id="e70cd-104">If your former employee had an organization phone, you can use the Exchange admin center to wipe and block that device so that all organization data is removed from the device and it can no longer connect to Office 365.</span></span> <span data-ttu-id="e70cd-105">如果您的組織使用基本行動性和安全性來管理行動裝置，您可以使用基本行動性和安全性來清除並封鎖這些裝置。</span><span class="sxs-lookup"><span data-stu-id="e70cd-105">If your organization uses Basic Mobility and Security to manage mobile devices, you can wipe and block those devices using Basic Mobility and Security.</span></span>

## <a name="wipe-mobile-device-using-the-exchange-admin-center"></a><span data-ttu-id="e70cd-106">使用 Exchange 系統管理中心來清除移動裝置</span><span class="sxs-lookup"><span data-stu-id="e70cd-106">Wipe mobile device using the Exchange admin center</span></span>

1. <span data-ttu-id="e70cd-107">移至 <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 系統管理中心</a>。</span><span class="sxs-lookup"><span data-stu-id="e70cd-107">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>
2. <span data-ttu-id="e70cd-108">在 Exchange 系統管理中心中，**流覽至 [** 收件者] [ \> **信箱**]。</span><span class="sxs-lookup"><span data-stu-id="e70cd-108">In the Exchange admin center, navigate to **Recipients** \> **Mailboxes**.</span></span>
3. <span data-ttu-id="e70cd-109">選取使用者，然後在 [行動 **裝置**] 底下，選取 [ **查看詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="e70cd-109">Select the user, and under **Mobile Devices**, select **View details**.</span></span>
4. <span data-ttu-id="e70cd-110">在 [行動 **裝置詳細資料**] 頁面的 [行動 **裝置**] 下，選取行動裝置，選取 [**清除資料** ![ 清除裝置] ](../../media/1c113a36-53cb-4974-884f-3ecd9535506e.png) ，然後選取 [**封鎖**]。</span><span class="sxs-lookup"><span data-stu-id="e70cd-110">On the **Mobile Device Details** page, under **Mobile devices**, select the mobile device, select **Wipe Data**![Wipe Device](../../media/1c113a36-53cb-4974-884f-3ecd9535506e.png), and then select **Block**.</span></span>
5. <span data-ttu-id="e70cd-111">選取 \*\*\*\*[儲存]。</span><span class="sxs-lookup"><span data-stu-id="e70cd-111">Select **Save**.</span></span>
   > [!TIP]
   > <span data-ttu-id="e70cd-112">請務必移除或停用內部部署 Blackberry Enterprise 服務中的使用者。</span><span class="sxs-lookup"><span data-stu-id="e70cd-112">Be sure you remove or disable the user from your on-premises Blackberry Enterprise Service.</span></span> <span data-ttu-id="e70cd-113">您也應停用使用者的任何 Blackberry 裝置。</span><span class="sxs-lookup"><span data-stu-id="e70cd-113">You should also disable any Blackberry devices for the user.</span></span> <span data-ttu-id="e70cd-114">如需有關如何停用使用者的特定步驟，請參閱 Blackberry Business Cloud Services Administration Guide。</span><span class="sxs-lookup"><span data-stu-id="e70cd-114">Refer to the Blackberry Business Cloud Services Administration Guide if you need specific steps on how to disable the user.</span></span>
