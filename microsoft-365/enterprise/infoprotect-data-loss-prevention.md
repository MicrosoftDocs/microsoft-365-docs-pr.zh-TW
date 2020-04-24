---
title: 步驟 5：設定資料外洩防護
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/19/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: 了解 Microsoft 365 中的資料外洩防護並且進行部署。
ms.openlocfilehash: e3d18bf54ecdfe11f8233163e7f200a70606d81d
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2020
ms.locfileid: "43636973"
---
# <a name="step-5-configure-data-loss-prevention"></a><span data-ttu-id="e5bf5-103">步驟 5：設定資料外洩防護</span><span class="sxs-lookup"><span data-stu-id="e5bf5-103">Step 5: Configure Data Loss Prevention</span></span>

<span data-ttu-id="e5bf5-104">*此為選用步驟，且同時適用於 Microsoft 365 企業版 E3 和 E5 版本*</span><span class="sxs-lookup"><span data-stu-id="e5bf5-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![階段 6：資訊保護](../media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="e5bf5-106">透過安全性與合規性中心的資料外洩防護 (DLP) 原則，您可以識別、監控及自動保護整個 Microsoft 365 的機密資訊。</span><span class="sxs-lookup"><span data-stu-id="e5bf5-106">With data loss prevention (DLP) policies in the Security & Compliance center, you can identify, monitor, and automatically protect sensitive information across Microsoft 365.</span></span> <span data-ttu-id="e5bf5-107">使用 DLP 原則，您可以：</span><span class="sxs-lookup"><span data-stu-id="e5bf5-107">With DLP policies, you can:</span></span>

- <span data-ttu-id="e5bf5-108">在多個位置識別敏感性資訊，例如 Exchange Online、SharePoint Online、商務用 OneDrive 及 Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="e5bf5-108">Identify sensitive information across many locations, such as Exchange Online, SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span>
- <span data-ttu-id="e5bf5-109">藉由封鎖文件的存取或封鎖包含文件的電子郵件，防止意外共用敏感性資訊。</span><span class="sxs-lookup"><span data-stu-id="e5bf5-109">Prevent the accidental sharing of sensitive information by blocking access to a document or blocking the email that contains it.</span></span>
- <span data-ttu-id="e5bf5-110">監視和保護 Excel、PowerPoint 和 Word 桌面版中的敏感性資訊。</span><span class="sxs-lookup"><span data-stu-id="e5bf5-110">Monitor and protect sensitive information in the desktop versions of Excel, PowerPoint, and Word.</span></span>
- <span data-ttu-id="e5bf5-111">透過電子郵件通知和原則提示協助使用者了解如何符合規範，而不中斷其工作流程。</span><span class="sxs-lookup"><span data-stu-id="e5bf5-111">Help users learn how to stay compliant without interrupting their workflow with email notifications and policy tips.</span></span> 
- <span data-ttu-id="e5bf5-112">檢視 DLP 報告以了解有哪些內容符合您的組織的 DLP 原則。</span><span class="sxs-lookup"><span data-stu-id="e5bf5-112">View DLP reports showing content that matches your organization's DLP policies.</span></span>

<span data-ttu-id="e5bf5-113">DLP 原則會指定：</span><span class="sxs-lookup"><span data-stu-id="e5bf5-113">A DLP policy specifies:</span></span>

- <span data-ttu-id="e5bf5-114">**何地：** 位置，例如 Exchange Online、SharePoint Online 和商務用 OneDrive 網站，以及 Microsoft Teams 聊天和頻道。</span><span class="sxs-lookup"><span data-stu-id="e5bf5-114">**Where:** Locations such as Exchange Online, SharePoint Online, and OneDrive for Business sites, as well as Microsoft Teams chats and channels.</span></span>
- <span data-ttu-id="e5bf5-115">**何時：** 內容必須在特定原則規則內符合的條件。</span><span class="sxs-lookup"><span data-stu-id="e5bf5-115">**When:** Conditions the content must match within a specific policy rule.</span></span>
- <span data-ttu-id="e5bf5-116">**如何：** 讓相符原則規則自動對相符條件採用的動作。</span><span class="sxs-lookup"><span data-stu-id="e5bf5-116">**How:** Actions within that matching policy rule to take automatically for the matching conditions.</span></span>

<span data-ttu-id="e5bf5-117">換句話說：</span><span class="sxs-lookup"><span data-stu-id="e5bf5-117">In other words:</span></span>

- <span data-ttu-id="e5bf5-118">對於這個位置中的文件 (何地)，如果內容符合規則的條件 (何時)，則自動採用規則中指定的動作 (如何)。</span><span class="sxs-lookup"><span data-stu-id="e5bf5-118">For a document in this location (where), if the content matches the conditions of a rule (when), then automatically take the actions specified in the rule (how).</span></span>

<span data-ttu-id="e5bf5-119">若要決定您需要的一組 DLP 原則，您必須分析文件，以及文件中需要進行資料外洩防護的資料類型。</span><span class="sxs-lookup"><span data-stu-id="e5bf5-119">To determine the set of DLP policies you need, you must analyze your documents and the types of data within them that need protection from data loss.</span></span> <span data-ttu-id="e5bf5-120">舉例來說，如果您是美國的金融組織，建立 DLP 原則來防止具有社會安全號碼的文件在組織外部共用，或以電子郵件傳送到組織外部的位置。</span><span class="sxs-lookup"><span data-stu-id="e5bf5-120">For example, if you are a financial organization in the United States of America, you would create a DLP policy that prevents documents with social security numbers from being shared outside the organization or sent in email to locations outside the organization.</span></span>

<span data-ttu-id="e5bf5-121">接下來，您進行設定並且使用測試位置來測試原則，以確保正確的 DLP 行為並且將誤判降至最低。</span><span class="sxs-lookup"><span data-stu-id="e5bf5-121">Next, you configure and test the policies with test locations to ensure the correct DLP behavior and to minimize false positives.</span></span>

<span data-ttu-id="e5bf5-122">最後，您透過通知員工有新的原則及其所需的行為並且擴大位置範圍，在貴組織中推出該原則。</span><span class="sxs-lookup"><span data-stu-id="e5bf5-122">Finally, you roll it out to your organization by informing the employees of the new policies and their desired behavior and widening the scope of the locations.</span></span>

<span data-ttu-id="e5bf5-123">如需詳細資訊，請參閱[開始使用 DLP 原則建議](https://docs.microsoft.com/office365/securitycompliance/get-started-with-dlp-policy-recommendations)。</span><span class="sxs-lookup"><span data-stu-id="e5bf5-123">For more information, see [Get started with DLP policy recommendations](https://docs.microsoft.com/office365/securitycompliance/get-started-with-dlp-policy-recommendations).</span></span>

<span data-ttu-id="e5bf5-124">作為過渡期的檢查點，您可以看到與此步驟相對應的[允出準則](infoprotect-exit-criteria.md#crit-infoprotect-step5)。</span><span class="sxs-lookup"><span data-stu-id="e5bf5-124">As an interim checkpoint, see the [exit criteria](infoprotect-exit-criteria.md#crit-infoprotect-step5) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="e5bf5-125">下一步</span><span class="sxs-lookup"><span data-stu-id="e5bf5-125">Next step</span></span>

|||
|:-------|:-----|
|![步驟 6](../media/stepnumbers/Step6.png)|[<span data-ttu-id="e5bf5-127">設定電子郵件加密</span><span class="sxs-lookup"><span data-stu-id="e5bf5-127">Configure email encryption</span></span>](infoprotect-email-encryption.md)|


