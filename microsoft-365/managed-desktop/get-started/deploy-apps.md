---
title: 將應用程式部署至裝置
description: 在 Microsoft 受管理的電腦裝置中新增及部署應用程式的資訊。
keywords: Microsoft 受管理的電腦、Microsoft 365、服務、檔、應用程式、商務營運應用程式、LOB 應用程式
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 8bfc53d46bdcb91c16e9f4a1ddbc8ab3f6dfb47e
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50922023"
---
# <a name="deploy-apps-to-devices"></a>將應用程式部署至裝置
加入 Microsoft 受管理的電腦的部分包括新增及部署使用者裝置的應用程式。 一旦您使用 Microsoft 受管理的電腦入口網站，您就可以新增及部署應用程式。 

整體程式看起來如下所示：
1. [新增應用程式至 Microsoft 受管理的電腦入口網站](#1)-這可以是現有的企業營運 (LOB) 應用程式，或是您已與 Intune 同步處理的應用商務用 Microsoft Store 程式。 
2. [Create Azure Active Directory (AD) 群組進行應用程式指派](#2)」-您將使用這些群組來管理 app 指派。
3. [指派應用程式給您的使用者](#3)

<span id="1" />

## <a name="step-1-add-apps-to-microsoft-managed-desktop-portal"></a>步驟1：將應用程式新增至 Microsoft 受管理的電腦入口網站
您可以新增[Win32 或 Windows MSI 型應用程式](#lob-apps)，或[商務用 Microsoft Store 應用 Microsoft 受管理的電腦程式](#msfb-apps)，並將其部署到 Microsoft 受管理的電腦裝置。

<span id="lob-apps">

###  <a name="win32-or-windows-msi-based-apps-to-microsoft-managed-desktop"></a>Microsoft 受管理的電腦所用的 Win32 或 Windows MSI 型應用程式

您可以將企業營運 (LOB) 應用程式新增至 Microsoft 受管理的電腦入口網站。 如需 Microsoft 受管理的電腦裝置上安裝之應用程式需求的詳細資訊，請參閱[Microsoft 受管理的電腦應用程式需求](../service-description/mmd-app-requirements.md)。

在此程式中，您將選取要新增的應用程式類型，然後設定並上傳應用程式來源。 

**將您的 LOB 應用程式或 Windows 應用程式新增至 Microsoft 受管理的電腦入口網站**

您可以登入 Microsoft 受管理的電腦入口網站，或登入 Intune，然後搜尋 Microsoft 受管理的電腦。 我們會顯示登入 Microsoft 受管理的電腦入口網站。 

1.    登入[Microsoft 受管理的電腦管理入口網站](https://aka.ms/mmdportal)。 
2.    在 [ **庫存**] 下，選取 [ **應用程式**]。
3.    在 [應用程式工作負載] 中，選取 [ **新增**]。
4.    在 [**新增應用程式**] 中，選取 [**企業營運的應用程式**] 或 **Windows app (Win32)**]。
    - 如果您已選取 [企業營運]**應用程式**，請參閱 [Add a Windows business business app to Microsoft Intune](/intune/lob-apps-windows) ，以取得有關新增及設定企業營運系統應用程式的說明。
    - 如果您已選取 **Windows 應用程式 (win32)**，請參閱 [Win32 應用程式管理](/intune/apps-win32-app-management)以取得新增及設定 Windows 應用程式的指示。

<span id="msfb-apps">

### <a name="microsoft-store-for-business-apps"></a>商務用 Microsoft Store 應用程式
若尚未註冊商務用 Microsoft Store，您可以在購買應用程式時註冊。 您有應用程式之後，您可以使用 Microsoft 受管理的電腦將其同步。 

**從商務用 Microsoft Store 購買應用程式**

1. 使用您的商務用 Microsoft Store 系統管理員帳戶登入[商務用 Microsoft Store](https://businessstore.microsoft.com) 。
2. 選取 [ **為我的群組購買**]。
3. 使用 [搜尋] 來找出您想要的應用程式，然後選取應用程式。
4. 在 [產品詳細資料] 中，選取 **[取得應用程式**]。 Microsoft Store 會將應用程式新增至您組織的 **產品**。

**強制 Intune 與商務用 Microsoft Store 之間的同步處理**
1. 登入 Microsoft 端點管理員系統[管理中心](https://go.microsoft.com/fwlink/?linkid=2109431)。
2. 選取 [**租使用者管理**  >  **連接器及標記**]  >  **商務用 Microsoft Store**。
3. 選取 [**同步** 處理]，以取得您從 Microsoft Store 購買的應用程式至 Intune。

**確認 Intune 與商務用 Microsoft Store 之間的同步處理為作用中狀態**
1. 使用您的商務用 Microsoft Store 系統管理員帳戶登入[商務用 Microsoft Store](https://businessstore.microsoft.com) 。
2. 選取 [ **管理**]。
3. 選取 [**設定**]，然後選取 [**發佈**]。
4. 在 [ **管理工具**] 下，確認已列出 Intune，且狀態 **為 [作用中]**。  

<span id="2" />

## <a name="step-2-create-azure-ad-groups"></a>步驟2：建立 Azure AD 群組

為每個應用程式建立三個 Azure AD 群組。 下表概述您將需要 (可用、必要和卸載的群組) 。 

應用程式指派類型 |    群組使用    | Azure AD 名稱範例
--- | --- | ---
可以使用 |  應用程式將可從公司入口網站應用程式或網站取得。 | MMD – *應用程式名稱* –可用
必要 |  App 已安裝在所選群組中的裝置上。 | MMD – *應用程式名稱* –必要
解除安裝 |  已從選取群組中的裝置卸載應用程式。 | MMD – *應用程式名稱* –卸載

將您的使用者新增至這些群組，讓應用程式可供使用、安裝應用程式，或是移除其 Microsoft 受管理的電腦裝置中的應用程式。 

<span id="3" />

## <a name="step-3-assign-apps-to-your-users"></a>步驟3：將應用程式指派給您的使用者

**若要將應用程式指派給您的使用者**

1. 登入[Microsoft 受管理的電腦管理入口網站](https://aka.ms/mmdportal)。
2. 在 [受管理的桌面] 窗格中，選取 [ **app**]。
3. 在 [應用程式工作負載] 中，選取您要指派使用者的應用程式，然後選取 [ **指派使用者群組**]。
4. 針對特定的應用程式，選取 [可用]、[必要]、[卸載]) 中的工作分派 (類型，並指派適當的群組。
5. 在 [指派應用程式] 窗格中，選取 **[確定]**。


## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a>開始使用 Microsoft 受管理電腦的步驟

1. [在系統管理入口網站中新增和驗證系統管理員連絡人](add-admin-contacts.md)
2. [調整條件式存取](conditional-access.md)
3. [指派授權](assign-licenses.md)
4. [部署 Intune 公司入口網站](company-portal.md)
5. [啟用企業狀態漫遊](enterprise-state-roaming.md)
6. [設定裝置](set-up-devices.md)
7. [讓您的使用者準備好使用裝置](get-started-devices.md)
8.  (本主題部署應用程式) 


<!--# Preparing apps for Microsoft Managed Desktop

This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.

-->