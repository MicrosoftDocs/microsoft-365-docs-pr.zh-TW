---
title: 為由 Office 365 進階郵件加密所加密的電子郵件設定到期日
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 10/8/2019
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: 透過自訂的署名範本，使用 Office 365 進階郵件加密來設定電子郵件的到期日，以擴充電子郵件的安全性。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f936ffa62f31e47f51fc1bcb2765195b0ea809af
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927783"
---
# <a name="set-an-expiration-date-for-email-encrypted-by-office-365-advanced-message-encryption"></a><span data-ttu-id="6feba-103">為由 Office 365 進階郵件加密所加密的電子郵件設定到期日</span><span class="sxs-lookup"><span data-stu-id="6feba-103">Set an expiration date for email encrypted by Office 365 Advanced Message Encryption</span></span>

<span data-ttu-id="6feba-104">Office 365 進階郵件加密包含[Microsoft 365 企業版 E5](https://www.microsoft.com/microsoft-365/enterprise/home)、Office 365 E5、Microsoft 365 E5 (非盈利性員工定價) 、Office 365 企業版 E5 (非盈利性員工定價) 和 Office 365 教育版 A5。</span><span class="sxs-lookup"><span data-stu-id="6feba-104">Office 365 Advanced Message Encryption is included in [Microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home), Office 365 E5, Microsoft 365 E5 (Nonprofit Staff Pricing), Office 365 Enterprise E5 (Nonprofit Staff Pricing), and Office 365 Education A5.</span></span> <span data-ttu-id="6feba-105">如果您的組織中有未包括 Office 365 進階郵件加密的訂閱，您可以使用 Microsoft 365 E3 的 Microsoft 365 E5 合規性 SKU 附加元件購買它，Microsoft 365 E3 (非盈利性員工定價) 或 Office 365 進階合規性的 SKU 附加元件，Microsoft 365 E3 Microsoft 365 E3 非盈利性員工定價 (，或) Office 365。</span><span class="sxs-lookup"><span data-stu-id="6feba-105">If your organization has a subscription that does not include Office 365 Advanced Message Encryption, you can purchase it with the Microsoft 365 E5 Compliance SKU add-on for Microsoft 365 E3, Microsoft 365 E3 (Nonprofit Staff Pricing), or the Office 365 Advanced Compliance SKU add-on for Microsoft 365 E3, Microsoft 365 E3 (Nonprofit Staff Pricing), or Office 365 SKUs.</span></span>

<span data-ttu-id="6feba-106">您可以使用郵件到期的電子郵件，讓使用者傳送給使用 OME 入口網站來存取加密電子郵件的外部收件者。</span><span class="sxs-lookup"><span data-stu-id="6feba-106">You can use message expiration on emails that your users send to external recipients who use the OME Portal to access encrypted emails.</span></span> <span data-ttu-id="6feba-107">您可以使用 OME 入口網站，透過在 Windows PowerShell 中指定到期日的自訂署名範本，以查看及回復組織所傳送的加密電子郵件。</span><span class="sxs-lookup"><span data-stu-id="6feba-107">You force recipients to use the OME portal to view and reply to encrypted emails sent by your organization by using a custom branded template that specifies an expiration date in Windows PowerShell.</span></span>

<span data-ttu-id="6feba-108">Office 365 全域系統管理員，當您套用公司品牌以自訂群組織的電子郵件訊息的外觀時，您也可以指定這些電子郵件的到期日期。</span><span class="sxs-lookup"><span data-stu-id="6feba-108">As an Office 365 global administrator, when you apply your company brand to customize the look of your organization's email messages, you can also specify an expiration for these email messages.</span></span> <span data-ttu-id="6feba-109">透過 Office 365 進階郵件加密，您可以建立多個範本，以用於來自組織的加密電子郵件。</span><span class="sxs-lookup"><span data-stu-id="6feba-109">With Office 365 Advanced Message Encryption, you can create multiple templates for encrypted emails that originate from your organization.</span></span> <span data-ttu-id="6feba-110">使用範本，您可以控制收件者存取使用者所傳送之郵件的時間長短。</span><span class="sxs-lookup"><span data-stu-id="6feba-110">Using a template, you can control how long recipients have access to mail sent by your users.</span></span>

<span data-ttu-id="6feba-111">當使用者收到具有到期日設定的郵件時，使用者會看到包裝電子郵件中的到期日。</span><span class="sxs-lookup"><span data-stu-id="6feba-111">When an end user receives mail that has an expiration date set, the user sees the expiration date in the wrapper email.</span></span> <span data-ttu-id="6feba-112">如果使用者嘗試開啟到期的郵件，則會在 OME 入口網站中顯示錯誤。</span><span class="sxs-lookup"><span data-stu-id="6feba-112">If a user tries to open an expired mail, an error appears in the OME portal.</span></span>

<span data-ttu-id="6feba-113">您只能將電子郵件的到期日期設定為外部收件者。</span><span class="sxs-lookup"><span data-stu-id="6feba-113">You can only set expiration dates for emails to external recipients.</span></span>

<span data-ttu-id="6feba-114">使用 Office 365 進階郵件加密時，每當您套用自訂品牌時，Office 365 都會對符合您套用範本之郵件流程規則的電子郵件套用包裝。</span><span class="sxs-lookup"><span data-stu-id="6feba-114">With Office 365 Advanced Message Encryption, anytime you apply custom branding, the Office 365 applies the wrapper to email that fits the mail flow rule to which you apply the template.</span></span> <span data-ttu-id="6feba-115">此外，如果您使用自訂署名，您只可以使用到期。</span><span class="sxs-lookup"><span data-stu-id="6feba-115">In addition, you can only use expiration if you use custom branding.</span></span>

## <a name="create-a-custom-branding-template-to-force-mail-expiration-by-using-powershell"></a><span data-ttu-id="6feba-116">使用 PowerShell 建立自訂品牌範本以強制郵件到期</span><span class="sxs-lookup"><span data-stu-id="6feba-116">Create a custom branding template to force mail expiration by using PowerShell</span></span>

1. <span data-ttu-id="6feba-117">[連線，以](/powershell/exchange/connect-to-exchange-online-powershell)具備組織中全域系統管理員許可權的帳戶來 Exchange Online PowerShell。</span><span class="sxs-lookup"><span data-stu-id="6feba-117">[Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) with an account that has global administrator permissions in your organization.</span></span>

2. <span data-ttu-id="6feba-118">執行 New-OMEConfiguration Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="6feba-118">Run the New-OMEConfiguration cmdlet.</span></span>

    ```powershell
    New-OMEConfiguration -Identity "Expire in 7 days" -ExternalMailExpiryInDays 7
    ```

<span data-ttu-id="6feba-119">其中：</span><span class="sxs-lookup"><span data-stu-id="6feba-119">Where:</span></span>

- <span data-ttu-id="6feba-120">`Identity` 是自訂範本的名稱。</span><span class="sxs-lookup"><span data-stu-id="6feba-120">`Identity` is the name of the custom template.</span></span>

- <span data-ttu-id="6feba-121">`ExternalMailExpiryInDays` 識別收件者可以在郵件到期之前保留郵件的天數。</span><span class="sxs-lookup"><span data-stu-id="6feba-121">`ExternalMailExpiryInDays` identifies the number of days that recipients can keep mail before it expires.</span></span> <span data-ttu-id="6feba-122">您可以使用1到730天之間的任何值。</span><span class="sxs-lookup"><span data-stu-id="6feba-122">You can use any value between 1–730 days.</span></span>

## <a name="more-information-about-office-365-advanced-message-encryption"></a><span data-ttu-id="6feba-123">Office 365 進階郵件加密的詳細資訊</span><span class="sxs-lookup"><span data-stu-id="6feba-123">More information about Office 365 Advanced Message Encryption</span></span>

- [<span data-ttu-id="6feba-124">Office 365 進階郵件加密</span><span class="sxs-lookup"><span data-stu-id="6feba-124">Office 365 Advanced Message Encryption</span></span>](ome-advanced-message-encryption.md)

- [<span data-ttu-id="6feba-125">撤銷由 Office 365 進階郵件加密所加密的電子郵件</span><span class="sxs-lookup"><span data-stu-id="6feba-125">Revoke email encrypted by Office 365 Advanced Message Encryption</span></span>](revoke-ome-encrypted-mail.md)

- [<span data-ttu-id="6feba-126">郵件原則及合規性服務說明</span><span class="sxs-lookup"><span data-stu-id="6feba-126">Message policy and compliance service description</span></span>](/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)