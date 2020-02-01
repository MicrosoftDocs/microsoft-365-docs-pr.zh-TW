---
title: 使用 Office 365 郵件加密為貴組織建立敏感性資訊類型原則
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
description: 摘要： Office 365 敏感資訊類型的郵件加密原則。
ms.openlocfilehash: a3767fb0f9fe5e565c49db4f9da94d75a3cee8a7
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/29/2020
ms.locfileid: "41601790"
---
# <a name="create-a-sensitive-information-type-policy-for-your-organization-using-office-365-message-encryption"></a><span data-ttu-id="67b0d-103">使用 Office 365 郵件加密為貴組織建立敏感性資訊類型原則</span><span class="sxs-lookup"><span data-stu-id="67b0d-103">Create a sensitive information type policy for your organization using Office 365 Message Encryption</span></span>

<span data-ttu-id="67b0d-104">您可以使用 [Exchange 郵件流程規則] 或 [Office 365 資料外洩防護 (DLP) 來建立敏感資訊類型原則與 Office 365 郵件加密。</span><span class="sxs-lookup"><span data-stu-id="67b0d-104">You can use either Exchange mail flow rules or Office 365 Data Loss Prevention (DLP) to create a sensitive information type policy with Office 365 Message Encryption.</span></span> <span data-ttu-id="67b0d-105">若要建立 Exchange 郵件流程規則，您可以使用 Exchange 系統管理中心 (EAC) 或 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="67b0d-105">To create an Exchange mail flow rule, you can use either the Exchange admin center (EAC) or PowerShell.</span></span>

## <a name="to-create-the-policy-by-using-mail-flow-rules-in-the-eac"></a><span data-ttu-id="67b0d-106">若要建立原則在 EAC 中使用郵件流程規則</span><span class="sxs-lookup"><span data-stu-id="67b0d-106">To create the policy by using mail flow rules in the EAC</span></span>

<span data-ttu-id="67b0d-107">登入 Exchange 系統管理中心 (EAC)，並移至 [**郵件流程** > **規則**。</span><span class="sxs-lookup"><span data-stu-id="67b0d-107">Sign in to the Exchange admin center (EAC) and go to **Mail flow** > **Rules**.</span></span> <span data-ttu-id="67b0d-108">在 [規則] 頁面上建立適用於 Office 365 郵件加密的規則。</span><span class="sxs-lookup"><span data-stu-id="67b0d-108">On the Rules page, create a rule that applies Office 365 Message Encryption.</span></span> <span data-ttu-id="67b0d-109">您可以建立規則，例如目前狀態的特定關鍵字或郵件或附件中的敏感資訊類型的條件為基礎。</span><span class="sxs-lookup"><span data-stu-id="67b0d-109">You can create a rule based on conditions such as the presence of certain keywords or sensitive information types in the message or attachment.</span></span>

### <a name="to-create-the-policy-by-using-mail-flow-rules-in-powershell"></a><span data-ttu-id="67b0d-110">若要建立原則藉由使用 PowerShell 中的郵件流程規則</span><span class="sxs-lookup"><span data-stu-id="67b0d-110">To create the policy by using mail flow rules in PowerShell</span></span>

<span data-ttu-id="67b0d-111">使用公司或學校帳戶具有您 Office 365 組織中的全域系統管理員權限啟動 Windows PowerShell 工作階段，連線至 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="67b0d-111">Use a work or school account that has global administrator permissions in your Office 365 organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="67b0d-112">如需詳細指示，請參閱[連線到 Exchange Online PowerShell](https://aka.ms/exopowershell)。</span><span class="sxs-lookup"><span data-stu-id="67b0d-112">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span> <span data-ttu-id="67b0d-113">使用 Set-irmconfiguration 和 New-transportrule 指令程式來建立原則。</span><span class="sxs-lookup"><span data-stu-id="67b0d-113">Use the Set-IRMConfiguration and New-TransportRule cmdlets to create the policy.</span></span>

## <a name="example-mail-flow-rule-created-with-powershell"></a><span data-ttu-id="67b0d-114">使用 PowerShell 建立範例郵件流程規則</span><span class="sxs-lookup"><span data-stu-id="67b0d-114">Example mail flow rule created with PowerShell</span></span>

<span data-ttu-id="67b0d-115">若要建立 Exchange 郵件流程規則，會自動加密傳送與組織外部的電子郵件的 PowerShell 中執行下列命令*僅加密*如果電子郵件或其附件包含下列的敏感資訊類型的原則：</span><span class="sxs-lookup"><span data-stu-id="67b0d-115">Run the following commands in PowerShell to create an Exchange mail flow rule that automatically encrypts emails sent outside your organization with the *Encrypt-Only* policy if the emails or their attachments contain the following sensitive information types:</span></span>

- <span data-ttu-id="67b0d-116">阿拉巴馬州銀行路由號碼</span><span class="sxs-lookup"><span data-stu-id="67b0d-116">ABA routing number</span></span>
- <span data-ttu-id="67b0d-117">信用卡號碼</span><span class="sxs-lookup"><span data-stu-id="67b0d-117">Credit card Number</span></span>
- <span data-ttu-id="67b0d-118">藥物執法機構 (DEA) 編號</span><span class="sxs-lookup"><span data-stu-id="67b0d-118">Drug Enforcement Agency (DEA) number</span></span>
- <span data-ttu-id="67b0d-119">美國 / 英國</span><span class="sxs-lookup"><span data-stu-id="67b0d-119">U.S. / U.K.</span></span> <span data-ttu-id="67b0d-120">護照號碼</span><span class="sxs-lookup"><span data-stu-id="67b0d-120">passport number</span></span>
- <span data-ttu-id="67b0d-121">美國銀行帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="67b0d-121">U.S. bank account number</span></span>
- <span data-ttu-id="67b0d-122">美國個別 Taxpayer 識別號碼 (ITIN)</span><span class="sxs-lookup"><span data-stu-id="67b0d-122">U.S. Individual Taxpayer Identification Number (ITIN)</span></span>
- <span data-ttu-id="67b0d-123">美國社會安全號碼 (SSN)</span><span class="sxs-lookup"><span data-stu-id="67b0d-123">U.S. Social Security Number (SSN)</span></span>

```powershell
Set-IRMConfiguration -DecryptAttachmentForEncryptOnly $true
New-TransportRule -Name "Encrypt outbound sensitive emails (out of box rule)" -SentToScope  NotInOrganization  -ApplyRightsProtectionTemplate "Encrypt" -MessageContainsDataClassifications @(@{Name="ABA Routing Number"; minCount="1"},@{Name="Credit Card Number"; minCount="1"},@{Name="Drug Enforcement Agency (DEA) Number"; minCount="1"},@{Name="U.S. / U.K. Passport Number"; minCount="1"},@{Name="U.S. Bank Account Number"; minCount="1"},@{Name="U.S. Individual Taxpayer Identification Number (ITIN)"; minCount="1"},@{Name="U.S. Social Security Number (SSN)"; minCount="1"}) -SenderNotificationType "NotifyOnly"
```

<span data-ttu-id="67b0d-124">如需詳細資訊，請參閱[Set-irmconfiguration](https://docs.microsoft.com/powershell/module/exchange/encryption-and-certificates/set-irmconfiguration?view=exchange-ps)和[New-transportrule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/New-TransportRule?view=exchange-ps)。</span><span class="sxs-lookup"><span data-stu-id="67b0d-124">For more information, see [Set-IRMConfiguration](https://docs.microsoft.com/powershell/module/exchange/encryption-and-certificates/set-irmconfiguration?view=exchange-ps) and [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/New-TransportRule?view=exchange-ps).</span></span>

## <a name="how-recipients-access-attachments"></a><span data-ttu-id="67b0d-125">收件者存取附件的方式</span><span class="sxs-lookup"><span data-stu-id="67b0d-125">How recipients access attachments</span></span>

<span data-ttu-id="67b0d-126">Office 365 加密郵件之後，收件者有不受限制存取附件當他們存取，並開啟其加密的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="67b0d-126">After Office 365 encrypts a message, recipients have unrestricted access to attachments when they access and open their encrypted email.</span></span>

## <a name="to-prepare-for-this-change"></a><span data-ttu-id="67b0d-127">若要準備進行這項變更</span><span class="sxs-lookup"><span data-stu-id="67b0d-127">To prepare for this change</span></span>

<span data-ttu-id="67b0d-128">若要更新任何適用的使用者文件和訓練資料準備，這項變更您組織中的人員。</span><span class="sxs-lookup"><span data-stu-id="67b0d-128">You may want to update any applicable end-user documentation and training materials to prepare people in your organization for this change.</span></span> <span data-ttu-id="67b0d-129">視您的使用者與共用這些 Office 365 郵件加密的資源：</span><span class="sxs-lookup"><span data-stu-id="67b0d-129">Share these Office 365 Message Encryption resources with your users as appropriate:</span></span>

- [<span data-ttu-id="67b0d-130">傳送、 檢視和回覆加密郵件的電腦版 Outlook 中</span><span class="sxs-lookup"><span data-stu-id="67b0d-130">Send, view, and reply to encrypted messages in Outlook for PC</span></span>](https://support.office.com/article/eaa43495-9bbb-4fca-922a-df90dee51980)
- [<span data-ttu-id="67b0d-131">Office 365 基本版影片： Office 郵件加密</span><span class="sxs-lookup"><span data-stu-id="67b0d-131">Office 365 Essentials Video: Office Message Encryption</span></span>](https://youtu.be/CQR0cG_iEUc)

## <a name="view-these-changes-in-the-audit-log"></a><span data-ttu-id="67b0d-132">稽核記錄中檢視這些變更</span><span class="sxs-lookup"><span data-stu-id="67b0d-132">View these changes in the Audit log</span></span>

<span data-ttu-id="67b0d-133">Office 365 稽核這項活動，並可供 Office 365 系統管理員。</span><span class="sxs-lookup"><span data-stu-id="67b0d-133">Office 365 audits this activity and makes it available to Office 365 administrators.</span></span> <span data-ttu-id="67b0d-134">這項操作是 'New-transportrule' 和程式碼片段的稽核記錄搜尋的安全性 & 合規性中心中來自範例稽核項目是下方：</span><span class="sxs-lookup"><span data-stu-id="67b0d-134">The operation is ‘New-TransportRule’ and a snippet of a sample audit entry from the Audit Log Search in Security & Compliance Center is below:</span></span>

```text
*{"CreationTime":"2018-11-28T23:35:01","Id":"a1b2c3d4-daa0-4c4f-a019-03a1234a1b0c","Operation":"New-TransportRule","OrganizationId":"123456-221d-12345 ","RecordType":1,"ResultStatus":"True","UserKey":"Microsoft Operator","UserType":3,"Version":1,"Workload":"Exchange","ClientIP":"123.456.147.68:17584","ObjectId":"","UserId":"Microsoft Operator","ExternalAccess":true,"OrganizationName":"contoso.onmicrosoft.com","OriginatingServer":"CY4PR13MBXXXX (15.20.1382.008)","Parameters": {"Name":"Organization","Value":"123456-221d-12346"{"Name":"ApplyRightsProtectionTemplate","Value":"Encrypt"},{"Name":"Name","Value":"Encrypt outbound sensitive emails (out of box rule)"},{"Name":"MessageContainsDataClassifications”…etc.*
```

## <a name="to-disable-or-customize-the-sensitive-information-types-policy"></a><span data-ttu-id="67b0d-135">若要停用或自訂的敏感資訊類型原則</span><span class="sxs-lookup"><span data-stu-id="67b0d-135">To disable or customize the sensitive information types policy</span></span>

<span data-ttu-id="67b0d-136">一旦您已經建立 Exchange 郵件流程規則，您可以[停用或編輯規則](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules#enable-or-disable-a-mail-flow-rule)移至 [**郵件流程** > **規則**在 Exchange 系統管理中心 (EAC) 和停用的規則 「*加密外寄機密電子郵件 （超出方塊規則）*」。</span><span class="sxs-lookup"><span data-stu-id="67b0d-136">Once you've created the Exchange mail flow rule, you can [disable or edit the rule](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules#enable-or-disable-a-mail-flow-rule) by going to **Mail flow** > **Rules** in the Exchange admin center (EAC) and disable the rule “*Encrypt outbound sensitive emails (out of box rule)*”.</span></span>
