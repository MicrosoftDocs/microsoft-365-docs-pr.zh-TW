---
title: Microsoft 365 已告知網路路由
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 1/21/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
description: Microsoft 365 已告知網路路由
ms.openlocfilehash: 40b4345ca80c5e90a07583b83b82368d4a35535a
ms.sourcegitcommit: 039205fdaaa2a233ff7e95cd91bace474b84b68c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/09/2020
ms.locfileid: "49611433"
---
# <a name="microsoft-365-informed-network-routing-preview"></a>Microsoft 365 已 (預覽告知網路路由) 

已通知網路路由是一項功能，可整合各種 Microsoft 365 應用程式與協力廠商軟體定義的網路 (SD-WAN) 解決方案，以優化和提升 Microsoft 服務端點的網路連線能力。 優化的 SD-WAN 連線可能會導致使用者體驗和效能提高。

>[!IMPORTANT]
>Microsoft 365 已告知網路路由目前處於預覽狀態。 如需此預覽的詳細資訊，包括接收協助的指引，請參閱 [Microsoft 365 已通知的網路路由公開預覽](https://go.microsoft.com/fwlink/?linkid=2151565)。

## <a name="overview"></a>概觀

已獲悉網路路由會在 Microsoft 與您的 SD-WAN 解決方案之間提供雙向資料共用通道。 針對您設定的每個辦公室位置和網際網路電路，Microsoft 會定期與 SD-WAN 解決方案共用意見反應，以供每個特定網際網路電路相關聯之網路流量所選取之 Microsoft 365 應用程式的品質。 使用此意見反應，SD-WAN 方案可以透過透過其他可用連結路由傳送 Microsoft 365 應用程式流量來採取智慧復原動作。 

特定網際網路電路（如增加延遲或高封包遺失）路徑中的服務品質到很難定期偵測到。 這些到對 Exchange Online、SharePoint、OneDrive 和 Microsoft 小組等應用程式的使用者體驗可能會造成不利的損害。 常見的情況包括對 Exchange 內容的搜尋速度很慢、在與 SharePoint 或 OneDrive 文件庫互動時，或在 Microsoft 小組中與通話或會議品質不良。

網路中的意見反應和復原機制，已通知路由搜尋會動態偵測這類問題，並通知部署的 SD-WAN 解決方案採取自動復原動作。

資料共用通道也可用於定期接收來自 SD-WAN 解決方案的網路層級光學資料，包括與裝置及連接電路相關聯的設定資訊和使用統計資料。 不會收集或儲存任何個人資訊。 所有收集的資訊都會匯總到辦公室位置和連線的網際網路電路。 這項資訊可協助 Microsoft 使用 Microsoft 365 服務和應用程式，更有效率地解決已報告的問題。

>[!NOTE]
>Microsoft 365 已通知網路路由支援 WW 商業雲端中的承租人，但不支援 GCC 中、GCC 高、DoD、德國或中國雲彩。

## <a name="requirements"></a>需求

### <a name="integrated-sd-wan-solutions"></a>整合的 SD-WAN 解決方案

Microsoft 正與不同的合作夥伴合作，以啟用與 Microsoft 365 的網路路由通知的整合。 目前啟用的解決方案包括下列各項：

| Device Maker | 方案名稱 | 最低版本 |
| --- | --- | --- |
| Cisco | [IOS XE SD-WAN](https://go.microsoft.com/fwlink/?linkid=2151460) | 20.4/17.4 |

### <a name="network-topology"></a>網路拓撲

已告知網路路由根據用來將網路流量傳送給 Microsoft 的公用 IP 位址，來識別與特定 office 位置和網際網路電路相關聯的流量。 

如果在分支地點沒有至少一部網路電路提供直接網際網路存取的情況下，網路傳送可能無法提供重要的價值。

### <a name="application-usage"></a>應用程式使用

應用程式經驗資料 (反映透過網路品質度量) 會透過 Microsoft Outlook 在執行 Windows、小組、SharePoint 及 OneDrive 的裝置上的使用方式收集。 評估網路電路的健康情況時，並不會考慮其他應用程式流量。

## <a name="enabling-informed-network-routing"></a>啟用已通知的網路路由

啟用已通知的網路路由需要多個步驟，有些步驟則必須在 SD-WAN 解決方案的設定介面內執行。 請諮詢您的 SD-WAN 解決方案廠商，以取得如何在使用 Microsoft 365 系統管理中心進行設定之前，啟動在 SD-WAN 解決方案內啟用網路通知之程式的指導方針。

當您準備好在 Microsoft 365 系統管理中心中啟用已通知的網路路由功能之後，請確定您具備必要的全域系統管理員許可權。

>[!IMPORTANT]
>為了提供所選 SD-WAN 解決方案所需的承租人層級應用程式許可權，以存取已通知的網路路由資料共用通道，您必須以全域系統管理員身分執行下列步驟。


### <a name="step-1-open-sd-wan-solution-configuration-options"></a>步驟1：開啟 SD-WAN 方案設定選項

在 [Microsoft 365 系統管理中心](https://admin.microsoft.com/)的左側流覽窗格中，選取 [ **健康 > 網路** 連線]。

本章節為您的組織提供匯總的網路連線度量，以及如何改善連線的指導方針。 請參閱 [Microsoft 365 系統管理中心的網路連線 (預覽) ](office-365-network-mac-perf-overview.md) ，以取得系統管理中心內可用之功能的其他資訊。

選取 [ **設定] > SD-WAN 解決方案** ] 以開啟 [已通知的網路路由設定] 窗格。 [ **設定** ] 底下顯示的其他選項適用于系統管理中心的一般網路連線指導方針，而且不需要啟用已通知的網路路由。

在 [設定] 窗格中，選取 [ **新增您的 SD-WAN 方案 (Preview)**]。

### <a name="step-2-select-your-sd-wan-solution-and-data-storage-location"></a>步驟2：選取您的 SD-WAN 方案和資料儲存位置

在下拉式方塊中，選取您已部署的 SD-WAN 方案，以及您想要將其相關聯的資料儲存在網路上的位置。 如需詳細資訊，請參閱 [資料存放區](#data-storage) 一節。

選取 [下一步]。

### <a name="step-3-accept-terms-for-sharing-of-data"></a>步驟3：接受共用資料的字詞

請仔細閱讀並認可與在 Microsoft 和您所選的 SD-WAN 方案中共用資料相關聯的提供字詞，然後選取指出的核取方塊。

選取 [下一步]。

### <a name="step-4-grant-permissions-to-the-sd-wan-solution"></a>步驟4：將許可權授與 SD-WAN 方案

這個步驟將會啟動使用 Azure Active Directory (Azure AD) 的許可權授與要求。 您將會被要求授與承租人層級的許可權，允許您選取的 SD-WAN 方案存取已通知的網路路由資料存放區，以及與租使用者相關聯的服務健康情況資訊。 此動作需要全域系統管理員角色許可權。

選取 [ **授與此應用程式的許可權** ] 連結，並遵循 Azure AD 要求。

當您完成許可權授與後，請選取 **[下一步]**。

### <a name="step-5-confirm-your-configuration-settings"></a>步驟5：確認您的設定設定

為您的租使用者啟用網路通知之路由的最後一個步驟是確認頁面，顯示您所提供的設定。 

現在已為您的租使用者啟用已通知的網路路由。

選取 [ **完成** ]，然後關閉 [SD-WAN 方案設定] 窗格。

## <a name="configuring-network-informed-routing"></a>設定網路通知的路由

您將在 SD-WAN 解決方案內，針對已通知的網路路由執行許多設定，例如設定如何在正常情況下路由傳送流量，以及在偵測到問題時，應使用的替代路徑。 如需這些設定步驟的詳細資訊，請參閱您的 SD-WAN 解決方案提供者。

每個辦公室位置都必須在 Microsoft 365 系統管理中心中設定，以告知網路路由可正確識別與網路線路相關聯的流量，以提供與這些位置的連線能力。

在 Microsoft 正在進行的網路遙測集合中，可能會自動偵測到 Office 位置。 因此，有些位置可能會預先填入租使用者的系統管理員中心。 

如果這些位置是正確的，您只需要為每個必要的位置啟用已通知的網路路由功能，並設定網際網路電路及其公用 IP 位址。 

如果自動偵測位置不正確，或您的租使用者中沒有預先填入的位置，您必須手動新增或編輯位置，以反映組織的準確拓撲。

### <a name="updating-locations"></a>更新位置

您租使用者的位置可在 [ **位置** ] 索引標籤下找到。位置可以直接在清單中編輯，或使用 CSV 檔案更新。

確定您想要啟用通知網路路由的每個辦公室位置都存在於此清單中。

>[!NOTE]
>收集樣本及其他評估相關資訊的 [ **位置** ] 清單中的欄與已通知的網路路由功能並不相關。

### <a name="enabling-a-location-for-informed-network-routing"></a>啟用通知網路路由的位置

1. 在 [ **位置** ] 清單中，從 [快速動作] 功能表中選取 [ **編輯** ]，以開啟 [位置設定] 窗格。

2. 選取 [ **使用 Microsoft 365 告知網路路由的位置**]。

3. 在 **此辦公室位置的 [出局 IP 位址範圍** ] 區段中，新增所有可提供網際網路連線到此 office 位置的網路電路。 確定每個電路都與代表網路流量的唯一公用 IP 位址子網相關聯。

4. 選取 **[儲存]** 以儲存變更。

## <a name="disabling-network-informed-routing"></a>停用網路通知路由

您可以透過重設 SD-WAN 方案設定，對整個租使用者停用已通知的網路路由功能。 雖然這會停止所有在 Microsoft 365 中處理的資料，您也應停用系統管理中心內網路通知的路由傳送。

### <a name="step-1-open-sd-wan-solution-configuration-options"></a>步驟1：開啟 SD-WAN 方案設定選項

在 [Microsoft 365 系統管理中心](https://admin.microsoft.com/) 中，選取左導覽窗格中的 [ **健康情況 > 網路連線能力** 。

選取 [ **設定] > SD-WAN 解決方案** ] 以開啟 [已通知的網路路由設定] 窗格。

設定窗格會顯示您目前設定的 SD-WAN 解決方案摘要。

### <a name="step-2-reset-your-configuration"></a>步驟2：重設您的設定

在 [設定] 窗格中，選取 [ **重設您的 SD-WAN 方案設定**]。

您的設定現在已重設，且已停用網路路由通知。 您可以隨時依照 [啟用已告知網路路由](#enabling-informed-network-routing)的步驟，隨時重新啟用該功能。

## <a name="data-storage"></a>資料儲存

在 Microsoft 與 SD-WAN 解決方案提供者之間交換的資料會儲存在初次啟用網路通知的位置時選取的資料儲存位置。 資料儲存位置選項代表地理區域，其中包含儲存資料的 Microsoft Azure 地區。

>[!NOTE]
>在預覽階段， **北美** 唯一可用的資料儲存位置。 在有通知的網路路由的一般可用性之前，將會提供額外的資料儲存位置。

資料會保留在此位置，最多30天。 停用時，會在此30天保留時段內移除所有剩餘的資料。

## <a name="related-topics"></a>相關主題

[Microsoft 365 系統管理中心的網路連線 (預覽) ](office-365-network-mac-perf-overview.md)

[Microsoft 365 Network Connectivity Location 服務 (預覽) ](office-365-network-mac-location-services.md)
