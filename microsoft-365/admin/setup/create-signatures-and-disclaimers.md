---
title: 建立整個組織的簽章及免責聲明
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 2d75860f-c527-4352-a7f6-73eba54c0c72
description: 了解如何新增進入或離開貴組織的所有電子郵件訊息的電子郵件簽名、 法律免責聲明或保密聲明。
ms.openlocfilehash: 3d95e92c4994a99ab3426133580d70453a2f83eb
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/24/2020
ms.locfileid: "42252384"
---
# <a name="create-organization-wide-signatures-and-disclaimers"></a>建立整個組織的簽章及免責聲明

 您可以在進入或離開貴組織的電子郵件中新增電子郵件簽名、法律免責聲明或保密聲明。您可以如下所示，設定將它套用至所有內送或外寄郵件。或者您也可以將它套用至特定郵件，例如包含特定字詞或文字模式的郵件。

 觀看有關建立的全公司的電子郵件簽章。 <br><br>
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1IEWf] 

如果您覺得這段影片很有幫助，請查看[適用於小型企業和 Microsoft 365 新手的完整訓練系列](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)。

## <a name="create-a-signature-that-applies-to-all-messages"></a>建立套用至所有郵件的簽名

> [!TIP]
> 整個組織的簽章不論他們的包含統稱為 「 免責聲明，」。 例如，他們可以只簽章，或也包含您的地址、 法律免責聲明或您想要的其他資訊。
    
::: moniker range="o365-worldwide"

移至位於 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 的系統管理中心。

::: moniker-end

::: moniker range="o365-germany"

移至位於 <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a> 的系統管理中心。

::: moniker-end

::: moniker range="o365-21vianet"

移至位於 <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn/adminportal</a> 的系統管理中心。

::: moniker-end

1. 選取 app 啟動器![Office 365 中的應用程式啟動器圖示](../media/7502f4ec-3c9a-435d-a7b4-b9cda85189a7.png)，然後選取 [**系統管理員**。
   
    找不到您要的 App 嗎？請從應用程式啟動器選取 [所有 App]**** 以查看依字母順序排序的可用 Office 365 App 清單。您可從該處搜尋特定的 App。 
    
2. 選取 [**系統管理中心**，，然後選擇 [ **Exchange**。
    
3. 郵件流程] 底下選取 [**規則**]。
    
4. 選取 [ **+** （新增） 圖示，然後選擇 [**套用免責聲明**。
    
5. 為這個規則命名。
    
6. 在 [**套用此規則**]，選取 **[套用到所有郵件]**。
    
    > [!TIP]
    > [深入了解](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/signatures#Scoping)您不想將免責聲明套用至所有郵件時的套用條件。 （此範圍的文章是針對 Exchange 伺服器，但它也適用於 Office 365）。 
  
7. [執行下列動作，請將保留選取**Append 免責聲明**。 
    
8.  選取 [**輸入文字**，然後輸入您的免責聲明。 
    
    > [!TIP]
    > [深入了解](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/signatures#FormatDisclaimer)如何設定免責聲明格式。 （此格式設定的文章是針對 Exchange 伺服器，但它也適用於 Office 365）。 

9. 選取 [**選取其中一個**，然後選擇 [**自動換行**做為後援選項。 然後 **[確定]**。 這表示，該免責聲明如果因為加密或其他郵件設定而無法新增，系統會將它包裝在郵件信封中。
    
10. 保留選取**此規則使用嚴重性層級的稽核**。 然後選擇 [**低**、**中**或**高**要用於郵件記錄。 
    
11. 選擇 [**強制**] 來開啟免責聲明立即，除非您想要測試其第一個。 
    
12. 選擇 [**更多選項**] 來納入其他條件或例外狀況。 
    
13. 選擇 [完成時，[**儲存**]。 
    
## <a name="limitations-of-office-365-organization-wide-signatures"></a>Office 365 組織整體簽章的限制

您無法執行 Office 365 簽章與下列動作：
  
- 插入的簽章正下方的最新的電子郵件回覆或轉寄
    
- 顯示使用者的寄件備份資料夾中的伺服器端電子郵件簽章
    
- 將圖像內嵌在電子郵件簽章
    
- 略過行包含無法更新的變數 (例如： 因為使用者未提供的值)
    
若要獲得這些結構元件及其他功能，使用協力廠商工具。 請網際網路搜尋**電子郵件簽章軟體**。 這些提供者的數字是金會員的 Microsoft 合作夥伴和其軟體提供這些功能。 
  
## <a name="more-resources"></a>其他資源

- 如需使用 PowerShell 的詳細資訊，請參閱[整個組織的郵件免責聲明、 簽章、 頁尾或 Office 365 中的標頭](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/disclaimers-signatures-footers-or-headers)。 
    

