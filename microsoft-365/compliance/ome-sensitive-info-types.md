---
title: 使用 Office 365 郵件加密建立機密資訊類型原則
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 8/28/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- Strat_O365_Enterprise
description: 瞭解如何使用 Office 365 郵件加密為組織建立機密資訊類型原則。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ad570f64122aecd245b912b1b6545a5950e838cc
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927741"
---
# <a name="create-a-sensitive-information-type-policy-for-your-organization-using-message-encryption"></a><span data-ttu-id="d89cf-103">使用郵件加密為組織建立機密資訊類型原則</span><span class="sxs-lookup"><span data-stu-id="d89cf-103">Create a sensitive information type policy for your organization using Message Encryption</span></span>

<span data-ttu-id="d89cf-104">您可以使用 Exchange 郵件流程規則或資料遺失防護 (DLP) 建立具有 Office 365 郵件加密的敏感資訊類型原則。</span><span class="sxs-lookup"><span data-stu-id="d89cf-104">You can use either Exchange mail flow rules or Data Loss Prevention (DLP) to create a sensitive information type policy with Office 365 Message Encryption.</span></span> <span data-ttu-id="d89cf-105">若要建立 Exchange 郵件流程規則，您可以使用 Exchange admin center (EAC) 或 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="d89cf-105">To create an Exchange mail flow rule, you can use either the Exchange admin center (EAC) or PowerShell.</span></span>

## <a name="to-create-the-policy-by-using-mail-flow-rules-in-the-eac"></a><span data-ttu-id="d89cf-106">使用 EAC 中的郵件流程規則建立原則</span><span class="sxs-lookup"><span data-stu-id="d89cf-106">To create the policy by using mail flow rules in the EAC</span></span>

<span data-ttu-id="d89cf-107"> (EAC) 登入 Exchange 系統管理中心，然後移至 **郵件流程**  >  **規則**。</span><span class="sxs-lookup"><span data-stu-id="d89cf-107">Sign in to the Exchange admin center (EAC) and go to **Mail flow** > **Rules**.</span></span> <span data-ttu-id="d89cf-108">在 [規則] 頁面上，建立套用 Office 365 郵件加密的規則。</span><span class="sxs-lookup"><span data-stu-id="d89cf-108">On the Rules page, create a rule that applies Office 365 Message Encryption.</span></span> <span data-ttu-id="d89cf-109">您可以根據狀況（例如郵件或附件中的某些關鍵字或機密資訊類型的存在性）來建立規則。</span><span class="sxs-lookup"><span data-stu-id="d89cf-109">You can create a rule based on conditions such as the presence of certain keywords or sensitive information types in the message or attachment.</span></span>

### <a name="to-create-the-policy-by-using-mail-flow-rules-in-powershell"></a><span data-ttu-id="d89cf-110">若要使用 PowerShell 中的郵件流程規則建立原則</span><span class="sxs-lookup"><span data-stu-id="d89cf-110">To create the policy by using mail flow rules in PowerShell</span></span>

<span data-ttu-id="d89cf-111">使用組織中具有全域系統管理員許可權的公司或學校帳戶，啟動 Windows PowerShell 會話，並連接至 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="d89cf-111">Use a work or school account that has global administrator permissions in your organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="d89cf-112">如需詳細指示，請參閱[連線到 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="d89cf-112">For instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="d89cf-113">使用 Set-IRMConfiguration 和 New-TransportRule Cmdlet 來建立原則。</span><span class="sxs-lookup"><span data-stu-id="d89cf-113">Use the Set-IRMConfiguration and New-TransportRule cmdlets to create the policy.</span></span>

## <a name="example-mail-flow-rule-created-with-powershell"></a><span data-ttu-id="d89cf-114">使用 PowerShell 建立的郵件流程規則範例</span><span class="sxs-lookup"><span data-stu-id="d89cf-114">Example mail flow rule created with PowerShell</span></span>

<span data-ttu-id="d89cf-115">在 PowerShell 中執行下列命令，以建立 Exchange 郵件流程規則，此規則會在電子郵件或其附件包含下列機密資訊類型時，自動以 [僅限加密] 選項加密組織外傳送的電子郵件：</span><span class="sxs-lookup"><span data-stu-id="d89cf-115">Run the following commands in PowerShell to create an Exchange mail flow rule that automatically encrypts emails sent outside your organization with the encrypt-only option if the emails or their attachments contain the following sensitive information types:</span></span>

- <span data-ttu-id="d89cf-116">ABA 路由號碼</span><span class="sxs-lookup"><span data-stu-id="d89cf-116">ABA routing number</span></span>
- <span data-ttu-id="d89cf-117">信用卡號碼</span><span class="sxs-lookup"><span data-stu-id="d89cf-117">Credit card Number</span></span>
- <span data-ttu-id="d89cf-118">藥物執行代理商 (DEA) 號碼</span><span class="sxs-lookup"><span data-stu-id="d89cf-118">Drug Enforcement Agency (DEA) number</span></span>
- <span data-ttu-id="d89cf-119">美國/英國</span><span class="sxs-lookup"><span data-stu-id="d89cf-119">U.S. / U.K.</span></span> <span data-ttu-id="d89cf-120">護照號碼</span><span class="sxs-lookup"><span data-stu-id="d89cf-120">passport number</span></span>
- <span data-ttu-id="d89cf-121">美國銀行帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="d89cf-121">U.S. bank account number</span></span>
- <span data-ttu-id="d89cf-122">ITIN) 的美國個別納稅人識別號碼 (</span><span class="sxs-lookup"><span data-stu-id="d89cf-122">U.S. Individual Taxpayer Identification Number (ITIN)</span></span>
- <span data-ttu-id="d89cf-123"> (SSN) 的 U.S. 社會安全號碼</span><span class="sxs-lookup"><span data-stu-id="d89cf-123">U.S. Social Security Number (SSN)</span></span>

```powershell
Set-IRMConfiguration -DecryptAttachmentForEncryptOnly $true
New-TransportRule -Name "Encrypt outbound sensitive emails (out of box rule)" -SentToScope  NotInOrganization  -ApplyRightsProtectionTemplate "Encrypt" -MessageContainsDataClassifications @(@{Name="ABA Routing Number"; minCount="1"},@{Name="Credit Card Number"; minCount="1"},@{Name="Drug Enforcement Agency (DEA) Number"; minCount="1"},@{Name="U.S. / U.K. Passport Number"; minCount="1"},@{Name="U.S. Bank Account Number"; minCount="1"},@{Name="U.S. Individual Taxpayer Identification Number (ITIN)"; minCount="1"},@{Name="U.S. Social Security Number (SSN)"; minCount="1"}) -SenderNotificationType "NotifyOnly"
```

<span data-ttu-id="d89cf-124">如需詳細資訊，請參閱 [Set-IRMConfiguration](/powershell/module/exchange/set-irmconfiguration) 和 [New-TransportRule](/powershell/module/exchange/new-transportrule)。</span><span class="sxs-lookup"><span data-stu-id="d89cf-124">For more information, see [Set-IRMConfiguration](/powershell/module/exchange/set-irmconfiguration) and [New-TransportRule](/powershell/module/exchange/new-transportrule).</span></span>

## <a name="how-recipients-access-attachments"></a><span data-ttu-id="d89cf-125">收件者如何存取附件</span><span class="sxs-lookup"><span data-stu-id="d89cf-125">How recipients access attachments</span></span>

<span data-ttu-id="d89cf-126">在 Microsoft 加密郵件後，收件者在存取及開啟其加密的電子郵件時，可不受限制地存取附件。</span><span class="sxs-lookup"><span data-stu-id="d89cf-126">After Microsoft encrypts a message, recipients have unrestricted access to attachments when they access and open their encrypted email.</span></span>

## <a name="to-prepare-for-this-change"></a><span data-ttu-id="d89cf-127">準備進行此變更</span><span class="sxs-lookup"><span data-stu-id="d89cf-127">To prepare for this change</span></span>

<span data-ttu-id="d89cf-128">您可能會想要更新任何適用的使用者檔和訓練材料，以準備組織中的人員進行此項變更。</span><span class="sxs-lookup"><span data-stu-id="d89cf-128">You may want to update any applicable end-user documentation and training materials to prepare people in your organization for this change.</span></span> <span data-ttu-id="d89cf-129">視您的使用者分享下列 Office 365 郵件加密資源：</span><span class="sxs-lookup"><span data-stu-id="d89cf-129">Share these Office 365 Message Encryption resources with your users as appropriate:</span></span>

- [<span data-ttu-id="d89cf-130">在電腦的 Outlook 中傳送、查看和回復加密郵件</span><span class="sxs-lookup"><span data-stu-id="d89cf-130">Send, view, and reply to encrypted messages in Outlook for PC</span></span>](https://support.microsoft.com/en-us/office/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980)
- [<span data-ttu-id="d89cf-131">Microsoft 365Essentials 影片： Office 郵件加密</span><span class="sxs-lookup"><span data-stu-id="d89cf-131">Microsoft 365 Essentials Video: Office Message Encryption</span></span>](https://youtu.be/CQR0cG_iEUc)

## <a name="view-these-changes-in-the-audit-log"></a><span data-ttu-id="d89cf-132">在審核記錄中查看這些變更</span><span class="sxs-lookup"><span data-stu-id="d89cf-132">View these changes in the audit log</span></span>

<span data-ttu-id="d89cf-133">Microsoft 365 會審核此活動，並使其可供系統管理員使用。</span><span class="sxs-lookup"><span data-stu-id="d89cf-133">Microsoft 365 audits this activity and makes it available to administrators.</span></span> <span data-ttu-id="d89cf-134">作業是「New-TransportRule」，而安全性 & 規範中心的「審計記錄」搜尋中的範例審核專案片段如下：</span><span class="sxs-lookup"><span data-stu-id="d89cf-134">The operation is 'New-TransportRule' and a snippet of a sample audit entry from the Audit Log Search in Security & Compliance Center is below:</span></span>

```text
*{"CreationTime":"2018-11-28T23:35:01","Id":"a1b2c3d4-daa0-4c4f-a019-03a1234a1b0c","Operation":"New-TransportRule","OrganizationId":"123456-221d-12345 ","RecordType":1,"ResultStatus":"True","UserKey":"Microsoft Operator","UserType":3,"Version":1,"Workload":"Exchange","ClientIP":"123.456.147.68:17584","ObjectId":"","UserId":"Microsoft Operator","ExternalAccess":true,"OrganizationName":"contoso.onmicrosoft.com","OriginatingServer":"CY4PR13MBXXXX (15.20.1382.008)","Parameters": {"Name":"Organization","Value":"123456-221d-12346"{"Name":"ApplyRightsProtectionTemplate","Value":"Encrypt"},{"Name":"Name","Value":"Encrypt outbound sensitive emails (out of box rule)"},{"Name":"MessageContainsDataClassifications"…etc.*
```

## <a name="to-disable-or-customize-the-sensitive-information-types-policy"></a><span data-ttu-id="d89cf-135">停用或自訂敏感資訊類型原則</span><span class="sxs-lookup"><span data-stu-id="d89cf-135">To disable or customize the sensitive information types policy</span></span>

<span data-ttu-id="d89cf-136">建立 Exchange 郵件流程規則之後，您可以在 Exchange 系統管理中心 (EAC) 中，移至 [**郵件流程** 規則] 以 [停用或編輯規則](/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules#enable-or-disable-a-mail-flow-rule)，  >  並停用 [*加密輸出的敏感電子郵件 (現成的規則)*] 規則。</span><span class="sxs-lookup"><span data-stu-id="d89cf-136">Once you've created the Exchange mail flow rule, you can [disable or edit the rule](/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules#enable-or-disable-a-mail-flow-rule) by going to **Mail flow** > **Rules** in the Exchange admin center (EAC) and disable the rule "*Encrypt outbound sensitive emails (out of box rule)*".</span></span>