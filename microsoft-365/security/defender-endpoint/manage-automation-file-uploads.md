---
title: 管理自動化檔上傳
description: 啟用內容分析並設定將送出以進行分析的副檔名和電子郵件附件擴充功能
keywords: 自動化，檔案，上傳，內容，分析，檔案，擴充，電子郵件，附件
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: c8935368e4439221f2ce21cfa620e540c02165f8
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185846"
---
# <a name="manage-automation-file-uploads"></a>管理自動化檔上傳

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>想要體驗 Defender for Endpoint？ [註冊免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-automationefileuploads-abovefoldlink)

啟用內容分析功能，讓某些檔案和電子郵件附件可自動上傳至雲端，以進行其他檢查，以進行自動調查。

指定副檔名名稱和電子郵件附件分機名稱，以識別檔案和電子郵件附件。 

例如，如果您將 *exe* 和 *bat* 新增為檔案或附件分機名稱，則會自動將這些分機號碼的所有檔案或附件傳送至雲端，以在自動調查期間進行其他檢查。 

## <a name="add-file-extension-names-and-attachment-extension-names"></a>新增副檔名名稱和附件分機名稱。

1. 在功能窗格中，選取 [**設定**  >  **自動化** 檔案上傳]。 

2. 切換 [內容分析] 設定為 [ **開啟** ] 和 [ **關閉**]。

3. 請以逗號設定下列副檔名及分隔副檔名：
   - 檔案 **副檔名**-電子郵件附件以外的可疑檔案會提交其他檢查
  

## <a name="related-topics"></a>相關主題
- [管理自動化資料夾排除](manage-automation-folder-exclusions.md)
