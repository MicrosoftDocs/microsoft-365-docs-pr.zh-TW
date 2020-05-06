---
title: 將應用程式部署至裝置
description: 有關新增及部署 Microsoft 受管理桌面裝置之應用程式的資訊。
keywords: Microsoft 受管理的桌面、Microsoft 365、服務、檔、應用程式、企業營運服務應用程式、LOB 應用程式
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 9fd6efc56441cfbe8a05404319246c5e0bbe10ab
ms.sourcegitcommit: eb3c7f473e8fe62624f52c9bb38dcd6a96fa58a3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/05/2020
ms.locfileid: "44046325"
---
# <a name="deploy-apps-to-devices"></a>將應用程式部署至裝置
上架至 Microsoft Managed Desktop 的一部分包括新增及部署使用者裝置的應用程式。 使用 Microsoft 受管理的桌面入口網站後，您可以新增及部署應用程式。 

整體程式看起來如下所示：
1. [新增應用程式至 Microsoft 受管理的桌面入口網站](#1)-這可以是現有的企業營運（LOB）應用程式，或您已與 Intune 同步處理的 Microsoft Store for business 應用程式。 
2. [建立應用程式指派的 Azure Active Directory （AD）群組](#2)-您將使用這些群組來管理應用程式指派。
3. [指派應用程式給您的使用者](#3)

<span id="1" />

## <a name="step-1-add-apps-to-microsoft-managed-desktop-portal"></a>步驟1：將應用程式新增至 Microsoft 受管理的桌面入口網站
您可以將[Win32 （或 WINDOWS MSI 型應用](#lob-apps)程式）或[Microsoft Store for Business App](#msfb-apps)新增至 microsoft managed desktop，然後將其部署至 Microsoft 受管理的桌面裝置。

<span id="lob-apps">

###  <a name="win32-or-windows-msi-based-apps-to-microsoft-managed-desktop"></a>以 Win32 或 Windows MSI 為基礎的應用程式至 Microsoft 受管理的電腦

您可以將企業營運（LOB）應用程式新增至 Microsoft 受管理的桌面入口網站。 如需 Microsoft 受管理的電腦裝置上安裝之應用程式需求的詳細資訊，請參閱[Microsoft Managed desktop app 需求](https://docs.microsoft.com/microsoft-365/managed-desktop/service-description/mmd-app-requirements)。

在此程式中，您將選取要新增的應用程式類型，然後設定並上傳應用程式來源。 

**將您的 LOB 應用程式或 Windows 應用程式新增至 Microsoft 受管理的桌面入口網站**

您可以登入 Microsoft 受管理的桌面入口網站，或登入 Intune，然後搜尋 Microsoft Managed Desktop。 我們會顯示登入 Microsoft 受管理的桌面入口網站。 

1.    登入[Microsoft Managed Desktop Admin 入口網站](https://aka.ms/mmdportal)。 
2.    在 [**庫存**] 下，選取 [**應用程式**]。
3.    在 [應用程式工作負載] 中，選取 [**新增**]。
4.    在 [**新增應用程式**] 中，選取 [**企業營運應用程式**] 或 **[Windows 應用程式（Win32）**]。
    - 如果您已選取 [企業營運]**應用程式**，請參閱[新增 Windows 營運 Windows 應用程式至 Microsoft Intune 以](https://docs.microsoft.com/intune/lob-apps-windows)取得有關新增及設定企業營運應用程式的指示。
    - 如果您選取了 **[Windows 應用程式（Win32）**]，請參閱[Win32 應用程式管理](https://docs.microsoft.com/intune/apps-win32-app-management)以取得新增及設定 Windows 應用程式的指示。

<span id="msfb-apps">

### <a name="microsoft-store-for-business-apps"></a>Microsoft Store for Business 應用程式
若尚未註冊 Microsoft Store for Business，您可以在購買應用程式時進行註冊。 您有應用程式之後，您可以使用 Microsoft 受管理的桌面進行同步處理。 

**從商務用 Microsoft Store 購買應用程式**

1. 使用您的 Microsoft Store for Business Admin account，登入[Microsoft store For business](https://businessstore.microsoft.com) 。
2. 選取 [**為我的群組購買**]。
3. 使用 [搜尋] 來找出您想要的應用程式，然後選取應用程式。
4. 在 [產品詳細資料] 中，選取 **[取得應用程式**]。 Microsoft Store 會將應用程式新增至貴組織的**產品**。

**強制 Intune 與 Microsoft Store for Business 之間的同步處理**
1. 以 Intune 管理員身分登入[Azure 入口網站](https://portal.azure.com/)，或為您的租使用者登入全域系統管理員
2. 選取 [**所有服務] > Intune**。 Intune 位於監控 + 管理區段中。
3. 在 Intune 窗格中，選取 [**用戶端應用程式**]，然後選取 [ **Microsoft Store for Business**]。
4. 選取 [**啟用**]，以透過 Intune 同步處理您的 Microsoft Store for Business 應用程式。
    - 若尚未註冊，請使用 Intune 註冊和關聯 Microsoft Store for Business 帳戶
    - 從您的 Intune 主控台中，選取商務用 Microsoft 書店中的應用程式將顯示的語言
    - 選取 [**同步**處理]，以使用 Intune 同步處理 Microsoft Store for Business 應用程式。
    - 確認 Microsoft Store for Business 與 Intune 之間的同步處理為作用中（下一步）。 

**確認 Intune 與 Microsoft Store for Business 之間的同步處理已啟用**
1. 使用您的 Microsoft Store for Business Admin account，登入[Microsoft store For business](https://businessstore.microsoft.com) 。
2. 選取 [**管理**]。
3. 選取 [**設定**]，然後選取 [**發佈**]。
4. 在 [**管理工具**] 下，確認已列出 Intune，且狀態**為 [作用中]**。  

<span id="2" />

## <a name="step-2-create-azure-ad-groups"></a>步驟2：建立 Azure AD 群組

為每個應用程式建立三個 Azure AD 群組。 下表概述您將需要的群組（可用、必要和卸載）。 

應用程式指派類型 |    群組使用    | Azure AD 名稱範例
--- | --- | ---
可以使用 |  該應用程式將可從公司入口網站應用程式或網站取得。 | MMD –*應用程式名稱*–可用
必要 |  App 已安裝在所選群組中的裝置上。 | MMD –*應用程式名稱*–必要
Uninstall |  已從選取群組中的裝置卸載應用程式。 | MMD –*應用程式名稱*–卸載

將您的使用者新增至這些群組，讓應用程式 availabe、安裝應用程式，或從 Microsoft 受管理的桌面裝置移除應用程式。 

<span id="3" />

## <a name="step-3-assign-apps-to-your-users"></a>步驟3：將應用程式指派給您的使用者

**若要將應用程式指派給您的使用者**

1. 登入[Microsoft Managed Desktop Admin 入口網站](https://aka.ms/mmdportal)。
2. 在 [受管理的桌面] 窗格中，選取 [ **app**]。
3. 在 [應用程式工作負載] 中，選取您要指派使用者的應用程式，然後選取 [**指派使用者群組**]。
4. 針對特定的應用程式，選取工作分派類型（[可用]、[必要]、[卸載]）並指派適當的群組。
5. 在 [指派應用程式] 窗格中，選取 **[確定]**。


## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a>開始使用 Microsoft 受管理電腦的步驟

1. [在系統管理入口網站中新增和驗證系統管理員連絡人](add-admin-contacts.md)
2. [調整條件式存取](conditional-access.md)
3. [指派授權](assign-licenses.md)
4. [部署 Intune 公司入口網站](company-portal.md)
5. [啟用企業狀態漫遊](enterprise-state-roaming.md)
6. [設定裝置](set-up-devices.md)
7. [讓您的使用者準備好使用裝置](get-started-devices.md)
8. 部署應用程式（本主題）


<!--# Preparing apps for Microsoft Managed Desktop

This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.

-->
