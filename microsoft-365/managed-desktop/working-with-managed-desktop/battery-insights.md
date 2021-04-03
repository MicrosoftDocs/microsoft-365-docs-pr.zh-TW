---
title: 電池深入解析
description: 顯示有關預測電池壽命和最上層電量消費者的資料的報告
keywords: Microsoft 受管理的電腦, Microsoft 365, 服務, 文件
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 32ab3a984d5ab46aac26989518cd3e570082d688
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579707"
---
# <a name="battery-insights"></a>電池深入解析
此視圖會為 Microsoft 受管理的桌面裝置提供電源、電池和應用程式使用方式度量。 在這些情況下，如果應用程式正在執行中且處於焦點，便會被視為「使用中」。

若要查看使用狀況資料，請選取 [ **電池** ] 索引標籤。

![[電池] 窗格：左上方的每個裝置模型的預測電池壽命：左上方 (依應用程式) 右下方（深入）。 右上方的檔連結](../../media/insights_battery.png)

## <a name="predicted-battery-life"></a>預測電池壽命

在 [ **預計電池壽命** ] 區域中，我們會針對您的裝置，依裝置模型所組織，提供預期電池壽命的預測。

> [!NOTE]
> 這項資料衍生自您從 Microsoft 管理的桌面部署（也是報告資料）的隨機 <em>選擇</em> 裝置中的能源使用量、使用時間和電池容量。

此表格提供預測電池壽命 (以小時為單位）) 、其他 Microsoft 受管理桌面部署中相同模型的平均電池壽命，以及在您的環境中報告此資料的裝置數量。 選取欄標題以排序資料。



## <a name="top-energy-consumers"></a>主要能源消費者

在 [ **最熱門的能源消費者** ] 區域中，您將會發現環境中的應用程式，在 milliWatt) 中消耗最高的能耗 (mWh。 顯示的應用程式為每個特定裝置，您可以在左側的 **預測電池壽命** 區段中選取。 例如，若要查看 Microsoft Surface Book 2 裝置的每個應用程式消耗量，請選取 [電池壽命] 區域中的那一列。 如果您未選取任何模型，則所顯示的應用程式消耗資料是針對我們所有具有共同資料的應用程式。

 在每個應用程式中，彩色區段會顯示應用程式在下列類別中所使用的能源使用方式：

- CPU
- 顯示器
- 網路
- 其他

"Other" 可以包含各種來源的能量消耗，例如磁片活動、行動寬頻使用量和對內部阻力的能量遺失。 

您可以使用右上角的功能表篩選此視圖，只顯示前景應用程式、背景應用程式或兩者。 前臺應用程式是指在過去28天內，已有使用者互動的應用程式，例如使用滑鼠選取某些專案。

## <a name="insights"></a>深入解析

**Insights** 區域會顯示 CPU 和網路類別中的前三個能源消費者。 與所有 Microsoft 受管理的桌面部署相比，這些專案消耗的能耗高於平均能耗。 由於大量取決於裝置使用時間和螢幕亮度設定，因此不會顯示顯示資源。 

選取 [ **詳細資料** ] 欄中的清單以取得詳細資訊。

## <a name="battery-optimization"></a>電池優化

Windows 10 提供許多 [裝置設定](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips) ，以改善電源使用狀況，並增加 Microsoft 受管理桌面裝置的電池壽命。 其中的部分設定可能會減少其他 Windows 功能，因此您也必須考慮其他因素，例如組織中裝置的角色。 Windows 支援會維護這些 [電池儲存提示](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips)的清單。

使用者可以自行調整某些設定，而不需要系統管理員提升或支援。 其他設定需要您組織的 IT 管理員提供支援。
