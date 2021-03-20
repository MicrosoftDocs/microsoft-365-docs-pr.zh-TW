---
title: 調整 Exchange Online 效能
ms.author: krowley
author: tracyp
manager: laurawi
ms.date: 12/14/2017
audience: Admin
ms.topic: troubleshooting
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom: Adm_O365
ms.assetid: 026e83cb-a945-4543-97b0-a8af6e80ac61
description: 本文包含的一般秘訣，以及其他資源的連結，可告訴您如何改善 Exchange Online 的效能。
ms.openlocfilehash: a7d3268f9f3cf1922319b03cf69d3f044272b27f
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909439"
---
# <a name="tune-exchange-online-performance"></a>調整 Exchange Online 效能

本文包含其他資源的一般秘訣和連結，可告訴您如何改善 Exchange Online 的效能，尤其是在遷移之前。 本文是 Office 365 專案的 [網路規劃和效能調整](./network-planning-and-performance.md) 的一部分。
   
## <a name="things-to-consider-in-order-to-improve-exchange-online-performance"></a>為了改善 Exchange Online 效能應考慮的事項

若要改善遷移速度並減少組織的 Exchange Online 頻寬限制，請考慮下列各項：
  
- **縮小信箱大小。** 信箱大小較小會提升遷移速度。 
    
- **在 Exchange 混合式部署中使用信箱移動功能。** 使用 Exchange 混合式部署時，離線郵件 (格式為。在遷移至 Exchange Online 時，不需要重新下載 .OST 檔案) 。 這會大幅減少下載頻寬需求。 
    
- **在網際網路流量低和內部部署 Exchange 使用的情況下，排定信箱移動的時間。** 當排程移動時，會將遷移要求提交至信箱複寫 proxy，而且不會立即進行。 
    
- **使用適用于網頁版 Outlook 的精益快顯。** 精益快顯透過轉譯伺服器上的某些元件，在 Microsoft Edge 或 Internet Explorer 中提供較小、佔用大量記憶體的特定電子郵件。 如需詳細資訊，請參閱 [使用精益快顯減少讀取郵件訊息時使用的記憶體](https://support.office.com/article/a6d6ba01-2562-4c3d-a8f1-78748dd506cf)。


## <a name="general-advice"></a>一般建議

- 請確定 outlook.office.com 的 DNS 查閱會在您的位置的邏輯專案位置輸入 MS 資料中心。

- 調研信箱快取，並選擇適當的選項 (re。 快取週期、共用信箱快取等) 。

- 讓您的 Outlook 資料在透過網際網路之前，可將 VPN 連線 (傳送到總公司) 。

- 請確定您的信箱資料符合資料夾的限制，以及專案的數量。
    
如需 Exchange 遷移效能的詳細資訊，請參閱 [Office 365 遷移效能和最佳作法](https://support.office.com/article/d9acb371-fd6c-4c14-aa8e-db5cbe39aa57)。
