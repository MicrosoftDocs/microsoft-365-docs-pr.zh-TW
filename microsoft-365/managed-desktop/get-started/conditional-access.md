---
title: 調整條件式存取
description: 如何排除特定的 Microsoft 帳戶
keywords: Microsoft 受管理的電腦，Microsoft 365 服務，文件
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 1b91186837ad558965d675f82d013a7081c7c7ec
ms.sourcegitcommit: 3d37043c0447359c952dc99026c219dd69f6fb8d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/06/2019
ms.locfileid: "38012453"
---
# <a name="adjust-conditional-access"></a><span data-ttu-id="da58e-104">調整條件式存取</span><span class="sxs-lookup"><span data-stu-id="da58e-104">Adjust conditional access</span></span>

<span data-ttu-id="da58e-105">如果您在組織中使用[條件式存取](https://docs.microsoft.com/azure/active-directory/conditional-access/overview)原則，您必須將它們設定成排除特定帳戶，以便 Microsoft 受管理的電腦可以正常運作。</span><span class="sxs-lookup"><span data-stu-id="da58e-105">If you use [conditional access](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) policies in your organization, you'll have to set them to exclude certain accounts so that Microsoft Managed Desktop can work properly.</span></span>

<span data-ttu-id="da58e-106">若要這樣做，請執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="da58e-106">To do this, follow these steps:</span></span>

1. <span data-ttu-id="da58e-107">請參閱 「 回復步驟 」 一節[How To： 規劃在 Azure Active Directory 條件式存取部署](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access#rollback-steps)。</span><span class="sxs-lookup"><span data-stu-id="da58e-107">Refer to the "Rollback steps" section of [How To: Plan your Conditional Access deployment in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access#rollback-steps).</span></span>
2. <span data-ttu-id="da58e-108">請依照那里排除所有原則的*現代化工作場所服務帳戶*群組。</span><span class="sxs-lookup"><span data-stu-id="da58e-108">Follow the steps there to exclude the *Modern Workplace Service Accounts* group for all policies.</span></span>


<span data-ttu-id="da58e-109">如果您有使用條件式存取的任何問題，請連絡系統管理員[支援](../working-with-managed-desktop/admin-support.md)。</span><span class="sxs-lookup"><span data-stu-id="da58e-109">If you have any difficulty with conditional access, contact admin [support](../working-with-managed-desktop/admin-support.md).</span></span>

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a><span data-ttu-id="da58e-110">若要開始使用 Microsoft 受管理電腦的步驟</span><span class="sxs-lookup"><span data-stu-id="da58e-110">Steps to get started with Microsoft Managed Desktop</span></span>

1. [<span data-ttu-id="da58e-111">新增及確認系統管理入口網站中的連絡人</span><span class="sxs-lookup"><span data-stu-id="da58e-111">Add and verify admin contacts in the Admin portal</span></span>](add-admin-contacts.md)
2. <span data-ttu-id="da58e-112">調整條件式存取 （本主題）</span><span class="sxs-lookup"><span data-stu-id="da58e-112">Adjust conditional access (this topic)</span></span>
3. [<span data-ttu-id="da58e-113">指派授權</span><span class="sxs-lookup"><span data-stu-id="da58e-113">Assign licenses</span></span>](assign-licenses.md)
4. [<span data-ttu-id="da58e-114">部署 Intune 公司入口網站</span><span class="sxs-lookup"><span data-stu-id="da58e-114">Deploy Intune Company Portal</span></span>](company-portal.md)
5. [<span data-ttu-id="da58e-115">啟用企業狀態漫遊</span><span class="sxs-lookup"><span data-stu-id="da58e-115">Enable Enterprise State Roaming</span></span>](enterprise-state-roaming.md)
6. [<span data-ttu-id="da58e-116">設定裝置</span><span class="sxs-lookup"><span data-stu-id="da58e-116">Set up devices</span></span>](set-up-devices.md)
7. [<span data-ttu-id="da58e-117">讓您的使用者準備好使用裝置</span><span class="sxs-lookup"><span data-stu-id="da58e-117">Get your users ready to use devices</span></span>](get-started-devices.md)
8. [<span data-ttu-id="da58e-118">部署應用程式</span><span class="sxs-lookup"><span data-stu-id="da58e-118">Deploy apps</span></span>](deploy-apps.md)