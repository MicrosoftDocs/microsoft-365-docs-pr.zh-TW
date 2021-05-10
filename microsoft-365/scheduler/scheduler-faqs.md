---
title: Microsoft 365 FAQs 的調度程式
ms.author: v-aiyengar
author: AshaIyengar21
manager: serdars
audience: Admin
ms.topic: article
ms.service: scheduler
localization_priority: Normal
description: Microsoft 365 FAQs 的調度程式
ms.openlocfilehash: 12c2c00761b9a10fac6c62bc4d7ff5909ac935a7
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/08/2021
ms.locfileid: "52286160"
---
# <a name="scheduler-for-microsoft-365-faqs"></a>Microsoft 365 FAQs 的調度程式

**問題：** 排程器與其他 cortana 功能的整合方式，例如 *小娜的 Windows*、*每日簡報電子郵件*，以及 *播放我的電子郵件*？</br>
排程器是來自其他 Cortana 功能的獨立服務。 其他 Cortana 功能可在租使用者層級停用，而排程器仍可使用 cortana@yourdomain.com 電子郵件地址來啟用。 目前，使用者只能透過電子郵件與計畫程式互動。

**問題：** 這只會與 Outlook 搭配運作嗎？ 其他電子郵件產品是否支援？</br>
只要您具有除上述三項需求以外的授權，使用者就可以從任何裝置上的任何電子郵件客戶 cortana@yourdomain.com 電子郵件。

**問題：** 連絡人是否可以位於 Outlook 和 GAL 或其他公司對等的個人連絡人清單中？</br>
會議出席者可以是公司內部或外部電子郵件地址的任何人。 不幸的是，排程現在無法透過在 GAL 中查閱的方式，自動將名稱轉譯為電子郵件地址/別名。

**問題：** 我可以使用已安裝版本 (內部部署) 版本 Outlook 的計畫程式嗎？</br>
排程器需要 Exchange Online。 無法與 Exchange Server (部署) 搭配使用。 可與任何電子郵件用戶端、Outlook 桌面、OWA、iOS、android、gmail 等等一起運作。

**問題：** 是否 Outlook 必須在背景中開啟？</br>
不需要在背景中開啟 Outlook。 您所需做的只是傳送 Cortana 電子郵件，並依據它來執行大量的工作。

## <a name="frequently-asked-trust-and-privacy-questions"></a>常見的信任和隱私權問題

**問題：** 排程程式的運作方式？</br>
排程器使用排程智慧 (AI) 擴充人工助理。 如果 AI 模型會以自然語言（透過 Cortana 通訊）產生支援支援，會議邀請便會升級至人員進行審閱和完成。

**問：** 神秘審閱已上報的要求嗎？ </br>
排程者助理是 Microsoft 供應商的安全性和隱私權保證 (因個人和高度機密資訊而) 認證。 

**問題：** SSPA 什麼可以查看？</br>
排程者和 SSPA 的助理可以查看已寄至 Cortana 的電子郵件。 在以執行緒傳送的電子郵件交換中，只會處理包含 Cortana 電子郵件地址的電子郵件，而不是新增 Cortana 之前的執行緒中的先前電子郵件。   

**問題：** 客戶資料是否會保留在排程器的資料 Flow 中？ </br>
排程器會儲存租使用者界限內的所有客戶內容，並依照 GDPR 指導方針保留資料，Microsoft 365 信任 & 隱私權原則，以及租使用者電子郵件原則。

**問題：** 排程者如何處理內部出席者的空閒/忙碌資料？ </br>
排程器的「自動化」會使用 *findMeetingTimes* 服務來識別出席者和召集人相互使用的時間。 此服務會為其他 Outlook 體驗，例如 Outlook 會議表單中 *建議的時間*。 空閒/忙碌出席者資訊不會明確地當作空閒/忙碌的封鎖使用。 

**問題：** 排程器 GDPR 是否相容？ </br>
可以。

**問題：** 神秘可以存取 Cortana 信箱嗎？ </br>
排程器處理傳送至您租使用者 Cortana 信箱的會議要求和相關聯的電子郵件。 除了在租使用者管理員要求的密碼箱核准之外，Microsoft 沒有任何其他存取 Cortana 信箱的許可權。  

**問題：** 客戶資料是否用於訓練 AI 模型？</br>
無 Microsoft 365 的計畫者內容可用於資料訓練集。 所有客戶內容均位於客戶租使用者。  

**問題：** 排程程式是否會處理加密郵件？</br>
否，計畫程式工作流程會拒絕加密郵件。 



