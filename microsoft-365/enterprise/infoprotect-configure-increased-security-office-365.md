---
title: 步驟 3：設定增強的 Microsoft 365 安全性
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/10/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: 了解及設定增強的 Microsoft 365 安全性。
ms.openlocfilehash: fcf023960679cf624f3ea7421ab92b1a450d2524
ms.sourcegitcommit: 3b2d3e2b38c4860db977e73dda119a465c669fa4
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/28/2019
ms.locfileid: "33400027"
---
# <a name="step-3-configure-increased-security-for-microsoft-365"></a><span data-ttu-id="3082f-103">步驟 3：設定增強的 Microsoft 365 安全性</span><span class="sxs-lookup"><span data-stu-id="3082f-103">Step 3: Configure increased security for Microsoft 365</span></span>

<span data-ttu-id="3082f-104">*這是必要步驟，且同時適用於 Microsoft 365 企業版 E3 和 E5 版本*</span><span class="sxs-lookup"><span data-stu-id="3082f-104">*This step is required and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="3082f-105">若要確保 Microsoft 365 訂用帳戶及其資料開始使用並保持安全抵禦惡意威脅，請設定下列各項：</span><span class="sxs-lookup"><span data-stu-id="3082f-105">To ensure that your Microsoft 365 subscription and its data start off and remain secure from malicious threats, configure the following:</span></span>

- [<span data-ttu-id="3082f-106">調整威脅管理原則</span><span class="sxs-lookup"><span data-stu-id="3082f-106">Tune threat management policies</span></span>](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security#tune-threat-management-policies-in-the-office-365-security--compliance-center)
- [<span data-ttu-id="3082f-107">Exchange Online 的其他全租用戶設定</span><span class="sxs-lookup"><span data-stu-id="3082f-107">Additional Exchange Online tenant-wide settings</span></span>](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security#configure-additional-exchange-online-tenant-wide-settings)
- [<span data-ttu-id="3082f-108">SharePoint 系統管理中心中的全租用戶共用原則</span><span class="sxs-lookup"><span data-stu-id="3082f-108">Tenant-wide sharing policies in the SharePoint admin center</span></span>](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security#configure-tenant-wide-sharing-policies-in-sharepoint-admin-center)
- [<span data-ttu-id="3082f-109">Azure Active Directory (Azure AD) 中的設定</span><span class="sxs-lookup"><span data-stu-id="3082f-109">Settings in Azure Active Directory (Azure AD)</span></span>](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security#configure-settings-in-azure-active-directory)

<span data-ttu-id="3082f-110">設定之後，您可以從以下位置取得安全性狀態的資訊：</span><span class="sxs-lookup"><span data-stu-id="3082f-110">Once configured, you can obtain information about your security status from:</span></span>

- [<span data-ttu-id="3082f-111">Microsoft 安全性中心的儀表板和報告</span><span class="sxs-lookup"><span data-stu-id="3082f-111">Dashboards and reports in the Microsoft security Center</span></span>](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security#view-dashboards-and-reports-in-the-security--compliance-center)
- [<span data-ttu-id="3082f-112">Microsoft 安全分數</span><span class="sxs-lookup"><span data-stu-id="3082f-112">Microsoft Secure Score</span></span>](https://docs.microsoft.com/office365/securitycompliance/microsoft-secure-score)

<span data-ttu-id="3082f-113">另一個安全性功能是 [Office 365 進階威脅防護 (ATP)](https://docs.microsoft.com/office365/securitycompliance/office-365-atp)，可透過以下方式協助組織更安全地進行共用作業：</span><span class="sxs-lookup"><span data-stu-id="3082f-113">An additional security feature is [Office 365 Advanced Threat Protection (ATP)](https://docs.microsoft.com/office365/securitycompliance/office-365-atp), which helps your organization collaborate more securely by:</span></span>

- <span data-ttu-id="3082f-114">保護電子郵件中的[連結](https://docs.microsoft.com/office365/securitycompliance/atp-safe-links)和[附件](https://docs.microsoft.com/office365/securitycompliance/atp-safe-attachments)。</span><span class="sxs-lookup"><span data-stu-id="3082f-114">Protecting [links](https://docs.microsoft.com/office365/securitycompliance/atp-safe-links) and [attachments](https://docs.microsoft.com/office365/securitycompliance/atp-safe-attachments) in email.</span></span> 
- <span data-ttu-id="3082f-115">為 Exchange Online 中的電子郵件以及 [SharePoint Online、商務用 OneDrive、Microsoft Teams 中的檔案](https://docs.microsoft.com/office365/securitycompliance/atp-for-spo-odb-and-teams)，提供詐騙情報和防網路釣魚的功能。</span><span class="sxs-lookup"><span data-stu-id="3082f-115">Providing spoof intelligence and anti-phishing capabilities for email in Exchange Online and [files in SharePoint Online, OneDrive for Business, and Microsoft Teams](https://docs.microsoft.com/office365/securitycompliance/atp-for-spo-odb-and-teams).</span></span> 

<span data-ttu-id="3082f-116">Office 365 ATP 僅在 Microsoft 365 企業版 E5 中提供。</span><span class="sxs-lookup"><span data-stu-id="3082f-116">Office 365 ATP is only available with Microsoft 365 Enterprise E5.</span></span>

|||
|:-------|:-----|
|![Microsoft Cloud 的測試實驗室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="3082f-118">測試實驗室指南：設定增強的 Microsoft 365 安全性</span><span class="sxs-lookup"><span data-stu-id="3082f-118">Test Lab Guide: Configure increased Microsoft 365 security</span></span>](increased-o365-security-microsoft-365-enterprise-dev-test-environment.md) |
|||

<span data-ttu-id="3082f-119">作為過渡期的檢查點，您可以看到與此步驟相對應的[允出準則](infoprotect-exit-criteria.md#crit-infoprotect-step3)。</span><span class="sxs-lookup"><span data-stu-id="3082f-119">As an interim checkpoint, see the [exit criteria](infoprotect-exit-criteria.md#crit-infoprotect-step3) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="3082f-120">下一步</span><span class="sxs-lookup"><span data-stu-id="3082f-120">Next step</span></span>


|||
|:-------|:-----|
|![](./media/stepnumbers/Step4.png)|<span data-ttu-id="3082f-121">[設定 Windows 資訊保護](infoprotect-deploy-windows-information-protection.md)</span><span class="sxs-lookup"><span data-stu-id="3082f-121">[](infoprotect-deploy-windows-information-protection.md)Configure Azure Information Protection</span></span>|


