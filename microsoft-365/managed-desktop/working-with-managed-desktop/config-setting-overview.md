---
title: Microsoft 受管理電腦的組態設定
description: 在 [可設定的設定與 Microsoft 受管理的電腦上的資訊
keywords: Microsoft 受管理的電腦、 Microsoft 365、 服務、 文件、 設定、 組態設定
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 2/14/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: 0d30e92eb9747079a7edc5a8fd198298508f342e
ms.sourcegitcommit: d38c0ce846bac19e876a03a59ed4f268c7bae389
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/27/2019
ms.locfileid: "30900262"
---
# <a name="configurable-settings---microsoft-managed-desktop"></a>可設定-Microsoft 受管理的電腦

Microsoft 受管理電腦部署設定及原則可套用至所有由 Microsoft 受管理電腦的裝置。 如需詳細資訊，請參閱[裝置設定](../service-description/device-policies.md)。

Microsoft 受管理電腦中的組態設定能讓 IT 系統管理員自訂及部署對其組織及商務的需求都是唯一的設定。 這些設定包括除了裝置組態設定和原則所管理的 Microsoft 受管理的電腦。  

可設定的變更是雲端中進行，並套用至您的 Microsoft 受管理的電腦裝置定義的部署群組中。 此程序會類似於 Microsoft 受管理電腦管理裝置 configuruation 設定和原則定義及管理服務所變更的方式。 藉由使用 Microsoft 受管理的電腦使用的部署變更的相同程序，您繼續往前移您的組織，使用新式 IT 管理作法。

## <a name="when-to-use-configurable-settings"></a>何時使用可設定的設定？

有幾次使用可設定的設定。 

**上架程序**– Microsoft 受管理的桌上型電腦建議您自訂組態設定，當您上架到 Microsoft 受管理的電腦服務，或當您上架大量的裝置 （20 封或以上）。 Microsoft 受管理的電腦系統管理入口網站中設定設定類別。 您在上架及存取系統管理入口網站之後，您可以決定您想要自訂您的組織、 進行的變更，階段的部署，然後再部署變更的設定類別。

**維持設定**-定期檢閱您的設定，並進行所需的更新。 您可能需要變更以支援您的企業中的變更。   

## <a name="setting-categories"></a>設定類別

以下是您可以自訂組態設定類別：
- [桌面背景圖片](config-setting-ref.md#desktop-background-picture)– 自訂 Microsoft 受管理的電腦裝置的桌面背景圖片。 
- [瀏覽器啟動頁面](config-setting-ref.md#browser-start-pages)– 新增開始頁面，以使用 Microsoft Edge。 請參閱 [啟動] 頁面上的瀏覽器
- [企業模式網站清單](config-setting-ref.md#enterprise-mode-site-list-location)– 新增網站和其相容性模式。 在清單上的網站會開始在 Internet Explorer 中。 
- [信任的網站](config-setting-ref.md#trusted-sites)-新增受信任的網站和設定每個網站的安全性區域。 
- [Proxy 網站例外](config-setting-ref.md#proxy)– 設定 proxy 伺服器位址數目和連接埠號碼，並新增 proxy 網站例外狀況。

每個設定類別可自訂及部署在其本身。 您可以將變更部署到多個設定類別在同一時間，不過，您只可以部署一個一次變更至設定類別。

例如：
- 您可以部署變更桌面背景圖片和受信任的網站，他們自己的部署，同時為每個。 
- 您無法在同一時間，將兩個部署部署至瀏覽器啟動頁面。 最新的部署將會停止仍在進行中的舊版部署。

## <a name="configurable-setting-process"></a>您可以設定程序

Microsoft 受管理電腦建議下列類似下面的程序時運用組織的組態設定：

**步驟 1-規劃**-了解可設定的設定，並決定要為您的組織設定哪些設定類別。 當您打算將變更部署到每個群組，請建立時間表。 規劃您的使用者符合您的內部的變更管理程序的通訊。 例如，如果您正在新增瀏覽器開始頁面，可讓您知道它們會有一組新的開始頁面在其瀏覽器中部署後的使用者。  

**步驟 2-設定和階段部署**-對 Microsoft 受管理的電腦系統管理入口網站中的組態設定進行變更。 讓使用者準備好部署階段所做的變更。 請記住，讓您了解變更，以及如何變更將會變更其裝置體驗的使用者。   

您設定及接 Microsoft 受管理的電腦系統管理入口網站中的變更。 如需詳細資訊，請參閱 <<c0>自訂組態設定。 

**步驟 3-傳達變更**傳達給您的使用者即將進行變更的相關資訊。 針對每個部署中，完成您的變更管理程序的一部分的通訊。 您應該清楚地影響使用者的運作方式，或他們將會看到其裝置上的任何變更。

**步驟 4-部署變更**-部署您的變更，以測試群組開始。 測試群組可讓您驗證與排解群組的任何問題與較少的裝置，再部署至較大的裝置群組的變更。 如果您遇到任何問題，您可以回復變更、 更新] 設定，並設置為新部署。 Microsoft 受管理的電腦建議您遵循結構化的方法，並將部署至群組順序如下： 測試、 第一個、 快速，然後廣泛。   

使用 Microsoft 受管理的電腦系統管理入口網站中管理所有組態設定。 如需詳細資訊，請參閱 < <b0>Deploy 變更</b0>。 

**步驟 5-追蹤修訂**： 追蹤您的變更進行上部署狀態。 對於每一項設定，您可以：
- **追蹤進度**– 部署變更之後的追蹤狀態。 狀態會變更為 [**進行中**，，然後任一**完成**，或**失敗**。 如果部署失敗，Microsoft 受管理的桌上型電腦操作調查此問題： 自動開啟支援要求。  
- **請參閱部署版本**– 分別部署變更有的版本號碼。
- **還原變更**– 回復變更會停止目前的部署，並回復到最後一個變更已部署至所有群組的所有群組。 您正在復原的最後一個已知良好設定值。
- **驗證變更**-部署完成之後，驗證所做的變更已套用您預期。  

如果部署失敗，或您無法回復變更]，[開啟支援要求](admin-support.md)與 Microsoft 受管理的桌上型電腦作業。 

如需詳細資訊，請參閱 <<c0>部署] 和 [追蹤記錄的組態設定。

## <a name="additional-resources"></a>其他資源
- [可設定的設定參考](config-setting-ref.md) 
- [部署組態設定](config-setting-deploy.md) 
