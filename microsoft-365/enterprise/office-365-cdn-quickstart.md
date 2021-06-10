---
title: Office 365 內容傳遞網路 (CDN) 快速入門
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 06/04/2020
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
- m365initiative-coredeploy
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- MET150
- SPO160
description: Office 365 內容傳遞網路 (CDN) 快速入門
ms.openlocfilehash: 3539ad1f11b27c60b5641976ae66a1480ef4be98
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921591"
---
# <a name="office-365-content-delivery-network-cdn-quickstart"></a>Office 365 內容傳遞網路 (CDN) 快速入門

您可以使用內建的 **Office 365 內容傳遞網路 (CDN)** 來主控靜態資產 (影像、JavaScript、樣式表、WOFF 檔) ，為 SharePoint 的線上頁面提供更好的效能。 Office 365 CDN 透過將靜態資產快取到更靠近提出要求之瀏覽器的位置 (這有助於加速下載以及減少延遲)，藉此改善效能。 此外，Office 365 CDN 使用 HTTP/2 通訊協定，以提升壓縮和 HTTP 流水線。 Office 365 CDN 服務包含在 SharePoint Online 訂閱的一部分。

如需詳細資訊指引，請參閱[Use the Office 365 內容傳遞網路 (CDN) SharePoint Online](use-microsoft-365-cdn-with-spo.md)。

>[!NOTE]
>Office 365 CDN 僅可用於實際執行 (全球) 雲端的承租人。 美國政府、中國和德國雲彩中的承租人目前不支援 Office 365 CDN。

## <a name="use-the-page-diagnostics-for-sharepoint-tool-to-identify-items-not-in-cdn"></a>使用 SharePoint 工具的頁面診斷來識別不在 CDN 中的專案

您可以使用 **網頁診斷程式 SharePoint 工具** 瀏覽器延伸名，輕鬆列出可以新增至 CDN 來源的 SharePoint 線上頁面中的資產。

**SharePoint 工具的頁面診斷** 功能是新 Microsoft Edge (和 Chrome 瀏覽器的瀏覽器延伸名， https://www.microsoft.com/edge) 可分析 SharePoint Online 現代入口網站和傳統發佈網站頁面。 該工具會針對每個分析頁面提供一份報告，顯示頁面如何針對定義的效能準則組執行。 若要安裝及了解「適用於 SharePoint 的頁面診斷」工具，請造訪[使用適用於 SharePoint Online 的頁面診斷工具](./page-diagnostics-for-spo.md)。

當您在 SharePoint 線上頁面上為 SharePoint 工具執行頁面診斷時，您可以按一下 [**診斷測試**] 索引標籤，以查看不是由 CDN 所主控的資產清單。 這些資產會列于 [標題 **內容傳遞網路 (CDN) ] 複選** 中，如下列螢幕擷取畫面所示。

![頁面診斷](../media/page-diagnostics-for-spo/pagediag-results-general.PNG)

>[!NOTE]
>網頁診斷工具只能用於 SharePoint Online，且無法在 SharePoint 系統頁面使用。

## <a name="cdn-overview"></a>CDN概述

Office 365 CDN 的設計方式是透過將經常存取的物件（例如影像和 javascript 檔案）散佈于一種高速通用網路上，減少頁面載入時間，並盡可能將主控物件的存取權提供給使用者，以最優化使用者的效能。 CDN 會從稱為 _來源_ 的位置提取資產。 來源可以是可透過 URL 存取的 SharePoint 網站、文件庫或資料夾。

Office 365 CDN 分為兩種基本類型：

- **公用 CDN** 的設計目的是用於 .js (JavaScript) 、CSS (StyleSheets) 、網頁字型檔案 (WOFF、WOFF2) 和非專有影像（如公司標誌）。
- **私人 CDN** 專門設計用來做為 PNG、JPG、JPEG 等圖像 () 。

您可以選擇同時包含組織的公開來源或私人來源。 大多陣列織會選擇實現兩者的組合。 公用和私人選項都提供類似的效能提升，但各項都有獨特的屬性和優點。 如需有關公用和私人 CDN 來源的詳細資訊，請參閱[選擇是否要公開或私營每個來源](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate)。

## <a name="how-to-enable-public-and-private-cdn-with-the-default-configuration"></a>如何使用預設設定來啟用公用和私人 CDN
變更租使用者 CDN 設定之前，您應該確認其符合組織的合規性、安全性和隱私權原則。

如需詳細的設定設定，或者您已啟用 CDN，且想要將其他位置 (來源) 中，請參閱[使用 CDN 線上管理命令介面設定及設定 Office 365 SharePoint](use-microsoft-365-cdn-with-spo.md#set-up-and-configure-the-office-365-cdn-by-using-the-sharepoint-online-management-shell)一節。

使用 SharePoint 線上管理命令介面連線租使用者：

```PowerShell
Connect-SPOService -Url https://<YourTenantName>-admin.sharepoint.com
```

若要讓您的組織使用預設設定的公開和私人來源，請輸入下列命令：

```PowerShell
Set-SPOTenantCdnEnabled -CdnType Both -Enable $true
```

這些 Cmdlet 的輸出應該如下所示：

![Set-SPOTenantCdnEnabled 的輸出](../media/O365-CDN/o365-cdn-enable-output.png)

## <a name="see-also"></a>另請參閱

[使用 Sharepoint Online 網頁診斷工具](./page-diagnostics-for-spo.md)

[使用 Office 365 內容傳遞網路 (CDN) 搭配 SharePoint Online](use-microsoft-365-cdn-with-spo.md)

[內容傳遞網路](./content-delivery-networks.md)

[Office 365 的網路規劃和效能調整](./network-planning-and-performance.md)

[SharePoint效能數列-Office 365 CDN 的影片系列](https://www.youtube.com/playlist?list=PLR9nK3mnD-OWMfr1BA9mr5oCw2aJXw4WA)