---
title: Microsoft 受管理的電腦系統管理入口網站中新增系統管理連絡人
description: 告訴我們人員連絡以取得焦點的每個區域。
keywords: Microsoft 受管理的電腦，Microsoft 365 服務，文件
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.collection: M365-modern-desktop
ms.openlocfilehash: 014404ab38ff5871289be186dec150115c3be6ec
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32277529"
---
# <a name="add-admin-contacts-in-microsoft-managed-desktop-admin-portal"></a>Microsoft 受管理的桌上型電腦管理入口網站中新增系統管理連絡人

有幾種方式與客戶的 Microsoft 受管理的電腦服務進行通訊。 若要簡化的通訊，並確保我們正在檢查的最佳的連絡人，您需要提供一組系統管理員連絡人。 Microsoft 受管理的桌上型電腦 IT 作業將連絡這些人員，以協助疑難排解問題，您的租用戶。 

## <a name="azure-active-directory-access-for-microsoft-managed-desktop-admin-portal"></a>Microsoft 受管理的桌上型電腦系統管理入口網站的 azure Active Directory 存取

Microsoft 受管理的桌上型電腦系統管理入口網站，必須具備存取入口網站的人員其中一種 Azure Active Directory (AD) 角色：
- 全域管理員
- Intune 服務管理員
- 計費系統管理員
- 服務支援系統管理員

全域系統管理員必須是要註冊 Microsoft 受管理電腦中的客戶一種。  所有的五個角色都相同的存取權，在系統管理入口網站中啟動和檢視工作。  如需有關如何在 Azure AD 中指派這些角色的詳細資訊，請參閱 < <b0>Azure Active Directory 中的系統管理員角色權限</b0>。 

## <a name="admin-contact-focus-areas"></a>系統管理連絡人的重點領域

系統管理連絡人應該是最佳的人員或群組，可以回答問題，並使不同的重點領域的決策。  Microsoft 受管理的桌上型電腦作業會連絡這些系統管理連絡人的涉及歸檔由客戶支援要求的問題。  這些系統管理連絡人會收到支援要求的更新和新郵件通知。  這些區域，包括：

焦點區域 | 如需問題
--- | ---
App | 疑難排解應用程式封裝
裝置 | 裝置健全狀況，使用 Microsoft 受管理的電腦裝置進行疑難排解
安全性 | 疑難排解安全性問題的 Microsoft 受管理的電腦裝置
其他 | 未涵蓋之其他方面的問題

無論您選擇讓知識和授權來決定 Microsoft 受管理的桌上型電腦環境這些連絡人需求。 當您上架您 Microsoft 受管理的桌上型電腦環境中，系統會提示您將連絡人新增本機服務台和安全性。 

系統管理連絡人都是必要時您[提交支援要求](../working-with-managed-desktop/support.md)。 您需要有支援要求的 [焦點] 區域的系統管理員連絡。 

**若要新增系統管理連絡人**

1.  登入[Microsoft 受管理的電腦系統管理入口網站](http://aka.ms/mwaasportal)。 

2.  **支援**] 底下選取 [**系統管理連絡人**]。 

    ![支援] 功能表中，系統管理連絡人](images/admincontacts.png)

3. 選取 [**新增**]。

    ![系統管理員入口網站加入] 按鈕](images/adminadd.png)

4.  選取**的焦點] 區域**，然後輸入連絡人的資訊。 

    ![[] 清單中的焦點的區域](images/areaoffocus.png)

5. 重複的每個區域的焦點。 

