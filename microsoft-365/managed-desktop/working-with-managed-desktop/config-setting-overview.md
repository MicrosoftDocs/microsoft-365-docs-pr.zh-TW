---
title: 可設定的 Microsoft 受管理的電腦設定
description: 具有 Microsoft 受管理的電腦的可設定設定資訊
keywords: Microsoft 受管理的電腦、Microsoft 365、服務、檔、設定、可設定的設定
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: bf8672ee6c3332ea6f8522f5086d72e58d1b9048
ms.sourcegitcommit: bdf65d48b20f0f428162c39ee997accfa84f4e5d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/20/2020
ms.locfileid: "49371487"
---
# <a name="configurable-settings---microsoft-managed-desktop"></a>可組態的設定 - Microsoft 受管理的電腦

Microsoft 受管理的電腦會部署套用至 Microsoft 受管理的電腦所管理之所有裝置的設定和原則。 如需詳細資訊，請參閱 [Device configuration](../service-description/device-policies.md)。

Microsoft 受管理的電腦中的可設定設定可讓系統管理員自訂及部署組織和業務需求獨有的設定。 這些設定除了 Microsoft 受管理的電腦所管理的裝置設定和原則之外。  

可設定的設定變更是在雲端中進行，並且套用至定義的部署群組中的 Microsoft 受管理的電腦裝置。 此程式類似于 Microsoft 受管理的電腦如何管理裝置設定設定和服務所定義及管理之原則的變更。 使用 Microsoft 受管理的電腦用來部署變更的相同程式，您可以繼續使用現代的 IT 管理做法，向前移動組織。

## <a name="when-to-use-configurable-settings"></a>何時使用可設定的設定？

有幾次使用可設定的設定。 

上 **架** 程式– Microsoft 受管理的電腦建議您在板載 to Microsoft 受管理的電腦服務時，或在您將大量裝置板載 (20 或以上) 時，自訂設定的設定。 設定類別是在 Microsoft 受管理的電腦管理入口網站中設定。 在架並可以存取系統管理員入口網站後，您可以決定要為組織自訂的設定類別、進行變更、暫存部署，然後部署變更。

**維護設定** -定期複查您的設定，並進行必要的更新。 您可能需要變更，以支援您的企業中的變更。   

## <a name="setting-categories"></a>設定類別

以下是您可以自訂的可設定的設定類別：
- [桌面背景圖片](config-setting-ref.md#desktop-background-picture)-自訂 Microsoft 受管理的電腦裝置的桌面背景圖片。 
- [瀏覽器開始頁面](config-setting-ref.md#browser-start-pages)–新增開始頁面以用於 Microsoft Edge。 請參閱瀏覽器開始頁面
- [Enterprise 模式網站清單](config-setting-ref.md#enterprise-mode-site-list-location)–新增網站和其相容性模式。 清單中的網站會在 Internet Explorer 中開始。 
- [受信任的網站](config-setting-ref.md#trusted-sites) –新增受信任的網站，並為每個網站設定安全區域。 
- [Proxy 網站例外](config-setting-ref.md#proxy) 狀況–設定 proxy 伺服器的位址號碼和埠號碼，並新增 proxy 網站例外。

每個設定類別都可以自訂並自行部署。 您可以同時在多個設定類別中部署變更，不過，您一次只能將一個變更部署至一個設定類別。

例如：
- 您可以同時在桌面背景圖片和信任的網站上部署變更，並將這些變更同時部署為自己的部署。 
- 您無法同時將兩個部署部署至瀏覽器開始頁面。 最近的部署會停止仍在進行中的早期部署。

## <a name="configurable-setting-process"></a>可設定的設定程式

當您使用組織的可設定設定時，Microsoft 受管理的電腦建議遵循類似下列的程式：

**步驟 1-Plan** -瞭解可設定的設定，並決定您要為組織設定的設定類別。 建立時程表，以供您預期每個群組的變更的部署。 規劃與您的內部變更管理流程的使用者通訊。 例如，如果您要新增瀏覽器開始頁面，請讓您的使用者知道他們會在部署後，在其瀏覽器中有一組新的起始頁面。  

**步驟 2-設定和階段部署**-在 Microsoft 受管理的電腦管理入口網站中變更可設定的設定。 暫存變更，以供部署。 請記得讓您的使用者瞭解變更，以及變更如何變更其裝置體驗。   

您可以在 Microsoft 受管理的電腦管理員入口網站中設定及暫存變更。 如需詳細資訊，請參閱 [自訂可設定的設定](config-setting-ref.md)。 

**步驟 3-交流變更** 傳達對您的使用者即將進行之變更的相關資訊。 針對每個部署，完成屬於變更管理程式的通訊。 您應該清楚地通告會影響使用者運作方式的任何變更，或是他們在裝置上看到的功能。

**步驟 4-部署變更** –部署您的變更（從 Test group 開始）。 測試群組可讓您驗證及疑難排解具有較少裝置的群組中的任何問題，再將變更部署至較大的裝置群組。 如果您遇到任何問題，您可以還原變更、更新設定，以及暫存新的部署。 Microsoft 受管理的電腦建議您遵循結構化方法，並依此順序部署至群組： Test、First、Fast 及寬泛。   

所有可設定的設定均使用 Microsoft 受管理的電腦系統管理入口網站來管理。 如需詳細資訊，請參閱 [部署變更](config-setting-deploy.md)。 

**步驟 5-追蹤變更** –追蹤部署狀態變更的進度。 您可以針對每個設定進行下列作業：
- **追蹤進度** –在您部署變更之後，追蹤狀態。 狀態會變更為 [ **正在進行中**]，然後 **完成**] 或 [ **失敗**]。 如果部署失敗，則會自動開啟支援要求，以調查問題的 Microsoft 受管理的電腦運作。  
- **請參閱部署的版本** –每個部署的變更都有一個版本號碼。
- **還原變更** –還原變更會停止目前的部署，並將所有群組還原為所有已部署至所有群組的變更。 您正在回復至最後一個已知良好的設定值。
- **驗證變更** -部署完成後，請依照預期的方式驗證所做的變更。  

如果部署失敗，或是您無法還原變更，請使用 Microsoft 受管理的電腦作業[開啟支援要求](admin-support.md)。 

如需詳細資訊，請參閱 [部署和追蹤可設定的設定](config-setting-deploy.md)。

## <a name="additional-resources"></a>其他資源
- [可設定的設定參考](config-setting-ref.md) 
- [部署可設定的設定](config-setting-deploy.md) 
