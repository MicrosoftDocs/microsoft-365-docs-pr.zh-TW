---
title: 步驟 2： 修正第一個事件
description: 如何開始修正 Microsoft 365 Defender 中的第一個事件。
keywords: 事件、警示、調查、關聯性、攻擊、電腦、裝置、使用者、identity、身分識別、信箱、電子郵件、365、microsoft、m365、事件回應、網路攻擊
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: ed597c55a646eb00d6e6d256c287b22c119f8148
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/10/2021
ms.locfileid: "52297341"
---
# <a name="step-2-remediate-your-first-incident"></a>步驟 2. 修正第一個事件

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用於：**
- Microsoft 365 Defender

Microsoft 365Defender 不僅提供偵測和分析功能，還提供惡意程式碼的包容和 eradication。 包容包含減少攻擊影響的步驟，eradication 可確保從網路中移除攻擊者活動的所有痕跡。  Microsoft 365Defender 提供數項修復動作，可根據您的作業系統和攻擊類型設定為[自動修復](m365d-autoir.md)。

Microsoft 365Defender 提供數種修正動作，讓分析員可以手動啟動。 動作分為兩類、裝置上的動作和檔案的動作。 某些動作可用於立即停止威脅，其他動作可協助進行進一步的鑒證分析。

## <a name="actions-on-devices"></a>裝置上的動作

- **隔離裝置** -此活動會立即封鎖所有網路流量 (internet 和內部) ，以將惡意程式碼傳播降至最低，並允許分析員繼續進行分析，而不會有惡意參與者能夠繼續攻擊。 唯一允許的連線是 Microsoft Defender for Identity service cloud，所以 Microsoft Defender 身分識別可以繼續監視裝置。 
- **限制應用程式執行** -若要限制應用程式的執行，請套用程式碼完整性原則，僅允許檔案以 Microsoft 發行的憑證簽署時執行。 這種限制方式可協助防止攻擊者控制已受損的裝置，並進一步執行惡意活動。
- **執行防病毒掃描**-Microsoft Defender 防毒軟體掃描可與其他防病毒解決方案一起執行，不論是否為使用中的防病毒解決方案。 若其他防病毒廠商產品為主要 endpoint protection 解決方案，您可以在被動模式中執行 Defender 防毒軟體。
- **啟動自動調查** -您可以在裝置上啟動新的一般用途自動調查。 在執行調查時，系統會將從裝置產生的任何其他警示新增至進行中的自動調查，直到完成調查為止。 此外，如果在其他裝置上看到相同威脅，就會將這些裝置新增至調查。
- **啟動 live response** -live response 是一種可讓您透過遠端命令介面連線立即存取裝置的功能。 這可讓您執行深入調查工作，並立即採取回應動作，及時包含識別威脅。 Live response 的設計目的是讓您可以收集法律調查資料、執行腳本、傳送可疑實體以進行分析、修正威脅，以及主動搜尋新興威脅。
- **收集調查套件** -在調查或回應過程中，您可以從裝置收集調查套件。 透過收集調查套件，您可以識別目前的裝置狀態，並進一步瞭解攻擊者所使用的工具和技術。 
- **請參閱威脅專家** (在裝置和檔案) 上的兩個動作皆可使用。您可以參閱 Microsoft 威脅專家，以取得更深入瞭解可能已遭破壞的裝置或裝置。 Microsoft 威脅專家可以直接從 Microsoft Defender 資訊安全中心內直接參與，以進行及時且準確的回應。 

## <a name="actions-on-files"></a>檔上的動作

- **停止和隔離** 檔-此動作包括停止執行中的程式、隔離檔案，以及刪除持久性資料，例如任何登錄機碼。 此巨集指令會在裝置上的 Windows 10，版本1703或更新版本之間生效，在過去30天內觀察到檔案。 
- **將指標新增至封鎖或允許** 檔案-透過 banning 潛在的惡意檔案或可疑惡意程式碼，避免進一步傳播您組織中的攻擊。 這項作業會使檔案無法在組織中的裝置上讀取、寫入或執行。
- **下載或收集** 檔案–這項動作可讓分析員以受密碼保護的 .zip 封存檔下載檔案，以供組織進一步分析。
- **深入分析** –此動作會在安全且充分受充分規范的雲端環境中執行檔案。 深入分析結果會顯示檔案的活動、觀測的行為和相關聯的專案，例如：刪除的檔案、登錄修改以及與 IP 位址的通訊。 

繼續執行偵測 [、會審及分析事件](first-incident-analyze.md#analyze-your-first-incident)中的範例，分析人員可以利用下列動作來修正此事件：

1. 立即重設使用者帳戶密碼
2. 隔離 Microsoft 365 Defender 中的裝置，直到深入分析完成
3. 確定惡意檔案已從 SharePoint 隔離
4. 檢查惡意軟體所影響的端點
5. 重建系統
6. 檢查其他使用者的類似 Microsoft Cloud App Security 警示
7. 在 Microsoft Defender for Endpoint 中建立自訂指示器，以封鎖 Tor IP 位址
8. 在 Microsoft Cloud App Security 中為這類警示（如下列影像所示）建立管理動作：

   :::image type="content" source="../../media/first-incident-remediate/first-incident-mcas-governance.png" alt-text="Microsoft Cloud App Security 入口網站中的管理動作範例"::: 
 
在 Microsoft 365 Defender 中，您可以套用及追蹤大部分的修復動作。 

## <a name="using-playbooks"></a>使用行動手冊

此外，您可以使用行動手冊建立自動修復。 目前，Microsoft[在 GitHub 上的行動手冊範本](https://github.com/microsoft/Microsoft-Cloud-App-Security/tree/master/Playbooks)可提供下列案例的行動手冊：

- 在要求使用者驗證之後移除敏感檔案共用
- 自動會審非常見國家警示
- 停用帳戶之前要求管理員執行的動作
- 停用惡意的收件匣規則

行動手冊使用 Power Automate 建立自訂自動程式自動化流程，以在觸發特定準則之後，自動執行某些動作。 組織可以從現有的範本或從頭開始建立行動手冊。 

以下為範例。
 
:::image type="content" source="../../media/first-incident-remediate/first-incident-power-automate.png" alt-text="Power Automate 自訂自動進程自動化流程的範例"::: 
 
行動手冊也可在 [後續事件檢查](first-incident-post.md) 期間建立，以從事件建立修正動作，以加快修正動作的速度。 

## <a name="next-step"></a>下一步

[![步驟3：瞭解如何執行事件的事件後檢查](../../media/first-incident-overview/first-incident-path-step3.png)](first-incident-post.md)

瞭解如何對 [事件執行後續事件複查](first-incident-post.md)。

## <a name="see-also"></a>請參閱

- [事件概觀](incidents-overview.md)
- [調查事件](investigate-incidents.md)
- [管理事件](manage-incidents.md)
