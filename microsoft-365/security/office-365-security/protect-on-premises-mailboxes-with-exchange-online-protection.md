---
title: 使用 Exchange Online Protection 保護內部部署的信箱
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 6/1/2017
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- GEU150
- GMA150
- GPA150
- MET150
ms.assetid: c5e95951-da67-4ec7-92c5-982abd477e69
ms.collection:
- M365-security-compliance
description: 即使您打算將部分或所有信箱裝載在內部部署，您仍然可以使用 Exchange Online Protection (EOP) 保護信箱。 若要設定連接器，您的帳戶必須是 Office 365 全域系統管理員或 Exchange 公司管理員 (組織管理角色群組)。 如需 Office 365 權限與 Exchange 權限之關係的相關資訊，請參閱由 21Vianet 營運的 Office 365 中指派系統管理員角色。 如果您的 Exchange 信箱均為內部部署，請遵循以下步驟以設定 EOP 服務。
ms.openlocfilehash: 5d7c306451529b15c0bccb56ed6b2cf103b01435
ms.sourcegitcommit: 5710ce729c55d95b8b452d99ffb7ea92b5cb254a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/11/2019
ms.locfileid: "39971561"
---
# <a name="protect-on-premises-mailboxes-with-exchange-online-protection"></a>使用 Exchange Online Protection 保護內部部署的信箱

> [!NOTE]
> 本文僅適用於中國 21Vianet 所營運的 Office 365。

即使您打算將部分或所有信箱裝載在內部部署，您仍然可以使用 Exchange Online Protection (EOP) 保護信箱。 若要設定連接器，您的帳戶必須是 Office 365 全域系統管理員或 Exchange 公司管理員 (組織管理角色群組)。 如需 Office 365 權限與 Exchange 權限之關係的相關資訊，請參閱[由 21Vianet 營運的 Office 365 中指派系統管理員角色](https://docs.microsoft.com/office365/admin/add-users/assign-admin-roles?&view=o365-21vianet)。 如果您的 Exchange 信箱均為內部部署，請遵循以下步驟以設定 EOP 服務。

## <a name="step-1-use-the-microsoft-365-admin-center-to-add-and-verify-your-domain"></a>步驟 1：使用 Microsoft 365 系統管理中心新增及確認您的網域

1. 在 Microsoft 365 系統管理中心中，瀏覽至 [設定] 將您的網域新增至服務。

2. 請遵循入口網站的步驟，將適用的 DNS 記錄新增到 DNS 主機提供者，以便驗證網域擁有權。

> [!TIP]
> 當您新增網域至此服務並設定 DNS 時，[新增網域和使用者至 21Vianet 營運的 Office 365](https://docs.microsoft.com/office365/admin/setup/add-domain?&view=o365-21vianet) (部分機器翻譯) 和 [管理您的 DNS 記錄時建立 Office 365 的 DNS 記錄](https://docs.microsoft.com/office365/admin/services-in-china/create-dns-records-when-you-manage-your-dns-records?&view=o365-21vianet) (部分機器翻譯)，是有用的參考資源。

### <a name="step-2-add-recipients-and-configure-the-domain-type"></a>步驟 2：新增收件者和設定網域類型

在設定您的郵件來進出 EOP 服務之前，建議您將收件者新增至服務。 有許多種作法，請參閱＜[管理 EOP 中的郵件使用者](manage-mail-users-in-eop.md)＞。 另外，如果您要啟用目錄架構邊緣封鎖 (DBEB)，以便在服務內新增收件者之後強制驗證收件者，則必須將網域類型設為「授權」。 如需 DBEB 的相關資訊，請參閱[使用目錄架構邊緣封鎖以拒絕傳送至無效收件者的郵件](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking) (部分機器翻譯)。

## <a name="step-3-use-the-eac-to-set-up-mail-flow"></a>步驟 3：使用 EAC 來設定郵件流程

在 Exchange 系統管理中心 (EAC) 內建立連接器，來啟用 EOP 與您內部部署郵件伺服器之間的郵件流程。 如需詳細指示，請參閱 [使用 Office 365 中的連接器設定郵件流程](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) (部分機器翻譯)。

 如何才能了解此工作是否正常運作？

 請參閱[驗證 Office 365 連接器以測試郵件流程](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow) (部分機器翻譯)。

## <a name="step-4-allow-inbound-port-25-smtp-access"></a>步驟 4：允許輸入連接埠 25 SMTP 存取

設定連接器之後，請等待 72 小時以允許傳播 DNS 記錄更新。 接著限制防火牆或郵件伺服器上的輸入連接埠 25 SMTP 流量，以僅接受來自 EOP 資料中心的郵件 (尤其是來自[ Office 365 URL 和 IP 位址範圍所列 IP 位址的郵件)。](https://docs.microsoft.com/office365/enterprise/managing-office-365-endpoints)(部分機器翻譯)。 這會限制您可接收的輸入郵件範圍，以保護內部部署環境的安全。 此外，若您在郵件伺服器上進行設定，以控制允許連線執行郵件轉送的 IP 位址，請一併更新這些設定。

> [!TIP]
> 將 SMTP 伺服器的連線時間設定設為超過 60 秒。此設定適用於大部分情況，例如在傳送具有大型附件的郵件時可稍許延遲。

## <a name="step-5-use-the-shell-to-ensure-that-spam-is-routed-to-each-users-junk-email-folder"></a>步驟 5：使用命令介面確保垃圾郵件路由傳送至每個使用者的垃圾電子郵件資料夾

為了確保垃圾電子郵件正確地路由傳送至每個使用者的 [垃圾郵件] 資料夾，您必須執行幾個設定步驟。 相關步驟請參閱＜[確保垃圾郵件路由傳送至每個使用者的垃圾電子郵件資料夾](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)＞ (英文)。 如果不要將郵件移至每個使用者的 [垃圾郵件] 資料夾，您可以在 Exchange 系統管理中心編輯內容篩選原則，以選擇其他動作。 如需詳細資訊，請參閱[設定您的垃圾郵件篩選原則](configure-your-spam-filter-policies.md)。

## <a name="step-6-use-the-microsoft-365-admin-center-to-point-your-mx-record-to-eop"></a>步驟 6：使用 Microsoft 365 系統管理中心將您的 MX 記錄指向 EOP

請遵循 Office 365 網域設定步驟來更新網域的 MX 記錄，以讓輸入電子郵件經過 EOP。 如需詳細資訊，您可以再次參考[管理 DNS 記錄時為 Office 365 建立 DNS 記錄](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) (部分機器翻譯)。

如何才能了解此工作是否正常運作？

 請參閱[驗證 Office 365 連接器以測試郵件流程](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow) (部分機器翻譯)。

到目前為止，您已確定有正確設定的輸出內部部署連接器可用來進行服務傳遞，並已確認 MX 記錄是指向 EOP。現在您可以選擇執行下列其他測試，以確認服務能夠成功將電子郵件傳遞至您的內部部署環境：

- 在 Remote Connectivity Analyzer 中，按一下 **[Office 365]** 索引標籤，然後執行位於 **[網際網路電子郵件測試]** 底下的 **[輸入 SMTP 電子郵件]** 測試。

- 從任何其網域符合您新增至此服務之網域的 Web 式電子郵件帳戶，傳送電子郵件給您組織中的郵件收件者。使用 Microsoft Outlook 或其他電子郵件用戶端，確認郵件已傳遞至內部部署信箱。

- 如果您想要執行輸出電子郵件測試，可以從組織中的使用者傳送電子郵件到 Web 式電子郵件帳戶，再確認郵件是否已收到。

## <a name="less-common-a-hybrid-setup-with-mailboxes-on-premises-and-in-the-cloud"></a>較不常見：具有內部部署和雲端信箱的混合式設定

如果您擁有 Exchange 信箱內部部署和 Exchange Online 中一個或多個雲端信箱，則您具有*混合式*設定。 在混合式設定中，例如空閒/忙碌行事曆共用和郵件路由等功能可在您的內部部署和雲端環境中共同作業。 將信箱移轉到 Exchange Online 時，可能會啟用混合式設定。 混合式環境的設定不同於 EOP 獨立防護。

您可以選擇混合式案例，以利用雲端式電子郵件給大部分員工使用。 您可以在執行這項作業的同時，將部分信箱裝載在內部部署；例如，針對法務部門。

混合式設定可能會很複雜，但也有許多優點。 若要深入了解如何使用 Exchange 設定混合式案例，請參閱 [Exchange Server 混合式部署](https://docs.microsoft.com/Exchange/exchange-hybrid) (部分機器翻譯)。
