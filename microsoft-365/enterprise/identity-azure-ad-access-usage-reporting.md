---
title: 步驟 13：監控租用戶和登入活動
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/01/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: 了解並設定 Azure AD 存取和使用情況報告。
ms.openlocfilehash: 997d52bc11036e1dbb7dcc6e1f9f48a59b2ddbf5
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/28/2018
ms.locfileid: "26866105"
---
# <a name="step-13-monitor-tenant-and-sign-in-activity"></a><span data-ttu-id="f76c0-103">步驟 13：監控租用戶和登入活動</span><span class="sxs-lookup"><span data-stu-id="f76c0-103">Step 13: Monitor tenant and sign-in activity</span></span>

<span data-ttu-id="f76c0-104">*此為選用步驟，且同時適用於 Microsoft 365 企業版 E3 和 E5 版本*</span><span class="sxs-lookup"><span data-stu-id="f76c0-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="f76c0-p101">在此步驟中，您將會使用 Azure AD 報告檢視稽核記錄和登入活動。兩種類型的報告皆可供使用。</span><span class="sxs-lookup"><span data-stu-id="f76c0-p101">In Step 13, you'll review audit logs and sign-in activity using Azure AD reporting. Two types of reports are available.</span></span>

<span data-ttu-id="f76c0-p102">**稽核記錄活動報告**會報告 Azure AD 租用戶中執行的每項工作歷程記錄。這份報告會回答如以下的問題：</span><span class="sxs-lookup"><span data-stu-id="f76c0-p102">The **Audit logs activity report** records the history of every task performed in your Azure AD tenant. This report answers questions like:</span></span>

- <span data-ttu-id="f76c0-109">哪個人員已將某人新增至系統管理群組？</span><span class="sxs-lookup"><span data-stu-id="f76c0-109">Who added someone to an admin group?</span></span>
- <span data-ttu-id="f76c0-110">哪個使用者正在登入特定的應用程式？</span><span class="sxs-lookup"><span data-stu-id="f76c0-110">Which users are signing into a specific app?</span></span>
- <span data-ttu-id="f76c0-111">密碼重設的發生次數？</span><span class="sxs-lookup"><span data-stu-id="f76c0-111">How many password resets are happening?</span></span>

<span data-ttu-id="f76c0-p103">**登入活動報告**會報告哪個人員執行稽核記錄報告所報告的工作。這份報告會回答如以下的問題：</span><span class="sxs-lookup"><span data-stu-id="f76c0-p103">The **Sign-ins activity report** records who performed the tasks reported by the audit logs report. This report answers questions like:</span></span>

- <span data-ttu-id="f76c0-114">針對調查中的特定使用者，他們的登入模式是什麼？</span><span class="sxs-lookup"><span data-stu-id="f76c0-114">For a specific user under investigation, what is their sign-in pattern?</span></span>
- <span data-ttu-id="f76c0-115">一天、週或月的登入活動量為何？</span><span class="sxs-lookup"><span data-stu-id="f76c0-115">What is my volume of sign-ins over a day, week, or month?</span></span>
- <span data-ttu-id="f76c0-116">這些登入嘗試不成功的次數有多少，且是針對哪一個帳戶？</span><span class="sxs-lookup"><span data-stu-id="f76c0-116">How many of these sign-in attempts were not successful, and for which accounts?</span></span>

<span data-ttu-id="f76c0-117">如需報告以及如何存取他們的詳細資訊，請參閱 [Azure Active Directory 報告](https://docs.microsoft.com/azure/active-directory/active-directory-reporting-azure-portal)。</span><span class="sxs-lookup"><span data-stu-id="f76c0-117">For more information about the reports and how to access them, see [Azure Active Directory reporting](https://docs.microsoft.com/azure/active-directory/active-directory-reporting-azure-portal).</span></span>

<span data-ttu-id="f76c0-118">在此步驟的結果中，您將了解這些報告以及如何使用這些報告來深入了解用於規劃與安全性目的之 Azure AD 事件與活動。</span><span class="sxs-lookup"><span data-stu-id="f76c0-118">As a result of this step, you'll gain awareness of these reports and an understanding of how you can use them to gain insights on Azure AD events and activities for planning and security purposes.</span></span>

## <a name="next-step"></a><span data-ttu-id="f76c0-119">下一步</span><span class="sxs-lookup"><span data-stu-id="f76c0-119">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step14.png)| [<span data-ttu-id="f76c0-120">允許使用者建立及管理自己的群組</span><span class="sxs-lookup"><span data-stu-id="f76c0-120">Allow users to create and manage their own groups</span></span>](identity-self-service-group-management.md) |
