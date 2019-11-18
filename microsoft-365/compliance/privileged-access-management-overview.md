---
title: Office 365 中的特殊權限存取管理
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
ms.custom: Ent_Solutions
ms.assetid: ''
description: 若要深入了解權限使用本主題存取 Office 365 中的管理
ms.openlocfilehash: 9bc2aab9c9758daf35aa14a41d7997a0bff5764f
ms.sourcegitcommit: 70e920f76526f47fc849df615de4569e0ac2f4be
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/07/2019
ms.locfileid: "38685472"
---
# <a name="privileged-access-management-in-office-365"></a>Office 365 中的特殊權限存取管理

> [!IMPORTANT]
> 本主題涵蓋功能目前僅適用於 Office 365 E5 和進階合規性 Sku 的部署和設定指導。

特殊權限存取管理可讓 Office 365 中的特殊權限的系統管理工作更精細的存取控制。 它可以協助保護您的組織使用現有的特殊權限的系統管理員帳戶具有常設存取權的敏感資料或存取重要的組態設定的外洩。 特殊權限存取管理需要使用者要求剛時間存取權完成提升權限和特殊權限的工作，透過高範圍及時間包住核准工作流程。 這可以讓使用者剛充份-存取執行工作的而不致曝露機密資料或重要的組態設定。 啟用 Office 365 中的特殊權限的存取管理可讓您的組織來操作以零常設權限，並提供一層的防禦常設系統管理存取權的弱點。

整合式的客戶加密箱和特殊權限的存取管理工作流程的快速概觀，請參閱此[客戶加密箱和 Office 365 影片中的特殊權限的存取管理](https://go.microsoft.com/fwlink/?linkid=2066800)。

## <a name="layers-of-protection"></a>保護層級

特殊權限存取管理輔助其他資料與存取權的功能保護 Office 365 安全性架構內。 包括安全性整合及分層方法的一部分的特殊權限的存取管理提供一種安全性模型，將最大化保護敏感資訊和 Office 365 組態設定。 此圖中，與原生 Office 365 資料加密和 Office 365 服務的角色型存取控制安全性模型提供的保護特殊權限的存取管理建置所示。 [Azure AD Privileged Identity Management](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure)搭配使用時，這兩項功能會提供與剛-階段存取在不同範圍的存取控制。

![在 Office 365 中的分層的保護](media/pam-layered-protection.png)

特殊權限存取管理 Office 365 中的定義及在**任務**層級設定範圍，而 Azure AD Privileged Identity Management 能夠執行多個任務套用**角色**層級的保護。 Azure AD 有權限身分識別管理主要允許管理 AD 角色和角色群組的存取，而特殊權限存取 Office 365 中的管理適用於僅在任務層級。

- **啟用特殊權限存取 Office 365 中的管理已使用 Azure AD Privileged Identity Management 時：** 在 Office 365 中新增特殊權限的存取管理提供另一個的細微層級的特殊權限存取 Office 365 的資料保護和稽核功能。

- **啟用 Azure AD Privileged Identity Management 時已經在使用特殊權限存取管理 Office 365 中：** 將 Azure AD Privileged Identity Management 新增至權限存取管理 Office 365 中的可以延伸至主要由使用者角色或身分識別所定義的 Office 365 外部資料的特殊權限的存取。  

## <a name="privileged-access-management-architecture-and-process-flow"></a>特殊權限的存取管理架構和處理程序流程

下列程序流程的每個大綱架構的特殊權限的存取和 Office 365 substrate、 與 Office 365 稽核]，Exchange 管理 runspace 的互動方式。

### <a name="step-1-configure-a-privileged-access-policy"></a>步驟 1： 設定特殊權限的存取原則

當您使用[Microsoft 365 系統管理中心](https://admin.microsoft.com)或 Exchange Management PowerShell 設定特殊權限的存取原則時，並定義原則的特殊權限存取功能程序和 Office 365 substrate 中的原則屬性。 活動已登入 Office 365 安全性與合規性中心。 原則現已啟用，並準備好處理傳入要求核准。

![步驟 1： 建立原則](media/pam-step1-policy-creation.jpg)

### <a name="step-2-access-request"></a>步驟 2： 存取要求

在[Microsoft 365 系統管理中心](https://admin.microsoft.com)或 Exchange Management PowerShell，使用者可以要求存取較高權限或特殊權限的工作。 特殊權限的存取功能會將要求傳送至已設定特殊權限存取原則和記錄的 Office 365 安全性與合規性中心的記錄檔中的活動的處理 Office 365 substrate。

![步驟 2： 存取要求](media/pam-step2-access-request.jpg)

### <a name="step-3-access-approval"></a>步驟 3： 存取權核准

核准要求就會產生和擱置的要求通知電子郵件傳送至核准者。 如果核准，特殊權限的存取要求處理核准為且工作已完成。 如果拒絕時，會封鎖工作並沒有存取權授與給要求者。 要求者要求核准或拒絕透過電子郵件訊息的通知。

![步驟 3： 存取權核准](media/pam-step3-access-approval.jpg)

### <a name="step-4-access-processing"></a>步驟 4： 存取處理

核准要求，會由 Exchange 管理 runspace 處理工作。 核准是針對特殊權限的存取原則檢查，且由 Office 365 substrate 處理。 任務的所有活動會都記錄在 Office 365 安全性與合規性中心。

![步驟 4： 存取處理](media/pam-step4-access-processing.jpg)

## <a name="frequently-asked-questions"></a>常見問題集

### <a name="what-skus-can-use-privileged-access-in-office-365"></a>Sku 可以使用特殊權限存取 Office 365 中？
特殊權限存取管理功能可供客戶使用 Office 365 E5 和進階合規性 Sku。

### <a name="when-will-privileged-access-support-office-365-workloads-beyond-exchange"></a>特殊權限的存取時支援超過 Exchange 的 Office 365 工作負載？
特殊權限存取管理則可在其他 Office 365 工作負載推出。 [Microsoft 365 藍圖](https://www.microsoft.com/microsoft-365/roadmap)如需詳細資訊，請造訪。

### <a name="my-organization-needs-more-than-30-privileged-access-policies-will-this-limit-be-increased"></a>我的組織需要 30 個以上的特殊權限的存取原則，會增加此限制？
是，引發 30 的特殊權限的存取原則，每個 Office 365 組織的目前限制是功能藍圖。

### <a name="do-i-need-to-be-a-global-admin-to-manage-privileged-access-in-office-365"></a>是否需要是全域系統管理員來管理 Office 365 中的特殊權限的存取？
否，您需要 Exchange 角色管理 」 角色指派給管理特殊權限的存取 Office 365 中的帳戶。 如果您不想要設定為獨立的帳戶權限的角色管理角色，全域系統管理員角色此角色包含預設，並可以管理特殊權限的存取。 核准者群組中包含的使用者不需要是全域系統管理員或具有 「 角色管理角色指派進行審核及核准要求。

### <a name="how-is-privileged-access-management-in-office-365-related-to-customer-lockbox"></a>如何為客戶加密箱與相關的 Office 365 中的特殊權限的存取管理？
當 Microsoft 存取資料時， [Customer Lockbox](https://docs.microsoft.com/office365/admin/manage/customer-lockbox-requests)可讓組織的存取控制層級。 特殊權限存取 Office 365 中的管理可讓更精細的存取控制組織內部的 Office 365 特殊權限的所有工作。

## <a name="ready-to-get-started"></a>準備好要開始了嗎？

啟動 [[設定您的組織特殊權限存取管理](privileged-access-management-configuration.md)]。

## <a name="learn-more"></a>深入了解

[互動式指南： 監視和控制管理員 」 工作與特殊權限存取管理](https://content.cloudguides.com/guides/Privileged%20Access%20Management)