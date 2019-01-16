---
title: 準備 Microsoft 應用程式受管理的桌面
description: ''
keywords: Microsoft 受管理的桌上型電腦、 [Microsoft 365 服務、 文件
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.openlocfilehash: b46e3de4a4cfe2140574ab9fc589e3a738bd2e17
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/16/2019
ms.locfileid: "26866322"
---
# <a name="preparing-apps-for-microsoft-managed-desktop"></a>準備 Microsoft 應用程式受管理的桌面

<!--This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.-->

<!--Applications: supported/onboard/deployment -->
 
查看 Microsoft 及 Microsoft 受管理的桌上型電腦的客戶同樣也請有重大、 尚未不同責任周圍搭配 Microsoft 受管理的桌上型電腦的應用程式。

## <a name="microsoft-responsibilities"></a>Microsoft 責任
**Office 365 應用程式**Microsoft 會提供完整的部署、 更新及支援的特定 Office 365 應用程式的服務。所有使用者會都收到基底的 Office 365 按一下此選項即可執行 64 位元版本的應用程式，讓使用者可以快速上手裝置的映像中包含一組。專案與 Visio 應用程式中的 Office 365 套裝軟體分別授權。 Microsoft 受管理的桌上型電腦會提供讓 IT 系統管理員管理授權及部署這些應用程式適當的組織部署群組。Microsoft 支援透過 Microsoft 受管理的桌上型電腦支援通道這些應用程式的使用者。

**企業營運系統應用程式**Microsoft 提供的管理及部署給使用者及其企業營運 (LOB) 應用程式作為 Intune 產品的一部分的 it 專業人員適用的工具。Microsoft 支援依照[企業營運系統應用程式](#line-of-business-applications)中的應用程式部署問題 

**部署 intune**Intune Microsoft 受管理的桌上型電腦 onboarding 允許採購應用程式，以透過 Intune 部署期間要連結到**Microsoft Store for Business** 。使 IT 管理員可以為使用者提供自助體驗 Microsoft 也會為一般使用者部署的公司入口網站的 web 型版本。

**應用程式的管理**Microsoft 可能會識別因其系統影響不適當的現代工作場所限制應用程式。識別應用程式時 Microsoft 將通知客戶與該應用程式需要移除租用戶。 

受限制的應用程式行為和應用程式需求的詳細資訊，請參閱[Microsoft 受管理的桌面應用程式需求](../service-description/mmd-app-requirements.md)

## <a name="customer-responsibilities"></a>客戶責任
Office 365 套裝軟體 Microsoft 的產能方案的核心和隨附於 Microsoft 365 授權的 Microsoft 受管理的桌上型電腦的所有使用者。Microsoft 會部署、 更新、 以及支援 Microsoft 受管理的桌上型電腦裝置的 Office 應用程式時仍有某些客戶會負責的區域。
- **將授權指派**-客戶負責將適當的授權指派給 Office 365 的使用者。 
- **新增使用者至安全性群組**-客戶與使用者需要 [專案] 或 [Visio IT 系統管理員必須那些將使用者新增至適當的部署群組。IT 系統管理員也是週期的負責管理這些使用者結束。 
- **新增元件部署 Office 365** -客戶負責部署到 Office 365 套裝軟體這必要的任何增益集。 

由於企業營運系統 (LOB) 應用程式是唯一的每個客戶、 客戶是負責管理未部署 microsoft 其組織內的所有應用程式。這包括：
- 決定需要哪些應用程式及誰需要它們
- 指派給這些使用者的應用程式
- 建立及維護 Azure Active Directory (AD) 群組來管理應用程式的工作分派 

客戶必須將 LOB 應用程式上傳至 Intune。他們是然後負責部署、 更新及透過其各自的生命週期解除委任這些應用程式以及管理其使用者針對這些應用程式的支援。

## <a name="office-applications"></a>Office 應用程式
Microsoft 365 E5 授權的一部分，是由 Microsoft 部署 Office 365 Standard Suite （64 位元）。 

如需詳細資訊，請參閱[Microsoft 受管理的桌上型電腦技術](../intro/technologies.md)<!--- and the other applications licensed under Office 365 E5 may be deployed by the customer using Intune’s deployment tools.-->

## <a name="line-of-business-applications"></a>企業營運系統應用程式
下表摘要責任跨企業營運系統 (LOB) 應用程式不同的階段。 

應用程式工作項目 |    客戶    | Microsoft
--- | --- | ---
**Onboarding 應用程式** |  |
識別應用程式所需的目標的使用者群組   | ![是](images/checkmark.png)  |
建立及管理的應用程式部署 Azure AD 群組 | ![是](images/checkmark.png) |   
**應用程式封裝** |  |
封裝應用程式，以符合 Intune 部署標準 （英文） |  ![是](images/checkmark.png) |  
將應用程式上傳至 Intune | ![是](images/checkmark.png)     |
Microsoft 受管理的桌上型電腦環境中測試應用程式 |    ![是](images/checkmark.png) |  
測試使用者的應用程式    | ![是](images/checkmark.png) |    
**部署** | |
管理，並將使用者指派至應用程式  | ![是](images/checkmark.png)  |
Intune 部署工具將傳遞給遠端用戶端應用程式| |   ![是](images/checkmark.png)
識別及部署到 Intune 的應用程式更新 | ![是](images/checkmark.png)    |
Unistall 及移除應用程式時已遭淘汰    | ![是](images/checkmark.png) |    
**管理** | |
購買和指派授權 |   ![是](images/checkmark.png)     |
提供企業營運系統應用程式的使用者支援  | ![是](images/checkmark.png) |
管理應用程式設定遠端    | ![是](images/checkmark.png) |

如需 LOB 應用程式需求的資訊，請參閱[Microsoft 受管理的桌面應用程式需求](../service-description/mmd-app-requirements.md)


## <a name="intune-application-deployment"></a>Intune 應用程式部署
透過 Microsoft 受管理的桌上型電腦管理入口網站或 Intune 入口網站可處理應用程式管理。Intune 的 app management 入口網站會顯示為 Windows、 Android、 及 iOS 部署的應用程式。Microsoft 受管理的桌上型電腦管理入口網站會限制 Windows 10 應用程式的檢視。二者都可透過 Azure 入口網站。 
* [Intune 應用程式管理基礎 （英文)](https://docs.microsoft.com/intune/app-management)
* [將應用程式新增至 Intune](https://docs.microsoft.com/intune/app-management)
   * [新增企業營運系統應用程式](https://docs.microsoft.com/intune/lob-apps-windows)
   * [將 Win32 應用程式新增至 Intune](https://docs.microsoft.com/intune/apps-win32-app-management)
   * [新增 web 應用程式](https://docs.microsoft.com/intune/web-app)
* [部署應用程式](https://docs.microsoft.com/intune/apps-deploy)
   * [將應用程式部署至 Windows 10](https://docs.microsoft.com/intune/apps-windows-10-app-deploy)
* 公司入口網站
   * [部署的公司入口網站](https://docs.microsoft.com/intune/store-apps-company-portal-app)
   * [設定公司入口網站應用程式](https://docs.microsoft.com/intune/company-portal-app)
