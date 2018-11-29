---
title: 設定適用於 Windows 10 電腦的裝置保護設定
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: bd66c26c-73a4-45a8-8642-3ea4ee7cd89d
description: 了解預設和 Microsoft 365 商務安全 Windows 10 裝置的其他設定。
ms.openlocfilehash: ebfe5f59e544b67e5a4f2ecd990031e9221ff8e5
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/28/2018
ms.locfileid: "26866115"
---
# <a name="set-device-protection-settings-for-windows-10-pcs"></a>設定適用於 Windows 10 電腦的裝置保護設定

## <a name="secure-windows-10-devices"></a>保護 Windows 10 裝置

觀看如何使用 Microsoft 365 商務版 來保護 Windows 10 裝置的影片：
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/a5734146-620a-4cec-8618-536b3ca37972?autoplay=false]
  
1. 使用全域系統管理員認證登入 [Microsoft 365 商務版](https://portal.office.com)。 
    
2. 在管理中心的 [**裝置原則**在卡片上，選擇 [**新增原則**]。
    
    ![Device policies card in the admin center.](media/27c12b61-d112-4348-b557-4f3e46204797.png)
  
3. 在 [**新增原則**] 窗格中，輸入此原則的唯一名稱。 
    
4. 在**原則類型**] 下選擇 [ **Windows 10 裝置設定**]。
    
5. 依序展開 [**安全 Windows 10 裝置**\>您想方式進行設定。如需詳細資訊，請參閱[可用的設定](protection-settings-for-windows-10-pcs.md#bkmk_availablesettings)。 
    
    您一律可以回復成預設值使用**預設設定重設**] 連結。 
    
    ![Add policy pane with Windows 10 Device configuration selected](media/fa9e2dc2-7eae-4c96-af34-765a1f641ecf.png)
  
6. 接下來決定**誰將會得到這些設定？** 如果您不想要使用預設**的所有使用者**安全性群組選擇**變更**搜尋人員將會得到這些設定的 [安全性] 群組\>**選取**。
    
7. 最後，選擇 [**完成**儲存原則]，並將其指派給裝置。 
    
## <a name="available-settings"></a>可用的設定

根據預設**上**都所有設定。會提供下列設定。
  
如需詳細資訊，請參閱 [Microsoft 365 商務版中的保護功能如何對應 Intune 設定](map-protection-features-to-intune-settings.md)。 
  
|||
|:-----|:-----|
|設定  <br/> |描述  <br/> |
|使用 Windows Defender 防毒軟體來協助保護電腦免於遭受病毒與其他威脅的侵害  <br/> |需要開啟 Windows Defender 防毒軟體，以保護電腦免於遭受連接至網際網路時的安全威脅。  <br/> |
|協助保護電腦免於遭受 Microsoft Edge 中的網路安全威脅  <br/> |開啟 Microsoft Edge 中的設定，以協助保護使用者免受惡意網站與下載檔案的威脅。  <br/> |
|使用能減少裝置受攻擊面的規則  <br/> |設定為 [開啟] 時，受攻擊面縮減能協助系統封鎖惡意程式碼通常會用來感染裝置的動作和 App。只有在 Windows Defender 防毒軟體設為 [開啟] 時，這項設定才能夠使用。請參閱[縮減受攻擊面](https://go.microsoft.com/fwlink/?linkid=870417)以深入了解。  <br/> |
|保護資料夾來抵擋勒索軟體等威脅  <br/> |這項設定使用受控資料夾存取權來保護公司資料，不讓可疑或惡意的 App 修改。系統會封鎖這類型的 App，不讓它們變更受保護資料夾中的資料。只有在 Windows Defender 防毒軟體設為 [開啟] 時，這項設定才能夠使用。請參閱[使用受控資料夾存取權來保護資料夾](https://go.microsoft.com/fwlink/?linkid=870418)以深入了解。  <br/> |
|避免連線到網際網路上可能有惡意之內容的網路存取行為  <br/> |請使用這項設定來封鎖前往聲譽不佳之網際網路位置 (可能裝載了網路釣魚詐騙郵件、惡意探索或其他惡意內容) 的連外使用者連線。只有在 Windows Defender 防毒軟體設為 [開啟] 時，這項設定才能夠使用。請參閱[保護您的網路](https://go.microsoft.com/fwlink/?linkid=870419)以深入了解。  <br/> |
|利用 BitLocker 來協助您保護電腦上的檔案和資料夾，抵擋未經授權的存取行為  <br/> |Bitlocker 能為電腦硬碟加密來保護資料，以及在電腦遺失或遭竊時保護資料來避免資料外洩。如需詳細資訊，請參閱 [Bitlocker 常見問題集](https://go.microsoft.com/fwlink/?linkid=871000)。  <br/> |
|允許使用者從 Microsoft Store 下載 App  <br/> |可讓使用者從下載及安裝的應用程式之 Microsoft 存放區。應用程式包含每個項目從遊樂場生產力工具]，讓我們保留**在**此設定，但您可以將它關閉的額外安全性。<br/> |
|允許使用者存取 Cortana  <br/> |Cortana 可以是非常有用 ！她可以設定開啟或關閉您、 授與指示，並請確定您已對時間的約會 （英文），因此我們保留此**上**預設。<br/> |
|允許使用者接收來自 Microsoft 的 Windows 祕訣和廣告  <br/> |Windows 祕訣相當實用，並且能在新功能推出時引導使用者。  <br/> |
|自動讓 Windows 10 裝置保持在最新狀態  <br/> |確保 Windows 10 裝置能自動收到最新的更新。  <br/> |
|閒置這段時間之後關閉裝置螢幕  <br/> |確保使用者閒置時，公司資料已受到保護。使用者可能會在咖啡館等公共場所工作，當使用者暫時離開或是分心時，他們的裝置就容易受到他人任意窺伺。此設定能讓您控制螢幕將於使用者閒置多久之後關閉。  <br/> |
   
  

