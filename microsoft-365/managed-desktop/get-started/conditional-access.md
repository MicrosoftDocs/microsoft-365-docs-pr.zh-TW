---
title: 調整條件式存取
description: 如何排除特定的 Microsoft 帳戶
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentation, Microsoft 受管理的電腦, Microsoft 365, 服務, 文件
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 1bc5d937616cba60c5af43fe22a7c4dccf89a55e
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42085803"
---
# <a name="adjust-conditional-access"></a><span data-ttu-id="5bb85-104">調整條件式存取</span><span class="sxs-lookup"><span data-stu-id="5bb85-104">Adjust conditional access</span></span>

<span data-ttu-id="5bb85-105">如果您在組織中使用[條件式存取](https://docs.microsoft.com/azure/active-directory/conditional-access/overview)原則，您必須將它們設定成排除特定帳戶，以便 Microsoft 受管理的電腦可以正常運作。</span><span class="sxs-lookup"><span data-stu-id="5bb85-105">If you use [conditional access](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) policies in your organization, you'll have to set them to exclude certain accounts so that Microsoft Managed Desktop can work properly.</span></span>

<span data-ttu-id="5bb85-106">若要這樣做，請執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="5bb85-106">To do this, follow these steps:</span></span>

1. <span data-ttu-id="5bb85-107">請參閱 「 回復步驟 」 一節[How To： 規劃在 Azure Active Directory 條件式存取部署](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access#rollback-steps)。</span><span class="sxs-lookup"><span data-stu-id="5bb85-107">Refer to the "Rollback steps" section of [How To: Plan your Conditional Access deployment in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access#rollback-steps).</span></span>
2. <span data-ttu-id="5bb85-108">請依照那里排除所有原則的*現代化工作場所服務帳戶*群組。</span><span class="sxs-lookup"><span data-stu-id="5bb85-108">Follow the steps there to exclude the *Modern Workplace Service Accounts* group for all policies.</span></span>


<span data-ttu-id="5bb85-109">如果您有使用條件式存取的任何問題，請連絡系統管理員[支援](../working-with-managed-desktop/admin-support.md)。</span><span class="sxs-lookup"><span data-stu-id="5bb85-109">If you have any difficulty with conditional access, contact admin [support](../working-with-managed-desktop/admin-support.md).</span></span>

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a><span data-ttu-id="5bb85-110">開始使用 Microsoft 受管理電腦的步驟</span><span class="sxs-lookup"><span data-stu-id="5bb85-110">Steps to get started with Microsoft Managed Desktop</span></span>

1. [<span data-ttu-id="5bb85-111">在系統管理入口網站中新增和驗證系統管理員連絡人</span><span class="sxs-lookup"><span data-stu-id="5bb85-111">Add and verify admin contacts in the Admin portal</span></span>](add-admin-contacts.md)
2. <span data-ttu-id="5bb85-112">調整條件式存取 （本主題）</span><span class="sxs-lookup"><span data-stu-id="5bb85-112">Adjust conditional access (this topic)</span></span>
3. [<span data-ttu-id="5bb85-113">指派授權</span><span class="sxs-lookup"><span data-stu-id="5bb85-113">Assign licenses</span></span>](assign-licenses.md)
4. [<span data-ttu-id="5bb85-114">部署 Intune 公司入口網站</span><span class="sxs-lookup"><span data-stu-id="5bb85-114">Deploy Intune Company Portal</span></span>](company-portal.md)
5. [<span data-ttu-id="5bb85-115">啟用企業狀態漫遊</span><span class="sxs-lookup"><span data-stu-id="5bb85-115">Enable Enterprise State Roaming</span></span>](enterprise-state-roaming.md)
6. [<span data-ttu-id="5bb85-116">設定裝置</span><span class="sxs-lookup"><span data-stu-id="5bb85-116">Set up devices</span></span>](set-up-devices.md)
7. [<span data-ttu-id="5bb85-117">讓您的使用者準備好使用裝置</span><span class="sxs-lookup"><span data-stu-id="5bb85-117">Get your users ready to use devices</span></span>](get-started-devices.md)
8. [<span data-ttu-id="5bb85-118">部署應用程式</span><span class="sxs-lookup"><span data-stu-id="5bb85-118">Deploy apps</span></span>](deploy-apps.md)
