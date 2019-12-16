---
title: 使用 Office 365 ATP 安全附件的動態傳遞和預覽
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: 04/19/2019
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: f16c9928-8e3d-4219-b994-271dc9a16272
ms.collection:
- M365-security-compliance
description: 當您設定 ATP 安全附件原則時，您選擇 [動態傳遞] 來避免郵件延遲，並讓人員預覽正在掃描的附件。
ms.openlocfilehash: 3cf914325b493098f61c84f27c102dd64fd7d8e9
ms.sourcegitcommit: 5710ce729c55d95b8b452d99ffb7ea92b5cb254a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/11/2019
ms.locfileid: "39970776"
---
# <a name="dynamic-delivery-and-previewing-with-office-365-atp-safe-attachments"></a>使用 Office 365 ATP 安全附件的動態傳遞和預覽

## <a name="overview"></a>概觀

[動態傳遞] 是一個選項，可以針對 [ATP 安全附件](atp-safe-attachments.md)進行選取。 請參閱這篇文章，了解 [Office 365 中的 ATP 安全附件](atp-safe-attachments.md)中的動態傳遞和附件預覽功能。

當貴組織[已設定 ATP 安全附件原則](set-up-atp-safe-attachments-policies.md)時，對於電子郵件附件的處理方式有數個選項。 其中包括 [封鎖]****、[取代]**** 以及 [動態傳遞]****。 視設定的 ATP 安全附件原則而定，電子郵件收件者在其附件進行掃描時，可能會遇到電子郵件傳遞的輕微延遲。 若要避免郵件延遲，請選擇 [動態傳遞]****。
  
## <a name="how-dynamic-delivery-works"></a>動態傳遞運作方式
  
動態傳遞會將電子郵件訊息的本文傳送給收件者，對於每個電子郵件附件使用預留位置，來避免電子郵件延遲。 系統會保留預留位置直到掃描附件的複本，並且由 [ATP 安全附件](atp-safe-attachments.md)判斷是安全的。 

- 因為每個附件都是乾淨的，可以開啟或下載。 

- 如果附件被認為是惡意的，則會將它傳送給隔離區，而貴組織安全小組 (例如，Office 365 全域系統管理員或安全性系統管理員) 中的某人可以[管理 Office 365 中的隔離郵件](manage-quarantined-messages-and-files.md)。

大部分 PDF 和 Office 文件都可以在 ATP 掃描正在進行時，在安全模式中預覽。 如果附件與動態傳遞預覽程式不相容，電子郵件收件者會看見附件預留位置，直到 ATP 安全附件掃描完成為止。

> [!TIP]
> 如果您使用的是行動裝置，且一開始 PDF 無法在 [動態傳遞] 預覽程式中轉譯，請嘗試使用您的行動瀏覽器登入 Office 365。

透過動態傳遞，使用者可以在他們的附件進行分析的同時，立即讀取及回覆電子郵件訊息。 

ATP 安全附件掃描會在您的 Office 365 資料所在的同一個區域中進行。 如需資料中心地理位置的詳細資訊，請參閱[您的資料位於何處？](https://products.office.com/where-is-your-data-located?geo=All)
  
## <a name="what-happens-when-someone-forwards-an-email-that-contains-an-attachment"></a>當有人轉寄含有附件的電子郵件時，會發生什麼情況？

假設組織針對其 [ATP 安全附件原則](set-up-atp-safe-attachments-policies.md)使用動態傳遞，且有人收到包含附件的電子郵件。 現在假設該人員將電子郵件轉寄給其他人。 會發生什麼情況？ 這取決於附加收件者是否包含在 ATP 安全附件原則中。
  
- 如果收件者涵蓋在使用 [動態傳遞] 選項的 ATP 安全附件原則中，則收件者會看到預留位置，並且可以預覽相容的檔案。
    
- 如果收件者未涵蓋在 ATP 安全附件原則中，則電子郵件和附件會通過，而不會有任何 ATP 安全附件掃描或附件預留位置。
    
## <a name="whats-required-for-dynamic-delivery-to-work"></a>動態傳遞運作需要哪些項目？

- 貴組織必須有 [Office 365 進階威脅防護](office-365-atp.md)
    
- 必須針對使用 [動態傳遞] 選項的 ATP 安全附件定義原則 (請參閱[在 Office 365 中設定 ATP 安全附件原則](set-up-atp-safe-attachments-policies.md))
    
- 貴組織的電子郵件必須在 Office 365 中託管。 雖然 [Office 365 進階威脅防護可以用於任何 SMTP 郵件傳輸代理程式](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#requirements-for-office-365-advanced-threat-protection-atp) (部分機器翻譯) (例如 Exchange Server)，但是適用於 ATP 安全附件的動態傳遞選項需要貴組織的電子郵件是在 Office 365 中託管。 如果您的電子郵件未在 Office 365 中託管，請選擇不同的 [ATP 安全附件原則選項](set-up-atp-safe-attachments-policies.md#step-3-learn-about-atp-safe-attachments-policy-options)，例如 [封鎖]****。
    
## <a name="additional-considerations"></a>其他考量因素

在某些情況下，動態傳遞不受支援。 包括下列各項：
  
- 在公用資料夾中的電子郵件訊息
    
- 使用自訂規則從使用者的信箱路由傳送出去又傳送回來的電子郵件訊息
    
- 移出 (自動或手動) 託管信箱並且移入其他位置 (包括封存資料夾) 的電子郵件訊息
    
- 已刪除的電子郵件訊息
    
- 處於錯誤狀態的使用者信箱搜尋資料夾
    
- Exchange Online 系統管理員已啟用 Exclaimer 的環境。 若要解決此問題，請參閱[使用 ATP 動態傳遞和 Exclaimer 時，不會傳遞含有附件的郵件](https://support.microsoft.com/help/4014438/messages-with-attachments-are-not-delivered-when-atp-dynamic-delivery)

- 使用 [安全多用途網際網路郵件延伸 (S/MIME)](s-mime-for-message-signing-and-encryption.md)) 加密的郵件

- 如果動態傳遞不受支援，ATP 安全附件將不會掃描電子郵件訊息。 不過，系統會根據您 [ATP 安全連結原則](set-up-atp-safe-links-policies.md)的設定方式，在傳遞具有附件 (含有 URL) 的電子郵件訊息時會進行檢查。 在這些情況下，會檢查電子郵件訊息和 Office 檔案中的 URL。
