---
title: 使用郵件流程規則來查看您的使用者報告給 Microsoft 哪些內容
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 8401f520-8e7c-467b-9e06-4a9fdb2ba548
ms.collection:
- M365-security-compliance
description: 您可以建立 Exchange 郵件流程規則，以防止使用者將電子郵件訊息傳送給 Microsoft 進行分析，並在您自己的安全性程序中使用它們
ms.openlocfilehash: fa8ff00b35ad551b47f6bc30b34b6d3b29cecc75
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37076188"
---
# <a name="use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft"></a>使用郵件流程規則來查看您的使用者報告給 Microsoft 哪些內容

有多種方法可以將誤判和誤判正常郵件傳送給 Microsoft，以進行分析。 身為管理員，您可以使用郵件流程規則來查看您的使用者會回報給 Microsoft 垃圾郵件、 非垃圾郵件和網路釣魚詐騙。 如需詳細資訊，請參閱[提交垃圾郵件、 非垃圾郵件和網路釣魚詐騙郵件提交給 Microsoft 進行分析](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md)。 相反地，您可以建立 Exchange 郵件流程規則 （也稱為傳輸規則） 以防止使用者將電子郵件訊息傳送給 Microsoft 進行分析，並在您自己的安全性程序中使用它們。
  
## <a name="what-do-you-need-to-know-before-you-begin"></a>開始之前有哪些須知？

預估完成時間：5 分鐘
  
您必須已獲指派權限，才能執行此程序或這些程序。 若要查看您需要哪些權限，請參閱[訊息原則及符合性權限](http://technet.microsoft.com/library/ec4d3b9f-b85a-4cb9-95f5-6fc149c3899b.aspx)主題中的 「 郵件流程規則 」 項目和[用戶端和行動裝置權限](http://technet.microsoft.com/library/57eca42a-5a7f-4c65-89f0-7a84f2dbea19.aspx)主題中的 「 Outlook web 信箱原則 」 項目。 
  
適用於此主題中程序的鍵盤快速鍵相關資訊，請參閱[Exchange 系統管理員的鍵盤快速鍵置在 Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)。
  
## <a name="use-the-eac-to-create-a-mail-flow-rule-to-view-users-manual-junk-phishing-and-not-junk-reports"></a>使用 EAC 來建立郵件流程規則，以檢視使用者手動垃圾郵件、 網路釣魚，並不是垃圾郵件報告

1. 在 EAC 中，瀏覽至 **[郵件流程]** \> **[規則]**。
    
2. 按一下 ![加入圖示](../media/ITPro-EAC-AddIcon.gif)，然後選取 **[建立新的規則]**。
    
3. 命名規則，然後按一下 **[更多選項]**。
    
4. 在 **[套用此規則，如果]** 下選取 **[收件者]**，然後選擇 **[位址包含任何這些文字]**。
    
5. 在 **[指定單字或片語]** 方塊中，執行下列作業： 
    - 型別`abuse@messaging.microsoft.com`，然後按一下 [![加入圖示](../media/ITPro-EAC-AddIcon.gif)，然後輸入`junk@office365.microsoft.com`，然後按一下 [![加入圖示](../media/ITPro-EAC-AddIcon.gif)。 這些電子郵件地址可用來將誤判正常郵件提交給 Microsoft。
    - 型別`phish@office365.microsoft.com`，然後按一下 [![加入圖示](../media/ITPro-EAC-AddIcon.gif)。 此電子郵件地址用來提交未接的網路釣魚郵件提交給 Microsoft。
    - 型別`false_positive@messaging.microsoft.com`，然後按一下 [![加入圖示](../media/ITPro-EAC-AddIcon.gif)，然後輸入`not_junk@office365.microsoft.com`，然後按一下 [![加入圖示](../media/ITPro-EAC-AddIcon.gif)。 這些電子郵件地址可用來將誤判郵件提交給 Microsoft。
    - 按一下 **[確定]**。
    
6. 在 [**執行下列動作**，選取 [ **[密件副本郵件到...** ，然後，然後選取您想要的信箱接收郵件。 
    
7. 您也可以視需要選取稽核規則、測試規則、在特定期間啟動規則等等選項。 施行規則之前，建議先測試規則一段時間。 請參閱[郵件流程規則程序](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rule-procedures)。 
    
8. 按一下 **[儲存]** 按鈕儲存規則。 它就會出現在規則清單中。 
    
建立並強制執行規則後，從組織傳送至指定的電子郵件地址的任何郵件都會複製到指定的信箱。
  

