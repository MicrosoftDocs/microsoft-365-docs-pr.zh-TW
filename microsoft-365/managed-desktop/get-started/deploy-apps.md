---
title: 將應用程式部署至裝置
description: 新增及部署至 Microsoft 受管理的電腦裝置的應用程式的資訊。
keywords: Microsoft 受管理的電腦、 Microsoft 365、 服務、 文件、 應用程式、-營運應用程式、 LOB 應用程式
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: a064a41fc7ab69e31d49553f600dfd6bb91ef7b0
ms.sourcegitcommit: 9083036e787cf997fbceb19c66af594d0fa81d0f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/13/2019
ms.locfileid: "38302910"
---
# <a name="deploy-apps-to-devices"></a>將應用程式部署至裝置
以 Microsoft 受管理的電腦上架一部分的包含新增和應用程式部署至使用者的裝置。 一旦您使用 Microsoft 受管理電腦入口網站，您可以新增並部署您的應用程式。 

整體程序看起來像這樣：
1. [新增應用程式連接至 Microsoft 受管理電腦入口網站](#1)-這可以現有的-營運 (LOB) 應用程式] 或來自使用 Intune，當您同步處理商務用 Microsoft Store 應用程式。 
2. [建立 Azure Active Directory (AD) 群組的應用程式工作分派](#2)-您將使用這些群組來管理應用程式工作分派。
3. [將應用程式指派給您的使用者](#3)

<span id="1" />

## <a name="step-1-add-apps-to-microsoft-managed-desktop-portal"></a>步驟 1： 將應用程式新增至 Microsoft 受管理電腦入口網站
您可以將[Win32 或 Windows MSI 型應用程式](#lob-apps)，或[Microsoft 網上商店商務應用程式](#msfb-apps)新增至 Microsoft 受管理的電腦，並再將其部署至 Microsoft 受管理的電腦裝置。

<span id="lob-apps">

###  <a name="win32-or-windows-msi-based-apps-to-microsoft-managed-desktop"></a>Win32 或 Windows MSI 型應用程式連接至 Microsoft 受管理的電腦

您可以將-營運 (LOB) 應用程式新增至 Microsoft 受管理電腦入口網站。 如需 Microsoft 受管理的電腦裝置上安裝的應用程式需求的資訊，請參閱[Microsoft 受管理的電腦應用程式需求](https://docs.microsoft.com/microsoft-365/managed-desktop/service-description/mmd-app-requirements)。

在此程序，您需選取哪一個您要新增，然後設定並上傳的應用程式來源應用程式。 

**若要將您的 LOB 應用程式或 Windows 應用程式新增至 Microsoft 受管理電腦入口網站**

您可以登入 Microsoft 受管理電腦入口網站，或登入 Intune，然後搜尋 Microsoft 受管理電腦的。 我們將顯示登入 Microsoft 受管理電腦入口網站。 

1.  登入[Microsoft 受管理的桌上型電腦系統管理入口網站](https://aka.ms/mmdportal)。 
2.  在 [**詳細目錄**] 下選取 [**應用程式**]。
3.  在 [應用程式的工作負載，選取 [**新增**。
4.  在 [**新增應用程式**中，選取 [ **-營運應用程式**或**Windows 應用程式 (Win32)**。
    - 如果您選取 **-營運應用程式**，請參閱[新增至 Microsoft Intune 的 Windows-營運應用程式](https://docs.microsoft.com/intune/lob-apps-windows)，以新增及設定-營運應用程式的相關指示。
    - 如果您選取**Windows 應用程式 (Win32)**，請參閱新增及設定 Windows 應用程式的指示[Win32 應用程式管理](https://docs.microsoft.com/intune/apps-win32-app-management)。

<span id="msfb-apps">

### <a name="microsoft-store-for-business-apps"></a>Microsoft 網上商店商務應用程式
如果您尚未註冊與商務用 Microsoft Store，您可以註冊時您購買應用程式。 您的應用程式之後，您可以使用 Microsoft 受管理的電腦同步它們。 

**若要購買來自商務用 Microsoft Store 應用程式**

1. [商務用 Microsoft Store](https://businessstore.microsoft.com)與 Microsoft 商店企業版系統管理員帳戶登入。
2. 選取 [**我的群組購買**]。
3. 使用搜尋來尋找所想要的話，該應用程式，然後選取 [應用程式。
4. 在產品詳細資料中，選取 [**取得應用程式**]。 Microsoft 網上商店將為您的組織新增至**產品 & 服務**的應用程式。

**若要強制執行 Intune 和商務用 Microsoft Store 間同步處理**
1. 登入[Azure 入口網站](https://portal.azure.com/)Intune 系統管理員或全域系統管理員為您的租用戶
2. 選取 [**所有服務 > Intune**]。 Intune 處於監視 + 管理] 區段中。
3. 在 [Intune] 窗格中，選取 [**用戶端應用程式**，然後再選取**商務用 Microsoft Store**。
4. 選取 [**啟用**]，以同步處理 Microsoft 商店商務應用程式使用 Intune。
    - 如果您還沒，簽署並關聯您的 Microsoft 儲存使用 Intune 商務帳戶
    - 選取 [將您 Intune 主控台中顯示來自商務用 Microsoft Store 應用程式中的語言
    - 選取 [**同步處理**來同步處理 Microsoft 商店商務應用程式使用 Intune]。
    - 確認商務用 Microsoft Store 與 Intune 之間同步處理正在使用中 （下一步）。 

**若要確認 Intune 和商務用 Microsoft Store 間同步處理正在使用中**
1. [商務用 Microsoft Store](https://businessstore.microsoft.com)與 Microsoft 商店企業版系統管理員帳戶登入。
2. 選取 [**管理**]。
3. 選取 [**設定**]，然後選取 [**分散**對齊。
4. 在 [**管理工具**]，確認 Intune 已列出，且狀態為**作用中**。  

<span id="2" />

## <a name="step-2-create-azure-ad-groups"></a>步驟 2： 建立 Azure AD 群組

建立三個 Azure AD 群組的每個應用程式。 下表概述您需要的群組 （適用於使用，有需要，以及解除安裝）。 

應用程式指派類型 |   群組使用   | 範例 Azure AD 的名稱
--- | --- | ---
可以使用 |  應用程式可從公司入口網站應用程式或網站。 | MMD –*應用程式名稱*-適用於
必要 |  在 [選取群組中的裝置上安裝應用程式。 | MMD –*應用程式名稱*-必要
Uninstall |  從選取群組中的裝置解除安裝應用程式。 | MMD –*應用程式名稱*-解除安裝

將您的使用者新增至這些群組，以進行應用程式可用、 安裝應用程式，或從他們的 Microsoft 受管理的電腦裝置中移除應用程式。 

<span id="3" />

## <a name="step-3-assign-apps-to-your-users"></a>步驟 3： 將應用程式指派給您的使用者

**若要將應用程式指派給您的使用者**

1. 登入[Microsoft 受管理的桌上型電腦系統管理入口網站](https://aka.ms/mmdportal)。
2. 在 [受管理的電腦] 窗格中，選取 [**應用程式**]。
3. 在 [應用程式的工作負載，選取您要指派使用者，並選取 [**指派使用者群組**的應用程式。
4. 特定應用程式中，選取工作分派類型 （適用於使用，有需要，解除安裝），並指派適當的群組。
5. 在 [指派應用程式] 窗格中，選取 **[確定]**。


## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a>若要開始使用 Microsoft 受管理電腦的步驟

1. [在系統管理入口網站中新增和驗證系統管理員連絡人](add-admin-contacts.md)
2. [調整條件式存取](conditional-access.md)
3. [指派授權](assign-licenses.md)
4. [部署 Intune 公司入口網站](company-portal.md)
5. [啟用企業狀態漫遊](enterprise-state-roaming.md)
6. [設定裝置](set-up-devices.md)
7. [讓您的使用者準備好使用裝置](get-started-devices.md)
8. 部署應用程式 （本主題）


<!--# Preparing apps for Microsoft Managed Desktop

This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.

-->
