---
title: 保護 Windows 10 裝置
f1.keywords:
- CSH
ms.author: sirkkuw
author: sirkkuw
manager: scotv
audience: Admin
ms.topic: conceptual
f1_keywords:
- O365E_BCSSetup4WindowsConfig
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 21e5551f-fa35-4f13-9418-f80d668b6a2b
description: 瞭解設定 Windows 10 裝置在登入其工作或學校帳戶時，可接收之預設裝置原則的設定。
ms.openlocfilehash: 85448507835b6310ca4136849be6a40caf6bb919
ms.sourcegitcommit: abf63669daf12993ad3353e4b578f41c8910b20f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/27/2020
ms.locfileid: "47289070"
---
# <a name="secure-windows-10-devices"></a>保護 Windows 10 裝置

本文適用于 Microsoft 365 商務版 Premium。

您在此進行的設定為預設 Windows 10 裝置原則的一部分。 透過其工作帳戶登入，所有連接 Windows 10 裝置的使用者（包括行動裝置和電腦）都會自動接收這些設定。 建議您在設定時先接受預設原則，並於稍後新增以特定使用者群組為目標的原則。
  
## <a name="settings-to-secure-windows-10-devices"></a>保護 Windows 10 裝置的設定

所有設定預設為 [ **開啟**]。 下列為可用的設定：
  
|||
|:-----|:-----|
|設定  <br/> |描述  <br/> |
|使用 Windows Defender 防毒軟體來協助保護電腦免於遭受病毒與其他威脅的侵害  <br/> |需要開啟 Windows Defender 防毒軟體，以保護電腦免於遭受連接至網際網路時的安全威脅。  <br/> |
|協助保護電腦免於遭受 Microsoft Edge 中的網路安全威脅  <br/> |開啟 Microsoft Edge 中的設定，以協助保護使用者免受惡意網站與下載檔案的威脅。  <br/> |
|利用 BitLocker 來協助您保護電腦上的檔案和資料夾，抵擋未經授權的存取行為  <br/> |Bitlocker 能為電腦硬碟加密來保護資料，以及在電腦遺失或遭竊時保護資料來避免資料外洩。 如需詳細資訊，請參閱 [BITLOCKER FAQ](https://go.microsoft.com/fwlink/?linkid=871000)。  <br/> |
|閒置這段時間之後關閉裝置螢幕  <br/> |確保使用者閒置時，公司資料已受到保護。使用者可能會在咖啡館等公共場所工作，當使用者暫時離開或是分心時，他們的裝置就容易受到他人任意窺伺。此設定能讓您控制螢幕將於使用者閒置多久之後關閉。  <br/> |
|