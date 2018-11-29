---
title: 新增 Microsoft 受管理的桌上型電腦管理入口網站中管理連絡人
description: 告訴我們要針對每個區域的焦點連絡的人。
keywords: Microsoft 受管理的桌上型電腦、 [Microsoft 365 服務、 文件
ms.service: m365-md
author: jdeckerms
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.openlocfilehash: 65dd8709c469826e2696015c13823c58eb10e342
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/28/2018
ms.locfileid: "26866298"
---
# <a name="add-admin-contacts-in-microsoft-managed-desktop-admin-portal"></a>新增 Microsoft 受管理的桌上型電腦管理入口網站中管理連絡人

有數種方式與客戶的 Microsoft 受管理的桌上型電腦服務通訊。若要簡化通訊並確定我們要檢查與最佳的連絡人，您需要提供一組管理連絡人。Microsoft 受管理的桌上型電腦 IT 作業將會連絡這些人員協助您的租用戶疑難排解問題。 

## <a name="azure-active-directory-access-for-microsoft-managed-desktop-admin-portal"></a>Azure Active Directory 存取 Microsoft 受管理的桌上型電腦管理入口網站

Microsoft 受管理的桌上型電腦管理入口網站需要存取入口網站的人員可以其中一種 Azure Active Directory (AD) 角色：
- 全域管理員
- Intune 服務管理員
- 計費管理員
- 服務支援管理員

如需有關這些角色及其在 Azure AD 為其指派的詳細資訊，請參閱[在 Azure Active Directory 中的系統管理員角色權限](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)。 

## <a name="admin-contact-focus-areas"></a>管理連絡人焦點區域

管理連絡人應最佳的人員或群組可回答的問題和進行不同的焦點區域的決策。這些區域包括：

焦點區域 | 如需問題
--- | ---
應用程式 | 疑難排解應用程式封裝
[裝置] | 裝置健康情況、 疑難排解與 Microsoft 受管理的桌上型電腦裝置
安全性 | 疑難排解 Microsoft 受管理的桌上型電腦裝置的安全性問題
其他 | 不涵蓋其他方面的問題

凡是您選擇的這些連絡人必須擁有的知識和授權來決定 Microsoft 受管理的桌上型電腦環境。當您開始您的 Microsoft 受管理的桌上型電腦環境中，系統將提示您將連絡人新增本機服務台及安全性。 

管理連絡人所需何時您[提交支援要求](../working-with-managed-desktop/support.md)。您需要有焦點區的支援要求管理員連絡。 

**若要新增管理連絡人**

1.  登入[Microsoft 受管理的桌上型電腦管理入口網站](http://aka.ms/mwaasportal)。 

2.  **支援**] 底下選取 [**系統管理連絡人**。 

    ![支援] 功能表中管理連絡人](images/admincontacts.png)

3. 選取 [**新增**]。

    ![Admin 入口網站新增] 按鈕](images/adminadd.png)

4.  選取**的焦點] 區域中**，輸入連絡人的資訊。 

    ![區域的焦點的清單](images/areaoffocus.png)

5. 重複針對每個區域的焦點。 

