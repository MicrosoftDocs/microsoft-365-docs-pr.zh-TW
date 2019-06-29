---
title: 部署 Microsoft 受管理電腦裝置的應用程式
description: 將應用程式新增及部署至 Microsoft 受管理的電腦裝置的資訊。
keywords: Microsoft 受管理的桌面、Microsoft 365、服務、檔、應用程式、企業營運應用程式、LOB 應用程式
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 5eac2e8c3023015bd034c51ad7e16a669a484772
ms.sourcegitcommit: 427c6459614d58f6ef7c74354ae1816423e22323
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/28/2019
ms.locfileid: "35390420"
---
# <a name="deploy-apps-to-microsoft-managed-desktop-devices"></a>將應用程式部署至 Microsoft 受管理的電腦裝置
上架的一部分加入 Microsoft 受管理的桌面, 包括在使用者的裝置中新增及部署應用程式。 一旦您使用 Microsoft 受管理的桌面入口網站, 您可以新增和部署您的應用程式。 

整體程式如下所示:
1. [將應用程式新增至 Microsoft 受管理的桌面入口網站](#1)-這可以是現有的企業營運 (LOB) 應用程式, 或您已與 Intune 同步處理的 Microsoft Store 中的應用程式。 
2. [建立應用程式指派的 Azure Active Directory (AD) 群組](#2)-您將使用這些群組來管理應用程式指派。
3. [將應用程式指派給您的使用者](#3)

<span id="1" />

## <a name="step-1-add-apps-to-microsoft-managed-desktop-portal"></a>步驟 1: 將應用程式新增至 Microsoft 受管理的桌面入口網站
您可以將[Win32 或 WINDOWS MSI 型應用](#lob-apps)程式, 或[Microsoft Store for Business App](#msfb-apps)新增至 Microsoft 受管理的電腦, 然後將其部署至 Microsoft 受管理的電腦裝置。

<span id="lob-apps">

###  <a name="win32-or-windows-msi-based-apps-to-microsoft-managed-desktop"></a>Microsoft 受管理的電腦的 Win32 或 Windows MSI 型應用程式

您可以將企業營運 (LOB) 應用程式新增至 Microsoft 受管理的桌面入口網站。 如需 Microsoft 受管理電腦裝置上所安裝之應用程式需求的相關資訊, 請參閱[Microsoft 受管理的桌面應用程式需求](https://docs.microsoft.com/microsoft-365/managed-desktop/service-description/mmd-app-requirements)。

在此程式中, 您將選取您要新增的應用程式類型, 然後設定及上傳應用程式來源。 

**將 LOB 應用程式或 Windows 應用程式新增至 Microsoft 受管理的桌面入口網站**

您可以登入 Microsoft 受管理的桌面入口網站, 或登入 Intune, 然後搜尋 Microsoft 受管理的電腦。 我們將會顯示 [登入 Microsoft 受管理的桌面入口網站]。 

1.  登入[Microsoft 受管理的桌面管理入口網站](http://aka.ms/mmdportal)。 
2.  在 [**清查**] 下, 選取 [**應用程式**]。
3.  在 [應用程式工作量] 中, 選取 [**新增**]。
4.  在 [**新增應用程式**] 中, 選取 [**企業營運應用程式**] 或 **[Windows 應用程式 (Win32)-預覽**]。
    - 如果您已選取**企業營運應用程式**, 請參閱[新增 Windows 營運企業應用程式至 Microsoft Intune](https://docs.microsoft.com/intune/lob-apps-windows) , 以取得新增和設定企業營運應用程式的相關指示。
    - 如果您選取 **[Windows app (Win32)-預覽**], 請參閱[Win32 app management](https://docs.microsoft.com/intune/apps-win32-app-management)以取得新增和設定 Windows 應用程式的指示。

<span id="msfb-apps">

### <a name="microsoft-store-for-business-apps"></a>商務用 Microsoft Store 應用程式
如果您尚未註冊商務用 Microsoft Store, 您可以在購買應用程式時註冊。 有您的應用程式之後, 您可以使用 Microsoft 受管理的電腦進行同步處理。 

**若要從商務用 Microsoft Store 購買應用程式**

1. 使用 Microsoft Store for Business Admin account 登入[Microsoft store For business](https://businessstore.microsoft.com) 。
2. 選取 [**為我的群組購買**]。
3. 使用搜尋來找出您想要的應用程式, 並選取該應用程式。
4. 在 [產品詳細資料] 中, 選取 [**取得應用程式**]。 Microsoft Store 會將應用程式新增至貴組織的**產品 & 服務**。

**強制執行 Intune 與 Microsoft Store for Business 之間的同步處理**
1. 以 Intune 系統管理員或您租使用者的全域系統管理員身分登入[Azure 入口網站](https://portal.azure.com/)
2. 選取 [**所有服務 > Intune**]。 Intune 位於 [監視 + 管理] 區段中。
3. 在 [Intune] 窗格中, 選取 [**用戶端應用程式**], 然後選取 [**商務用 Microsoft Store**]。
4. 選取 [**啟用**], 以使用 Intune 同步處理商務應用程式的 Microsoft Store。
    - 如果您還沒有使用 Intune 註冊並關聯 Microsoft Store for Business 帳戶
    - 選取您的 Intune 主控台中用來進行商務用 Microsoft Store 應用程式的語言
    - 選取 [**同步**處理], 以使用 Intune 同步處理商務應用程式的 Microsoft Store。
    - 確認 Microsoft Store for Business 與 Intune 之間的同步處理已啟用 (下一個步驟)。 

**確認 Intune 與 Microsoft Store for Business 之間的同步處理處於作用中狀態**
1. 使用 Microsoft Store for Business Admin account 登入[Microsoft store For business](https://businessstore.microsoft.com) 。
2. 選取 [**管理**]。
3. 選取 [**設定**], 然後選取 [**分散**]。
4. 在 [**管理工具**] 下, 確認已列出 Intune, 且狀態為 [已**啟用**]。  

<span id="2" />

## <a name="step-2-create-azure-ad-groups"></a>步驟 2: 建立 Azure AD 群組

為每個應用程式建立三個 Azure AD 群組。 下表概述您將需要的群組 (可供使用、需要和卸載)。 

應用程式指派類型 |   群組使用   | 範例 Azure AD 名稱
--- | --- | ---
可以使用 |  此應用程式可從公司入口網站應用程式或網站取得。 | MMD –*應用程式名稱*-可用
必要 |  應用程式會安裝在選取群組中的裝置上。 | MMD –*應用程式名稱*-必要
Uninstall |  從選取的群組中的裝置卸載應用程式。 | MMD –*應用程式名稱*–卸載

將您的使用者新增至這些群組, 以讓應用程式 availabe、安裝應用程式, 或從 Microsoft 受管理的電腦裝置中移除應用程式。 

<span id="3" />

## <a name="step-3-assign-apps-to-your-users"></a>步驟 3: 將應用程式指派給您的使用者

**將應用程式指派給您的使用者**

1. 登入[Microsoft 受管理的桌面管理入口網站](http://aka.ms/mmdportal)。
2. 在 [受管理的桌面] 窗格中選取 [**應用程式**]。
3. 在 [應用程式工作量] 中, 選取您要指派使用者的應用程式, 然後選取 [**指派使用者群組**]。
4. 針對特定應用程式, 選取 [工作分派類型] ([可用]、[必要]、[卸載]), 並指派適當的群組。
5. 在 [指派應用程式] 窗格中, 選取 **[確定]**。

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
