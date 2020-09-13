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
description: 使用 Office 365 Advanced Message Encryption，透過自訂的署名範本來設定電子郵件的到期日，以擴充電子郵件的安全性。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0dcf9c82f9204f1357b49411d0ca87e87007eb96
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/12/2020
ms.locfileid: "47546157"
---
# <a name="set-an-expiration-date-for-email-encrypted-by-office-365-advanced-message-encryption"></a><span data-ttu-id="2cd84-103">為由 Office 365 進階郵件加密所加密的電子郵件設定到期日</span><span class="sxs-lookup"><span data-stu-id="2cd84-103">Set an expiration date for email encrypted by Office 365 Advanced Message Encryption</span></span>

<span data-ttu-id="2cd84-104">Office 365 Advanced Message Encryption 包含在 [Microsoft 365 企業版 e5](https://www.microsoft.com/microsoft-365/enterprise/home)、Office 365 E5、Microsoft 365 E5 (非盈利性員工定價) 、Office 365 企業版 E5 (非盈利性員工定價) 和 Office 365 教育版 A5。</span><span class="sxs-lookup"><span data-stu-id="2cd84-104">Office 365 Advanced Message Encryption is included in [Microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home), Office 365 E5, Microsoft 365 E5 (Nonprofit Staff Pricing), Office 365 Enterprise E5 (Nonprofit Staff Pricing), and Office 365 Education A5.</span></span> <span data-ttu-id="2cd84-105">如果您的組織中有未包含 Office 365 Advanced Message Encryption 的訂閱，您可以使用 microsoft 365 E5 相容性 SKU 附加元件（適用于 Microsoft 365 E3）購買它; microsoft 365 E3 (非盈利性員工定價) ，或 Office 365 的高級合規性 SKU 附加元件（適用于 Microsoft 365 E3），Microsoft 365 E3 (非盈利性員工定價) 或 Office 365 SKUs。</span><span class="sxs-lookup"><span data-stu-id="2cd84-105">If your organization has a subscription that does not include Office 365 Advanced Message Encryption, you can purchase it with the Microsoft 365 E5 Compliance SKU add-on for Microsoft 365 E3, Microsoft 365 E3 (Nonprofit Staff Pricing), or the Office 365 Advanced Compliance SKU add-on for Microsoft 365 E3, Microsoft 365 E3 (Nonprofit Staff Pricing), or Office 365 SKUs.</span></span>

<span data-ttu-id="2cd84-106">您可以使用郵件到期的電子郵件，讓使用者傳送給使用 OME 入口網站來存取加密電子郵件的外部收件者。</span><span class="sxs-lookup"><span data-stu-id="2cd84-106">You can use message expiration on emails that your users send to external recipients who use the OME Portal to access encrypted emails.</span></span> <span data-ttu-id="2cd84-107">您可以使用 OME 入口網站，透過在 Windows Powershell 中指定到期日的自訂署名範本，以查看及回復組織所傳送的加密電子郵件。</span><span class="sxs-lookup"><span data-stu-id="2cd84-107">You force recipients to use the OME portal to view and reply to encrypted emails sent by your organization by using a custom branded template that specifies an expiration date in Windows Powershell.</span></span>

<span data-ttu-id="2cd84-108">作為 O365 全域管理員，當您套用公司品牌以自訂群組織的電子郵件訊息的外觀時，您也可以指定這些電子郵件的到期日期。</span><span class="sxs-lookup"><span data-stu-id="2cd84-108">As an O365 global administrator, when you apply your company brand to customize the look of your organization's email messages, you can also specify an expiration for these email messages.</span></span> <span data-ttu-id="2cd84-109">使用 Office 365 Advanced Message Encryption，您可以建立多個範本，以用於來自組織的加密電子郵件。</span><span class="sxs-lookup"><span data-stu-id="2cd84-109">With Office 365 Advanced Message Encryption, you can create multiple templates for encrypted emails that originate from your organization.</span></span> <span data-ttu-id="2cd84-110">使用範本，您可以控制收件者存取使用者所傳送之郵件的時間長短。</span><span class="sxs-lookup"><span data-stu-id="2cd84-110">Using a template, you can control how long recipients have access to mail sent by your users.</span></span>

<span data-ttu-id="2cd84-111">當使用者收到具有到期日設定的郵件時，使用者會看到包裝電子郵件中的到期日。</span><span class="sxs-lookup"><span data-stu-id="2cd84-111">When an end user receives mail that has an expiration date set, the user sees the expiration date in the wrapper email.</span></span> <span data-ttu-id="2cd84-112">如果使用者嘗試開啟到期的郵件，則會在 OME 入口網站中顯示錯誤。</span><span class="sxs-lookup"><span data-stu-id="2cd84-112">If a user tries to open an expired mail, an error appears in the OME portal.</span></span>

<span data-ttu-id="2cd84-113">您只能將電子郵件的到期日期設定為外部收件者。</span><span class="sxs-lookup"><span data-stu-id="2cd84-113">You can only set expiration dates for emails to external recipients.</span></span>

<span data-ttu-id="2cd84-114">使用 Office 365 Advanced Message Encryption 時，無論您何時套用自訂品牌，Office 365 都會對符合郵件流程規則的電子郵件套用您要套用範本的包裝。</span><span class="sxs-lookup"><span data-stu-id="2cd84-114">With Office 365 Advanced Message Encryption, anytime you apply custom branding, the Office 365 applies the wrapper to email that fits the mail flow rule to which you apply the template.</span></span> <span data-ttu-id="2cd84-115">此外，如果您使用自訂署名，您只可以使用到期。</span><span class="sxs-lookup"><span data-stu-id="2cd84-115">In addition, you can only use expiration if you use custom branding.</span></span>

## <a name="create-a-custom-branding-template-to-force-mail-expiration-by-using-powershell"></a><span data-ttu-id="2cd84-116">使用 PowerShell 建立自訂品牌範本以強制郵件到期</span><span class="sxs-lookup"><span data-stu-id="2cd84-116">Create a custom branding template to force mail expiration by using PowerShell</span></span>

1. <span data-ttu-id="2cd84-117">使用具備組織中全域系統管理員許可權的帳戶，連線[至 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) 。</span><span class="sxs-lookup"><span data-stu-id="2cd84-117">[Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) with an account that has global administrator permissions in your organization.</span></span>

2. <span data-ttu-id="2cd84-118">執行 Set-omeconfiguration Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="2cd84-118">Run the New-OMEConfiguration cmdlet.</span></span>

     ```powershell
     New-OMEConfiguration -Identity "Expire in 7 days" -ExternalMailExpiryInDays 7
     ```

<span data-ttu-id="2cd84-119">其中：</span><span class="sxs-lookup"><span data-stu-id="2cd84-119">Where:</span></span>

- <span data-ttu-id="2cd84-120">`Identity` 是自訂範本的名稱。</span><span class="sxs-lookup"><span data-stu-id="2cd84-120">`Identity` is the name of the custom template.</span></span>

- <span data-ttu-id="2cd84-121">`ExternalMailExpiryInDays` 識別收件者可以在郵件到期之前保留郵件的天數。</span><span class="sxs-lookup"><span data-stu-id="2cd84-121">`ExternalMailExpiryInDays` identifies the number of days that recipients can keep mail before it expires.</span></span> <span data-ttu-id="2cd84-122">您可以使用1到730天之間的任何值。</span><span class="sxs-lookup"><span data-stu-id="2cd84-122">You can use any value between 1–730 days.</span></span>

## <a name="more-information-about-office-365-advanced-message-encryption"></a><span data-ttu-id="2cd84-123">有關 Office 365 Advanced Message Encryption 的詳細資訊</span><span class="sxs-lookup"><span data-stu-id="2cd84-123">More information about Office 365 Advanced Message Encryption</span></span>

- [<span data-ttu-id="2cd84-124">Office 365 進階郵件加密</span><span class="sxs-lookup"><span data-stu-id="2cd84-124">Office 365 Advanced Message Encryption</span></span>](ome-advanced-message-encryption.md)

- [<span data-ttu-id="2cd84-125">撤銷由 Office 365 進階郵件加密所加密的電子郵件</span><span class="sxs-lookup"><span data-stu-id="2cd84-125">Revoke email encrypted by Office 365 Advanced Message Encryption</span></span>](revoke-ome-encrypted-mail.md)

- [<span data-ttu-id="2cd84-126">郵件原則及合規性服務說明</span><span class="sxs-lookup"><span data-stu-id="2cd84-126">Message policy and compliance service description</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)
