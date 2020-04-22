---
title: 設定 EOP 服務
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: d74c6ddf-11b0-43ee-b298-8bb0340895f0
description: 本主題說明如何設定 Microsoft Exchange Online Protection (EOP)。 如果您從 Office 365 網域精靈進入這裡，而您不希望使用 Exchange Online Protection 的話，請回到 Office 365 網域精靈。 如果您正在尋找如何設定連接器的詳細資訊，請參閱＜使用 Office 365 中的連接器設定郵件流程＞。
ms.openlocfilehash: 9a2c876ac7696adfcabf87d4ad13e29374509f1b
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2020
ms.locfileid: "43638305"
---
# <a name="set-up-your-eop-service"></a>設定 EOP 服務

本主題說明如何設定 Microsoft Exchange Online Protection (EOP)。如果您從 Office 365 網域精靈進入這裡，而您不希望使用 Exchange Online Protection 的話，請回到 Office 365 網域精靈。如果您正在尋找如何設定連接器的詳細資訊，請參閱[Configure mail flow using connectors in Office 365](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)。

> [!NOTE]
> 本主題假設您擁有內部部署信箱，且您想要使用 EOP 來保護這些信箱 (稱為「獨立」案例)。 如果您想要使用 Exchange Online 在雲端中裝載所有的信箱，並不需要完成本主題中所有的步驟。 移至[比較 Exchange Online 方案](https://products.office.com/exchange/compare-microsoft-exchange-online-plans)以註冊及購買雲端信箱。 如果您想要將一部分信箱裝載在內部部署、一部分信箱裝載在雲端中，這稱為「混合」案例。 這需要更進階的郵件流程設定。 [Exchange Server Hybrid Deployments](https://docs.microsoft.com/exchange/exchange-hybrid) 會說明混合郵件流程，並提供一些說明相關設定方式的連結。

## <a name="what-do-you-need-to-know-before-you-begin"></a>開始之前有哪些須知？

- 完成此工作的預估時間：1 小時

- 若要設定連接器，您的帳戶必須是全域管理員或 Exchange 公司管理員（組織管理角色群組）。 如需詳細資訊，請參閱 [EOP 中的功能權限](feature-permissions-in-eop.md)。

- 如果您尚未註冊 EOP，請造訪 [Exchange Online Protection](https://products.office.com/exchange/exchange-email-security-spam-protection)，並選擇購買或試用服務。

- 如需適用於本主題中程序的快速鍵相關資訊，請參閱 [Exchange Online 中 Exchange 系統管理中心的鍵盤快速鍵](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)。

> [!TIP]
> 有問題嗎？ 在 [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) 論壇中尋求協助。

## <a name="step-1-use-the-microsoft-365-admin-center-to-add-and-verify-your-domain"></a>步驟 1：使用 Microsoft 365 系統管理中心 新增及確認您的網域

1. 在 [Microsoft 365 管理中心](https://docs.microsoft.com/office365/admin/admin-overview/about-the-admin-center)中，移至 **[設定]** 將您的網域新增至服務。

2. 請遵循這些步驟，將適用的 DNS 記錄新增到 DNS 主機提供者，以便驗證網域擁有權。

> [!TIP]
> 當您新增網域至此服務並設定 DNS 時，[新增網域至 Office 365](https://docs.microsoft.com/office365/admin/setup/add-domain) 和 [在任一 DNS 主機服務提供者建立 Office 365 的 DNS 記錄](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider)是有用的參考資源。

## <a name="step-2-add-recipients-and-optionally-enable-dbeb"></a>步驟 2：新增收件者並選擇性地啟用 DBEB

在設定您的郵件來進出 EOP 服務之前，建議您將收件者新增至服務。有許多種作法，請參閱＜[管理 EOP 中的郵件使用者](manage-mail-users-in-eop.md)＞。另外，如果您要啟用目錄架構邊緣封鎖 (DBEB)，以便在服務內新增收件者之後強制驗證收件者，則必須將網域類型設為「授權」。如需 DBEB 的相關資訊，請參閱[Use Directory Based Edge Blocking to Reject Messages Sent to Invalid Recipients](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking)。

## <a name="step-3-use-the-eac-to-set-up-mail-flow"></a>步驟 3：使用 EAC 來設定郵件流程

在 Exchange 系統管理中心（EAC）中建立連接器，以啟用 EOP 與內部部署郵件伺服器之間的郵件流程。如需詳細指示，請參閱[設定連接器以在 Microsft 365 和您自己的電子郵件伺服器之間路由傳送郵件](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail)。

### <a name="how-do-you-know-this-task-worked"></a>如何才能了解此工作是否正常運作？

檢查服務和環境之間的郵件流程。 如需詳細資訊，請參閱透過[您的 Microsoft 365 連接器驗證測試郵件流程](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow)。

## <a name="step-4-allow-inbound-port-25-smtp-access"></a>步驟 4：允許輸入連接埠 25 SMTP 存取

設定連接器之後，請等待 72 小時以允許傳播 DNS 記錄更新。接著限制防火牆或郵件伺服器上的通訊埠 25 SMTP 流量，以僅接受來自 EOP 資料中心的郵件 (尤其是來自 [Exchange Online Protection IP 位址](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges) 所列 IP 位址的郵件)。這會限制您可接收的輸入郵件範圍，以保護內部部署環境的安全。此外，若您在郵件伺服器上進行設定，以控制允許連線執行郵件轉送的 IP 位址，請一併更新這些設定。

> [!TIP]
> 將 SMTP 伺服器的連線時間設定設為超過 60 秒。 此設定適用於大部分情況，例如，在傳送具有大型附件的郵件時可稍許延遲。

## <a name="step-5-ensure-that-spam-is-routed-to-each-users-junk-email-folder"></a>步驟5：確定垃圾郵件路由傳送至每個使用者的 [垃圾郵件] 資料夾

為了確保垃圾電子郵件正確地路由傳送至每個使用者的 [垃圾郵件] 資料夾，您必須執行幾個設定步驟。 [設定獨立 EOP 中的步驟，將垃圾郵件傳遞至混合式環境中的 [垃圾郵件] 資料夾](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)。

如果不要將郵件移至每個使用者的 [垃圾郵件] 資料夾，您可以在 Exchange 系統管理中心編輯內容篩選原則，以選擇其他動作。 如需詳細資訊，請參閱[在 Office 365 中設定反垃圾郵件原則](configure-your-spam-filter-policies.md)。

## <a name="step-6-use-the-microsoft-365-admin-center-to-point-your-mx-record-to-eop"></a>步驟 6：使用 Microsoft 365 系統管理中心 將您的 MX 記錄指向 EOP

遵循網域設定步驟，更新您網域的 MX 記錄，讓輸入電子郵件流過 EOP。請務必將 MX 記錄直接指向 EOP，而不是讓協力廠商篩選服務轉送電子郵件給 EOP。如需詳細資訊，您可以再次參考[Office 365 的建立 DNS 記錄](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider)。

### <a name="how-do-you-know-this-task-worked"></a>如何才能了解此工作是否正常運作？

到目前為止，您已確定有正確設定的輸出內部部署連接器可用來進行服務傳遞，並已確認 MX 記錄是指向 EOP。現在您可以選擇執行下列其他測試，以確認服務能夠成功將電子郵件傳遞至您的內部部署環境：

- 檢查服務和環境之間的郵件流程。 如需詳細資訊，請參閱透過[您的 Microsoft 365 連接器驗證測試郵件流程](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow)。

- 從任何其網域符合您新增至此服務之網域的 Web 式電子郵件帳戶，傳送電子郵件給您組織中的郵件收件者。使用 Microsoft Outlook 或其他電子郵件用戶端，確認郵件已傳遞至內部部署信箱。

- 如果您想要執行輸出電子郵件測試，可以從組織中的使用者傳送電子郵件到 Web 式電子郵件帳戶，再確認郵件是否已收到。

> [!TIP]
> 當您完成設定時，不需要執行額外步驟即可讓 EOP 移除垃圾郵件和惡意軟體。 EOP 會自動移除垃圾郵件和惡意軟體。 不過，您可以根據本身的商務需求來微調 EAC 中的設定。 如需相關資訊，請參閱＜[Office 365 中的反垃圾郵件和反惡意程式碼保護](anti-spam-and-anti-malware-protection.md)＞。 <br/><br/> 現在您的服務在執行中，建議您閱讀[設定 EOP 的最佳作法](best-practices-for-configuring-eop.md)，其中會說明設定好 EOP 後的建議設定和注意事項。
