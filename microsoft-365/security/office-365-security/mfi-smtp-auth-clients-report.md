---
title: SMTP 驗證用戶端報告
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
description: 系統管理員可以了解 SMTP 驗證的用戶端報表中安全性 & 合規性中心中的郵件流程儀表板。
ms.openlocfilehash: e80ee36fd7e94cc4dc2791f71ae594f0182b4269
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42082605"
---
# <a name="smtp-auth-clients-report"></a>SMTP 驗證用戶端報告

**SMTP 驗證的用戶端**報表會醒目提示 SMTP 驗證用戶端提交通訊協定，由使用者或系統帳戶，在您的組織中的使用。 此舊版通訊協定 （使用端點 smtp.office365.com） 只提供基本驗證]，且容易受到正由遭入侵帳戶傳送電子郵件。  此報告可讓您檢查有不尋常的活動。 它也顯示 TLS 流量資料的用戶端或裝置使用 SMTP 驗證]。

郵件流程儀表板中顯示小工具指示的使用者或服務帳戶所擁有的 SMTP 驗證通訊協定過去 7 天的數目。

![SMTP 驗證的用戶端報表中安全性 & 合規性中心中的郵件流程儀表板](../../media/smtp-auth-clients-report-selected.png)

按一下 [] 小工具會開啟提供 TLS 流量及磁碟區的彙總的檢視的最後一週彈出式視窗。

![SMTP 驗證的用戶端報告中的彈出式視窗](../../media/smtp-auth-clients-flyout.png)

當您按一下 [ **SMTP 驗證的用戶端報告**] 連結時，您會看到兩個主要的資料樞紐分析表和兩個資料檢視。 資料樞紐分析表，而**傳送大量** **TLS 流量**。 [資料] 檢視，而圖表 details] 資料表。

**傳送大量**檢視會顯示使用 SMTP 驗證指定的時間範圍內所傳送的郵件數目。 您可以藉由按一下 [**篩選器**調整範圍。 圖表會依照寄件者網域。 您可以看到下拉式清單中**顯示的資料**中選取該網域的每個網域的個別的資料。

![在 [SMTP 驗證傳送大量的用戶端報告](../../media/smtp-auth-clients-report-sending-volume.png)

您可以檢視寄件者的詳細的資訊，以及其訊息計數藉由按一下 [**檢視詳細資料] 表格**。 若要傳回的圖表，請按一下 [**檢視報告**。

![傳送大量 SMTP 驗證的用戶端報告的詳細資料表格](../../media/smtp-auth-clients-report-details-sending-volume.png)

**TLS 流量**樞紐分析表是很重要，因為 TLS1.0 和 Office 365 中的 TLS1.1 即將來臨的 deprecation >。 許多傳統的裝置和應用程式將無法傳送電子郵件，如果他們只能夠 TLS1.0 使用 SMTP 驗證]。這個樞紐分析表可讓您以找出並採取動作的使用者和仍在使用 TLS 的舊版本的系統帳戶。

![在 SMTP 驗證用戶端的 TLS 流量報告](../../media/smtp-auth-clients-report-tls-usage.png)

您可以檢視的寄件者，他們會使用 SMTP 驗證的 TLS 版本的詳細的資訊，以及其訊息計數藉由按一下 [**檢視詳細資料] 表格**。 若要傳回的圖表，請按一下 [**檢視報告**。

您也可以藉由按一下 [要求報告下載版本更詳細的報告。

![SMTP 驗證的用戶端報告中的 TLS 使用狀況詳細資料表格](../../media/smtp-auth-clients-report-details-tls-usage.png)

## <a name="see-also"></a>另請參閱

如需郵件流量儀表板中其他郵件流程深入解析之詳細資訊，請參閱[安全性與合規性中心中郵件流程深入解析](mail-flow-insights-v2.md)。
