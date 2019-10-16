---
title: Microsoft 受管理電腦中更新的處理方式
description: 保持最新 Microsoft 受管理的電腦是權衡方式速度與穩定性。
keywords: Microsoft 受管理的電腦，Microsoft 365 服務，文件
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: ed95d7d854422fe0cd2379e21b5de36a0c680c4b
ms.sourcegitcommit: eed48c21790d31a85292f7e39bf1e30c42f10d36
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/15/2019
ms.locfileid: "37523578"
---
# <a name="how-updates-are-handled-in-microsoft-managed-desktop"></a>Microsoft 受管理電腦中更新的處理方式


<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/update-rings); do not delete.-->

<!--Update management -->

Microsoft 受管理的電腦會將所有的裝置連接到新式的基於雲端的基礎結構。 保持 Windows、 Office、 驅動程式、 韌體和 Microsoft 網上商店商務應用程式的最新狀態是權衡方式速度與穩定性。 部署群組將會用來確保作業系統更新，原則會導入安全的方式。 

由 Microsoft 發行的更新是累加的並可分類為 「 品質] 或 [功能更新。
如需詳細資訊，請參閱[適用於企業的 Windows 更新： 更新類型](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb#update-types)。 

## <a name="update-groups"></a>更新群組

Microsoft 受管理的電腦使用四個 Azure AD 群組管理更新：

- **測試**： 用來驗證 Microsoft 受管理電腦原則變更，作業系統系統更新功能更新，以及其他變更推送至租用戶。 不應該放置在測試群組中任何使用者。 測試群組是免除任何已建立的服務等級協定和使用者支援。 此群組適用於驗證的新原則] 或 [作業系統 hanges 應用程式相容性。  
- **第一個**： 包含早期軟體採納者和可能受到搶鮮版更新的裝置。 如果有程式以測試環狀測試期間未深入涵蓋的案例，此群組中的裝置可能會遇到中斷。
- **Fast**： 來透過穩定性的優先順序速度。 適用於偵測品質問題，其提供給廣泛群組之前。 此群組做為下一個圖層的驗證，但通常更穩定，比測試與第一個群組。 
- **廣泛**： 有可用的功能和品質更新的最後一個群組。 此群組包含大多數的租用戶中的使用者，並因此偏好穩定性使用透過部署中的速度。 應執行的應用程式的測試環境是最穩定在這裡。 

> [!NOTE]
> 如果您需要將使用者移至不同的更新群組，提交支援要求。 如需提交支援要求的詳細資訊，請參閱[Microsoft 受管理電腦的支援](support.md)。 如果您自行移動使用者，將還原移動。

如需詳細資訊的角色與責任與這些部署群組，請參閱[Microsoft 受管理的桌上型電腦角色和責任](../intro/roles-and-responsibilities.md)

如何更新部署的運作：
- Microsoft 受管理電腦部署根據以下指定的排程的新功能或品質更新。
- 部署期間，Microsoft 受管理的電腦會監視的失敗或中斷 （根據診斷資料和使用者支援系統）。 如果任何偵測到，會立即暫停部署，以目前和未來的所有群組。
    - 範例： 如果發現問題時，同時部署品質更新的第一個群組，然後更新部署至名字]、 [Fast 和 [廣泛將所有暫停，直到問題解決為止。
    - 可由 Microsoft 受管理的桌上型電腦系統管理入口網站中歸檔票證報告相容性問題。
- 功能和品質更新獨立暫停。 暫停是作用中的預設值，為 35 天但是可以降低或根據是否已修復此問題： 延伸。
- 一旦群組未暫停，部署會繼續根據下列的排程。
- 此部署程序適用於功能和品質更新，但是時間表而異每個。




<table>
<tr><th colspan="5">更新部署設定</th></tr>
<tr><th>更新類型</th><th>測試</th><th>名字</th><th>快速</th><th>廣泛</th></tr>
<tr><td>作業系統的品質更新</td><td>0 天</td><td>0 天</td><td>0 天</td><td>3 天</td></tr>
<tr><td>作業系統功能更新</td><td>0 天</td><td>30 天</td><td>60 天</td><td>90 天</td></tr>
<tr><td>驅動程式/韌體</td><td colspan="4">遵循品質更新的排程</td></tr>
<tr><td>防毒定義</td><td colspan="4">更新每個掃描</td></tr>
<tr><td>Office 365 專業增強版</td><td colspan="4">採用 Office 的每月通道
</table>

Office 365 專業增強版每月通道的相關資訊，請參閱[Office 365 專業增強版更新通道的概觀](https://docs.microsoft.com/deployoffice/overview-of-update-channels-for-office-365-proplus)。

>[!NOTE]
>這些延期期間刻意為了確保高的安全性和效能標準的所有使用者。 此外，跨所有 Microsoft 受管理的電腦裝置和不同範圍及更新的影響所收集的資料為基礎，Microsoft 受管理的電腦會保留彈性，可修改 ad 上的任何及所有部署群組的上述延期期間的長度特別為基礎。
>
>Microsoft 受管理的電腦進行獨立評估的每個要評估其和實用性至其受管理的租用戶的 Windows 功能版本。 因此，Microsoft 受管理的電腦可能或可能不會部署所有的 Windows 功能更新。 

## <a name="windows-insider-program"></a>Windows 測試人員計畫

Microsoft 受管理的電腦不支援 Windows 測試人員計畫的一部分的裝置。 Windows 測試人員計畫用來驗證搶鮮版 Windows 軟體，僅適用於不重要的裝置。 雖然這是很重要的 Microsoft 計劃，但它不是實際執行環境中的廣泛部署。 

與 Windows 測試人員組建找到任何裝置可能會放入測試群組，而且會是免除更新的服務等級協定及從 Microsoft 受管理電腦的使用者支援。

## <a name="bandwidth-management"></a>頻寬管理

我們所有的作業系統和驅動程式更新使用[傳遞最佳化](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization)。 這將最小化的搜尋從公司網路內的對等的更新從 Windows Update 服務的下載大小。


