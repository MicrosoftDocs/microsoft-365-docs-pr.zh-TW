---
title: 準備應用程式以使用 Microsoft 受管理的電腦
description: ''
keywords: Microsoft 受管理的電腦，Microsoft 365 服務，文件
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.collection: M365-modern-desktop
ms.openlocfilehash: be28760fc3facdb21643943ace11deda378d437c
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32289061"
---
# <a name="preparing-apps-for-microsoft-managed-desktop"></a>準備應用程式以使用 Microsoft 受管理的電腦

<!--This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.-->

<!--Applications: supported/onboard/deployment -->
 
Microsoft 和 Microsoft 受管理電腦的客戶同樣也有重大、 尚未不同職責周圍搭配 Microsoft 受管理電腦的應用程式。

## <a name="microsoft-responsibilities"></a>Microsoft 責任
**Office 365 應用程式**Microsoft 會提供完整的部署、 更新和支援的特定的 Office 365 應用程式的服務。 所有使用者會都收到 Office 365 隨執行，以便使用者可以快速上手，裝置的映像中包含的應用程式 64 位元版本的基底集。 Project 和 Visio 應用程式中的 Office 365 套件將分別獲得授權。  Microsoft 受管理的電腦會提供讓 IT 系統管理員管理授權及部署這些應用程式適當地為其組織的部署群組。 Microsoft 將會支援透過 Microsoft 受管理的桌上型電腦支援頻道這些應用程式的使用者。

**營運應用程式**Microsoft 提供工具的 IT 系統管理員管理及部署至使用者其-營運 (LOB) 應用程式作為 Intune 產品的一部分。 Microsoft 將支援如同詳細的[行的商務應用程式](#line-of-business-applications)的應用程式部署問題 

**使用 Intune 部署**Intune 會連結至**商務用 Microsoft Store** ，讓採購應用程式以透過 Intune 部署 Microsoft 受管理的電腦上架期間。 Microsoft 也會部署至使用者從 Microsoft 網上商店的公司入口網站應用程式，以便 IT 系統管理員可以為使用者提供自助體驗。

**應用程式管理**Microsoft 可能會找出受限制的應用程式，這並不適合現代化工作場所增進因其系統的影響。 識別此類應用程式時 Microsoft 將會通知客戶，而該應用程式需要從租用戶中移除。 

如需有關受限制的應用程式行為和應用程式需求的詳細資訊，請參閱 < <b0>Microsoft 受管理的電腦應用程式需求</b0>

## <a name="customer-responsibilities"></a>客戶責任
Office 365 套件是核心 Microsoft 的生產力供應項目，隨附於 Microsoft 受管理電腦的所有使用者的 Microsoft 365 授權。 Microsoft 部署、 更新，以及支援 Microsoft 受管理的電腦裝置的 Office 應用程式時仍有一些客戶有責任的區域。
- **指派授權**的客戶負責將適當的授權指派給使用者的 Office 365。 
- **新增使用者至安全性群組**-的客戶與使用者需要 Project 或 Visio，IT 系統管理員必須將這些使用者加入適當的部署群組。 IT 系統管理員也負責管理這些使用者的生命週期結束。 
- **新增元件部署 Office 365**的客戶負責部署至 Office 365 套件這必要的任何增益集。 

由於-營運 (LOB) 應用程式是唯一的每個客戶，客戶負責管理其組織未部署由 Microsoft 中的所有應用程式。 其中包括：
- 決定哪些應用程式所需及他們需要由誰
- 將應用程式指派給這些使用者
- 建立及管理應用程式的工作分派的維護 Azure Active Directory (AD) 群組 

客戶必須將 LOB 應用程式上傳到 Intune。 然後，他們必須負責部署、 更新，並透過其各自的週期，解除委任這些應用程式，以及管理這些應用程式的使用者的支援。

## <a name="office-applications"></a>Office 應用程式
Microsoft 365 E5 授權的一部分，Microsoft 被部署 Office 365 Standard Suite （64 位元）。 

如需詳細資訊，請參閱 < <b0>Microsoft 受管理電腦技術</b0> <!--- and the other applications licensed under Office 365 E5 may be deployed by the customer using Intune’s deployment tools.-->

## <a name="line-of-business-applications"></a>線條的商務應用程式
下表總結了責任，跨-營運 (LOB) 應用程式的不同階段。 

應用程式的工作項目 |    客戶    | Microsoft
--- | --- | ---
**上架應用程式** |  |
識別應用程式所需的目標的使用者群組   | ![是](images/checkmark.png)  |
建立及管理應用程式部署 Azure AD 群組 | ![是](images/checkmark.png) |   
**應用程式封裝** |  |
封裝應用程式，以符合 Intune 部署標準 |  ![是](images/checkmark.png) |  
將應用程式上傳到 Intune | ![是](images/checkmark.png)     |
Microsoft 受管理的桌上型電腦環境中測試應用程式 |    ![是](images/checkmark.png) |  
測試與使用者的應用程式    | ![是](images/checkmark.png) |    
**部署** | |
管理，並將使用者指派給應用程式  | ![是](images/checkmark.png)  |
Intune 部署工具會傳遞至遠端用戶端應用程式| |   ![是](images/checkmark.png)
識別並部署到 Intune 應用程式更新 | ![是](images/checkmark.png)    |
Unistall] 和 [移除應用程式時已停用    | ![是](images/checkmark.png) |    
**管理** | |
視需要而定，並指派授權 |   ![是](images/checkmark.png)     |
提供-營運應用程式的使用者支援  | ![是](images/checkmark.png) |
管理應用程式設定遠端    | ![是](images/checkmark.png) |

如需 LOB 應用程式需求的詳細資訊，請參閱 < <b0>Microsoft 受管理的電腦應用程式需求</b0>


## <a name="intune-application-deployment"></a>Intune 應用程式部署
透過 Microsoft 受管理的桌上型電腦系統管理入口網站，或透過 Intune 入口網站，可以處理應用程式管理。 Intune 的應用程式管理入口網站顯示部署 for Windows、 Android 和 iOS 的應用程式。 Microsoft 受管理的桌上型電腦系統管理入口網站限制檢視以 Windows 10 應用程式。 兩者都可透過 Azure 入口網站。 
* [Intune 應用程式管理基本概念](https://docs.microsoft.com/intune/app-management)
* [將應用程式新增至 Intune](https://docs.microsoft.com/intune/app-management)
   * [新增-營運應用程式](https://docs.microsoft.com/intune/lob-apps-windows)
   * [將 Win32 應用程式新增至 Intune](https://docs.microsoft.com/intune/apps-win32-app-management)
   * [新增 web 應用程式](https://docs.microsoft.com/intune/web-app)
* [部署應用程式](https://docs.microsoft.com/intune/apps-deploy)
   * [將應用程式部署至 Windows 10](https://docs.microsoft.com/intune/apps-windows-10-app-deploy)
* 公司入口網站
   * [部署在公司入口網站](https://docs.microsoft.com/intune/store-apps-company-portal-app)
   * [設定公司入口網站應用程式](https://docs.microsoft.com/intune/company-portal-app)
