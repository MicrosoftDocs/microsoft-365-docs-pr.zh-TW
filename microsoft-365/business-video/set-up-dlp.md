---
title: 防止資料外洩
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- adminvideo
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: 瞭解如何管理設定資料遺失防護原則。
ms.openlocfilehash: 04dbbcfd39186b8161fb497b72ddb070fbfb7471
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/02/2021
ms.locfileid: "51580435"
---
# <a name="prevent-data-loss-with-dlp"></a>使用 DLP 防止資料遺失

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3TGvL?autoplay=false]

資料遺失防護原則可協助識別及保護您公司的機密資訊，例如社會安全號碼或醫療記錄。 

## <a name="try-it"></a>試試看吧！

1. 若要開始，請移至系統 [管理中心](https://admin.microsoft.com)，然後選取 [ **安裝**]。
1. 向下滾動以 **設定資料遺失防護**，然後選取 [ **查看**]，然後再進行 **管理**。
1. 若要編輯原則，請選取它，然後選擇 [ **編輯原則**]，然後選取要變更的專案。 例如，選取 [變更掃描的 **位置** ]。
1. 若要在 Microsoft Teams 中啟用內容的掃描，請開啟切換切換至 [**開啟**] 位置，然後選取 [**儲存**]。
1. 若要編輯原則設定，請選取 [ **編輯**]。
1. 您必須設定個別的規則，套用至偵測到的少量機密內容。 擴充低音量規則。 選擇 [ **編輯規則**]。
1. 請複查您的設定，並視需要加以調整。 例如，您可以選擇 **自訂電子郵件文字** 和 **自訂原則提示文字**。 選取 ****[儲存]。
1. 針對高容量規則重複此步驟。 選取 [ **儲存**]，然後 **關閉**]。
1. 若要建立新原則，請選取 [ **建立原則**]。
1. 您可以建立自訂原則或從範本開始。 例如，若要建立 HIPAA 原則，請選取 [ **醫學與健康** 情況範本]，然後選取 [ **美國健康情況保險業法案 (HIPAA])**。 選取 [下一步]。
1. 輸入原則的名稱和描述。 選取 [下一步]。
1. 選擇要掃描的位置。 選取 [下一步]。
1. 選擇您要保護的內容類型。 選取 [下一步]。
1. 選擇偵測到敏感資訊時所要執行的動作。 選取 [下一步]。
1. 自訂您的存取權和覆寫許可權。 選取 [下一步]。
1. 選擇您想要原則生效的時間。 選取 [下一步]。
1. 請複查您的設定，然後選取 [ **建立**]。 當原則生效後，包含所述敏感資訊的電子郵件將會遭到封鎖，而且嘗試傳送該資訊的寄件者會看到警告訊息。