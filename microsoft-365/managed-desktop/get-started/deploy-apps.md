---
title: 部署 Microsoft 受管理的桌上型電腦裝置的應用程式
description: 新增與應用程式部署至 Microsoft 受管理的桌上型電腦裝置的資訊。
keywords: Microsoft 受管理的桌上型電腦、 Microsoft 365、 服務、 文件、 應用程式、 企業營運系統應用程式、 LOB 應用程式
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 01/17/2019
ms.openlocfilehash: 65d45be5ddb21d8f2cac876a1c8f93b2bbddf7b8
ms.sourcegitcommit: 0fc00286d7dc8cafddf9d17a98a375503b9551e6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/18/2019
ms.locfileid: "29341600"
---
# <a name="deploy-apps-to-microsoft-managed-desktop-devices"></a>將應用程式部署到 Microsoft 受管理的桌上型電腦裝置
Microsoft 受管理的桌上型電腦的 onboarding 一部分包括新增及應用程式部署至使用者的裝置。一旦您使用 Microsoft 受管理的桌上型電腦入口網站，您可新增及部署您的應用程式。 

整體程序看起來如下：
1. [新增至 Microsoft 受管理的桌上型電腦入口網站的應用程式](#1)-這可以現有的企業營運系統 (LOB) 應用程式] 或從 intune 是否已同步處理企業的 Microsoft 存放區的應用程式。 
2. [建立 Azure Active Directory (AD) 群組的應用程式工作分派](#2)-您將使用這些群組來管理應用程式工作分派。
3. [指派給使用者的應用程式](#3)

<span id="1" />

## <a name="step-1-add-apps-to-microsoft-managed-desktop-portal"></a>步驟 1： 將應用程式新增至 Microsoft 受管理的桌上型電腦入口網站
您可以將[Win32 或 Windows MSI 型應用程式](#lob-apps)，或[Microsoft 存放區商務應用程式](#msfb-apps)新增至 Microsoft 受管理的桌上型電腦，和再將其部署至 Microsoft 受管理的桌上型電腦裝置。

<span id="lob-apps">

###  <a name="win32-or-windows-msi-based-apps-to-microsoft-managed-desktop"></a>Win32 或 Windows MSI 型應用程式向 Microsoft 受管理的桌面

您可以將您的企業營運系統 (LOB) 應用程式新增至 Microsoft 受管理的桌上型電腦入口網站。如需 Microsoft 受管理的桌上型電腦裝置上安裝的應用程式需求的資訊，請參閱[Microsoft 受管理的桌面應用程式需求](https://docs.microsoft.com/microsoft-365/managed-desktop/service-description/mmd-app-requirements)。

在此程序，您將會選取哪種您要新增並設定並上傳的應用程式來源應用程式。 

**若要將您的 LOB 應用程式或 Windows 應用程式新增至 Microsoft 受管理的桌上型電腦入口網站**

您可以登入 Microsoft 受管理的桌上型電腦入口網站或登入 Intune 並再搜尋 Microsoft 受管理的桌面。我們將會顯示 Microsoft 受管理的桌上型電腦入口網站登入。 

1.  登入[Microsoft 受管理的桌上型電腦管理入口網站](http://aka.ms/mmdportal)。 
2.  在 [**詳細目錄**] 下選取 [**應用程式**。
3.  在應用程式的工作量，選取 [**新增**。
4.  在 [**新增應用程式**中，選取 [**企業營運系統應用程式**或**Windows 應用程式 (Win32)-預覽**]。
    - 如果您選取**企業營運系統應用程式**，請參閱新增和設定企業營運系統應用程式上的指示[新增至 Microsoft Intune 的 Windows 企業營運系統應用程式](https://docs.microsoft.com/intune/lob-apps-windows)。
    - 如果您選取 [ **Windows 應用程式 (Win32)-預覽**，請參閱新增及設定 Windows 應用程式上的指示[Win32 應用程式的管理](https://docs.microsoft.com/intune/apps-win32-app-management)。

<span id="msfb-apps">

### <a name="microsoft-store-for-business-apps"></a>Microsoft 商務應用程式的存放區
如果您尚未註冊與 Microsoft Store for Business，您可以註冊時您購物應用程式。您的應用程式之後，您可以使用 Microsoft 受管理的桌上型電腦同步處理它們。 

**若要購買從 Microsoft 存放區的商務應用程式**

1. 登入與商務系統帳戶您 Microsoft Store [For Business 的 Microsoft 存放區](https://businessstore.microsoft.com)。
2. 選取 [**我的群組購買**。
3. 使用搜尋來尋找所想，該應用程式及選取的應用程式。
4. 在產品的詳細資訊，請選取 [**取得應用程式**]。Microsoft 存放區將您的組織新增至**產品 & 服務**的應用程式。

**若要強制 Intune 和 Microsoft Store for Business 之間的同步處理**
1. 您的租用戶的登入[Azure 入口網站](https://portal.azure.com/)為 Intune 系統或全域管理員
2. 選取 [**所有服務 > Intune**。Intune 是在監視 + 管理] 區段中。
3. 在 Intune] 窗格中，選取**用戶端應用程式**，然後再選取**適用於企業的 Microsoft 存放區**。
4. 選取 [同步處理的商務應用程式的 intune 您 Microsoft 存放區的 [**啟用**]。
    - 如果您尚未選取、 簽署並關聯您的 Microsoft 儲存 intune 商務帳戶
    - 選取 [在其中從 Microsoft 存放區的商務應用程式會顯示 Intune 主控台中的語言
    - 選取 [同步處理的商務應用程式的 intune 您 Microsoft 存放區**同步處理**。
    - 確認已啟用 Microsoft Store for Business 和 Intune 之間同步處理 （下一步）。 

**若要確認 Intune 和 Microsoft Store for Business 之間的同步處理是使用中**
1. 登入與商務系統帳戶您 Microsoft Store [For Business 的 Microsoft 存放區](https://businessstore.microsoft.com)。
2. 選取 [**管理**]。
3. 選取 [**設定**]，然後選取 [ **Distribute**。
4. 在 [**管理工具**] 確認已列出 Intune 且狀態為**作用中**。  

<span id="2" />

## <a name="step-2-create-azure-ad-groups"></a>步驟 2： 建立 Azure AD 群組

建立每個應用程式的三個 Azure AD 群組。下表概述您需要的群組 （線上] 有需要，以及解除安裝）。 

工作分派類型的應用程式 |   群組使用   | 範例 Azure AD 的名稱
--- | --- | ---
可以使用 |  應用程式會提供來自公司入口網站應用程式或網站。 | MMD –*應用程式名稱*-線上
必要 |  在選取群組的裝置上安裝應用程式。 | MMD –*應用程式名稱*-所需
[解除安裝] |  載入應用程式會從選取的群組中的裝置在解除安裝。 | MMD –*應用程式名稱*-解除安裝

將使用者新增至這些群組以進行應用程式可用、 安裝應用程式，或從使用者的 Microsoft 受管理的桌上型電腦裝置中移除應用程式。 

<span id="3" />

## <a name="step-3-assign-apps-to-your-users"></a>步驟 3： 指派給使用者的應用程式

**若要指派給使用者的應用程式**

1. 登入[Microsoft 受管理的桌上型電腦管理入口網站](http://aka.ms/mmdportal)。
2. 在受管理的桌上型電腦] 窗格中，選取 [**應用程式**。
3. 在應用程式的工作量，選取您要指派使用者並選取**指定的使用者群組**之應用的程式。
4. 針對特定的應用程式、 選取工作分派類型 （線上] 有需要，解除安裝），並指派適當的群組。
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