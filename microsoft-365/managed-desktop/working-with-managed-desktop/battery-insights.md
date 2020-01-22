---
title: 電池深入解析
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentation, Microsoft 受管理的電腦, Microsoft 365, 服務, 文件
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: b14ef9970aa709ad5e23fdae467992497a1331e8
ms.sourcegitcommit: 3dca80f268006658a0b721aa4f6df1224c7964dc
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2020
ms.locfileid: "41260137"
---
# <a name="battery-insights"></a>電池深入解析
此檢視提供您的 Microsoft 受管理的電腦裝置電源、 電和應用程式使用狀況計量。 進行這些工作，應用程式被視為 「 使用 」 中，如果它正在執行，並在焦點。

若要檢視流量資料，請選取 [**電池**] 索引標籤。

![電池窗格： 跨底部預測電池壽命，每個裝置模型在左上方] （依應用程式） 的上方能源消費者，在右上] 觀點資料表。 在右上方的文件連結。](images/insights_battery.png)

## <a name="predicted-battery-life"></a>預測的電池壽命

在**Predicted 電池壽命**] 區域中，我們會提供您的裝置，依裝置型號的預期的電池壽命預測。

> [!NOTE]
> 此資料被衍生自取樣能源使用量、 使用量的時間及從隨機<em>選取範圍</em>內的裝置 Microsoft 受管理電腦部署也會報告資料的電池容量。

表提供預測的電池壽命 （以小時為單位），平均電池壽命的相同模型其他 Microsoft 受管理電腦的部署，並報告您環境中的此資料的裝置數目。 藉由選取欄標題來排序資料。



## <a name="top-energy-consumers"></a>上方能源消費者

在**上方能源消費者**] 區域中，您會發現應用程式耗用 milliWatt 小時 (mWh) 中的大部分能源您環境中。 顯示應用程式是每個特定裝置，向左**Predicted 電池壽命**區段中選取。 例如，若要查看您 Microsft Surface Book 2 的裝置的每個應用程式使用率，請電池壽命區域中選取該資料列。 如果您未選取任何模型，所顯示的應用程式耗用資料是我們統稱有資料的所有應用程式。

 每個應用程式，彩色的區段顯示您的應用程式的能源使用這些類別之間通訊：

- CPU
- 顯示
- 網路
- 其他

「 其他 」 可能包含能源所消耗的各種來源，例如磁碟活動、 行動寬頻使用量和能源至內部的抗拒遺失。 

應用程式中顯示 * * Top 能源取用者 」

您可以篩選此檢視，以顯示只有前景應用程式、 背景應用程式]，或兩者皆使用功能表右上角。 前景應用程式 」 是指有鎖 28 天內，例如選取某個項目與滑鼠與使用者互動。

## <a name="insights"></a>深入資訊

**深入了解**區域顯示上方的三個能源消費者 CPU 及網路類別。 這些項目會耗用高於平均能源相較於所有 Microsoft 受管理電腦部署。 我們不顯示顯示資源，因為它，取決於裝置使用量的時間和螢幕亮度設定。 

如需詳細資訊的**詳細資料**] 欄中，請選取 [清單]。

## <a name="battery-optimization"></a>電池最佳化

Windows 10 可提供許多[裝置設定](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips)] 若要改善 power 使用量增加您的 Microsoft 受管理的電腦裝置的電池壽命。 其中一些設定可以降低其他 Windows 功能，所以您也必須考慮其他因素影響，例如您組織中裝置的角色。 Windows 支援維護[電池省電祕](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips)這些的清單。

使用者可以調整自己而不需要系統管理員權限提高或支援某些設定。 其他設定需要支援您的組織從 IT 系統管理員。
