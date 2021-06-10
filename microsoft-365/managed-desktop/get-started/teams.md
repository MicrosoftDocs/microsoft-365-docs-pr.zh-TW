---
title: Microsoft Teams
description: 如何在裝置上安裝 Teams，以及之後更新
keywords: Microsoft 受管理的電腦、Microsoft 365、服務、檔、應用程式、商務營運應用程式、LOB 應用程式
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: ITPro
ms.openlocfilehash: 01a3adc7829bbb94f36649f69ba6ef15dbe6b3c2
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50920653"
---
# <a name="microsoft-teams"></a>Microsoft Teams

[Teams](https://www.microsoft.com/microsoft-365/microsoft-teams/group-chat-software)是組織的[郵件應用程式](https://support.microsoft.com/office/microsoft-teams-basics-6d5f52e6-5306-4096-ac24-c3082b79eaf0)，也提供即時共同作業和通訊、會議，以及檔案與應用程式共用的工作區。

## <a name="initial-deployment"></a>初始部署

大多數的硬體廠商尚不會將 Teams 納入映射的一部分，所以 Microsoft 受管理的電腦使用 Microsoft Intune 將 Teams 部署到裝置。 所有受管理的裝置皆已安裝[Teams .msi 套件](/MicrosoftTeams/msi-deployment#how-the-microsoft-teams-msi-package-works)，以確保登入裝置的所有使用者都已 Microsoft Teams 準備好使用。 當套件第一次完成安裝時，Teams 會自動啟動，並新增桌面的快捷方式。

### <a name="microsoft-intune-changes"></a>Microsoft Intune 變更

Microsoft 受管理的電腦會將兩個應用程式新增至您的 Azure AD 組織，以供 Microsoft Teams。 將其部署到適用于裝置的64位或32位用戶端：  

- 新式工作場所– Teams 機器寬安裝程式 x64  
- 新式工作場所– Teams 機器寬安裝 x32

## <a name="updates"></a>更新

Teams 會從 Microsoft 365 Apps 企業版進行個別的更新路徑，而且桌面用戶端會自動更新自身。 Teams 每隔幾小時檢查一次更新，下載這些更新，然後等候電腦閒置，再以無訊息方式安裝更新。  

Teams 的產品群組不允許系統管理員控制更新，所以 Microsoft 受管理的電腦使用[標準的自動更新通道](/microsoftteams/teams-client-update#can-admins-deploy-updates-instead-of-teams-auto-updating)。

### <a name="manually-updating-teams"></a>手動更新 Teams

個別使用者也可以從   應用程式右上角的 [ **設定檔**] 下拉式功能表中選取 [檢查更新]，以下載更新   。 如果有可用的更新，當電腦閒置時，它會被下載並以無訊息方式安裝。

## <a name="delivery-optimization-of-updates"></a>更新的傳遞優化

預設會開啟 Teams 更新的傳遞優化，不需要系統管理員或使用者採取任何動作。