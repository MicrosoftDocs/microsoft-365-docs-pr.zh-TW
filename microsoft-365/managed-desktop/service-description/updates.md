---
title: Microsoft 受管理電腦中更新的處理方式
description: 保持最新的 Microsoft 受管理的桌上型電腦是速度和穩定性的平衡。
keywords: Microsoft 受管理的桌上型電腦、 [Microsoft 365 服務、 文件
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 01/09/2019
ms.openlocfilehash: bee6381b0f2b7b1e2d929329c3cf628ab7657678
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/16/2019
ms.locfileid: "26866225"
---
# <a name="how-updates-are-handled-in-microsoft-managed-desktop"></a>Microsoft 受管理電腦中更新的處理方式


<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/update-rings); do not delete.-->

<!--Update management -->

Microsoft 受管理的桌上型電腦連接至現代雲端式基礎結構的所有裝置。保持 Windows、 Office、 發行的驅動程式、 韌體和 Microsoft 存放區商務應用程式更新的最新是速度和穩定性的平衡。部署鈴響會用來確保 OS 和原則導安全的方式。 

## <a name="update-groups"></a>更新群組

Microsoft 受管理的桌上型電腦管理更新使用 Azure AD 的四個群組：

- 測試： 對非實際執行裝置用來驗證變更前的租用戶其餘跨部署所做的變更。在此響鈴的裝置已超出範圍所記載的使用者支援。 
- 第一個： 包含早期的軟體採用者和裝置可能會受限於發行前更新。
- Fast： 設定與穩定性優先順序速度。適用於偵測品質問題之前所提供的廣泛的群組。 
- 列出： 有可用的功能和品質更新的最後一個群組。此群組包含使用者的承租人，讓大多數與因此偏重穩定性透過在部署的速度。

在 Microsoft 發行的更新累計且可能會歸類為品質或功能的更新。如需詳細資訊，請參閱[Windows Update： 常見問題集](https://support.microsoft.com/help/12373/windows-update-faq)。 

如何更新部署的運作：
- Microsoft 受管理的桌上型電腦部署根據下列指定的排程的新功能或品質更新。
- 在部署期間 Microsoft 受管理的桌上型電腦監視的失敗或中斷 （根據遙測信號和使用者支援系統）。如果任何偵測再部署至所有目前和未來群組立即暫停。
    - 範例： 時部署的第一個群組的品質更新發現問題時，然後更新部署至第一個、 Fast、 及列出將所有暫停，直到問題已解決。
    - 可能會回報的歸檔票證 Microsoft 受管理的桌上型電腦 IT 管理員入口網站中的相容性問題。
- 功能和品質更新單獨暫停。暫停作用中的預設 35 天但是可以降低或延伸根據是否會在於問題。
- 一旦群組未暫停，部署繼續根據以下的排程。
- 此部署程序但是時間表而異各項功能和品質更新適用於。

<table>
<tr><th colspan="5">更新部署設定</th></tr>
<tr><th>更新類型</th><th>測試</th><th>第一個</th><th>快速</th><th>廣泛</th></tr>
<tr><td>作業系統的品質更新</td><td>0 天</td><td>0 天</td><td>0 天</td><td>為 3 天</td></tr>
<tr><td>作業系統的功能更新</td><td>0 天</td><td>30 天</td><td>60 天</td><td>90 天</td></tr>
<tr><td>發行的驅動程式/韌體</td><td colspan="4">遵循品質更新的排程</td></tr>
<tr><td>防毒定義</td><td colspan="4">更新的每個掃描</td></tr>
</table>

刻意設計這些延期期間被用來確保高的安全性與效能標準 （英文） 的所有使用者。此外，跨所有 Microsoft 受管理的桌上型電腦裝置不同範圍與更新的影響收集的資料為基礎，Microsoft 受管理的桌上型電腦會保留彈性，可修改任何及所有部署 ad 群組的上述延期期間的長度臨機操作基礎。

## <a name="windows-insider-program"></a>Windows 內部程式

Microsoft 受管理的桌上型電腦不支援 Windows 內部程式的一部分的裝置。Windows 內部程式用來驗證測試版 Windows 軟體與適用於非關鍵性關鍵裝置的。雖然這是重要的 Microsoft 計劃，它不是廣泛實際執行環境中部署。 

與 Windows 內部組建找到任何裝置將會放入測試群組而且無法供更新服務等級協定 (Sla。

## <a name="bandwidth-management"></a>頻寬管理

傳遞最佳化適用於所有作業系統的系統與驅動程式更新。它將最小化所希望從公司網路內的對等更新下載大小從 Windows Update (WU) 服務。


