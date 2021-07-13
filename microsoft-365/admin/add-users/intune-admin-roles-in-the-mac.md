---
title: 關於 Microsoft 365 系統管理中心的 Intune 系統管理員角色
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
description: 系統管理員角色會與商務功能對應，並提供在系統管理中心執行特定工作的權限。 例如，服務系統管理員向 Microsoft 開啟支援票證。
ms.openlocfilehash: bee35191e7e80313521891a1efc1780489902ae8
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/12/2021
ms.locfileid: "53394324"
---
# <a name="intune-admin-roles-in-the-microsoft-365-admin-center"></a>Microsoft 365 系統管理中心的 Intune 系統管理員角色

Microsoft 365 或 Office 365 訂閱隨附一組系統管理員角色，您可以使用 Microsoft 365 系統管理中心將這些角色指派給貴組織的使用者。各個系統管理員角色會對應常用的商務功能，並提供權限給貴組織內部人員，以在系統管理中心中執行特定工作。。

Microsoft 365 系統管理中心可讓您管理某些 Microsoft Intune 角色。 不過，這些角色是 Intune 系統管理中心中可用角色的子集。 正在尋找 Microsoft Intune 的詳細角色描述嗎？ 請參閱 [使用 Microsoft Intune 的角色型存取控制 (RBAC)](/mem/intune/fundamentals/role-based-access-control)。

如需在 Microsoft 365 系統管理中心指派角色的詳細資訊，請參閱[指派系統管理員角色](assign-admin-roles.md)。

在 Microsoft 365 系統管理中心中，您可以移至 [角色]，然後選取任何角色來開啟其詳細資料窗格。 選取 [權限] 索引標籤，以檢視系統管理員指派該角色具備權限之工作的詳細清單。 選取 [已指派] 或 [指派的系統管理員] 索引標籤來將使用者新增至角色。

## <a name="microsoft-intune-roles-available-in-the-microsoft-365-admin-center"></a>Microsoft 365 系統管理中心提供的 Microsoft Intune 角色

|系統管理員角色     |誰應獲指派此角色？  |
|---------|---------|
|應用程式管理員     |   將應用程式管理員角色指派給管理行動裝置應用程式之應用程式生命週期、設定原則管理的應用程式，以及檢視裝置資訊和組態設定檔的使用者。  |
|技術支援中心操作員     |   將技術支援中心操作員角色指派給指派應用程式和原則給使用者和裝置的使用者。 |
|Intune 角色系統管理員    |   將 Intune 角色系統管理員指派給可指派 Intune 權限給其他系統管理員，並可管理自訂和內建 Intune 角色的使用者。   |
|原則和設定檔管理員     |   將原則和設定檔管理員角色指派給使用者管理合規性原則、組態設定檔和 Apple 註冊。   |
|唯讀操作員     |   將唯讀操作員角色指派給只能檢視使用者、裝置、註冊詳細資料和設定的使用者。   |
|學校系統管理員     |   將學校系統管理員角色指派給使用者，以取得在 Intune 教育版中管理 Windows 10 和 iOS 裝置、應用程式和設定的完整存取權。   |

## <a name="delegated-administration-for-microsoft-partners"></a>Microsoft 合作夥伴的委派系統管理

如果您正與 Microsoft 合作夥伴合作，您可以指派系統管理員角色給他們。他們也可以反過來指派系統管理員角色給您公司 (或他們公司) 中的使用者。例如，如果他們正在設定並為您管理線上組織，您可能會想要他們這樣做。
  
合作夥伴可以指派以下角色： 
  
- 完全管理：擁有等同於全域系統管理員的權限，但透過合作夥伴中心管理多重要素驗證除外。

- 有限系統管理，所具權限等同於服務台系統管理員。

在合作夥伴可以將這些角色指派給使用者之前，您必須先將該合作夥伴新增為您帳戶的委派系統管理員。 此程序是由獲授權的合作夥伴初始化。 合作夥伴會傳送電子郵件給您，詢問您是否想要授與其權限，以做為委派的系統管理員。如需指示，請參閱[授權或移除合作夥伴關係](../misc/add-partner.md)。
  
## <a name="related-content"></a>相關內容

[關於 Microsoft 365 系統管理員角色](about-admin-roles.md) (文章)\
[指派系統管理員角色](assign-admin-roles.md) (文章)\
[Microsoft 365 系統管理中心的活動報告](../activity-reports/activity-reports.md) (文章)