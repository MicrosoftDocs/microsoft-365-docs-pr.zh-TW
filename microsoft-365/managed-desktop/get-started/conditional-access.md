---
title: 註冊之後調整設定
description: 如何排除某些 Microsoft 帳戶
keywords: Microsoft 受管理的電腦, Microsoft 365, 服務, 文件
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: ca919798480698f92bba094c3755b3eccce30888
ms.sourcegitcommit: c1f9a1b2a34146c51c9e33c4119a388b249ce7a9
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/14/2021
ms.locfileid: "49867967"
---
# <a name="adjust-settings-after-enrollment"></a>註冊之後調整設定

在 Microsoft Managed Desktop 中完成註冊後，可能需要調整某些管理設定。 若要在需要時檢查及調整，請遵循下列步驟：

1. 查看下一節所述的 Microsoft Intune 和 Azure Active Directory 設定。
2. 如果有任何專案適用于您的環境，請進行所述的調整。
3. 如果您想要仔細檢查所有設定是否正確，您可以重新執行 [ [準備工作] 評估工具](https://aka.ms/mmdart) ，以確保與 Microsoft 管理的桌面沒有任何衝突。

> [!NOTE]
> 當您在下列月份繼續作業時，如果您在登記至 Microsoft Intune、Azure Active Directory 或 Microsoft 365 中的原則之後變更 microsoft 受管理的電腦，Microsoft 受管理的桌面可能會停止運作。 若要避免服務的問題，請在變更所列的原則之前，先檢查 [準備工作評估工具所發現之修正問題](../get-ready/readiness-assessment-fix.md) 中所述的特定設定。 您也可以隨時重新執行準備工作評估工具。


## <a name="microsoft-intune-settings"></a>Microsoft Intune 設定

- Autopilot 部署設定檔：如果您使用任何 Autopilot 原則，請將每個原則更新為排除 **現代的工作場所裝置-所有** Azure AD 群組。 若要更新這些設定，請在 [**工作分派**] 底下的 [**排除的群組**] 區段中，選取 **新式的工作場所裝置-** 在 Microsoft 管理的桌上型電腦註冊期間建立的所有 Azure AD 群組。 Microsoft 受管理的桌面也會建立 Autopilot 設定檔，在 **新式的 Workplace Autopilot 設定檔**) 中，它會有 "新式 workplace" (。 當您更新自己的 Autopilot 設定檔時，請確定您 *不會* 排除 **新式的工作區裝置-** 從 Microsoft Managed Desktop 所建立之 **新式 workplace Autopilot 設定檔** 中的所有 Azure AD 群組。

- 條件式存取原則：如果您在 Microsoft 受管理的桌上型電腦註冊後，針對 Azure AD、Microsoft Intune 或 Microsoft Defender for Endpoint 建立相關的任何新的條件式存取原則，請將 **新式的 Workplace Service 帳戶** 從這些原則中排除。 如需步驟，請參閱 [條件式存取：使用者和群組](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups)。 Microsoft 受管理的桌面維護個別的條件式存取原則，以限制存取這些帳戶。 若要查看 Microsoft 受管理的電腦條件式存取原則 (**新式工作場所–安全工作站**) ，請移至 Microsoft 端點管理員，並流覽至 [**端點安全性**] 中的 [**條件式存取**]。 請勿修改由 Microsoft Managed Desktop 所建立且名稱中包含 "新式 Workplace" 的任何 Azure AD 條件式存取原則。

- 多重要素驗證：如果您在 Microsoft 受管理的桌上型電腦註冊後，在與 Azure AD、Intune 或 Microsoft Defender for Endpoint 相關的條件式存取原則中建立任何新的多重要素驗證需求，請從這些位置排除 **新式的 Workplace Service 帳戶** Azure AD 群組。 如需步驟，請參閱 [條件式存取：使用者和群組](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups)。 Microsoft 受管理的桌面維護個別的條件式存取原則，以限制此群組的成員存取權。 若要查看 Microsoft 受管理的電腦條件式存取原則 (**新式工作場所-**) ，請移至 Microsoft 端點管理員，並流覽至 [**端點安全性**] 中的 [**條件式存取**]。 

- Windows 10 更新環：針對您已建立的任何 Windows 10 更新鈴聲原則，從每個原則中排除 **所有** Azure AD 群組。 如需步驟，請參閱 [建立和指派更新環](https://docs.microsoft.com/mem/intune/protect/windows-10-update-rings#create-and-assign-update-rings)。 Microsoft 受管理的桌面也會建立一些更新環原則，所有的更新環原則，都是「新式工作」的名稱 (例如 **新式的工作區更新原則 [廣泛的]**、 **新式的工作區更新原則 [Fast]**、 **新式的工作區更新原則 [First]**，以及 **新式的工作區更新原則 [Test]**) 。 當您更新您自己的原則時，請確定您 *未* 排除 **新式的工作場所裝置-所有** Azure AD 群組從 Microsoft 受管理的桌面所建立。


## <a name="azure-active-directory-settings"></a>Azure Active Directory 設定

自助密碼重設：如果您針對所有使用者使用自助密碼重設，請調整指派，以排除 Microsoft 受管理的桌面服務帳戶。 若要調整此指派，請為除了 Microsoft Managed Desktop service 帳戶 *以外* 的所有使用者建立 Azure AD 動態群組，然後將該群組用於工作分派，而不是「所有使用者」。

為了協助您尋找及排除服務帳戶，以下是您可以使用的動態查詢範例：

```Console
(user.objectID -ne null) and (user.userPrincipalName -ne "MSADMIN@TENANT.onmicrosoft.com") and (user.userPrincipalName -ne "MSADMININT@TENANT.onmicrosoft.com") and (user.userPrincipalName -ne "MWAAS_SOC_RO@TENANT.onmicrosoft.com") and (user.userPrincipalName -ne "MWAAS_WDGSOC@TENANT.onmicrosoft.com") and (user.userPrincipalName -ne "MSTEST@TENANT.onmicrosoft.com")
```

在此查詢中，以租使用者功能變數名稱取代 @TENANT。



## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a>開始使用 Microsoft 受管理電腦的步驟

1. [在系統管理入口網站中新增和驗證系統管理員連絡人](add-admin-contacts.md)
2.  (本文登記後調整設定) 
3. [指派授權](assign-licenses.md)
4. [部署 Intune 公司入口網站](company-portal.md)
5. [啟用企業狀態漫遊](enterprise-state-roaming.md)
6. [設定裝置](set-up-devices.md)
7. [讓您的使用者準備好使用裝置](get-started-devices.md)
8. [部署應用程式](deploy-apps.md)
