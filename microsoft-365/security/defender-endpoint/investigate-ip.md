---
title: 調查與警示相關聯的 IP 位址
description: 使用調查選項檢查裝置與外部 IP 位址之間可能的通訊。
keywords: 調查、調查、IP 位址、警示、microsoft defender atp、外部 IP
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
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.date: 04/24/2018
ms.technology: mde
ms.openlocfilehash: 003abd854e34bb5a9a05f675313ba6c4f6ce1d71
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186038"
---
# <a name="investigate-an-ip-address-associated-with-a-microsoft-defender-for-endpoint-alert"></a>調查與 Microsoft Defender for Endpoint 警示相關聯的 IP 位址

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


>想要體驗 Defender for Endpoint？ [註冊免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

檢查裝置與外部網際網路通訊協定之間可能的通訊 (IP) 位址。

識別組織中與可疑或已知惡意的 IP 位址（例如 Command 和 Control (C2) 伺服器）通訊的所有裝置，協助判斷遭到破壞的潛在範圍、關聯的檔案和受感染的裝置。

您可以從 [IP 位址] 視圖中的下列區段找到資訊：

- 全球 IP
- 反向 DNS 名稱
- 與此 IP 相關的警示
- 組織中的 IP
- 流行

## <a name="ip-worldwide-and-reverse-dns-names"></a>IP 全球和反向 DNS 名稱

「IP 位址詳細資料」區段會顯示 IP 位址（如其 ASN 和其反向 DNS 名稱）的屬性。

## <a name="alerts-related-to-this-ip"></a>與此 IP 相關的警示

與 **此 ip 區段相關的警示** ，提供與 ip 相關聯的警示清單。

## <a name="ip-in-organization"></a>組織中的 IP

[ **組織中的 ip** ] 區段提供組織中 ip 位址的流行詳細資料。

## <a name="prevalence"></a>流行

「 **傳播** 」區段會顯示已連接至此 ip 位址的裝置數量，以及第一次及最後一次看到此 ip 位址的時間。 您可以依時段篩選此區段的結果;預設週期為30天。

## <a name="most-recent-observed-devices-with-ip"></a>最近觀測的裝置（含 IP）

[使用 IP 的 **最近觀測的裝置** ] 區段提供按時間排序的事件，以及在 IP 位址上觀測到的相關警示。

**調查外部 IP：**

1. 從 **搜尋** 列下拉式功能表中選取 [ **IP** ]。
2. 在 [ **搜尋** ] 欄位中輸入 IP 位址。
3. 按一下搜尋圖示或按 **enter** 鍵。

會顯示 IP 位址的詳細資訊，包括：註冊詳細資料 (如果可用) 、反向 IPs (例如，組織中的網域) 、與此 IP 位址通訊的組織內的設備 (，以及組織中透過此 IP 位址進行通訊所觀察到的裝置。

> [!NOTE]
> 只會傳回與組織中裝置通訊所看到之 IP 位址的搜尋結果。

使用搜尋篩選以定義搜尋準則。 您也可以使用 [時程表] 搜尋方塊，篩選組織中所看到之所有裝置的顯示結果，這些裝置會透過 IP 位址、與通訊相關聯的檔案及最後一個日期所看到的方式進行通訊。

按一下任一裝置名稱將會帶您前往該裝置的視圖，您可以在其中繼續調查報告的警示、行為和事件。

## <a name="related-topics"></a>相關主題

- [查看和組織 Microsoft Defender for Endpoint 警示佇列](alerts-queue.md)
- [管理 Microsoft Defender for Endpoint 警示](manage-alerts.md)
- [調查 Microsoft Defender for Endpoint 警示](investigate-alerts.md)
- [調查與 Microsoft Defender for Endpoint alert 相關聯的檔案](investigate-files.md)
- [調查 Microsoft Defender for Endpoint Devices 清單中的裝置](investigate-machines.md)
- [調查與 Microsoft Defender for Endpoint alert 相關聯的網域](investigate-domain.md)
- [調查 Microsoft Defender for Endpoint 中的使用者帳戶](investigate-user.md)
