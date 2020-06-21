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
ms.custom:
- seo-marvel-apr2020
description: 系統管理員可以在安全性 & 合規性中心的郵件流程儀表板中瞭解 SMTP 驗證用戶端報告。
ms.openlocfilehash: 90d008bf775c692431fb5b832652ceb97f9fd760
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/19/2020
ms.locfileid: "44818816"
---
# <a name="smtp-auth-clients-report"></a>SMTP 驗證用戶端報告

**Smtp 驗證用戶端**報告會強調使用者或組織中的系統帳戶如何使用 SMTP 驗證用戶端提交通訊協定。 這種舊版通訊協定（使用端點 smtp.office365.com）只提供基本驗證，而且很容易受到受損帳戶的使用以傳送電子郵件。  此報告可讓您檢查不尋常的活動。 此外，它也會顯示使用 SMTP 驗證之用戶端或裝置的 TLS 使用狀況資料。

[郵件流程] 儀表板中顯示的小工具會指出過去7天內，已使用 SMTP 驗證通訊協定的使用者或服務帳戶數目。

![安全性 & 規範中心內的郵件流程儀表板中的 SMTP 驗證用戶端報告](../../media/smtp-auth-clients-report-selected.png)

按一下小工具會開啟浮出的浮出區，可提供過去一周的 TLS 使用狀況和磁片區的匯總視圖。

![SMTP 驗證用戶端報告中的浮出控制項](../../media/smtp-auth-clients-flyout.png)

當您按一下 [ **SMTP 驗證用戶端] 報告**連結時，您會看到兩個主要資料旋轉和兩個資料檢視。 資料轉動是傳送**量**和**TLS 使用方式**。 資料檢視是圖表和詳細資料表格。

[傳送**大量**] 視圖會顯示在指定的時間範圍內，使用 SMTP 驗證傳送的郵件數目。 您可以按一下 [**篩選**] 來調整此範圍。 圖表是由寄件者網域所組織。 您可以在 [**顯示資料**] 下拉式清單中選取網域，以查看每個網域的個別資料。

![在 SMTP Auth 用戶端報告中傳送磁片區](../../media/smtp-auth-clients-report-sending-volume.png)

您可以按一下 [ **view details table**]，以查看有關寄件者及其郵件數目的詳細資訊。 若要回到圖表，請按一下 [ **View report**]。

![SMTP 驗證用戶端報告中傳送磁片區的詳細資料表格](../../media/smtp-auth-clients-report-details-sending-volume.png)

**Tls 使用狀況**pivot 很重要，因為在 Office 365 中即將推出的 TLS 1.0 和 tls 1.1 即將過時。 許多舊版裝置和應用程式只有能夠搭配使用 TLS 1.0 搭配 SMTP 驗證，否則無法傳送電子郵件。此樞紐分析表可讓您識別仍然使用舊版 TLS 的使用者和系統帳戶，並對其採取動作。

![SMTP 驗證用戶端報告中的 TLS 使用狀況](../../media/smtp-auth-clients-report-tls-usage.png)

您可以透過按一下 [**查看詳細資料] 表格**，查看寄件者的詳細資訊、這些寄件者所使用的 TLS 版本，以及其郵件數目。 若要回到圖表，請按一下 [ **View report**]。

您也可以按一下 [要求報告]，下載更詳細的報表版本。

![SMTP 驗證用戶端報告中 TLS 使用狀況的詳細資料表格](../../media/smtp-auth-clients-report-details-tls-usage.png)

## <a name="related-topics"></a>相關主題

如需郵件流量儀表板中其他郵件流程深入解析之詳細資訊，請參閱[安全性與合規性中心中郵件流程深入解析](mail-flow-insights-v2.md)。
