---
title: 調整條件式存取
description: 如何排除某些 Microsoft 帳戶
keywords: Microsoft 受管理的電腦, Microsoft 365, 服務, 文件
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 8844c50f5faba609b3f5f53adc5ab45ba1dbaa74
ms.sourcegitcommit: 126d22d8abd190beb7101f14bd357005e4c729f0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/30/2020
ms.locfileid: "46529680"
---
# <a name="adjust-conditional-access"></a><span data-ttu-id="e9e74-104">調整條件式存取</span><span class="sxs-lookup"><span data-stu-id="e9e74-104">Adjust conditional access</span></span>

<span data-ttu-id="e9e74-105">如果您在組織中使用[條件式存取](https://docs.microsoft.com/azure/active-directory/conditional-access/overview)原則，則必須將其設定為排除某些帳戶，Microsoft 受管理的桌上型電腦才能正常運作。</span><span class="sxs-lookup"><span data-stu-id="e9e74-105">If you use [conditional access](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) policies in your organization, you'll have to set them to exclude certain accounts so that Microsoft Managed Desktop can work properly.</span></span>

<span data-ttu-id="e9e74-106">如果要執行這項操作，請依照下列步驟執行：</span><span class="sxs-lookup"><span data-stu-id="e9e74-106">To do this, follow these steps:</span></span>

1. <span data-ttu-id="e9e74-107">請參閱 how [to：在 Azure Active Directory 中規劃條件式存取部署](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access#rollback-steps)的「回滾步驟」一節。</span><span class="sxs-lookup"><span data-stu-id="e9e74-107">Refer to the "Rollback steps" section of [How To: Plan your Conditional Access deployment in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access#rollback-steps).</span></span>
2. <span data-ttu-id="e9e74-108">請遵循這裡所述的步驟，排除所有原則的*現代 Workplace Service 帳戶*群組。</span><span class="sxs-lookup"><span data-stu-id="e9e74-108">Follow the steps there to exclude the *Modern Workplace Service Accounts* group for all policies.</span></span>


<span data-ttu-id="e9e74-109">如果您有設定條件式存取的任何困難，請與系統管理員[支援](../working-with-managed-desktop/admin-support.md)人員聯繫。</span><span class="sxs-lookup"><span data-stu-id="e9e74-109">If you have any difficulty with conditional access, contact admin [support](../working-with-managed-desktop/admin-support.md).</span></span>

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a><span data-ttu-id="e9e74-110">開始使用 Microsoft 受管理電腦的步驟</span><span class="sxs-lookup"><span data-stu-id="e9e74-110">Steps to get started with Microsoft Managed Desktop</span></span>

1. [<span data-ttu-id="e9e74-111">在系統管理入口網站中新增和驗證系統管理員連絡人</span><span class="sxs-lookup"><span data-stu-id="e9e74-111">Add and verify admin contacts in the Admin portal</span></span>](add-admin-contacts.md)
2. <span data-ttu-id="e9e74-112">調整條件式存取（本主題）</span><span class="sxs-lookup"><span data-stu-id="e9e74-112">Adjust conditional access (this topic)</span></span>
3. [<span data-ttu-id="e9e74-113">指派授權</span><span class="sxs-lookup"><span data-stu-id="e9e74-113">Assign licenses</span></span>](assign-licenses.md)
4. [<span data-ttu-id="e9e74-114">部署 Intune 公司入口網站</span><span class="sxs-lookup"><span data-stu-id="e9e74-114">Deploy Intune Company Portal</span></span>](company-portal.md)
5. [<span data-ttu-id="e9e74-115">啟用企業狀態漫遊</span><span class="sxs-lookup"><span data-stu-id="e9e74-115">Enable Enterprise State Roaming</span></span>](enterprise-state-roaming.md)
6. [<span data-ttu-id="e9e74-116">設定裝置</span><span class="sxs-lookup"><span data-stu-id="e9e74-116">Set up devices</span></span>](set-up-devices.md)
7. [<span data-ttu-id="e9e74-117">讓您的使用者準備好使用裝置</span><span class="sxs-lookup"><span data-stu-id="e9e74-117">Get your users ready to use devices</span></span>](get-started-devices.md)
8. [<span data-ttu-id="e9e74-118">部署應用程式</span><span class="sxs-lookup"><span data-stu-id="e9e74-118">Deploy apps</span></span>](deploy-apps.md)
