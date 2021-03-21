---
title: Microsoft Teams
description: 如何在裝置上安裝團隊以及如何在以後更新
keywords: Microsoft 受管理的桌面、Microsoft 365、服務、檔、應用程式、企業營運服務應用程式、LOB 應用程式
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

[團隊](https://www.microsoft.com/microsoft-365/microsoft-teams/group-chat-software) 是組織的 [郵件應用程式](https://support.microsoft.com/office/microsoft-teams-basics-6d5f52e6-5306-4096-ac24-c3082b79eaf0) ，也為您的組織提供即時共同作業和通訊、會議，以及檔案與應用程式共用的工作區。

## <a name="initial-deployment"></a>初始部署

大多數的硬體廠商尚未加入小組做為影像的一部分，因此 Microsoft Managed Desktop 會使用 Microsoft Intune 將小組部署至您的裝置。 所有受管理的裝置皆已安裝 [團隊 .msi 套件](/MicrosoftTeams/msi-deployment#how-the-microsoft-teams-msi-package-works) ，以確保登入裝置的所有使用者都有準備好使用的 Microsoft 團隊。 當套件第一次完成安裝時，小組會自動啟動並新增桌面的快捷方式。

### <a name="microsoft-intune-changes"></a>Microsoft Intune 變更

Microsoft Managed Desktop 將兩個應用程式新增至您的 Microsoft 小組 Azure AD 組織。 將其部署到適用于裝置的64位或32位用戶端：  

- 新式的工作場所–小組電腦內安裝程式 x64  
- 新式工作區-小組電腦範圍的安裝 x32

## <a name="updates"></a>更新

小組遵循來自 Microsoft 365 應用程式的不同更新路徑，而且桌面用戶端會自動更新自身。 小組每隔幾小時檢查一次更新，下載這些更新，然後等候電腦閒置，再無訊息安裝更新。  

「小組」產品群組不允許系統管理員控制更新，所以 Microsoft 受管理的桌面會使用標準的「 [自動更新」通道](/microsoftteams/teams-client-update#can-admins-deploy-updates-instead-of-teams-auto-updating)。

### <a name="manually-updating-teams"></a>手動更新團隊

個別使用者也可以從   應用程式右上角的 [ **設定檔**] 下拉式功能表中選取 [檢查更新]，以下載更新   。 如果有可用的更新，當電腦閒置時，它會被下載並以無訊息方式安裝。

## <a name="delivery-optimization-of-updates"></a>更新的傳遞優化

小組的傳遞優化預設會開啟，且不需要系統管理員或使用者採取任何動作。