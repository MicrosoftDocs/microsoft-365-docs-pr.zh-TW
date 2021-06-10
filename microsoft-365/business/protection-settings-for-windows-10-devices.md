---
title: 編輯或設定 Windows 10 裝置的應用程式保護設定
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
manager: scotv
audience: Admin
ms.topic: article
f1_keywords:
- Win10AppPolicy
- O365E_Win10AppPolicy
- BCS365_Win10AppPolicy
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
ms.assetid: 02e74022-44af-414b-9d74-0ebf5c2197f0
description: 瞭解如何建立或編輯使用者個人 Windows 10 裝置上的應用程式管理原則及保護工作檔。
ms.openlocfilehash: aa270c563e6bdce6fd48f8713d7db3ce23921925
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/02/2021
ms.locfileid: "51580007"
---
# <a name="set-or-edit-application-protection-settings-for-windows-10-devices"></a>設定或編輯 Windows 10 裝置的應用程式保護設定

本文適用于 Microsoft 365 商務進階版。

## <a name="edit-an-app-management-policy-for-windows-10"></a>編輯 Windows 10 的應用程式管理原則

1. 移至位於 <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> 的系統管理中心。     
2. 在左側導覽中，選擇 [ **裝置** \> **原則** ]。
1. 選擇現有的 Windows 應用程式原則，然後 **編輯**。
1. 選擇您要變更的設定旁的 [ **編輯** ]，然後再按一下 [ **儲存**]。

## <a name="create-an-app-management-policy-for-windows-10"></a>建立適用於 Windows 10 的應用程式管理原則

如果您的使用者擁有個人 Windows 10 裝置並會在其中處理工作的話，您也可以在保護您在這些裝置上的資料。
  
1. 移至位於 <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> 的系統管理中心。 
2. 在左側導覽中，選擇 [ **裝置** \> **原則**] [ \> **新增**]。
3. 在 [ **新增原則** ] 窗格中，輸入這個原則的唯一名稱。 
4. 在 [**原則類型**] 底下，選擇 [**應用程式管理] Windows 10**。
5. 在 [ **裝置類型**] 底下，選擇 [ **個人** 或 **公司擁有**]。
6. **加密工作** 檔案會自動開啟。 
7. 如果您不想讓使用者將工作檔案儲存在其 **電腦上**，請將 [**防止使用者將公司資料複製到個人檔案，並強制使用者** 將工作檔案儲存至] 商務用 OneDrive。 
9. 展開 **Windows 裝置上的復原資料**。 我們建議您 **將其開啟**。
    您必須先建立資料修復代理憑證，才能瀏覽至其位置。 如需相關指示，請參閱 [Create and verify an (EFS) Data Recovery Agent (DRA) 憑證](/windows/security/information-protection/windows-information-protection/create-and-verify-an-efs-dra-certificate)。
    
    根據預設，工作檔案加密所使用的祕密金鑰會儲存在裝置中，且與使用者設定檔關聯。 只有該使用者可以開啟並解密該檔案。 不過，如果裝置遺失或是使用者遭到移除，檔案就會一直停留在加密狀態。 系統管理員可以使用資料復原代理程式 (DRA) 憑證來解密檔案。
    
    ![Browse to Data Recovery Agent certificate.](../media/7d7d664f-b72f-4293-a3e7-d0fa7371366c.png)
  
10. 如果您想要新增其他網域或 SharePoint 線上位置，請展開 [**保護其他網路和雲端位置**]，以確保所有列出之應用程式中的檔案受到保護。 如果您需要為任何欄位輸入多個項目，請在每個項目之間插入分號 (;)。
    
    ![Expand Protect additional network and cloud locations, and enter domains or SharePoint Online sites you own.](../media/7afaa0c7-ba53-456d-8c61-312c45e09625.png)
  
11. 下一步決定 **神秘會取得這些設定嗎？** 如果您不想要使用預設的 [ **所有使用者** ] 安全性群組，請選擇 [ **變更**]，然後選取將取得這些設定的安全性群組 \> ****。
12. 最後，選擇 [ **新增** ] 以儲存原則，並將其指派給裝置。