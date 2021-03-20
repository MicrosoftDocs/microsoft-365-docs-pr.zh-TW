---
title: 建立整個組織的簽名和免責聲明
f1.keywords:
- NOCSH
ms.author: twerner
author: twernermsft
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- TRN_M365B
- OKR_SMB_Videos
- seo-marvel-may2020
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 2d75860f-c527-4352-a7f6-73eba54c0c72
description: 瞭解如何管理電子郵件簽名，包括輸入或離開組織之所有電子郵件的法律免責聲明或披露聲明。
ms.openlocfilehash: b599ef8b6d0bb236b6111bae86c92409601e00d0
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50914231"
---
# <a name="create-organization-wide-signatures-and-disclaimers"></a>建立整個組織的簽名和免責聲明

 您可以在進入或離開組織的電子郵件中新增電子郵件簽章、法律免責聲明或披露報表，以管理電子郵件簽名。 您可以如下所示，設定將它套用至所有內送或外寄郵件。 或者您也可以將它套用至特定郵件，例如包含特定字詞或文字模式的郵件。

 觀賞有關如何建立全公司的電子郵件簽名的簡短影片。 <br><br>
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1IEWf] 

如果您覺得這段影片很有幫助，請查看[適用於小型企業和 Microsoft 365 新手的完整訓練系列](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)。

## <a name="create-a-signature-that-applies-to-all-messages"></a>建立套用至所有郵件的簽名

> [!TIP]
> 全組織的簽名稱為「免責聲明」，不論包括什麼。 例如，他們可以只是簽名，也可以包含您想要的位址、法律免責聲明或其他資訊。
    
::: moniker range="o365-worldwide"

移至位於 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 的系統管理中心。

::: moniker-end

::: moniker range="o365-germany"

移至位於 <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a> 的系統管理中心。

::: moniker-end

::: moniker range="o365-21vianet"

移至位於 <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn/adminportal</a> 的系統管理中心。

::: moniker-end

1. 選取應用程式啟動器 ![ 圖示 ](../../media/7502f4ec-3c9a-435d-a7b4-b9cda85189a7.png) ，然後選取 [ **管理**]。
   
    Can't find the app you're looking for? 從應用程式啟動器中，選取 [ **所有應用程式** ]，以查看您可以使用之應用程式的字母順序清單。 From there, you can search for a specific app. 
    
2. 選取 [系統 **管理中心**]，然後選擇 [ **Exchange**]。
    
3. 在 [郵件流程] 下，選取 [ **規則**]。
    
4. 選取 [ **+** (Add) 圖示，然後選擇 [套用 **免責聲明**]。
    
5. 為這個規則命名。
    
6. 在 [套用 **此規則**] 底下，選取 **[套用到所有郵件]**。
    
    > [!TIP]
    > [深入了解](/Exchange/policy-and-compliance/mail-flow-rules/signatures#Scoping)您不想將免責聲明套用至所有郵件時的套用條件。  (此範圍的文章適用于 Exchange Server，但也適用于 Microsoft 365。 )  
  
7. 在 [執行下列作業] 底下，保留 **[附加免責聲明** ] 選取狀態。 
    
8.  選取 [ **輸入文字** ]，然後輸入免責聲明。 
    
    > [!TIP]
    > [深入了解](/Exchange/policy-and-compliance/mail-flow-rules/signatures#FormatDisclaimer)如何設定免責聲明格式。  (此格式化文章適用于 Exchange Server，但也適用于 Microsoft 365。 )  

9. 選取 [ **選取其中一項** ]，然後選擇 [ **包裝** 為回退] 選項。 然後按一下 **[確定]**。 這表示，該免責聲明如果因為加密或其他郵件設定而無法新增，系統會將它包裝在郵件信封中。
    
10. 選取 [ **以嚴重性層級審核此規則** ]。 然後選擇 [ **低**]、[ **中**] 或 [ **高** ]，以用於消息記錄檔。 
    
11. 選擇 [ **強制** ] 立即開啟免責聲明，除非您要先加以測試。 
    
12. 選擇 [ **更多選項** ] 以包含其他條件或例外狀況。 
    
13. 完成後，請選擇 [ **儲存** ]。 
    
## <a name="limitations-of-organization-wide-signatures"></a>組織的寬碼限制

在 Microsoft 365 中管理電子郵件簽名時，無法執行下列動作：
  
- 將簽章直接插入最近的電子郵件回復或轉寄
    
- 在使用者的 [已傳送的郵件] 資料夾中顯示伺服器端的電子郵件簽名
    
- 在電子郵件簽名中嵌入影像
    
- 略過包含無法更新的變數的列 (例如，因為沒有為使用者提供值) 
    
若要取得這些和其他功能來管理電子郵件簽名，請使用協力廠商工具。 請對 **電子郵件簽名軟體** 執行網際網路搜尋。 許多提供者都是 Microsoft 金牌合作夥伴，其軟體會提供這些功能。 
  
## <a name="more-resources"></a>其他資源

- 如需使用 PowerShell 的詳細資訊，請參閱 [整個組織郵件免責聲明、簽章、頁尾或 Exchange Online 中的標頭](/exchange/security-and-compliance/mail-flow-rules/disclaimers-signatures-footers-or-headers) 。