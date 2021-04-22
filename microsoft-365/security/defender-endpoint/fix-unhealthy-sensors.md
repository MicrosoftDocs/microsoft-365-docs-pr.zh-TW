---
title: 修正 Microsoft Defender for Endpoint 中的狀況不良感應器
description: 修正報告為錯誤設定或非使用中的設備感應器，以供服務接收來自裝置的資料。
keywords: 誤設定、非使用中、修復感應器、感應器狀況、無感應器資料、感應器資料、受損通訊、通訊
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
ms.date: 11/06/2020
ms.technology: mde
ms.openlocfilehash: c4cdc80170b49a111f476d2d17222c41e2b5c55f
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935362"
---
# <a name="fix-unhealthy-sensors-in-microsoft-defender-for-endpoint"></a>修正 Microsoft Defender for Endpoint 中的狀況不良感應器

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

- 想要體驗適用於端點的 Microsoft Defender 嗎？ [注册免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-fixsensor-abovefoldlink)

分類為設定錯誤或非使用中的裝置會因原因不同而加以標記。 本節提供一些有關可能導致裝置分類為非使用中或設定不當的說明。

## <a name="inactive-devices"></a>非使用中的裝置

非使用中的裝置不一定會因問題而標示。 對裝置執行下列動作可能會造成裝置分類為非使用中：

### <a name="device-is-not-in-use"></a>裝置未使用中

如果裝置由於任何原因尚未使用超過7天，它會保持入口網站中的「非使用中」狀態。

### <a name="device-was-reinstalled-or-renamed"></a>裝置已重新安裝或重新命名
重新安裝或重新命名的裝置會在 Microsoft Defender Security Center 中產生新的裝置實體。 在入口網站中，舊的裝置實體仍會保持「非使用中」狀態。 如果您重新安裝裝置，並部署了端點套件的 Defender 套件，請搜尋新的裝置名稱，以確認裝置正常報告。

### <a name="device-was-offboarded"></a>裝置已 offboarded
如果裝置 offboarded，它仍會出現在 [裝置] 清單中。 7天后，裝置健康狀態應該變更為 [非使用中]。

### <a name="device-is-not-sending-signals"></a>裝置未傳送信號
如果裝置在任何原因（包括設定未設定的裝置分類中的條件）上，不會將任何信號傳送至任何 Microsoft Defender for Endpoint 通道，則會將裝置視為非使用中。 

您期望裝置處於「主動」狀態嗎？ [開啟支援票證](https://support.microsoft.com/getsupport?wf=0&tenant=ClassicCommercial&oaspworkflow=start_1.0.0.0&locale=en-us&supportregion=en-us&pesid=16055&ccsid=636206786382823561)。

## <a name="misconfigured-devices"></a>錯誤的裝置
設定錯誤的裝置可進一步分類為：
- 受損的通訊
- 無感應器資料

### <a name="impaired-communications"></a>受損的通訊
此狀態表示裝置與服務之間的通訊有限。

下列建議的動作可協助修正已設定不當之裝置的相關問題，但通訊已受損：

- [確定裝置具有網際網路連線](troubleshoot-onboarding.md#troubleshoot-onboarding-issues-on-the-device)</br>
  適用於端點的 Microsoft Defender 感應器需要 Microsoft Windows HTTP (WinHTTP) 回報感應器資料，並與適用於端點的 Microsoft Defender 服務通訊。

- [驗證 Endpoint service URLs 的用戶端與 Microsoft Defender 的連線能力](configure-proxy-internet.md#verify-client-connectivity-to-microsoft-defender-for-endpoint-service-urls)</br>
  驗證 proxy 設定是否順利完成，該 WinHTTP 可以透過您環境中的 proxy 伺服器探索和通訊，而且 proxy 伺服器允許流量至 Microsoft Defender for Endpoint service URLs。

如果您採取了糾正動作但裝置狀態仍設定不正確，請 [開啟支援票證](https://go.microsoft.com/fwlink/?LinkID=761093&clcid=0x409)。

### <a name="no-sensor-data"></a>無感應器資料
錯誤設定的裝置具有狀態 ' 無感應器資料」與服務的通訊，但只能報告部分感應器資料。
遵循下列動作，修正與錯誤設定的裝置相關的已知問題，狀態為「沒有感應器資料」：

- [確定裝置具有網際網路連線](troubleshoot-onboarding.md#troubleshoot-onboarding-issues-on-the-device)</br>
  適用於端點的 Microsoft Defender 感應器需要 Microsoft Windows HTTP (WinHTTP) 回報感應器資料，並與適用於端點的 Microsoft Defender 服務通訊。

- [驗證 Endpoint service URLs 的用戶端與 Microsoft Defender 的連線能力](configure-proxy-internet.md#verify-client-connectivity-to-microsoft-defender-for-endpoint-service-urls)</br>
  驗證 proxy 設定是否順利完成，該 WinHTTP 可以透過您環境中的 proxy 伺服器探索和通訊，而且 proxy 伺服器允許流量至 Microsoft Defender for Endpoint service URLs。

- [確定已啟用診斷資料服務](troubleshoot-onboarding.md#ensure-the-diagnostics-service-is-enabled)</br>
如果裝置的報告不正確，您可能需要檢查 Windows 10 診斷資料服務是否設定為自動啟動，並在端點上執行。

- [確定原則未停用 Microsoft Defender 防毒程式](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)</br>
如果您的裝置執行的是協力廠商反惡意軟體用戶端，則該 Defender 代理程式需要 Microsoft Defender 防毒程式的早期發行反惡意軟體 (ELAM) 驅動程式才能啟用。

如果您採取了糾正動作但裝置狀態仍設定不正確，請 [開啟支援票證](https://go.microsoft.com/fwlink/?LinkID=761093&clcid=0x409)。

## <a name="see-also"></a>另請參閱
- [檢查 Microsoft Defender for Endpoint 中的感應器健康狀態](check-sensor-status.md)
