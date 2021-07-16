---
title: 使用具有畫布的 Microsoft Teams 類別
ms.author: v-cichur
author: cichur
manager: serdars
ms.reviewer: sovaish
audience: admin
ms.topic: article
ms.service: o365-administration
f1.keywords:
- CSH
ms.collection: M365-modern-desktop
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: 將 Microsoft Teams 類別與畫布整合
ms.openlocfilehash: e8ab45de84fe8325f6d5b349deb96aa831d54e36
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/15/2021
ms.locfileid: "53454682"
---
# <a name="use-microsoft-teams-classes-with-canvas"></a>使用具有畫布的 Microsoft Teams 類別

Microsoft Teams 類別是 Learning 工具互通性 (LTI) 應用程式，可協助教育者和學生輕鬆流覽其 Learning 管理系統 (LMS) 和 Teams。 使用者可以直接從 LMS 中存取與其課程相關聯的類別小組。

## <a name="prerequisites-before-deployment"></a>部署之前的必要條件

> [!NOTE]
> 目前的類別 Teams LTI 只支援在有限範圍內 Microsoft Azure Active Directory (AAD) 同步處理畫布使用者。 
> - 您的租使用者必須在 (電子郵件、使用者識別碼或 SIS 識別碼) 和 Microsoft AAD 中的 UPN 的畫布欄位之間完全符合。 我們正在努力展開對同步處理功能的彈性，但是與此同時，在與 AAD 中的 UPN 不相符的任何使用者，也不會將其新增至與 AAD 同步處理的 Teams 類別中。 
> - 只有一個 Microsoft 租使用者可以用於在畫布和 Microsoft 之間對應使用者。
> - 您必須先關閉 SDS，才能使用類別 Teams LTI，以避免重複群組。

## <a name="microsoft-office-365-admin"></a>Microsoft Office 365管理

在管理 Instructure 畫布內的 Microsoft Teams 整合之前，請務必在完成 canvas 管理員設定之前，讓您的組織中組織 Microsoft Office 365 系統管理員核准的畫布 Azure 應用程式的 **Microsoft Teams 同步處理畫布** Microsoft Azure。

1. 登入畫布。

2. 選取全域導覽中的 [ **管理** ] 連結，然後選取您的帳戶。

3. 在 [系統 **管理] 導覽** 中，選取 [**設定**] 連結，然後選取 [整合] 索引標籤。

4. 開啟開啟開啟的開啟以啟用 Microsoft Teams 同步處理。

   ![團隊-同步處理](media/teams-sync.png)

5. 輸入您的 Microsoft 租使用者名稱和登入屬性。

   login 屬性將用於將 Canvas 使用者與 Azure Active Directory 使用者關聯。

6. 選取 [**更新設定** 完畢之後。

7. 若要核准對畫布的 **Microsoft Teams-Sync-canvas** Azure app 的存取權，請選取 [**授與承租人存取** 連結]。 您將會重新導向至 Microsoft Identity Platform 系統管理員同意端點。

   ![許可權](media/permissions.png)

8. 選取 [ **接受**]。

## <a name="canvas-admin"></a>畫布管理員

設定 Microsoft Teams LTI 1.3 整合。

做為畫布管理員時，您需要在環境內新增 Microsoft Teams 類別 LTI 應用程式。 請記下應用程式的 LTI 用戶端識別碼。

 - Microsoft Teams 類別-170000000000570

1. 存取 **管理員設定**  >  **應用程式**。

2. 選取 [ **+ App** ]，以新增 Teams LTI 應用程式。

   ![外部應用程式](media/external-apps.png)

3. 選取 [ **依用戶端識別碼** ] 設定類型。

   ![新增應用程式](media/add-app.png)

4. 輸入提供的用戶端識別碼，然後選取 [ **提交**]。

   您會注意到用戶端識別碼的 Microsoft Teams 類別 LTI 應用程式名稱，以確認。

5. 選取 [安裝]。

   Microsoft Teams 類別 LTI 應用程式將會新增至外部應用程式的清單。
   
## <a name="enabling-the-lti-app-for-canvas-courses"></a>為 Canvas 課程啟用 LTI 應用程式

若要在課程內使用 LTI 應用程式，Canvas 課程的指導員必須啟用整合同步。每門課程都必須由指導員啟用，以供建立相對應的團隊。小組建立沒有全域機制。 這是設計為防止不想要建立的小組的預防措施。

請參閱教師的教師 [檔](https://support.microsoft.com/topic/use-microsoft-teams-classes-in-your-lms-preview-ac6a1e34-32f7-45e6-b83e-094185a1e78a#ID0EBD=Instructure_Canvas) ，以針對每門課程啟用 LTI 應用程式，並完成整合安裝。
