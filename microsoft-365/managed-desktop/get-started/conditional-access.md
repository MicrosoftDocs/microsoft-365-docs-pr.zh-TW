---
title: 在登記後調整設定
description: 如何排除某些 Microsoft 帳戶
keywords: Microsoft 受管理的電腦, Microsoft 365, 服務, 文件
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 76a73372cc7517c3241390e58c28b0b02bffd664
ms.sourcegitcommit: 4cbb4ec26f022f5f9d9481f55a8a6ee8406968d2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/01/2020
ms.locfileid: "49527694"
---
# <a name="adjust-settings-after-enrollment"></a>在登記後調整設定

在 Microsoft Managed Desktop 中完成註冊後，您必須調整某些 Microsoft Intune 和 Azure Active Directory (Azure AD) 設定，以允許管理及維護安全性。 設定下列設定，以排除包含 Microsoft 受管理桌面裝置和使用者的 Azure AD 群組。 如需排除群組的步驟，請參閱 [條件式存取：使用者和群組](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups#exclude-users)。

## <a name="microsoft-intune-settings"></a>Microsoft Intune 設定

- Autopilot 部署設定檔：排除 **新式的工作裝置-所有**  Azure AD 群組。 如需步驟，請參閱 [使用 Windows Autopilot 在 Intune 中註冊 Windows 裝置](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot)。
- 條件式存取原則：排除 **新式的 Workplace Service 帳戶** Azure AD 群組。 如需步驟，請參閱 [條件式存取：使用者和群組](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups)。
- 多重要素驗證：請確定任何需要多重要素驗證的條件式存取原則排除 **新式的 Workplace Service 帳戶** Azure AD 群組。 如需詳細資訊，請參閱 [條件式存取原則](../get-ready/readiness-assessment-fix.md#conditional-access-policies) 和 [條件式存取：針對所有使用者需要 MFA](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)。
- 安全性基準：排除 **新式的工作區裝置-所有**  Azure AD 群組。 如需步驟，請參閱 [使用安全性基準在 Intune 中設定 Windows 10 裝置](https://docs.microsoft.com/mem/intune/protect/security-baselines)。
- Windows 10 更新環：排除 **現代的工作場所裝置-所有**  Azure AD 群組。 如需步驟，請參閱 [在 Intune 中管理 Windows 10 軟體更新](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure)。


## <a name="azure-active-directory-settings"></a>Azure Active Directory 設定

自助密碼重設： **選擇 [選取** ] [設定]，然後選取 [ **新式工作區裝置]-[所有** Azure AD 群組]。 如需詳細資訊，請參閱 [教學課程：讓使用者可以使用 Azure Active Directory 自助密碼重設來解除鎖定帳戶或重設密碼](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-enable-sspr)。



## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a>開始使用 Microsoft 受管理電腦的步驟

1. [在系統管理入口網站中新增和驗證系統管理員連絡人](add-admin-contacts.md)
2.  (本文登記後調整設定) 
3. [指派授權](assign-licenses.md)
4. [部署 Intune 公司入口網站](company-portal.md)
5. [啟用企業狀態漫遊](enterprise-state-roaming.md)
6. [設定裝置](set-up-devices.md)
7. [讓您的使用者準備好使用裝置](get-started-devices.md)
8. [部署應用程式](deploy-apps.md)
