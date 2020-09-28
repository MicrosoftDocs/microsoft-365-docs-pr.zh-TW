---
title: 在基本行動及安全性中管理裝置存取設定
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
ms.custom:
- AdminSurgePortfolio
search.appverid:
- MET150
description: 基本行動性和安全性可協助您保護和管理行動裝置。
ms.openlocfilehash: e66465d312c4268aca82677fa4e517aaeb822ce3
ms.sourcegitcommit: aeb94601a81db3ead8610c2f36cff30eb9fe10e7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/10/2020
ms.locfileid: "47430104"
---
# <a name="manage-device-access-settings-in-basic-mobility-and-security"></a><span data-ttu-id="ed8a6-103">在基本行動及安全性中管理裝置存取設定</span><span class="sxs-lookup"><span data-stu-id="ed8a6-103">Manage device access settings in Basic Mobility and Security</span></span>

<span data-ttu-id="ed8a6-104">如果您使用基本行動性和安全性，則可能是無法使用基本行動性和安全性來管理的裝置。</span><span class="sxs-lookup"><span data-stu-id="ed8a6-104">If you're using Basic Mobility and Security, there might be devices that you can't manage with Basic Mobility and Security.</span></span> <span data-ttu-id="ed8a6-105">如果是的話，您應該封鎖 Exchange ActiveSync app 存取 Microsoft 365 電子郵件，以供基本行動及安全性所不支援的行動裝置使用。</span><span class="sxs-lookup"><span data-stu-id="ed8a6-105">If so, you should block Exchange ActiveSync app access to Microsoft 365 email for mobile devices that aren't supported by Basic Mobility and Security.</span></span> <span data-ttu-id="ed8a6-106">這可協助您保護組織中的資訊，使其超過多種裝置。</span><span class="sxs-lookup"><span data-stu-id="ed8a6-106">This helps secure your organization information across more devices.</span></span>

<span data-ttu-id="ed8a6-107">請使用下列步驟：</span><span class="sxs-lookup"><span data-stu-id="ed8a6-107">Use these steps:</span></span>

1. <span data-ttu-id="ed8a6-108">使用您的全域系統管理員帳戶登入 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="ed8a6-108">Sign in to  Microsoft 365 with your global admin account.</span></span>
    
2. <span data-ttu-id="ed8a6-109">在您的瀏覽器中輸入：  [https://protection.office.com](https://protection.office.com/) 。</span><span class="sxs-lookup"><span data-stu-id="ed8a6-109">In your browser, type: [https://protection.office.com](https://protection.office.com/).</span></span>    

    >[!IMPORTANT]
    ><span data-ttu-id="ed8a6-110">如果這是您第一次使用 MDM for Microsoft 365 商務標準，請在這裡啟動： [啟動行動裝置管理](https://admin.microsoft.com/EAdmin/Device/IntuneInventory.aspx)。</span><span class="sxs-lookup"><span data-stu-id="ed8a6-110">If this is the first time you're using MDM for Microsoft 365 Business Standard, activate it here: [Activate Mobile Device Management](https://admin.microsoft.com/EAdmin/Device/IntuneInventory.aspx).</span></span> <span data-ttu-id="ed8a6-111">啟動之後，使用 [Office 365 安全性 & 合規性](https://protection.office.com/)來管理裝置。</span><span class="sxs-lookup"><span data-stu-id="ed8a6-111">After you've activated it, manage your devices with [Office 365 Security & Compliance](https://protection.office.com/).</span></span>

3. <span data-ttu-id="ed8a6-112">移至 [資料遺失防護 > **裝置管理**   >  **裝置原則**]，然後選取 [ **管理整個組織的裝置存取設定**]。</span><span class="sxs-lookup"><span data-stu-id="ed8a6-112">Go to Data loss prevention > **Device management** > **Device policies**, and select **Manage organization-wide device access settings**.</span></span>
    
4. <span data-ttu-id="ed8a6-113">選取 [ **封鎖**]。</span><span class="sxs-lookup"><span data-stu-id="ed8a6-113">Select **Block**.</span></span>

    :::image type="content" source="../../media/basic-mobility-security/bms-5-block-access.png" alt-text="基本行動及安全性封鎖存取核取方塊":::

5. <span data-ttu-id="ed8a6-115">選取 [ **儲存**]。</span><span class="sxs-lookup"><span data-stu-id="ed8a6-115">Select **Save**.</span></span> 

<span data-ttu-id="ed8a6-116">若要瞭解基本行動性和安全性可支援哪些裝置，請參閱 [基本行動性和安全性的功能](capabilities.md)。</span><span class="sxs-lookup"><span data-stu-id="ed8a6-116">To learn what devices Basic Mobility and Security supports, see [Capabilities of Basic Mobility and Security](capabilities.md).</span></span>