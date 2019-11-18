---
title: 為由 Office 365 進階郵件加密所加密的電子郵件設定到期日
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
description: 與 Office 365 進階郵件加密功能掌握 Office 365 郵件加密 (OME)，您可以擴充您的電子郵件安全性設定的自訂品牌範本透過電子郵件到期日。
ms.openlocfilehash: 6790cc7103ad098419bde96b93738424626cd0cc
ms.sourcegitcommit: 70e920f76526f47fc849df615de4569e0ac2f4be
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/07/2019
ms.locfileid: "38685467"
---
# <a name="set-an-expiration-date-for-email-encrypted-by-office-365-advanced-message-encryption"></a><span data-ttu-id="5e20b-103">為由 Office 365 進階郵件加密所加密的電子郵件設定到期日</span><span class="sxs-lookup"><span data-stu-id="5e20b-103">Set an expiration date for email encrypted by Office 365 Advanced Message Encryption</span></span>

<span data-ttu-id="5e20b-104">Office 365 進階郵件加密隨附於[Microsoft 365 企業版 E5](https://www.microsoft.com/microsoft-365/enterprise/home)、 Office 365 E5、 Microsoft 365 E5 （非營利組織版人員價格），Office 365 企業版 E5 （非營利組織版人員價格） 和 Office 365 教育版 A5。</span><span class="sxs-lookup"><span data-stu-id="5e20b-104">Office 365 Advanced Message Encryption is included in [Microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home), Office 365 E5, Microsoft 365 E5 (Nonprofit Staff Pricing), Office 365 Enterprise E5 (Nonprofit Staff Pricing), and Office 365 Education A5.</span></span> <span data-ttu-id="5e20b-105">如果貴組織擁有不包含 Office 365 進階郵件加密的訂閱，您可以購買它與 Microsoft 365 E5 規範 SKU 附加元件的 Microsoft 365 E3，Microsoft 365 E3 （非營利組織版人員價格），或 Office 365 進階為 Microsoft 365 E3，Microsoft 365 E3 的合規性 SKU 附加元件 （非營利組織版人員價格），或 Office 365 Sku。</span><span class="sxs-lookup"><span data-stu-id="5e20b-105">If your organization has a subscription that does not include Office 365 Advanced Message Encryption, you can purchase it with the Microsoft 365 E5 Compliance SKU add-on for Microsoft 365 E3, Microsoft 365 E3 (Nonprofit Staff Pricing), or the Office 365 Advanced Compliance SKU add-on for Microsoft 365 E3, Microsoft 365 E3 (Nonprofit Staff Pricing), or Office 365 SKUs.</span></span>

<span data-ttu-id="5e20b-106">您可以使用郵件到期上您的使用者傳送給外部收件者使用 OME 入口網站來存取加密的電子郵件的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="5e20b-106">You can use message expiration on emails that your users send to external recipients who use the OME Portal to access encrypted emails.</span></span> <span data-ttu-id="5e20b-107">您強制使用 OME 入口網站，以檢視和回覆加密所使用 Windows Powershell 中指定到期日的自訂品牌的範本貴組織所傳送的電子郵件的收件者。</span><span class="sxs-lookup"><span data-stu-id="5e20b-107">You force recipients to use the OME portal to view and reply to encrypted emails sent by your organization by using a custom branded template that specifies an expiration date in Windows Powershell.</span></span>

<span data-ttu-id="5e20b-108">以 O365 全域系統管理員身分，當您套用公司品牌自訂外觀的 Office 365 組織的電子郵件，您也可以指定這些電子郵件訊息的到期日。</span><span class="sxs-lookup"><span data-stu-id="5e20b-108">As an O365 global administrator, when you apply your company brand to customize the look of your Office 365 organization's email messages, you can also specify an expiration for these email messages.</span></span> <span data-ttu-id="5e20b-109">使用 Office 365 進階郵件加密，您可以建立多個範本發出的加密電子郵件從您的組織。</span><span class="sxs-lookup"><span data-stu-id="5e20b-109">With Office 365 Advanced Message Encryption, you can create multiple templates for encrypted emails that originate from your organization.</span></span> <span data-ttu-id="5e20b-110">使用範本，您可以控制多久收件者可以存取您的使用者所傳送的郵件。</span><span class="sxs-lookup"><span data-stu-id="5e20b-110">Using a template, you can control how long recipients have access to mail sent by your users.</span></span>

<span data-ttu-id="5e20b-111">當使用者收到郵件已設定到期日時，使用者會看到的包裝函式電子郵件的到期日期。</span><span class="sxs-lookup"><span data-stu-id="5e20b-111">When an end user receives mail that has an expiration date set, the user sees the expiration date in the wrapper email.</span></span> <span data-ttu-id="5e20b-112">如果使用者嘗試開啟過期的郵件，則會在 OME 入口網站中出現的錯誤。</span><span class="sxs-lookup"><span data-stu-id="5e20b-112">If a user tries to open an expired mail, an error appears in the OME portal.</span></span>

<span data-ttu-id="5e20b-113">您只能設定到期日的電子郵件給外部收件者。</span><span class="sxs-lookup"><span data-stu-id="5e20b-113">You can only set expiration dates for emails to external recipients.</span></span>

<span data-ttu-id="5e20b-114">使用 Office 365 進階郵件加密，只要您將自訂品牌套 Office 365 適用於包裝函式電子郵件符合您要套用該範本的郵件流程規則。</span><span class="sxs-lookup"><span data-stu-id="5e20b-114">With Office 365 Advanced Message Encryption, anytime you apply custom branding, the Office 365 applies the wrapper to email that fits the mail flow rule to which you apply the template.</span></span> <span data-ttu-id="5e20b-115">此外，您只可以使用到期，如果您使用自訂品牌。</span><span class="sxs-lookup"><span data-stu-id="5e20b-115">In addition, you can only use expiration if you use custom branding.</span></span>

## <a name="create-a-custom-branding-template-to-force-mail-expiration-by-using-powershell"></a><span data-ttu-id="5e20b-116">建立自訂品牌範本，以藉由使用 PowerShell 來強制郵件到期</span><span class="sxs-lookup"><span data-stu-id="5e20b-116">Create a custom branding template to force mail expiration by using PowerShell</span></span>

1. <span data-ttu-id="5e20b-117">搭配 Office 365 組織中具有全域系統管理員權限的帳戶，[連線到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell) 。</span><span class="sxs-lookup"><span data-stu-id="5e20b-117">[Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell) with an account that has global administrator permissions in your Office 365 organization.</span></span>

2. <span data-ttu-id="5e20b-118">執行新增 Set-omeconfiguration 指令程式。</span><span class="sxs-lookup"><span data-stu-id="5e20b-118">Run the New-OMEConfiguration cmdlet.</span></span>

     ```powershell
     New-OMEConfiguration -Identity "Expire in 7 days" -ExternalMailExpiryInDays 7
     ```

<span data-ttu-id="5e20b-119">其中：</span><span class="sxs-lookup"><span data-stu-id="5e20b-119">Where:</span></span>

- <span data-ttu-id="5e20b-120">`Identity`是自訂樣板的名稱。</span><span class="sxs-lookup"><span data-stu-id="5e20b-120">`Identity` is the name of the custom template.</span></span>

- <span data-ttu-id="5e20b-121">`ExternalMailExpiryInDays`識別收件者可以保留郵件過期前的天數。</span><span class="sxs-lookup"><span data-stu-id="5e20b-121">`ExternalMailExpiryInDays` identifies the number of days that recipients can keep mail before it expires.</span></span> <span data-ttu-id="5e20b-122">您可以使用 1 – 730 天之間的任何值。</span><span class="sxs-lookup"><span data-stu-id="5e20b-122">You can use any value between 1–730 days.</span></span>

## <a name="more-information-about-office-365-advanced-message-encryption"></a><span data-ttu-id="5e20b-123">Office 365 進階郵件加密的詳細資訊</span><span class="sxs-lookup"><span data-stu-id="5e20b-123">More information about Office 365 Advanced Message Encryption</span></span>

- [<span data-ttu-id="5e20b-124">Office 365 進階郵件加密</span><span class="sxs-lookup"><span data-stu-id="5e20b-124">Office 365 Advanced Message Encryption</span></span>](ome-advanced-message-encryption.md)

- [<span data-ttu-id="5e20b-125">撤銷由 Office 365 進階郵件加密所加密的電子郵件</span><span class="sxs-lookup"><span data-stu-id="5e20b-125">Revoke email encrypted by Office 365 Advanced Message Encryption</span></span>](revoke-ome-encrypted-mail.md)

- [<span data-ttu-id="5e20b-126">郵件原則及符合性服務說明</span><span class="sxs-lookup"><span data-stu-id="5e20b-126">Message policy and compliance service description</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)
