---
title: 使用事件檢視器審閱事件和錯誤
description: 取得 Microsoft Defender for Endpoint service 所報告之所有事件的必要) ，以取得描述及進一步的疑難排解步驟 (。
keywords: 疑難排解、事件檢視器、記錄摘要、失敗代碼、失敗、Microsoft Defender for Endpoint service、無法啟動、已中斷、無法啟動
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
ms.date: 05/21/2018
ms.technology: mde
ms.openlocfilehash: a8b7268e89470a85a34015967b69abb1818fe64f
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933838"
---
# <a name="review-events-and-errors-using-event-viewer"></a>使用事件檢視器審閱事件和錯誤

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用於：**
- 事件檢視器
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>想要體驗適用於端點的 Microsoft Defender 嗎？ [注册免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-enablesiem-abovefoldlink)

您可以在個別裝置的 [事件檢視器](https://msdn.microsoft.com/library/aa745633(v=bts.10).aspx) 中審閱事件 IDs。

例如，如果裝置未出現在 [ **裝置] 清單** 中，您可能需要在裝置上尋找事件 IDs。 您可以使用此表格來決定進一步的疑難排解步驟。

**開啟事件檢視器，並尋找 Microsoft Defender for Endpoint service 事件記錄檔：**

1. 在 [Windows] 功能表上，按一下 [ **開始** ]，輸入 **事件檢視器**，然後按 **enter** 鍵。

2. 在 [記錄檔] 清單的 [**記錄摘要**] 下，向內滾動，直到看到 [ **Microsoft-Windows------Windows-** 按兩下專案以開啟記錄檔。

   a.  您也可以透過擴充 **應用程式和服務記錄**  >  **Microsoft**  >  **Windows**  >  **感知**，然後按一下 [**操作**] 來存取記錄。

   > [!NOTE]
   > 判斷是指用來表示為 Microsoft Defender for Endpoint 供電的行為感應器的內部名稱。

3. 服務所記錄的事件會出現在記錄檔中。 如需服務所記錄的事件清單，請參閱下表。

<table>
<tbody style="vertical-align:top;">
<tr>
<th>事件識別碼</th>
<th>訊息</th>
<th>描述</th>
<th>動作</th>
</tr>
<tr>
<td>1</td>
<td>Microsoft Defender for Endpoint service 已開始 (版本 <code>variable</code>) 。</td>
<td>發生于系統啟動、關機和上架期間。</td>
<td>正常運作通知;不需要任何動作。</td>
</tr>
<tr>
<td>第</td>
<td>Microsoft Defender for Endpoint service 關閉。</td>
<td>當裝置關閉或 offboarded 時會發生此事件。</td>
<td>正常運作通知;不需要任何動作。</td>
</tr>
<tr>
<td>個</td>
<td>無法啟動 Microsoft Defender for Endpoint service。 失敗代碼： <code>variable</code> 。</td>
<td>服務未啟動。</td>
<td>請複查其他訊息，以判斷可能的原因及疑難排解步驟。</td>
</tr>
<tr>
<td>4 </td>
<td>Microsoft Defender for Endpoint service 已于的伺服器取得聯繫 <code>variable</code> 。</td>
<td>Variable = 端點處理伺服器的 Defender URL。<br>
此 URL 會比對防火牆或網路活動中所看到的。</td>
<td>正常運作通知;不需要任何動作。</td>
</tr>
<tr>
<td>5 </td>
<td>Microsoft Defender for Endpoint service 無法連線至上的伺服器 <code>variable</code> 。</td>
<td>Variable = 端點處理伺服器的 Defender URL。<br>
服務無法與位於該 URL 的外部處理伺服器聯繫。</td>
<td>檢查 URL 的連線。 請參閱 <a href="configure-proxy-internet.md" data-raw-source="[Configure proxy and Internet connectivity](configure-proxy-internet.md)">設定 proxy 和網際網路連線</a>。</td>
</tr>
<tr>
<td>6 </td>
<td>Microsoft Defender for Endpoint service 未架，且找不到任何上架參數。</td>
<td>裝置沒有正確板載，而且不會向入口網站回報。</td>
<td>在啟動服務之前，必須先執行上架。<br>
檢查是否已正確部署上架設定和腳本。 嘗試重新部署設定套件。<br>
請參閱 <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">板載 Windows 10 裝置</a>。</td>
</tr>
<tr>
<td>7 </td>
<td>Microsoft Defender for Endpoint service 無法讀取上架參數。 失敗： <code>variable</code> 。</td>
<td>Variable = 詳細的錯誤描述。 裝置沒有正確板載，而且不會向入口網站回報。</td>
<td>檢查是否已正確部署上架設定和腳本。 嘗試重新部署設定套件。<br>
請參閱 <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">板載 Windows 10 裝置</a>。</td>
</tr>
<tr>
<td>8 </td>
<td>Microsoft Defender for Endpoint service 無法清除其設定。 失敗代碼： <code>variable</code> 。</td>
<td><b>在上架期間：</b> 服務無法在上架期間清除其設定。 上架處理常式會繼續進行。 <br><br> <b>脫離時：</b> 服務無法在脫離期間清除其設定。 脫離處理常式完成，但服務仍在執行中。
 </td>
<td>上<b>架：</b>不需要任何動作。 <br><br> <b>脫離：</b> 重新開機系統。<br>
請參閱 <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">板載 Windows 10 裝置</a>。</td>
</tr>
<tr>
<td>9 </td>
<td>Microsoft Defender for Endpoint service 無法變更其啟動類型。 失敗代碼： <code>variable</code> 。</td>
<td><b>在上架期間：</b> 裝置沒有正確板載，而且不會向入口網站回報。 <br><br><b>脫離時：</b> 無法變更服務啟動類型。 脫離處理常式會繼續進行。 </td>
<td>檢查是否已正確部署上架設定和腳本。 嘗試重新部署設定套件。<br>
請參閱 <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">板載 Windows 10 裝置</a>。</td>
</tr>
<tr>
<td>10 </td>
<td>Microsoft Defender for Endpoint service 無法保留上架資訊。 失敗代碼： <code>variable</code> 。</td>
<td>裝置沒有正確板載，而且不會向入口網站回報。</td>
<td>檢查是否已正確部署上架設定和腳本。 嘗試重新部署設定套件。<br>
請參閱 <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">板載 Windows 10 裝置</a>。</td>
</tr>
<tr>
<td>11 </td>
<td>上架服務已完成的 Defender 或重新加入。</td>
<td>裝置架正確。</td>
<td>正常運作通知;不需要任何動作。<br>
可能需要數小時的時間，裝置才會出現在入口網站中。</td>
</tr>
<tr>
<td>12 </td>
<td>Microsoft Defender for Endpoint 無法套用預設設定。</td>
<td>服務無法套用預設設定。</td>
<td>此錯誤應在一小段時間後解決。</td>
</tr>
<tr>
<td>13</td>
<td>Microsoft Defender for Endpoint 設備識別碼已計算： <code>variable</code> 。</td>
<td>正常工作處理程式。</td>
<td>正常運作通知;不需要任何動作。</td>
</tr>
<tr>
<td>15 </td>
<td>Microsoft Defender for Endpoint 無法使用 URL: 啟動命令通道 <code>variable</code> 。</td>
<td>Variable = 端點處理伺服器的 Defender URL。<br>
服務無法與位於該 URL 的外部處理伺服器聯繫。</td>
<td>檢查 URL 的連線。 請參閱 <a href="configure-proxy-internet.md" data-raw-source="[Configure proxy and Internet connectivity](configure-proxy-internet.md)">設定 proxy 和網際網路連線</a>。</td>
</tr>
<tr>
<td>17 </td>
<td>Microsoft Defender for Endpoint service 無法變更連線的使用者經驗和遙測服務位置。 失敗代碼： <code>variable</code> 。</td>
<td>Windows 遙測服務發生錯誤。</td>
<td><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">確定已啟用診斷資料服務</a>。<br>
檢查是否已正確部署上架設定和腳本。 嘗試重新部署設定套件。<br>
請參閱 <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">板載 Windows 10 裝置</a>。</td>
</tr>
<tr>
<td>18 </td>
<td>已完成 OOBE (Windows 歡迎) 。</td>
<td>只有在任何 Windows 更新安裝完畢後，服務才會啟動。</td>
<td>正常運作通知;不需要任何動作。</td>
</tr>
<tr>
<td>19</td>
<td>OOBE (Windows 歡迎) 尚未完成。</td>
<td>只有在任何 Windows 更新安裝完畢後，服務才會啟動。</td>
<td>正常運作通知;不需要任何動作。<br>
如果此錯誤在系統重新開機之後仍然存在，請確定所有 Windows 更新已完整安裝。</td>
</tr>
<tr>
<td>共</td>
<td>無法等候 OOBE (Windows 歡迎) 完成。 失敗代碼： <code>variable</code> 。</td>
<td>內部錯誤。</td>
<td>如果此錯誤在系統重新開機之後仍然存在，請確定所有 Windows 更新已完整安裝。</td>
</tr>
<tr>
<td>0.25</td>
<td>Microsoft Defender for Endpoint service 無法重設登錄中的健康狀態。 失敗代碼： <code>variable</code> 。</td>
<td>裝置沒有正確板載。
它會向入口網站回報，但服務可能不會顯示在 SCCM 或登錄中的註冊。</td>
<td>檢查是否已正確部署上架設定和腳本。 嘗試重新部署設定套件。<br>
請參閱 <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">板載 Windows 10 裝置</a>。</td>
</tr>
<tr>
<td>得到</td>
<td>Microsoft Defender for Endpoint service 無法在登錄中設定上架狀態。 失敗代碼： <code>variable</code> 。</td>
<td>裝置沒有正確板載。<br>
它會向入口網站回報，但服務可能不會顯示在 SCCM 或登錄中的註冊。</td>
<td>檢查是否已正確部署上架設定和腳本。 嘗試重新部署設定套件。<br>
請參閱 <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">板載 Windows 10 裝置</a>。</td>
</tr>
<tr>
<td>7</td>
<td>Microsoft defender for Endpoint service 無法啟用 Microsoft Defender 防毒軟體中的感知感知模式。 上架過程失敗。 失敗代碼： <code>variable</code> 。</td>
<td>一般情況下，如果其他即時惡意程式碼產品已在裝置上正常執行，則 Microsoft Defender 防病毒會進入特殊的被動狀態，而且裝置會向 Defender 報告端點。</td>
<td>檢查是否已正確部署上架設定和腳本。 嘗試重新部署設定套件。<br>
請參閱 <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">板載 Windows 10 裝置</a>。<br>
確定即時反惡意程式碼保護運作正常。</td>
</tr>
<tr>
<td>日</td>
<td>Microsoft Defender 連線使用者經驗與遙測服務註冊失敗。 失敗代碼： <code>variable</code> 。</td>
<td>Windows 遙測服務發生錯誤。</td>
<td><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">確定已啟用診斷資料服務</a>。<br>
檢查是否已正確部署上架設定和腳本。 嘗試重新部署設定套件。<br>
請參閱 <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">板載 Windows 10 裝置</a>。</td>
</tr>
<tr>
<td>29</td>
<td>無法讀取脫離參數。 錯誤類型： %1，錯誤碼： %2，描述： %3 </td>
<td>當系統可以&#39;t 讀取脫離參數時，就會發生此事件。</td>
<td>確定裝置具有網際網路存取權，然後再次執行整個脫離程式。 確定脫離套件尚未過期。</td>
</tr>
<tr>
<td>大約</td>
<td>Microsoft Defender for Endpoint service 無法停用 Microsoft Defender 防病毒中的感知感知模式。 失敗代碼： <code>variable</code> 。</td>
<td>一般情況下，如果其他即時惡意程式碼產品已在裝置上正常執行，則 Microsoft Defender 防病毒會進入特殊的被動狀態，而且裝置會向 Defender 報告端點。</td>
<td>檢查是否已正確部署上架設定和腳本。 嘗試重新部署設定套件。<br>
請參閱 <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">板載 Windows 10 裝置</a><br>
確定即時反惡意程式碼保護運作正常。</td>
</tr>
<tr>
<td>加</td>
<td>Microsoft Defender 連線使用者經驗與遙測服務登出失敗。 失敗代碼： <code>variable</code> 。</td>
<td>在上架期間執行 Windows 遙測服務時發生錯誤。 脫離處理常式會繼續進行。</td>
<td><a href="troubleshoot-onboarding.md#ensure-the-diagnostic-data-service-is-enabled" data-raw-source="[Check for errors with the Windows telemetry service](troubleshoot-onboarding.md#ensure-the-diagnostic-data-service-is-enabled)">使用 Windows 遙測服務檢查錯誤</a>。</td>
</tr>
<tr>
<td>32</td>
<td>Microsoft Defender for Endpoint service 無法在脫離程式後要求自行停用。 失敗代碼： %1</td>
<td>脫離時發生錯誤。</td>
<td>重新開機裝置。</td>
</tr>
<tr>
<td>33</td>
<td>Microsoft Defender for Endpoint service 無法保留感知 GUID。 失敗代碼： <code>variable</code> 。</td>
<td>唯一識別碼是用來表示每個向入口網站回報的裝置。<br>
如果識別碼不存在，相同的裝置可能會出現在入口網站的兩倍。</td>
<td>請檢查裝置的登入權利，以確定服務可更新登錄。</td>
</tr>
<tr>
<td>34</td>
<td>Microsoft Defender for Endpoint service 無法將其自我新增為對連接的使用者經驗和遙測服務的相依性，導致上架處理常式失敗。 失敗代碼： <code>variable</code> 。</td>
<td>Windows 遙測服務發生錯誤。</td>
<td><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">確定已啟用診斷資料服務</a>。<br>
檢查是否已正確部署上架設定和腳本。 嘗試重新部署設定套件。<br>
請參閱 <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">板載 Windows 10 裝置</a>。</td>
</tr>
<tr>
<td>35</td>
<td>Microsoft Defender for Endpoint service 無法將其自我移除為對連接的使用者經驗和遙測服務的依賴性。 失敗代碼： <code>variable</code> 。</td>
<td>在脫離時執行 Windows 遙測服務時發生錯誤。 脫離處理常式會繼續進行。
</td>
<td>使用 Windows 診斷資料服務檢查錯誤。</td>
</tr>
<tr>
<td>36</td>
<td>Microsoft Defender 連線使用者經驗和遙測服務註冊成功。 完成碼： <code>variable</code> 。</td>
<td>已成功完成登錄使用者經驗與遙測服務之端點的 Defender 註冊。</td>
<td>正常運作通知;不需要任何動作。</td>
</tr>
<tr>
<td>37</td>
<td>Microsoft Defender for Endpoint A 模組即將超出其配額。 模組： %1，配額： {%2} {%3}，配額利用率百分比： %4。</td>
<td>裝置幾乎已使用目前24小時視窗的已分配配額。 即將受到節流。</td>
<td>正常運作通知;不需要任何動作。</td>
</tr>
<tr>
<td>38</td>
<td>網路連線識別為低。 Microsoft Defender for Endpoint 會每隔 %1 分鐘與伺服器取得聯繫。 流量 %2，網際網路可用： %3，可用空閒網路： %4。</td>
<td>裝置使用的是計量/收費網路，且將不會頻繁地聯繫伺服器。</td>
<td>正常運作通知;不需要任何動作。</td>
</tr>
<tr>
<td>39</td>
<td>網路連線識別為正常。 Microsoft Defender for Endpoint 會每隔 %1 分鐘與伺服器取得聯繫。 流量 %2，網際網路可用： %3，可用空閒網路： %4。</td>
<td>裝置未使用計量中/付費的連線，因此會照常聯繫伺服器。</td>
<td>正常運作通知;不需要任何動作。</td>
</tr>
<tr>
<td>40</td>
<td>電池狀態識別為 [低]。 Microsoft Defender for Endpoint 會每隔 %1 分鐘與伺服器取得聯繫。 電池狀態： %2。</td>
<td>裝置的電池計量低，且將不會頻繁地與伺服器取得聯繫。</td>
<td>正常運作通知;不需要任何動作。</td>
</tr>
<tr>
<td>41</td>
<td>電池狀態識別為 [正常]。 Microsoft Defender for Endpoint 會每隔 %1 分鐘與伺服器取得聯繫。 電池狀態： %2。</td>
<td>裝置的電池計量低，且會照常聯繫伺服器。</td>
<td>正常運作通知;不需要任何動作。</td>
</tr>
<tr>
<td>42</td>
<td>Microsoft Defender for Endpoint 元件無法執行動作。 元件： %1，動作： %2，例外狀況類型： %3，例外訊息： %4</td>
<td>內部錯誤。 無法啟動服務。</td>
<td>如果此錯誤仍然存在，請與支援人員聯繫。</td>
</tr>
<tr>
<td>43</td>
<td>Microsoft Defender for Endpoint 元件無法執行動作。 元件： %1，動作： %2，例外狀況類型： %3，例外錯誤： %4，例外資訊： %5</td>
<td>內部錯誤。 無法啟動服務。</td>
<td>如果此錯誤仍然存在，請與支援人員聯繫。</td>
</tr>
<tr>
<td>44</td>
<td>終結點服務的已完成的 Defender 服務。</td>
<td>已 offboarded 服務。</td>
<td>正常運作通知;不需要任何動作。</td>
</tr>
<tr>
<td>45</td>
<td>無法註冊並啟動事件追蹤會話 [%1]。 錯誤碼： %2</td>
<td>建立 ETW 會話時，啟動服務時發生錯誤。 這會導致服務啟動失敗。</td>
<td>如果此錯誤仍然存在，請與支援人員聯繫。</td>
</tr>
<tr>
<td>46</td>
<td>由於資源缺乏，無法註冊並啟動事件追蹤會話 [%1]。 錯誤碼： %2。 這很可能是因為活動中的事件追蹤會話太多。 服務會在1分鐘後重試。</td>
<td>因為資源缺乏，所以在建立 ETW 會話時，啟動服務時發生錯誤。 服務已開始且正在執行，但在啟動 ETW 會話之前，不會報告任何感應器事件。</td>
<td>正常運作通知;不需要任何動作。 服務每分鐘會嘗試啟動會話。</td>
</tr>
<tr>
<td>47</td>
<td>已成功註冊並啟動事件追蹤會話-在先前的失敗嘗試之後復原。</td>
<td>此事件會在成功啟動 ETW 會話後，遵循上一個事件。</td>
<td>正常運作通知;不需要任何動作。</td>
</tr>
<tr>
<td>48</td>
<td>無法將提供者 [%1] 新增至事件追蹤會話 [%2]。 錯誤碼： %3。 這表示不會報告來自此提供者的事件。</td>
<td>無法將提供者新增至 ETW 會話。 因此，不會報告提供者事件。</td>
<td>檢查錯誤碼。 如果此錯誤仍然存在，請聯繫支援人員。</td>
</tr>
</tr>
<tr>
   <td>49</td>
   <td>接收和忽略的雲端設定命令無效。 版本： %1，狀態： %2，錯誤碼： %3，郵件： %4</td>
   <td>從已忽略的雲端服務接收到不正確設定檔。</td>
   <td>如果此錯誤仍然存在，請與支援人員聯繫。</td>
</tr>
<tr>
   <td>50</td>
   <td>已成功套用新的雲端設定。 版本： %1。</td>
   <td>已成功從雲端服務套用新設定。</td>
   <td>正常運作通知;不需要任何動作。</td>
</tr>
<tr>
   <td>51</td>
   <td>無法套用新的雲端設定，版本： %1。 已成功套用最後一個已知良好的設定，版本 %2。</td>
   <td>從雲端服務接收到錯誤的設定檔。 已成功套用上一個正確的設定。</td>
   <td>如果此錯誤仍然存在，請與支援人員聯繫。</td>
</tr>
<tr>
   <td>52</td>
   <td>無法套用新的雲端設定，版本： %1。 也無法套用最後一個已知良好的設定，版本 %2。 已成功套用預設設定。</td>
   <td>從雲端服務接收到錯誤的設定檔。 無法套用最近一次的正確設定，且已套用預設設定。</td>
   <td>服務會在5分鐘內嘗試下載新的設定檔。 如果您看不到事件 #50-請與支援人員聯繫。</td>
</tr>
<tr>
   <td>53</td>
   <td>從持久性儲存體載入雲端設定，版本： %1。</td>
   <td>在服務啟動時從持久性儲存體載入設定。</td>
   <td>正常運作通知;不需要任何動作。</td>
</tr>
<tr>
   <td>55</td>
   <td>無法建立安全的 ETW 自動記錄器。 失敗代碼： %1</td>
   <td>無法建立安全的 ETW 記錄記錄。</td>
   <td>重新開機裝置。 如果此錯誤仍然存在，請與支援人員聯繫。</td>
</tr>
<tr>
   <td>56</td>
   <td>無法移除 Secure ETW 自動記錄器。 失敗代碼： %1</td>
   <td>無法在脫離時移除 secure ETW 會話。</td>
   <td>聯繫支援人員。</td>
</tr>
<tr>
   <td>57</td>
   <td>出於疑難排解目的，捕獲機器的快照。</td>
   <td>會收集調查套件（也稱為取證套件）。</td>
   <td>正常運作通知;不需要任何動作。</td>
</tr>
<tr>
   <td>59</td>
   <td>開始命令： %1</td>
   <td>開始回應命令的執行。</td>
   <td>正常運作通知;不需要任何動作。</td>
</tr>
<tr>
   <td>60</td>
   <td>無法執行命令 %1，錯誤： %2。</td>
   <td>無法執行回應命令。</td>
   <td>如果此錯誤仍然存在，請與支援人員聯繫。</td>
</tr>
<tr>
   <td>61</td>
   <td>資料收集命令參數無效： SasUri： %1，compressionLevel： %2。</td>
   <td>無法讀取或剖析資料收集命令引數 (不正確引數) 。</td>
   <td>如果此錯誤仍然存在，請與支援人員聯繫。</td>
</tr>
<tr>
   <td>62</td>
   <td>無法啟動連線使用者體驗和遙測服務。 失敗代碼： %1</td>
   <td>連線的使用者經驗和遙測 (diagtrack) 服務無法啟動。 不會從此機器傳送非 Microsoft Defender for Endpoint 遙測。</td>
   <td>請參閱事件記錄檔中的更多疑難排解提示： Microsoft-Windows-UniversalTelemetryClient/Operational。</td>
</tr>
<tr>
   <td>63</td>
   <td>更新外部服務的啟動類型。 名稱： %1，實際啟動類型： %2，預期啟動類型： %3，退出程式碼： %4</td>
   <td>更新的外部服務啟動類型。</td>
   <td>正常運作通知;不需要任何動作。</td>
</tr>
<tr>
   <td>64</td>
   <td>開始已停止的外部服務。 名稱： %1，退出程式碼： %2</td>
   <td>啟動外部服務。</td>
   <td>正常運作通知;不需要任何動作。</td>
</tr>
<tr>
   <td>65</td>
   <td>無法載入 Microsoft Security 事件元件微篩選器驅動程式。 失敗代碼： %1</td>
   <td>無法載入 MsSecFlt.sys 的 filesystem 微篩選器。</td>
   <td>重新開機裝置。 如果此錯誤仍然存在，請與支援人員聯繫。</td>
</tr>
<tr>
   <td>66</td>
   <td>原則更新：延遲模式-%1</td>
   <td>已更新 C&C connection frequency 原則。</td>
   <td>正常運作通知;不需要任何動作。</td>
</tr>
<tr>
   <td>68</td>
   <td>服務的啟動類型是意外的。 服務名稱： %1，實際啟動類型： %2，預期啟動類型： %3</td>
   <td>意外的外部服務啟動類型。</td>
   <td>修正外部服務啟動類型。</td>
</tr>
<tr>
   <td>69</td>
   <td>服務已停止。 服務名稱： %1</td>
   <td>停止外部服務。</td>
   <td>啟動外部服務。</td>
</tr>
<tr>
   <td>70</td>
   <td>原則更新：允許範例集合-%1</td>
   <td>已更新範例集合原則。</td>
   <td>正常運作通知;不需要任何動作。</td>
</tr>
<tr>
   <td>71</td>
   <td>已成功執行命令： %1</td>
   <td>已成功執行命令。</td>
   <td>正常運作通知;不需要任何動作。</td>
</tr>
<tr>
   <td>72</td>
   <td>嘗試傳送第一個完整的電腦設定檔報告。 結果代碼： %1</td>
   <td>僅供參考。</td>
   <td>正常運作通知;不需要任何動作。</td>
</tr>
<tr>
   <td>73</td>
   <td>平臺： %1 的感知開始</td>
   <td>僅供參考。</td>
   <td>正常運作通知;不需要任何動作。</td>
</tr>
<tr>
   <td>74</td>
   <td>登錄中的裝置標記超過長度限制。 標記名稱： %2。 長度限制： %1。</td>
   <td>Device 標記超過長度限制。</td>
   <td>使用較短的裝置標記。</td>
</tr>
<tr>
   <td>81</td>
   <td>無法為端點 ETW 自動記錄器建立 Microsoft Defender。 失敗代碼： %1</td>
   <td>無法建立 ETW 會話。</td>
   <td>重新開機裝置。 如果此錯誤仍然存在，請與支援人員聯繫。</td>
</tr>
<tr>
   <td>82</td>
   <td>無法為端點 ETW 自動記錄器移除 Microsoft Defender。 失敗代碼： %1</td>
   <td>無法刪除 ETW 會話。</td>
   <td>聯繫支援人員。</td>
</tr>
<tr>
   <td>84</td>
   <td>設定 Windows Defender 防毒程式執行模式。 強制被動模式： %1，結果代碼： %2。</td>
   <td>設定 (主動或被動) 的 defender 執行模式。</td>
   <td>正常運作通知;不需要任何動作。</td>
</tr>
<tr>
   <td>85</td>
   <td>無法觸發 Microsoft Defender for Endpoint executable。 失敗代碼： %1</td>
   <td>Starring SenseIR 可執行檔失敗。</td>
   <td>重新開機裝置。 如果此錯誤仍然存在，請與支援人員聯繫。</td>
</tr>
<tr>
   <td>86</td>
   <td>重新開始已停止應啟動的外部服務。 名稱： %1，退出程式碼： %2</td>
   <td>重新開機外部服務。</td>
   <td>正常運作通知;不需要任何動作。</td>
</tr>
<tr>
   <td>87</td>
   <td>無法啟動外部服務。 名稱： %1</td>
   <td>無法啟動外部服務。</td>
   <td>聯繫支援人員。</td>
</tr>
<tr>
   <td>88</td>
   <td>重新更新外部服務的啟動類型。 名稱： %1，實際啟動類型： %2，預期啟動類型： %3，退出程式碼： %4</td>
   <td>已更新外部服務的啟動類型。</td>
   <td>正常運作通知;不需要任何動作。</td>
</tr>
<tr>
   <td>89</td>
   <td>無法更新外部服務的啟動類型。 名稱： %1，實際啟動類型： %2，預期啟動類型： %3</td>
   <td>無法更新外部服務的啟動類型。</td>
   <td>聯繫支援人員。</td>
</tr>
<tr>
   <td>90</td>
   <td>無法設定 System Guard Runtime Monitor 以連接地理區域 %1 中的雲端服務。 失敗代碼： %2</td>
   <td>System Guard Runtime Monitor 不會將證明資料傳送至雲端服務。</td>
   <td>檢查註冊路徑的許可權： "HKLM\Software\Microsoft\Windows\CurrentVersion\Sgrm"。 若未發現任何問題，請與支援人員聯繫。</td>
</tr>
<tr>
   <td>91</td>
   <td>無法移除 System Guard Runtime Monitor 地理區域資訊。 失敗代碼： %1</td>
   <td>System Guard Runtime Monitor 不會將證明資料傳送至雲端服務。</td>
   <td>檢查註冊路徑的許可權： "HKLM\Software\Microsoft\Windows\CurrentVersion\Sgrm"。 若未發現任何問題，請與支援人員聯繫。</td>
</tr>
<tr>
   <td>92</td>
   <td>因為超過資料配額，所以停止傳送感應器網路資料配額。 會在配額週期過後繼續傳送。 狀態遮罩： %1</td>
   <td>超過節流限制。</td>
   <td>正常運作通知;不需要任何動作。</td>
</tr>
<tr>
   <td>93</td>
   <td>繼續傳送感應器網路資料。 狀態遮罩： %1</td>
   <td>繼續網路資料提交。</td>
   <td>正常運作通知;不需要任何動作。</td>
</tr>
<tr>
   <td>94</td>
   <td>Microsoft Defender for Endpoint executable 已開始</td>
   <td>SenseCE 可執行檔已開始。</td>
   <td>正常運作通知;不需要任何動作。</td>
</tr>
<tr>
   <td>95</td>
   <td>Microsoft Defender for Endpoint 可執行檔已結束</td>
   <td>SenseCE 可執行檔已結束。</td>
   <td>正常運作通知;不需要任何動作。</td>
</tr>
<tr>
   <td>96</td>
   <td>Microsoft Defender for Endpoint Init 已呼叫。 結果代碼： %2</td>
   <td>SenseCE 可執行檔叫用 MCE 初始化。</td>
   <td>正常運作通知;不需要任何動作。</td>
</tr>
<tr>
   <td>97</td>
   <td>DLP 案例中的雲端存在連線性問題</td>
   <td>存在會影響 DLP 分類流程的網路連線問題。</td>
   <td>請檢查網路連線性。</td>
</tr>
<tr>
   <td>98</td>
   <td>已還原 DLP 案例的雲端連接</td>
   <td>已還原網路的連線，且 DLP 分類流程可以繼續。</td>
   <td>正常運作通知;不需要任何動作。</td>
</tr>
<tr>
   <td>99</td>
   <td>在與伺服器通訊時，感知發生下列錯誤： (% 1) 。 結果： (% 2) </td>
   <td>發生通訊錯誤。</td>
   <td>如需詳細資訊，請參閱事件記錄檔中的下列事件。</td>
</tr>
<tr>
   <td>100</td>
   <td>無法啟動 Microsoft Defender for Endpoint to executable。 失敗代碼： %1</td>
   <td>SenseCE 可執行檔無法啟動。</td>
   <td>重新開機裝置。 如果此錯誤仍然存在，請與支援人員聯繫。</td>
</tr>
<tr>
   <td>102</td>
   <td>Microsoft Defender for Endpoint 網路偵測和回應可執行檔已開始</td>
   <td>SenseNdr 可執行檔已開始。</td>
   <td>正常運作通知;不需要任何動作。</td>
</tr>
<tr>
   <td>103</td>
   <td>Microsoft Defender for Endpoint 網路偵測和回應可執行檔已結束</td>
   <td>SenseNdr 可執行檔已結束。</td>
   <td>正常運作通知;不需要任何動作。</td>
</tr>
</tbody>
</table>

>想要體驗適用於端點的 Microsoft Defender 嗎？ [注册免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-eventerrorcodes-belowfoldlink)

## <a name="related-topics"></a>相關主題
- [將 Windows 10 裝置上線](configure-endpoints.md)
- [設定裝置 proxy 和網際網路連線設定](configure-proxy-internet.md)
- [為適用於端點的 Microsoft Defender 疑難排解](troubleshoot-onboarding.md)
