---
title: Microsoft 受管理電腦中更新的處理方式
description: 保持最新的 Microsoft 受管理的桌上型電腦是速度和穩定性的平衡。
keywords: Microsoft 受管理的桌上型電腦、 [Microsoft 365 服務、 文件
ms.service: m365-md
author: jdeckerms
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.openlocfilehash: 513e03b7d703e0a9f78281ddac764d8a29ed5c8f
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/28/2018
ms.locfileid: "26866225"
---
# <a name="how-updates-are-handled-in-microsoft-managed-desktop"></a>Microsoft 受管理電腦中更新的處理方式


<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/update-rings); do not delete.-->

<!--Update management -->

Microsoft 受管理的桌上型電腦連接至現代雲端式基礎結構的所有裝置。保持 Windows、 Office、 發行的驅動程式、 韌體和 Microsoft 存放區商務應用程式更新的最新是速度和穩定性的平衡。部署鈴響會用來確保 OS 和原則導安全的方式。 

## <a name="update-rings"></a>更新鈴響

Microsoft 受管理的桌上型電腦管理更新使用 Azure AD 的四個群組：

- 測試： 測試及驗證的客戶租用戶中所做的變更只設計測試響鈴。  
- 第一個： 第一次的目的是使用有限的 tech 知識願意早期安裝軟體並遵循某些預先發行更新的使用者才初期測試響鈴。
- Fast: Fast 響鈴為其中我們預期想大型一組使用者。 此響鈴的目標是保留裝置更新和安全與軟體傳遞快速速度。  
- 廣泛： 慢速響鈴為平衡的傳統 roll 超出品質和功能的更新。 品質更新仍會在 fast 傳遞的腳步，但不是會立即。 

響鈴系統中的更新可分類為 「 品質，或更新的功能：
- 品質更新包括安全性、 critical、 和驅動程式更新。 這些是通常是每月的更新。 
- 功能的更新中包含不僅安全性及品質修訂但還重要功能新增及變更;他們是分號每年發行。 

撥打升級的運作方式：
- Microsoft 受管理的桌上型電腦部署根據下列指定的排程的新功能或品質更新。
- 在部署期間 Microsoft 受管理的桌上型電腦監視的失敗或其他中斷 （透過遙測有空與我們使用者支援系統）;如果任何偵測再部署至所有目前和未來鈴響立即暫停。
    - 範例： 時的品質更新部署至第一個環發現問題時，然後先、 Fast、 及列出將所有暫停直到問題已解決。
    - 可能會回報的歸檔票證 Microsoft 受管理的桌上型電腦 IT 管理員入口網站中的相容性問題。
- 功能和品質更新單獨暫停。 暫停作用中的預設為 35 天但是可以降低或延伸根據是否會在於問題。
- 一旦鈴響未暫停，部署繼續根據以下的排程。
- 此升級程序但是時間表而異各項功能和品質更新適用於。

<table>
<tr><th colspan="5">鈴響和延期設定</th></tr>
<tr><th>更新類型</th><th>測試響鈴</th><th>第一個</th><th>快速</th><th>廣泛</th></tr>
<tr><td>作業系統的品質更新</td><td>0 天</td><td>0 天</td><td>1 天</td><td>5 天</td></tr>
<tr><td>作業系統的功能更新</td><td>半年度通道 （目標） + 0 天</td><td>半年度通道 （目標） + 30 天</td><td>半年度通道 （目標） + 60 天</td><td>半年度通道 + 30 天</td></tr>
<tr><td>發行的驅動程式/韌體</td><td colspan="4">遵循品質更新的排程</td></tr>
<tr><td>防毒定義</td><td colspan="4">更新的每個掃描</td></tr>
<tr><td>若要執行的 office 親加號 click</td><td colspan="4">對齊半年度通道</td></tr>
</table>


## <a name="windows-insider-program"></a>Windows 內部程式

Microsoft 受管理的桌上型電腦不支援 Windows 內部程式的一部分的裝置。此程式用來驗證測試版 Windows 軟體與適用於非關鍵性關鍵裝置的。雖然這是重要的 Microsoft 計劃，它不是廣泛實際執行環境中部署。 

與 Windows 內部組建找到任何裝置將會放入測試響鈴而且無法供更新 Sla。

## <a name="bandwidth-management"></a>頻寬管理

傳遞最佳化適用於所有作業系統的系統與驅動程式更新。它將最小化所希望從公司網路內的對等更新下載大小從 Windows Update (WU) 服務。


