---
title: Microsoft 受管理的桌上型電腦的組態設定
description: 在 Microsoft 受管理的桌上型電腦的組態設定的資訊
keywords: Microsoft 受管理的桌上型電腦、 Microsoft 365、 服務、 文件、 設定、 可設定的設定
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 2/14/2019
ms.openlocfilehash: 64560a1eb597072dd99c1538b0131e3cd807899c
ms.sourcegitcommit: 1942a860d1b65e1f8062564ec4703b953e0c2fd7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/20/2019
ms.locfileid: "30122243"
---
# <a name="configurable-settings---microsoft-managed-desktop"></a>可設定-Microsoft 受管理的桌上型電腦

Microsoft 受管理的桌上型電腦部署設定及原則可套用至所有由 Microsoft 受管理的桌上型電腦管理的裝置。如需詳細資訊，請參閱[裝置設定](../service-description/device-policies.md)。

Microsoft 受管理的桌上型電腦中的組態設定將 IT 系統管理員提供一種方式來自訂和部署對其組織及商務需求都是唯一的設定。這些設定是除了裝置組態設定及管理 Microsoft 受管理的桌上型電腦的原則。  

可設定的設定變更是在雲端中進行並套用您 Microsoft 受管理的桌上型電腦中的裝置已定義的部署鈴響。此程序會類似於 Microsoft 受管理的桌上型電腦管理變更裝置 configuruation 設定和原則定義及管理服務的方式。藉由使用 Microsoft 受管理的桌上型電腦使用進行部署變更的相同程序，您繼續使用現代 IT 管理作法往前移，您的組織。

## <a name="when-to-use-configurable-settings"></a>何時使用組態設定？

有一些時間來使用組態設定。 

**佈建程序**– Microsoft 受管理的桌上型電腦建議您在您開始 Microsoft 受管理的桌上型電腦服務時自訂組態設定，或當您開始大量的裝置 （20 或多個）。設定類別來設定 Microsoft 受管理的桌上型電腦管理入口網站。您已 onboarded 以及可以存取系統入口網站之後，您可以決定您要自訂您的組織、 進行的變更的部署階段及再部署變更的設定類別。

**維持設定**-定期檢閱您的設定並進行所需的更新。您可能需要變更以支援您的企業中的變更。   

## <a name="setting-categories"></a>設定類別

這些是您可以自訂的組態設定類別：
- [桌面背景圖片](config-setting-ref.md#desktop-background-picture)– 自訂 Microsoft 受管理的桌上型電腦裝置桌面背景圖片。 
- [瀏覽器啟動頁面](config-setting-ref.md#browser-start-pages)– 來搭配 Microsoft Edge 新增起始頁面。請參閱起始畫面的瀏覽器
- [企業模式網站清單](config-setting-ref.md#enterprise-mode-site-list-location)– 新增網站，以及其相容性模式。在清單上的網站會啟動 Internet Explorer 中。 
- [信任的網站](config-setting-ref.md#trusted-sites)-新增受信任的網站以及每個網站的設定安全性區域。 
- [Proxy 網站例外](config-setting-ref.md#proxy)– 設定 proxy 伺服器位址和連接埠號碼，並新增 proxy 網站例外狀況。

可以自訂及部署在其上每個設定類別。可以同時將變更部署到多個設定類別，不過，您可以僅部署一次一個變更到設定類別。

例如：
- 您可對桌面背景圖片和受信任的站台，他們自己的部署，同時為每個部署的變更。 
- 您不能部署至瀏覽器開始頁面的兩個部署在同一時間。最新的部署將會停止仍正在進行中的舊版部署。

## <a name="configurable-setting-process"></a>可設定的設定程序

整體程序如下所示。 

**步驟 1-規劃**-了解可設定的設定並決定您要為組織設定的設定類別。規劃您的使用者通訊符合您的內部變更管理程序。例如，若要新增瀏覽器開始頁面，可讓您知道它們將擁有一組新的開始頁面在瀏覽器中部署之後的使用者。  

**步驟 2-設定和分段執行部署**-對 Microsoft 受管理的桌上型電腦管理入口網站中的組態設定進行變更。讓他們準備好部署階段所做的變更。請記得讓使用者知道的變更和所做的變更將會如何變更其裝置使用體驗。   

您設定和分段執行 Microsoft 受管理的桌上型電腦管理入口網站中的變更。如需詳細資訊，請參閱 ＜ [Customize 組態設定](config-setting-ref.md)。 

**步驟 3-通訊的變更**通訊使用者即將產生之變更的相關資訊。針對每個部署中，完成您變更管理程序的一部分的通訊。您應該清楚地影響使用者的運作方式，或就會看到其裝置上的任何變更。

**步驟 4-部署變更**-部署您的變更，開頭測試響鈴。測試響鈴可讓您驗證及疑難排解較少的裝置鈴響中任何問題再部署至較大的裝置群組的變更。如果您執行發生任何問題，您可以將回復變更、 更新設定和分段執行新的部署。Microsoft 受管理的桌上型電腦建議您遵循結構化的方法和部署至鈴響順序如下： 測試、 第一個、 快速且然後廣泛。   

使用 Microsoft 受管理的桌上型電腦管理入口網站管理所有組態設定。如需詳細資訊，請參閱 ＜ [Deploy 變更](config-setting-deploy.md)。 

**步驟 5-追蹤修訂**– 上部署狀態追蹤正在進行變更。每項設定，您可以：
- **追蹤進度**– 追蹤狀態之後部署變更。狀態會變更為 [**進行中**，然後再可以是**Complete**、 」 或 「**失敗**。如果部署失敗，支援要求自動開啟調查問題 Microsoft 受管理的桌上型電腦作業。  
- **請參閱部署版本**– 分別部署變更具有版本號碼。
- **還原變更**– 回復變更會停止目前的部署，並回復至已部署至所有鈴響的最後一個變更所有鈴響。您會回復為上次正確設定值。
- **驗證變更**-部署完成之後，驗證您如預期般已套用變更。  

如果部署失敗，或無法回復變更 Microsoft 受管理的桌上型電腦作業[開啟支援要求](admin-support.md)。 

如需詳細資訊，請參閱 ＜ [Deploy 和追蹤可設定的設定](config-setting-deploy.md)。

## <a name="additional-resources"></a>其他資源
- [可設定的設定參考 （英文)](config-setting-ref.md) 
- [部署組態設定](config-setting-deploy.md) 
