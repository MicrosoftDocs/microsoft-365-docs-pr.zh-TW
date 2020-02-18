---
title: 步驟 3：設定增強的 Microsoft 365 安全性
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
description: 了解及設定增強的 Microsoft 365 安全性。
ms.openlocfilehash: eabf0d60f3cfb61b7fffcc688a080ba99f83293e
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42067240"
---
# <a name="step-3-configure-increased-security-for-microsoft-365"></a><span data-ttu-id="1a225-103">步驟 3：設定增強的 Microsoft 365 安全性</span><span class="sxs-lookup"><span data-stu-id="1a225-103">Step 3: Configure increased security for Microsoft 365</span></span>

<span data-ttu-id="1a225-104">*此為必要步驟，且同時適用於 Microsoft 365 企業版 E3 和 E5 版本*</span><span class="sxs-lookup"><span data-stu-id="1a225-104">*This step is required and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![階段 6：資訊保護](../media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="1a225-106">若要確保 Microsoft 365 訂用帳戶及其資料開始使用並保持安全抵禦惡意威脅，請設定下列各項：</span><span class="sxs-lookup"><span data-stu-id="1a225-106">To ensure that your Microsoft 365 subscription and its data start off and remain secure from malicious threats, configure the following:</span></span>

- [<span data-ttu-id="1a225-107">調整威脅管理原則</span><span class="sxs-lookup"><span data-stu-id="1a225-107">Tune threat management policies</span></span>](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security#tune-threat-management-policies-in-the-microsoft-365-security-center)
- [<span data-ttu-id="1a225-108">Exchange Online 的其他全租用戶設定</span><span class="sxs-lookup"><span data-stu-id="1a225-108">Additional Exchange Online tenant-wide settings</span></span>](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security#configure-additional-exchange-online-tenant-wide-settings)
- [<span data-ttu-id="1a225-109">SharePoint 系統管理中心中的全租用戶共用原則</span><span class="sxs-lookup"><span data-stu-id="1a225-109">Tenant-wide sharing policies in the SharePoint admin center</span></span>](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security#configure-tenant-wide-sharing-policies-in-sharepoint-admin-center)
- [<span data-ttu-id="1a225-110">Azure Active Directory (Azure AD) 中的設定</span><span class="sxs-lookup"><span data-stu-id="1a225-110">Settings in Azure Active Directory (Azure AD)</span></span>](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security#configure-settings-in-azure-active-directory)

<span data-ttu-id="1a225-111">設定之後，您可以從以下位置取得安全性狀態的資訊：</span><span class="sxs-lookup"><span data-stu-id="1a225-111">Once configured, you can obtain information about your security status from:</span></span>

- [<span data-ttu-id="1a225-112">Microsoft 安全性中心的儀表板和報告</span><span class="sxs-lookup"><span data-stu-id="1a225-112">Dashboards and reports in the Microsoft security Center</span></span>](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security#view-dashboards-and-reports-in-the-security-and-compliance-centers)
- [<span data-ttu-id="1a225-113">Microsoft 安全分數</span><span class="sxs-lookup"><span data-stu-id="1a225-113">Microsoft Secure Score</span></span>](https://docs.microsoft.com/office365/securitycompliance/microsoft-secure-score)

<span data-ttu-id="1a225-114">另一個安全性功能是 [Office 365 進階威脅防護 (ATP)](https://docs.microsoft.com/office365/securitycompliance/office-365-atp)，可透過以下方式協助組織更安全地進行共用作業：</span><span class="sxs-lookup"><span data-stu-id="1a225-114">An additional security feature is [Office 365 Advanced Threat Protection (ATP)](https://docs.microsoft.com/office365/securitycompliance/office-365-atp), which helps your organization collaborate more securely by:</span></span>

- <span data-ttu-id="1a225-115">保護電子郵件中的[連結](https://docs.microsoft.com/office365/securitycompliance/atp-safe-links)和[附件](https://docs.microsoft.com/office365/securitycompliance/atp-safe-attachments)。</span><span class="sxs-lookup"><span data-stu-id="1a225-115">Protecting [links](https://docs.microsoft.com/office365/securitycompliance/atp-safe-links) and [attachments](https://docs.microsoft.com/office365/securitycompliance/atp-safe-attachments) in email.</span></span> 
- <span data-ttu-id="1a225-116">為 Exchange Online 中的電子郵件以及 [SharePoint Online、商務用 OneDrive、Microsoft Teams 中的檔案](https://docs.microsoft.com/office365/securitycompliance/atp-for-spo-odb-and-teams)，提供詐騙情報和防網路釣魚的功能。</span><span class="sxs-lookup"><span data-stu-id="1a225-116">Providing spoof intelligence and anti-phishing capabilities for email in Exchange Online and [files in SharePoint Online, OneDrive for Business, and Microsoft Teams](https://docs.microsoft.com/office365/securitycompliance/atp-for-spo-odb-and-teams).</span></span> 

<span data-ttu-id="1a225-117">Office 365 ATP 僅在 Microsoft 365 E5 中提供。</span><span class="sxs-lookup"><span data-stu-id="1a225-117">Office 365 ATP is only available with Microsoft 365 E5.</span></span>

|||
|:-------|:-----|
|![Microsoft Cloud 的測試實驗室指南](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="1a225-119">測試實驗室指南：設定增強的 Microsoft 365 安全性</span><span class="sxs-lookup"><span data-stu-id="1a225-119">Test Lab Guide: Configure increased Microsoft 365 security</span></span>](increased-o365-security-microsoft-365-enterprise-dev-test-environment.md) |
|||

<span data-ttu-id="1a225-120">作為過渡期的檢查點，您可以看到與此步驟相對應的[允出準則](infoprotect-exit-criteria.md#crit-infoprotect-step3)。</span><span class="sxs-lookup"><span data-stu-id="1a225-120">As an interim checkpoint, see the [exit criteria](infoprotect-exit-criteria.md#crit-infoprotect-step3) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="1a225-121">下一步</span><span class="sxs-lookup"><span data-stu-id="1a225-121">Next step</span></span>


|||
|:-------|:-----|
|![步驟 4](../media/stepnumbers/Step4.png)|[<span data-ttu-id="1a225-123">設定 Windows 資訊保護</span><span class="sxs-lookup"><span data-stu-id="1a225-123">Configure Windows Information Protection</span></span>](infoprotect-deploy-windows-information-protection.md)|


