---
title: Windows 安全性更新深入解析
description: ''
keywords: Microsoft 受管理的電腦, Microsoft 365, 服務, 文件
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: b3b1f43217b3be285f20925065bf9710a38f9606
ms.sourcegitcommit: cebbdd393dcfd93ff43a1ab66ad70115853f83e7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/03/2021
ms.locfileid: "52739769"
---
# <a name="windows-security-update-insights"></a>Windows 安全性更新深入解析
此視圖提供 Microsoft 受管理的電腦裝置之安全性更新狀態的概覽。 

若要查看使用狀況資料，請選取 [ <strong>Windows 安全性更新</strong>] 索引標籤。

![Windows 安全性更新窗格：在左欄中，裝置狀態和更新版本的橫條圖，更新 center column 中的「部署進度」和「使用中裝置的百分比」和「作用中裝置的百分比」，以及在右列中到達95% 部署目標所需的天數。](../../media/update-insights.jpg)

## <a name="device-status"></a>裝置狀態

若要 Windows 更新來更新裝置，必須將這些裝置連線到網際網路，而且至少需要六小時才能進行休眠，其中兩個必須是連續的。 雖然不符合這些需求的裝置可能會更新，但符合這些需求的裝置會更新最高的可能性。 

使用下列條款，我們會在 Windows 更新內容中分類裝置活動：

- <strong>Active：</strong>符合最低活動準則的裝置 (六個小時、兩個連續的安全性更新版本) ，且已使用 Microsoft Intune 至少每五天簽入。
- 已<strong>同步處理：</strong>過去28天內，已使用 Intune 簽入的裝置
- 不<strong>同步：</strong>過去28天內，<i>未</i>以 Intune 簽入的裝置




## <a name="update-version-status"></a>更新版本狀態

Microsoft 每月的第二個星期二發行安全性更新。 每個發行版本本都會針對已知的安全性弱點新增重要的更新。 Microsoft 受管理的電腦保證每月更新95% 的受管理裝置的最新可用安全性更新。 安全性更新有時會在其他時間發行，以迫切解決新的威脅。 Microsoft 受管理的電腦以類似的方式來部署這些更新。

我們會使用下列條款來分類安全性更新版本的狀態：

- <strong>Current：</strong> 目前月內發行更新的裝置
- <strong>舊：</strong> 執行上個月發行之更新的裝置
- <strong>舊：</strong> 在前一個月之前，執行已發行之任何安全性更新的裝置

您應該會看到<strong>較舊</strong>類別中的一些裝置-大量或成長中的人口可能表示您應該向 Microsoft 受管理的電腦報告的系統性問題，我們可以進行調查。


## <a name="deployment-progress"></a>部署進度

在每個安全性更新發行週期開始時，Microsoft 受管理的電腦會取得裝置人口的快照，並在該人口的95% 的位置設定其部署目標。 「 <strong>部署進度</strong> 」區域會顯示一項歷史趨勢，每日更新，追蹤每個版本的更新部署符合此目標的程度。 此圖只會顯示具有主動狀態的裝置。

您可以使用右上角的下拉式功能表，查看先前更新週期的資料。 您在此功能表中選取的期間會套用至整個頁面上的所有資訊。

<strong>根據「部署」群組區域更新</strong>的使用中裝置，會顯示每個 Microsoft 受管理的電腦部署群組的更新安裝進度，以提供不同的視圖。

[ <strong>到達目標天數</strong> ] 區域會顯示要使用目前的安全性更新來更新之總裝置數目的95% 時所花費的時間。 進行部署時，此區域會顯示 <strong>仍更新</strong> ，直到選取的更新到達95% 目標為止。

## <a name="device-details-area"></a>裝置詳細資料區域

儀表板底部是顯示裝置之詳細資訊的表格，包括 [裝置狀態](#device-status) 和 [更新版本狀態](#update-version-status)。 您可以搜尋此清單，或按任何列出的值加以篩選。


![顯示裝置名稱、指派使用者、裝置狀態、更新版本、作業系統版本以及裝置上次同步處理日期欄的裝置詳細資料表格。](../../media/security-update-insights-device-table-sterile.png)
