---
title: 在裝置上安裝 Intune 公司入口網站
description: 在 Microsoft 受管理的電腦裝置上安裝公司入口網站應用程式的相關資訊
keywords: Microsoft 受管理的電腦、Microsoft 365、公司入口網站
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: f9f36d6ca14be610ce9374380349264439282a6a
ms.sourcegitcommit: 1206319a5d3fed8d52a2581b8beafc34ab064b1c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/29/2021
ms.locfileid: "52086682"
---
# <a name="install-intune-company-portal-on-devices"></a>在裝置上安裝 Intune 公司入口網站

Microsoft 受管理的電腦需要 IT 管理員為其具有 Microsoft 受管理的電腦裝置的使用者安裝 Intune 公司入口網站。 以下是貴組織的一些優點：
- 使用者有一個位置可流覽及安裝可用的應用程式。 
- IT 系統管理員可以依類別組織使用者的應用程式。  
- 某些應用程式 (例如 Microsoft Project 和 Microsoft Visio) 需要公司入口網站以 Microsoft 受管理的電腦部署。
- IT 管理員可以自訂群組織的公司入口網站。 這包括品牌影像、在本機支援連絡人中新增，等等。 如需詳細資訊，請參閱 how [to Configure the Microsoft Intune 公司入口網站應用程式](/intune/company-portal-app)。   

本主題說明將 Intune 公司入口網站部署至 Microsoft 受管理的電腦使用者的處理常式。 整體程式看起來如下所示：
1. 從商務用 Microsoft Store 購買公司入口網站，並與 Intune 同步
2. 將公司入口網站指派給您的使用者
3. 向使用者傳達變更

## <a name="step-1---purchase-company-portal-from-microsoft-store-for-business-and-sync-with-intune"></a>步驟 1-從商務用 Microsoft Store 購買公司入口網站，並與 Intune 同步處理
如需如何購買應用程式和與 Intune 同步的資訊，請參閱將 *應用程式部署至 Microsoft 受管理的電腦裝置*[商務用 Microsoft Store 應用程式](deploy-apps.md#msfb-apps)。

本主題提供下列資訊： 
- 從商務用 Microsoft Store 購買公司入口網站 
- 強制 Intune 與商務用 Microsoft Store 之間的同步處理
- 驗證 Intune 與商務用 Microsoft Store 之間的主動同步處理 

## <a name="step-2---assign-company-portal-to-your-users"></a>步驟 2-將公司入口網站指派給您的使用者
在 Microsoft 受管理的電腦中進行註冊後，系統會自動將公司入口網站部署至您的租使用者，並在組織中的 Microsoft 受管理的電腦裝置上安裝應用程式。

## <a name="step-3---communicate-change-to-your-users"></a>步驟 3-向使用者傳達變更
做為您組織的 IT 管理員，請務必讓您的使用者瞭解如何在組織中使用公司入口網站。 Microsoft 受管理的電腦建議：
- 從公司入口網站安裝應用程式的步驟。 如需詳細資訊，請參閱 [在您的裝置上安裝和共用應用程式](/intune-user-help/install-apps-cpapp-windows)。
- 如何將要求傳送給 IT 管理員，以取得目前無法使用的應用程式。 如需詳細資訊，請參閱 [要求適用于工作或學校的應用程式](/intune-user-help/install-apps-cpapp-windows#request-an-app-for-work-or-school)。  

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a>開始使用 Microsoft 受管理電腦的步驟

1. [在系統管理入口網站中新增和驗證系統管理員連絡人](add-admin-contacts.md)
2. [調整條件式存取](conditional-access.md)
3. [指派授權](assign-licenses.md)
4. 部署 Intune 公司入口網站 (本主題) 
5. [啟用企業狀態漫遊](enterprise-state-roaming.md)
6. [設定裝置](set-up-devices.md)
7. [讓您的使用者準備好使用裝置](get-started-devices.md)
8. [部署應用程式](deploy-apps.md)
