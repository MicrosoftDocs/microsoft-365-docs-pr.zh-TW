---
title: 步驟 3：設定增強的 Office 365 安全性
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/16/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: 了解並設定增強的 Office 365 安全性，包括 Office 365 ATP。
ms.openlocfilehash: 0344778b8d8f9940dc6267a39eac2f4cfb261f9a
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/28/2018
ms.locfileid: "26866645"
---
# <a name="step-3-configure-increased-security-for-office-365"></a><span data-ttu-id="b7f99-103">步驟 3：設定增強的 Office 365 安全性</span><span class="sxs-lookup"><span data-stu-id="b7f99-103">Step 3: Configure increased security for Office 365</span></span>

<span data-ttu-id="b7f99-104">*此為必要步驟，且同時適用於 Microsoft 365 企業版 E3 和 E5 版本*</span><span class="sxs-lookup"><span data-stu-id="b7f99-104">*This step is required and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="b7f99-105">若要確保 Office 365 訂用帳戶及其資料開始使用並保持安全抵禦惡意威脅，請參閱[設定 Office 365 租用戶的增強安全性](https://support.office.com/article/Configure-your-Office-365-tenant-for-increased-security-8d274fe3-db51-4107-ba64-865e7155b355)，並設定下列的額外安全性：</span><span class="sxs-lookup"><span data-stu-id="b7f99-105">To ensure that your Office 365 subscription and its data start off and remain secure from malicious threats, see [Configure your Office 365 tenant for increased security](https://support.office.com/article/Configure-your-Office-365-tenant-for-increased-security-8d274fe3-db51-4107-ba64-865e7155b355) and configure the following additional security:</span></span>

- <span data-ttu-id="b7f99-106">Office 365 安全與規範中心中的威脅管理原則</span><span class="sxs-lookup"><span data-stu-id="b7f99-106">Threat management policies in the Office 365 Security & Compliance Center</span></span>
- <span data-ttu-id="b7f99-107">Exchange Online 的其他全租用戶設定</span><span class="sxs-lookup"><span data-stu-id="b7f99-107">Additional Exchange Online tenant-wide settings</span></span>
- <span data-ttu-id="b7f99-108">SharePoint 系統管理中心中的全租用戶共用原則</span><span class="sxs-lookup"><span data-stu-id="b7f99-108">Tenant-wide sharing policies in the SharePoint admin center</span></span>
- <span data-ttu-id="b7f99-109">Azure Active Directory 中的設定</span><span class="sxs-lookup"><span data-stu-id="b7f99-109">Settings in Azure Active Directory</span></span>

<span data-ttu-id="b7f99-110">設定之後，您可以從以下位置取得安全性狀態的資訊：</span><span class="sxs-lookup"><span data-stu-id="b7f99-110">Once configured, you can obtain information about your security status from:</span></span>

- <span data-ttu-id="b7f99-111">安全與規範中心中的儀表板和報告</span><span class="sxs-lookup"><span data-stu-id="b7f99-111">Dashboards and reports in the Security & Compliance Center</span></span>
- [<span data-ttu-id="b7f99-112">Office 365 安全分數</span><span class="sxs-lookup"><span data-stu-id="b7f99-112">Office 365 Secure Score</span></span>](https://securescore.office.com/)
 
  <span data-ttu-id="b7f99-113">若要存取此頁面，您必須以 Office 365 租用戶系統管理員的身分登入。</span><span class="sxs-lookup"><span data-stu-id="b7f99-113">To access this page, you must be signed in as an Office 365 tenant admin.</span></span>

<span data-ttu-id="b7f99-114">您也可以使用 Cloud App Security 或 Office 365 雲端 App 安全性來監視安全性事件並採取行動。如需詳細資訊，請參閱 [Office 365 Cloud App Security 概觀](https://support.office.com/article/Overview-of-Office-365-Cloud-App-Security-81f0ee9a-9645-45ab-ba56-de9cbccab475)。</span><span class="sxs-lookup"><span data-stu-id="b7f99-114">You can also use Cloud App Security or Office 365 Cloud App Security to monitor for security events and act. For more information, see [Overview of Office 365 Cloud App Security](https://support.office.com/article/Overview-of-Office-365-Cloud-App-Security-81f0ee9a-9645-45ab-ba56-de9cbccab475).</span></span>

<span data-ttu-id="b7f99-115">另一個安全性功能是 Office 365 進階威脅防護 (ATP)，可透過以下方式協助組織更安全地進行共用作業：</span><span class="sxs-lookup"><span data-stu-id="b7f99-115">An additional security feature is Office 365 Advanced Threat Protection (ATP), which helps your organization collaborate more securely by:</span></span>

- <span data-ttu-id="b7f99-116">電子郵件中的保護連結和附件。</span><span class="sxs-lookup"><span data-stu-id="b7f99-116">Protecting links and attachments in email.</span></span> 
- <span data-ttu-id="b7f99-117">為 Exchange Online 中的電子郵件以及 SharePoint Online、商務用 OneDrive、Microsoft Teams 中的檔案，提供詐騙情報和防網路釣魚的功能。</span><span class="sxs-lookup"><span data-stu-id="b7f99-117">Providing spoof intelligence and anti-phishing capabilities for email in Exchange Online and files in SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span> 

>[!Note]
><span data-ttu-id="b7f99-p101">Microsoft 365 企業版 E5 內含 Office 365 ATP。如果您有 Microsoft 365 企業版 E3，可以單獨購買 ATP 授權。</span><span class="sxs-lookup"><span data-stu-id="b7f99-p101">Office 365 ATP is included with Microsoft 365 Enterprise E5. If you have Microsoft 365 Enterprise E3, you can purchase individual licenses for ATP.</span></span>
>

<span data-ttu-id="b7f99-120">若要啟用 Office 365 ATP，請參閱[開啟](https://support.office.com/article/Office-365-ATP-for-SharePoint-OneDrive-and-Microsoft-Teams-26261670-db33-4c53-b125-af0662c34607#turniton)。</span><span class="sxs-lookup"><span data-stu-id="b7f99-120">To enable Office 365 ATP, see [Turn it on](https://support.office.com/article/Office-365-ATP-for-SharePoint-OneDrive-and-Microsoft-Teams-26261670-db33-4c53-b125-af0662c34607#turniton).</span></span>

<span data-ttu-id="b7f99-121">如需詳細資訊，請參閱 [Office 365 ATP SharePoint、OneDrive 及 Microsoft Teams](https://support.office.com/article/Office-365-ATP-for-SharePoint-OneDrive-and-Microsoft-Teams-26261670-db33-4c53-b125-af0662c34607)。</span><span class="sxs-lookup"><span data-stu-id="b7f99-121">For more information, see [Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams](https://support.office.com/article/Office-365-ATP-for-SharePoint-OneDrive-and-Microsoft-Teams-26261670-db33-4c53-b125-af0662c34607).</span></span>


|||
|:-------|:-----|
|![Microsoft Cloud 的測試實驗室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="b7f99-123">測試實驗室指南：設定增強的 Office 365 安全性</span><span class="sxs-lookup"><span data-stu-id="b7f99-123">Test Lab Guide: Configure increased Office 365 security</span></span>](increased-o365-security-microsoft-365-enterprise-dev-test-environment.md) |
|||

<span data-ttu-id="b7f99-124">作為過渡期的檢查點，您可以看到與此步驟相對應的[允出準則](infoprotect-exit-criteria.md#crit-infoprotect-step4)。</span><span class="sxs-lookup"><span data-stu-id="b7f99-124">As an interim checkpoint, see the [exit criteria](infoprotect-exit-criteria.md#crit-infoprotect-step4) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="b7f99-125">下一步</span><span class="sxs-lookup"><span data-stu-id="b7f99-125">Next step</span></span>


|||
|:-------|:-----|
|![](./media/stepnumbers/Step4.png)|[<span data-ttu-id="b7f99-126">設定特殊權限存取管理</span><span class="sxs-lookup"><span data-stu-id="b7f99-126">Configure privileged access management</span></span>](infoprotect-configure-privileged-access-management.md)|


