---
title: 部署 Microsoft 受管理的電腦裝置的應用程式
description: 新增及部署至 Microsoft 受管理的電腦裝置的應用程式的資訊。
keywords: Microsoft 受管理的電腦、 Microsoft 365、 服務、 文件、 應用程式、-營運應用程式、 LOB 應用程式
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 5ccb240460958d5978f4fd19e08652123790784e
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32282519"
---
# <a name="deploy-apps-to-microsoft-managed-desktop-devices"></a>將應用程式部署至 Microsoft 受管理的電腦裝置
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

1.  登入[Microsoft 受管理的桌上型電腦系統管理入口網站](http://aka.ms/mmdportal)。 
2.  在 [**詳細目錄**] 下選取 [**應用程式**]。
3.  在 [應用程式的工作負載，選取 [**新增**。
4.  在 [**新增應用程式**中，選取 [ **-營運應用程式**或**Windows 應用程式 (Win32)-預覽**]。
    - 如果您選取 **-營運應用程式**，請參閱[新增至 Microsoft Intune 的 Windows-營運應用程式](https://docs.microsoft.com/intune/lob-apps-windows)，以新增及設定-營運應用程式的相關指示。
    - 如果您選取**Windows 應用程式 (Win32)-預覽**，請參閱新增及設定 Windows 應用程式的指示[Win32 應用程式管理](https://docs.microsoft.com/intune/apps-win32-app-management)。

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
Uninstall |  載入應用程式是從選取群組中的裝置解除安裝。 | MMD –*應用程式名稱*-解除安裝

將您的使用者新增至這些群組，以進行應用程式可用、 安裝應用程式，或從他們的 Microsoft 受管理的電腦裝置中移除應用程式。 

<span id="3" />

## <a name="step-3-assign-apps-to-your-users"></a>步驟 3： 將應用程式指派給您的使用者

**若要將應用程式指派給您的使用者**

1. 登入[Microsoft 受管理的桌上型電腦系統管理入口網站](http://aka.ms/mmdportal)。
2. 在 [受管理的電腦] 窗格中，選取 [**應用程式**]。
3. 在 [應用程式的工作負載，選取您要指派使用者，並選取 [**指派使用者群組**的應用程式。
4. 特定應用程式中，選取工作分派類型 （適用於使用，有需要，解除安裝），並指派適當的群組。
5. 在 [指派應用程式] 窗格中，選取 **[確定]**。

<!--# Preparing apps for Microsoft Managed Desktop

This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.

Applications: supported/onboard/deployment
 
Microsoft and Microsoft Managed Desktop customers have equally critical, yet different responsibilities around applications used with Microsoft Managed Desktop.

## Microsoft responsibilities
**Office 365 apps**
Microsoft will provide full service for the deployment, update, and support of specific Office 365 apps. All users will receive the base set of Office 365 click to run, 64 bit version of applications included in the device’s image so that a user can quickly become productive. The Project and Visio applications in of the Office 365 suite are licensed separately.  Microsoft Managed Desktop will provide deployment groups allowing the IT Administrator to manage licenses and deploy these applications appropriately for their organization. Microsoft will support end users of these applications through the Microsoft Managed Desktop Support channels.

**Line-of-business apps**
Microsoft provides tooling for IT Administrators to manage and deploy their line-of-business (LOB) applications to end users as a part of the Intune product. Microsoft will support application deployment issues as detailed in [Line-of-business applications](#line-of-business-applications) 

**Deploy with Intune**
Intune will be linked to the **Microsoft Store for Business** during Microsoft Managed Desktop onboarding allowing procured apps to be deployed through Intune. Microsoft will also deploy the web-based version of the Company Portal to end users so that IT Administrators can provide a self-service experience for end users.

**App management**
Microsoft may identify restricted applications which are not suitable for the modern workplace because of their system impact. When such an application is identified Microsoft will notify the customer and that application will need to be removed from the tenant. 

For more information on restricted app behaviors and app requirements, see [Microsoft Managed Desktop app requirements](../service-description/mmd-app-requirements.md)

## Customer responsibilities
The Office 365 Suite is core to Microsoft’s productivity offerings and is included in the Microsoft 365 License for all Microsoft Managed Desktop users. While Microsoft deploys, updates, and supports Office Applications to Microsoft Managed Desktop Devices there are still some areas for which the customer is responsible.
- **Assign licenses** - Customers are responsible for assigning the appropriate licenses to end users for Office 365. 
- **Add users to security groups** - For customers with users who need Project or Visio, the IT administrator must add those users to the appropriate deployment groups. IT administrators are also responsible for managing end of life for those users. 
- **Deploy Office 365 Add Ons** - Customers are responsible for deploying any plugins to the Office 365 suite which are deemed necessary. 

Since line-of-business (LOB) apps are unique for each customer, customers are responsible for managing all applications within their organization not deployed by Microsoft. This includes:
- Deciding which apps are needed and who needs them
- Assigning apps to those users
- Create and maintain Azure Active Directory (AD) groups for managing app assignments 

The customer must upload LOB apps to Intune. They are then responsible for deploying, updating, and decommissioning those applications over their respective lifecycles, as well as managing support for these apps for their users.

## Office applications
As part of the Microsoft 365 E5 license, Office 365 Standard Suite (64 Bit) is deployed by Microsoft. 

For details, see [Microsoft Managed Desktop technologies](../intro/technologies.md) <!--- and the other applications licensed under Office 365 E5 may be deployed by the customer using Intune’s deployment tools.

## Line-of-business applications
This table summarizes responsibilities across the different phases for line-of-business (LOB) applications. 

Application work items |    Customer    | Microsoft
--- | --- | ---
**Onboarding apps** |  |
Identify applications needed for targeted user groups   | ![yes](images/checkmark.png)  |
Create and manage Azure AD groups for app deployment | ![yes](images/checkmark.png) |   
**App Packaging** |  |
Package apps to meet Intune deployment standards |  ![yes](images/checkmark.png) |  
Upload apps to Intune | ![yes](images/checkmark.png)     |
Test apps in Microsoft Managed Desktop environment |    ![yes](images/checkmark.png) |  
Test apps with end users    | ![yes](images/checkmark.png) |    
**Deployment** | |
Manage and assign users to applications  | ![yes](images/checkmark.png)  |
Intune deployment tools delivers application to remote clients| |   ![yes](images/checkmark.png)
Identify and deploy application updates through Intune | ![yes](images/checkmark.png)    |
Unistall and remove applications when they have been retired    | ![yes](images/checkmark.png) |    
**Management** | |
Procure and assign licenses |   ![yes](images/checkmark.png)     |
Provide end-user support for line-of-business apps  | ![yes](images/checkmark.png) |
Manage app settings remotely    | ![yes](images/checkmark.png) |

For information on LOB application requirements, see [Microsoft Managed Desktop application requirements](../service-description/mmd-app-requirements.md)


## Intune application deployment
Application management can be handled through the Microsoft Managed Desktop Admin portal, or through the Intune portal. Intune’s app management portal shows applications deployed for Windows, Android, and iOS. Microsoft Managed Desktop Admin portal limits the view to Windows 10 applications. Both are available through the Azure Portal. 
* [Intune app management basics](https://docs.microsoft.com/intune/app-management)
* [Add apps to Intune](https://docs.microsoft.com/intune/app-management)
   * [Add a line-of-business App](https://docs.microsoft.com/intune/lob-apps-windows)
   * [Add Win32 apps to Intune](https://docs.microsoft.com/intune/apps-win32-app-management)
   * [Add web applications](https://docs.microsoft.com/intune/web-app)
* [Deploy apps](https://docs.microsoft.com/intune/apps-deploy)
   * [Deploy apps to Windows 10](https://docs.microsoft.com/intune/apps-windows-10-app-deploy)
* Company Portal
   * [Deploy the Company Portal](https://docs.microsoft.com/intune/store-apps-company-portal-app)
   * [Configure the Company Portal app](https://docs.microsoft.com/intune/company-portal-app)-->