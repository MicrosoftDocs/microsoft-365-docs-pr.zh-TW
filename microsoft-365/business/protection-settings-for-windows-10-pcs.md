---
title: 為 Windows 10 電腦編輯或建立裝置保護設定
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
manager: scotv
audience: Admin
ms.topic: article
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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: bd66c26c-73a4-45a8-8642-3ea4ee7cd89d
description: 瞭解可在 Microsoft 365 for business to secure Windows 10 裝置的設定。
ms.openlocfilehash: acfb27b2e4592d4ed1e446a63c9495ae07d916de
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/02/2021
ms.locfileid: "51578220"
---
# <a name="edit-or-create-device-protection-settings-for-windows-10-pcs"></a>為 Windows 10 電腦編輯或建立裝置保護設定

本文適用于 Microsoft 365 商務進階版。

在設定頁面上設定預設 Windows 保護設定後，您可以新增套用至所有使用者或一組使用者的新保護設定。 您也可以編輯任何已建立的專案。

## <a name="create-protection-settings-for-windows-10-devices"></a>為 Windows 10 裝置建立保護設定

觀看如何使用 Microsoft 365 商務進階版保護 Windows 10 裝置的影片：
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/a5734146-620a-4cec-8618-536b3ca37972?autoplay=false]
  
1. 移至位於 <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> 的系統管理中心。 
2. 在左側導覽中，選擇 [ **裝置** \> **原則**] [ \> **新增**]。
3. 在 [ **新增原則** ] 窗格中，輸入這個原則的唯一名稱。 
4. 在 [**原則類型**] 底下，選擇 [ **Windows 10 裝置** 設定]。
5. 展開 [**安全的 Windows 10 裝置**] 設定 \> 您想要的設定。 如需詳細資訊，請參閱 [可用設定](#available-settings)。 
    
    您可以隨時使用 [ **重設預設值設定** ] 連結，以回到預設設定。 
    
    ![Add policy pane with Windows 10 Device configuration selected](../media/fa9e2dc2-7eae-4c96-af34-765a1f641ecf.png)
  
6. 下一步決定 **神秘會取得這些設定嗎？** 如果您不想要使用預設的 [ **所有使用者** ] 安全性群組，請選擇 [ **變更**]，然後搜尋將取得這些設定的安全性群組 \> ****。
7. 最後，選擇 [ **完成** ] 以儲存原則，並將其指派給裝置。 

## <a name="edit-windows-10-protection-settings"></a>編輯 Windows 10 保護設定
 
1. 移至位於 <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> 的系統管理中心。     
2. 在左側導覽中，選擇 [ **裝置** \> **原則** ]。
1. 選擇現有的 Windows 裝置原則，然後 **編輯**。
1. 選擇您要變更的設定旁的 [ **編輯** ]，然後再按一下 [ **儲存**]。

## <a name="available-settings"></a>可用的設定

所有設定預設為 [ **開啟**]。 下列為可用的設定。
  
如需詳細資訊，請參閱[Microsoft 365 中的保護功能進階版對應至 Intune 設定](map-protection-features-to-intune-settings.md)。 
  
|||
|:-----|:-----|
|設定  <br/> |描述  <br/> |
|使用 Windows Defender 防毒軟體來協助保護電腦免於遭受病毒與其他威脅的侵害  <br/> |需要開啟 Windows Defender 防毒軟體，以保護電腦免於遭受連接至網際網路時的安全威脅。  <br/> |
|協助保護電腦免於遭受 Microsoft Edge 中的網路安全威脅  <br/> |開啟 Microsoft Edge 中的設定，以協助保護使用者免受惡意網站與下載檔案的威脅。  <br/> |
|使用能減少裝置受攻擊面的規則  <br/> |設定為 [開啟] 時，受攻擊面縮減能協助系統封鎖惡意程式碼通常會用來感染裝置的動作和 App。只有在 Windows Defender 防毒軟體設為 [開啟] 時，這項設定才能夠使用。請參閱[縮減受攻擊面](/windows/security/threat-protection/microsoft-defender-atp/exploit-protection)以深入了解。  <br/> |
|保護資料夾來抵擋勒索軟體等威脅  <br/> |這項設定使用受控資料夾存取權來保護公司資料，不讓可疑或惡意的 App 修改。 系統會封鎖這類型的 App，不讓它們變更受保護資料夾中的資料。 只有在 Windows Defender 防毒軟體設為 [開啟] 時，這項設定才能夠使用。 請參閱 [使用可控資料夾存取保護資料夾](/mem/configmgr/protect/deploy-use/create-deploy-exploit-guard-policy#bkmk_CFA) 以深入瞭解。  <br/> |
|避免連線到網際網路上可能有惡意之內容的網路存取行為  <br/> |使用此設定來封鎖向低信譽 Internet 位置（可能會主控網路釣魚詐騙、入侵或其他惡意內容）的外寄使用者連線。 只有在 Windows Defender 防毒軟體設定為 [**開啟**] 時，才可使用此設定。 如需詳細資訊，請參閱 [保護您的網路](/windows/security/threat-protection/windows-defender-antivirus/configure-real-time-protection-windows-defender-antivirus)。  <br/> |
|利用 BitLocker 來協助您保護電腦上的檔案和資料夾，抵擋未經授權的存取行為  <br/> |Bitlocker 能為電腦硬碟加密來保護資料，以及在電腦遺失或遭竊時保護資料來避免資料外洩。 如需詳細資訊，請參閱 [BITLOCKER FAQ](/windows/security/information-protection/bitlocker/bitlocker-frequently-asked-questions)。  <br/> |
|允許使用者從 Microsoft Store 下載 App  <br/> |讓使用者從 Microsoft Store 下載並安裝 App。 應用程式包括從遊戲到生產力工具的所有專案，因此我們將此設定保留為 **開啟**，但您可以關閉此設定，以進行額外的安全性。  <br/> |
|允許使用者存取 Cortana  <br/> |Cortana 非常實用！ Cortana 可以為您開啟或關閉您的設定、提供行車方案，並確定您已開啟約會時間，因此我們預設會將此設定保留為 **開啟** 。  <br/> |
|允許使用者接收來自 Microsoft 的 Windows 祕訣和廣告  <br/> |Windows 祕訣相當實用，並且能在新功能推出時引導使用者。  <br/> |
|自動讓 Windows 10 裝置保持在最新狀態  <br/> |確保 Windows 10 裝置能自動收到最新的更新。  <br/> |
|閒置這段時間之後關閉裝置螢幕  <br/> |確保使用者閒置時，公司資料已受到保護。使用者可能會在咖啡館等公共場所工作，當使用者暫時離開或是分心時，他們的裝置就容易受到他人任意窺伺。此設定能讓您控制螢幕將於使用者閒置多久之後關閉。  <br/> |