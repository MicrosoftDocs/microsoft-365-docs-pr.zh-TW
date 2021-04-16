---
title: Microsoft Defender for Endpoint 中的裝置健康情況和符合性報告
description: 使用裝置健康情況和合規性報告追蹤裝置健康狀態偵測、防病毒狀態、作業系統平臺及 Windows 10 版本
keywords: 健康狀態、防毒程式、作業系統平臺、windows 10 版本、版本、健康情況、規範、狀態
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
ms.openlocfilehash: 35100a4b8bdaee23c427816450e948ced9ed3191
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/16/2021
ms.locfileid: "51860288"
---
# <a name="device-health-and-compliance-report-in-microsoft-defender-for-endpoint"></a>Microsoft Defender for Endpoint 中的裝置健康情況和符合性報告

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> 想要體驗適用於端點的 Microsoft Defender 嗎？ [注册免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

裝置狀態報表提供組織中裝置的高層級資訊。 報告包含趨勢資訊，顯示感應器狀況狀態、防病毒狀態、作業系統平臺及 Windows 10 版本。

儀表板分為兩個區段： ![ 裝置報表的影像](images/device-reports.png)
 
區段 | 說明
:---|:---
1 | 裝置趨勢
第 | 目前日期 (裝置摘要) 
 
 
## <a name="device-trends"></a>裝置趨勢 
依預設，裝置趨勢會顯示30天期間的裝置資訊，從最近的全天結束。 若要深入瞭解組織中發生的趨勢，您可以調整顯示的時段，以微調報告期間。 若要調整時段，請從下拉式選項中選取時間範圍：
 
- 30 天
- 3 個月
- 6 個月
- 自訂

>[!NOTE]
>這些篩選器僅適用于 [裝置趨勢] 區段。 它不會影響裝置摘要區段。

## <a name="device-summary"></a>裝置摘要 
在裝置趨勢顯示趨勢裝置資訊時，裝置摘要會顯示裝置資訊的範圍是目前的日期。 

>[!NOTE]
>在 [摘要] 區段中反映的資料範圍是在目前日期之前的180天。 例如，如果今天的日期是2019年3月27日，則 [摘要] 區段中的資料會反映從9月28日開始，2018到3月 2019 27 日的數位。<br>
> 在 [趨勢] 區段上套用的篩選不會在 [摘要] 區段上套用。 
 
[裝置趨勢] 區段可讓您向下流覽至已套用對應篩選的 [裝置] 清單。 例如，按一下感應器健康狀態卡片上的非作用中的條碼，會顯示 [裝置] 清單，其中的結果只會顯示其感應器狀態為「非使用中」的裝置。 
 
 
 
## <a name="device-attributes"></a>裝置屬性
報告是由顯示下列裝置屬性的卡片所組成：
 
- **健康狀態**：顯示裝置上感應器狀態的相關資訊，提供作用中裝置的匯總視圖、未使用的通訊、非使用中或未看到的感應器資料。
  
- **Active Windows 10 裝置的防毒程式狀態**：顯示裝置數目及 Microsoft Defender 防病毒的狀態。
    
- **作業系統平臺**：顯示組織記憶體在的作業系統平臺散佈。 
 
- **Windows 10 版本**：顯示組織中 windows 10 裝置和其版本的散佈。
 
 
 
## <a name="filter-data"></a>篩選資料
 
使用提供的篩選，以包含或排除具有特定屬性的裝置。

您可以從裝置屬性選取多個要套用的篩選器。 
 
>[!NOTE]
>這些篩選器適用于報告中的 **所有** 卡片。
 
例如，若要顯示具有使用中感應器健全狀態的 Windows 10 裝置相關資料：
 
1. 在 [篩選] 底下 **> 感應器健全狀況狀態 > Active**。
2. 然後，選取 [ **作業系統平臺] > Windows 10**。
3. 選取 **套用**。


## <a name="related-topic"></a>相關主題
- [威脅防護報告](threat-protection-reports.md)
