---
title: 高級郵件加密
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 10/16/2019
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
description: 「高級郵件加密」可讓系統管理員更進一步使用受保護的郵件，以協助組織滿足其相容性義務。
ms.openlocfilehash: 8c650c47c1853102e4e2d142040e49724ef707e0
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923953"
---
# <a name="advanced-message-encryption"></a><span data-ttu-id="949c5-103">高級郵件加密</span><span class="sxs-lookup"><span data-stu-id="949c5-103">Advanced Message Encryption</span></span>

<span data-ttu-id="949c5-104">Office 365 Advanced Message Encryption 包含在 [Microsoft 365 企業版 e5](https://www.microsoft.com/microsoft-365/enterprise/home)、Office 365 E5、Microsoft 365 E5 (非盈利性員工定價) 、Office 365 企業版 E5 (非盈利性員工定價) 和 Office 365 教育版 A5。</span><span class="sxs-lookup"><span data-stu-id="949c5-104">Office 365 Advanced Message Encryption is included in [Microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home), Office 365 E5, Microsoft 365 E5 (Nonprofit Staff Pricing), Office 365 Enterprise E5 (Nonprofit Staff Pricing), and Office 365 Education A5.</span></span> <span data-ttu-id="949c5-105">如果您的組織中有未包含 Office 365 Advanced Message Encryption 的訂閱，您可以使用 microsoft 365 E5 相容性 SKU 附加元件（適用于 Microsoft 365 E3）進行購買。 Microsoft 365 E3 (非盈利性員工定價) 或 Office 365 Advanced 合規性 SKU 附加元件（適用于 Microsoft 365 E3），Microsoft 365 E3 (非盈利性員工定價) ，Office 365 SKUs，或 Microsoft 365 E5/A5 資訊保護和控管 SKU 附加元件（適用于 Microsoft 365 A3/E3）。</span><span class="sxs-lookup"><span data-stu-id="949c5-105">If your organization has a subscription that does not include Office 365 Advanced Message Encryption, you can purchase it with the Microsoft 365 E5 Compliance SKU add-on for Microsoft 365 E3, Microsoft 365 E3 (Nonprofit Staff Pricing), or the Office 365 Advanced Compliance SKU add-on for Microsoft 365 E3, Microsoft 365 E3 (Nonprofit Staff Pricing), Office 365 SKUs, or the Microsoft 365 E5/A5 Information Protection and Governance SKU add-on for Microsoft 365 A3/E3.</span></span>

<span data-ttu-id="949c5-106">進階郵件加密可協助客戶滿足需要對外部收件者更靈活控制，以及其對加密電子郵件存取的合規性義務。</span><span class="sxs-lookup"><span data-stu-id="949c5-106">Advanced Message Encryption helps customers meet compliance obligations that require more flexible controls over external recipients and their access to encrypted emails.</span></span> <span data-ttu-id="949c5-107">使用 Office 365 中的高級郵件加密，您可以控制在組織外與自動原則共用的敏感電子郵件。</span><span class="sxs-lookup"><span data-stu-id="949c5-107">With Advanced Message Encryption in Office 365, you can control sensitive emails shared outside the organization with automatic policies.</span></span> <span data-ttu-id="949c5-108">您可以設定這些原則來識別敏感資訊類型，例如 PII、財務或健康情況 IDs，也可以使用關鍵字來增強保護。</span><span class="sxs-lookup"><span data-stu-id="949c5-108">You configure these policies to identify sensitive information types such as PII, Financial, or Health IDs, or you can use keywords to enhance protection.</span></span> <span data-ttu-id="949c5-109">設定原則之後，您可以使用自訂的署名電子郵件範本對原則進行配對，然後新增到期日，以對符合原則的電子郵件進行特殊的控制。</span><span class="sxs-lookup"><span data-stu-id="949c5-109">Once you've configured the policies, you pair policies with custom branded email templates and then add an expiration date for extra control of emails that fit the policy.</span></span> <span data-ttu-id="949c5-110">此外，系統管理員可以隨時撤銷郵件存取權，透過安全的網頁入口網站進一步控制從外部存取的加密電子郵件。</span><span class="sxs-lookup"><span data-stu-id="949c5-110">Also, admins can further control encrypted emails accessed externally through a secure web portal by revoking access to the mail at any time.</span></span>

<span data-ttu-id="949c5-111">您只能撤銷及設定傳送給外部收件者之電子郵件的到期日。</span><span class="sxs-lookup"><span data-stu-id="949c5-111">You can only revoke and set an expiration date for emails sent to external recipients.</span></span>

## <a name="get-started-with-office-365-advanced-message-encryption"></a><span data-ttu-id="949c5-112">開始使用 Office 365 Advanced Message Encryption</span><span class="sxs-lookup"><span data-stu-id="949c5-112">Get started with Office 365 Advanced Message Encryption</span></span>

<span data-ttu-id="949c5-113">下列文章說明如何設定及使用高級郵件加密。</span><span class="sxs-lookup"><span data-stu-id="949c5-113">The following articles describe how you set up and use Advanced Message Encryption.</span></span>

<span data-ttu-id="949c5-114">您的組織必須具有包含 Office 365 Advanced Message Encryption 的訂閱。</span><span class="sxs-lookup"><span data-stu-id="949c5-114">Your organization must have a subscription that includes Office 365 Advanced Message Encryption.</span></span> <span data-ttu-id="949c5-115">如需支援之訂閱的詳細資訊，請參閱 [郵件原則及符合性服務描述](/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)。</span><span class="sxs-lookup"><span data-stu-id="949c5-115">For detailed information about supported subscriptions, see the [Message policy and compliance service description](/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance).</span></span>

<span data-ttu-id="949c5-116">若尚未設定 Office 365 郵件加密，請參閱 [設定新的 office 365 郵件加密功能](set-up-new-message-encryption-capabilities.md)。</span><span class="sxs-lookup"><span data-stu-id="949c5-116">If you do not have Office 365 Message Encryption set up already, see [Set up new Office 365 Message Encryption capabilities](set-up-new-message-encryption-capabilities.md).</span></span>

<span data-ttu-id="949c5-117">使用高級郵件加密時，您不只限於單一署名範本。</span><span class="sxs-lookup"><span data-stu-id="949c5-117">With Advanced Message Encryption you're not limited to a single branding template.</span></span> <span data-ttu-id="949c5-118">相反地，您可以建立及使用多個商標範本。</span><span class="sxs-lookup"><span data-stu-id="949c5-118">Instead, you can create and use multiple branding templates.</span></span> <span data-ttu-id="949c5-119">如需詳細資訊，請參閱 [將貴組織的品牌新增至加密郵件](add-your-organization-brand-to-encrypted-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="949c5-119">For information, see [Add your organization's brand to your encrypted messages](add-your-organization-brand-to-encrypted-messages.md).</span></span>

<span data-ttu-id="949c5-120">[設定 Office 365 高級郵件加密所加密之電子郵件的到期日](ome-advanced-expiration.md)。</span><span class="sxs-lookup"><span data-stu-id="949c5-120">[Set an expiration date for email encrypted by Office 365 Advanced Message Encryption](ome-advanced-expiration.md).</span></span> <span data-ttu-id="949c5-121">控制在組織外共用的敏感電子郵件使用自動原則，透過將安全的 web 入口網站的存取權終止至加密的電子郵件，增強保護。</span><span class="sxs-lookup"><span data-stu-id="949c5-121">Control sensitive emails shared outside the organization with automatic policies that enhance protection by expiring access through a secure web portal to encrypted emails.</span></span>

<span data-ttu-id="949c5-122">[撤銷 Office 365 高級郵件加密所加密的電子郵件](revoke-ome-encrypted-mail.md)。</span><span class="sxs-lookup"><span data-stu-id="949c5-122">[Revoke email encrypted by Office 365 Advanced Message Encryption](revoke-ome-encrypted-mail.md).</span></span> <span data-ttu-id="949c5-123">控制組織外共用的敏感電子郵件，並透過安全的 web 入口網站撤銷加密的電子郵件，增強保護。</span><span class="sxs-lookup"><span data-stu-id="949c5-123">Control sensitive emails shared outside the organization and enhance protection by revoking access through a secure web portal to encrypted emails.</span></span>  

<span data-ttu-id="949c5-124">使用 Office 365 Advanced Message Encryption 時，無論您何時套用自訂商標範本，Microsoft 都會對符合您套用範本之郵件流程規則的電子郵件套用包裝。</span><span class="sxs-lookup"><span data-stu-id="949c5-124">With Office 365 Advanced Message Encryption, anytime you apply a custom branding template, Microsoft applies a wrapper to email that fits the mail flow rule to which you apply the template.</span></span> <span data-ttu-id="949c5-125">您只能撤銷郵件，並將到期日期套用至使用者透過入口網站取得的郵件。</span><span class="sxs-lookup"><span data-stu-id="949c5-125">You can only revoke messages and apply expiration dates to messages that users receive through the portal.</span></span> <span data-ttu-id="949c5-126">換句話說，已套用自訂商標範本的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="949c5-126">In other words, email that has a custom branding template applied.</span></span> <span data-ttu-id="949c5-127">如需詳細資訊和範例，請參閱 [確保所有外部收件者都使用 OME 入口網站來讀取加密郵件](manage-office-365-message-encryption.md#ensure-all-external-recipients-use-the-ome-portal-to-read-encrypted-mail)的指導方針。</span><span class="sxs-lookup"><span data-stu-id="949c5-127">For more information and an example, see the guidance in [Ensure all external recipients use the OME Portal to read encrypted mail](manage-office-365-message-encryption.md#ensure-all-external-recipients-use-the-ome-portal-to-read-encrypted-mail).</span></span>