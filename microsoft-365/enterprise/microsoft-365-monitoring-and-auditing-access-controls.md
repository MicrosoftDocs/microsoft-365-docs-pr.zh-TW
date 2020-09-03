---
title: Microsoft 365 監控和審計存取控制
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
f1.keywords:
- NOCSH
description: 摘要： Microsoft 365 內可用之監控和審核存取控制的摘要。
ms.openlocfilehash: ba79ba2263940e5677ada412f467a429e584b8ff
ms.sourcegitcommit: c029834c8a914b4e072de847fc4c3a3dde7790c5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/02/2020
ms.locfileid: "47332289"
---
# <a name="monitoring-and-auditing-access-controls-in-microsoft-365"></a><span data-ttu-id="b4f68-103">在 Microsoft 365 中監控和審計存取控制</span><span class="sxs-lookup"><span data-stu-id="b4f68-103">Monitoring and Auditing Access Controls in Microsoft 365</span></span>

<span data-ttu-id="b4f68-104">Microsoft 對 Microsoft 365 內所有的委派、許可權和作業執行大量監控和審核。</span><span class="sxs-lookup"><span data-stu-id="b4f68-104">Microsoft performs extensive monitoring and auditing of all delegation, privileges, and operations that occur within Microsoft 365.</span></span> <span data-ttu-id="b4f68-105">Microsoft 365 存取控制是以最低許可權原則為基礎的自動化程式，且包含資料存取控制和審核：</span><span class="sxs-lookup"><span data-stu-id="b4f68-105">Microsoft 365 access control is an automated process built on the principle of least privilege and incorporating data access controls and audits:</span></span>

- <span data-ttu-id="b4f68-106">所有允許的存取可對唯一的使用者進行追蹤。</span><span class="sxs-lookup"><span data-stu-id="b4f68-106">All permitted access is traceable to a unique user.</span></span> <span data-ttu-id="b4f68-107">系統管理員負責處理客戶內容。</span><span class="sxs-lookup"><span data-stu-id="b4f68-107">Administrators are accountable for their handling of customer content.</span></span>
- <span data-ttu-id="b4f68-108">會捕獲存取控制要求、核准和管理作業記錄檔，以進行安全性和惡意事件的分析。</span><span class="sxs-lookup"><span data-stu-id="b4f68-108">Access control requests, approvals, and administrative operations logs are captured for analysis of security and malicious events.</span></span>
- <span data-ttu-id="b4f68-109">存取層級會以接近即時的安全性群組成員資格來檢查，以確保只有具備授權的業務理由和符合資格需求的使用者才可以存取系統。</span><span class="sxs-lookup"><span data-stu-id="b4f68-109">Access levels are reviewed in near real-time based on security group membership to ensure that only users who have authorized business justifications and meet the eligibility requirements have access to the systems.</span></span>
- <span data-ttu-id="b4f68-110">Microsoft 365、其存取控制及支援服務（包括 Azure Active Directory 和實體資料中心）都會定期以獨立協力廠商進行審核，以相容 [ISO/IEC 27001](https://www.microsoft.com/TrustCenter/Compliance/iso-iec-27001)、 [ISO/IEC 27018](https://www.microsoft.com/TrustCenter/Compliance/iso-iec-27018)、 [SOC](https://www.microsoft.com/TrustCenter/Compliance/SOC)、 [FedRAMP](https://www.microsoft.com/TrustCenter/Compliance/FedRAMP)和其他 [標準](https://www.microsoft.com/TrustCenter/Compliance?service=Office#Icons)。</span><span class="sxs-lookup"><span data-stu-id="b4f68-110">Microsoft 365, its access controls, and supporting services, including Azure Active Directory and physical datacenters, are regularly audited by independent third-parties for compliance with [ISO/IEC 27001](https://www.microsoft.com/TrustCenter/Compliance/iso-iec-27001), [ISO/IEC 27018](https://www.microsoft.com/TrustCenter/Compliance/iso-iec-27018), [SOC](https://www.microsoft.com/TrustCenter/Compliance/SOC), [FedRAMP](https://www.microsoft.com/TrustCenter/Compliance/FedRAMP), and other [standards](https://www.microsoft.com/TrustCenter/Compliance?service=Office#Icons).</span></span>
- <span data-ttu-id="b4f68-111">Microsoft 365 工程師必須進行年度安全性訓練、查看更高的 access 最佳程式，以及認可 Microsoft 的安全性和隱私權原則，以維護服務的權利。</span><span class="sxs-lookup"><span data-stu-id="b4f68-111">Microsoft 365 engineers must take yearly security training, review elevated access best procedures, and acknowledge Microsoft's security and privacy policies to maintain entitlements to the service.</span></span>

<span data-ttu-id="b4f68-112">偵測到可疑活動時（例如短期間內的多個失敗的登入），會觸發自動提醒。</span><span class="sxs-lookup"><span data-stu-id="b4f68-112">Automated alerts trigger when suspicious activity is detected, such as multiple failed logins within a short period.</span></span> <span data-ttu-id="b4f68-113">Microsoft 365 安全性回應小組使用電腦學習和大量資料分析，以查看和分析活動、尋找不規則的存取模式，以及主動回應反常和違法的活動。</span><span class="sxs-lookup"><span data-stu-id="b4f68-113">The Microsoft 365 Security Response team uses machine learning and big data analysis to review and analyze activity, look for irregular access patterns, and proactively respond to anomalous and illicit activities.</span></span> <span data-ttu-id="b4f68-114">Microsoft 也採用一支專門的滲透測試小組，並在週期性的紅色小組和藍色小組練習中尋找，以找出服務中的安全性和存取控制問題。</span><span class="sxs-lookup"><span data-stu-id="b4f68-114">Microsoft also employs a dedicated team of penetration testers and engages in periodic Red Team and Blue Team exercises to find security and access control issues in the service.</span></span> <span data-ttu-id="b4f68-115">客戶可以使用「審核報告」和 Microsoft 365 提供的管理活動 API，來驗證存取控制系統的效能。</span><span class="sxs-lookup"><span data-stu-id="b4f68-115">Customers can verify the effectiveness of access control systems by using audit reports and the management activity API provided by Microsoft 365.</span></span>

<span data-ttu-id="b4f68-116">如需詳細資訊，請參閱 Microsoft 365 中的 [Office 365 管理活動 API 參考](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference) 和 [審核與報告](microsoft-365-auditing-and-reporting-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="b4f68-116">For more information, see [Office 365 Management Activity API reference](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference) and [Auditing and reporting in Microsoft 365](microsoft-365-auditing-and-reporting-overview.md).</span></span>
