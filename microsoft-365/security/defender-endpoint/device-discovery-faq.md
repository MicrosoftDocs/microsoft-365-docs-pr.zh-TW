---
title: 裝置探索常見問題
description: " (FAQs) 有關裝置探索的常見問題解答，請找出相關的常見問題解答。"
keywords: 裝置探索，探索，被動式，主動，網路，可視性，伺服器，工作站，板載，未受管理的裝置
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 1c61e69b5c8d414ab229fa8bf64eb657a6e40304
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245957"
---
# <a name="device-discovery-frequently-asked-questions"></a>裝置探索常見問題

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]

 (FAQs) 有關裝置探索的詳細資訊，請找出常見問題的答案。

## <a name="what-is-basic-discovery-mode"></a>何謂基本探索模式？
這種模式可讓每個 Microsoft Defender for Endpoint 架裝置收集網路資料，並探索鄰居裝置。 架端點會以被動方式收集網路中的事件，並從中抽取裝置資訊。 不會發起任何網路流量。 架端點只會從架裝置所看到的每個網路流量提取資料。 這項資料可用於列出您網路中未受管理的裝置。

## <a name="can-i-disable-basic-discovery"></a>可否停用基本探索？
您可以選擇透過 [ [高級功能](advanced-features.md) ] 頁面關閉裝置探索。 不過，您的網路中未受管理的裝置會失去可視性。 

## <a name="what-is-standard-discovery-mode"></a>何謂 Standard discovery mode？
 在此模式中，架至 Microsoft Defender for Endpoint 的端點可以積極探查網路中的觀察裝置，以豐富網路流量) 所收集的資料 (。 強烈建議使用此模式來建立可靠且連貫的設備清查。 如果您選擇停用此模式，並選取 [基本探索] 模式，您的網路中可能只會獲得有限的非受管理端點的可見度。

## <a name="can-i-control-which-devices-perform-standard-discovery"></a>我可以控制哪些裝置會執行標準探索？
 您可以自訂用來執行標準探索的裝置清單。 您可以在所有也支援此功能的架裝置上啟用 Standard discovery， (目前 Windows 10 裝置只) 或透過指定裝置的裝置標籤選取裝置的子集或子集。 在此情況下，所有其他裝置將設定為只執行基本探索。 設定可在 [裝置探索設定] 頁面中取得。

## <a name="can-i-exclude-unmanaged-devices-from-the-device-inventory-list"></a>我是否可以從裝置庫存清單中排除未受管理的裝置？
是的，您可以從裝置庫存清單套用篩選器以排除未受管理的裝置。 您也可以在 API 查詢上使用 [上架狀態] 欄，以篩選出未受管理的裝置。 


## <a name="which-onboarded-devices-can-perform-discovery"></a>哪些架裝置可以執行探索？
 在 Windows 10 版本1809或更新版本上執行的架裝置可以執行探索。

## <a name="what-happens-if-my-onboarded-devices-is-connected-to-my-home-network-or-to-public-access-point"></a>如果我的架裝置連線到我的家用網路或公用存取點會發生什麼情況？
 探索引擎會區別公司網路中所接收的網路事件與公司網路以外的網路事件。 透過將網路識別碼關聯到所有租使用者的用戶端，事件會在從私人網路和公司網路接收的事件之間加以區別。 例如，如果網路中的大部分裝置報告其連線至相同的網路名稱，且其預設閘道和 DHCP 伺服器位址相同，則會假設此網路可能是公司網路。 私人網路裝置不會列在庫存中，也不會主動加以探測。

## <a name="what-protocols-are-you-capturing-and-analyzing"></a>您在捕獲和分析哪些通訊協定？
 根據預設，在 Windows 10 版本1809或更新版本上執行的所有架裝置都是在捕獲和分析下列通訊協定： ARP、CDP、DHCP、DHCPv6、IP (標頭) 、LLDP、LLMNR、mDNS、MNDP、NBNS、SSDP、TCP (標頭) 、UDP (標頭) 、WSD

## <a name="which-protocols-do-you-use-for-active-probing-in-standard-discovery"></a>您在 Standard discovery 中用於使用中探測的通訊協定為何？
 當裝置設定為執行標準探索時，會使用下列通訊協定來探測公開的服務： ARP、FTP、HTTP、ICMP、LLMNR、NBNS、RDP、SIP、SMTP、SNMP、SSH、Telnet、UPNP、WSD、SMB、NBSS、IPP、PJL

## <a name="how-can-i-exclude-targets-from-being-probed-with-standard-discovery"></a>如何排除目標，使其不會透過標準探索來探測？
 如果您的網路上有不應該主動探測的裝置，您也可以定義排除清單以避免掃描這些裝置。 設定可在 [裝置探索設定] 頁面中取得。

## <a name="can-i-exclude-devices-from-being-discovered"></a>是否可以排除探索的裝置？
 隨著裝置探索使用被動式方法探索網路中的裝置，您可以在庫存中探索與架裝置通訊的任何裝置，並在庫存中列出。 您可以只從作用中的探查排除裝置。

## <a name="how-frequent-is-the-active-probing"></a>使用中探查的頻率如何？
 當顯示裝置特性的變更時，將會主動探測裝置 (每1到3周) 以確定現有的資訊是最新的。

## <a name="my-security-tool-raised-alert-on-unicastscannerps1-or-port-scanning-activity-initiated-by-it-what-should-i-do"></a>我的安全性工具在其所啟動的 UnicastScanner.ps1 或埠掃描活動上發出警示，我該怎麼做？
 使用中的探查腳本是由 Microsoft 簽署且安全的。 您可以將下列路徑新增至您的排除清單： `C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Downloads\*.ps`


## <a name="what-is-the-amount-of-traffic-being-generated-by-the-standard-discovery-active-probe"></a>標準探索使用中探查產生的流量量為何？
 作用中的探查可產生高達架裝置與已探測裝置之間的流量，每次探測嘗試

## <a name="why-is-there-a-discrepancy-between-can-be-onboarded-devices-in-the-device-inventory-and-the-number-of-devices-to-onboard-in-the-dashboard-tile"></a>為何裝置庫存中的「可以架」裝置有差異，以及儀表板磚中的「裝置到板載」的數目為何？
您可能注意到裝置清查中的「可以架」的列出裝置數目、「Microsoft Defender for Endpoint」和「裝置上架」儀表板小工具之間的差異。

 安全性建議及儀表板小工具適用于網路上穩定的裝置。不包括短暫裝置、來賓裝置及其他。 建議在持續性裝置上，這也是指組織的整體安全性分數。

## <a name="can-i-onboard-unmanaged-devices-that-were-found"></a>是否可以板載找到的受管理裝置？
 可以。 網路中未受管理的端點會向您的網路引進弱點和風險。 將其上架至服務可提高安全性。 


