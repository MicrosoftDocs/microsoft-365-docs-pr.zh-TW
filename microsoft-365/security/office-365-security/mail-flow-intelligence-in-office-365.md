---
title: 郵件流程智慧
f1.keywords:
- NOCSH
ms.author: siosulli
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: troubleshooting
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c29f75e5-c16e-409e-a123-430691e38276
description: 系統管理員可以深入瞭解與使用 (連接器（也稱為「郵件流程情報」) ）相關聯之郵件傳遞的錯誤碼。
ms.openlocfilehash: 5339bf2117a87cd940c4b96b3d00b7b8ba78a1da
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/11/2020
ms.locfileid: "49658854"
---
# <a name="mail-flow-intelligence-in-eop"></a>EOP 中的郵件流程情報

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


在使用 Exchange Online 或獨立 Exchange online Protection 中信箱的 Microsoft 365 組織中 (EOP) 組織沒有 Exchange Online 信箱，您通常會使用連接器將電子郵件訊息從 EOP 路由傳送至您的內部部署電子郵件環境。 您也可以使用連接器將來自 Microsoft 365 的郵件路由傳送至夥伴組織。 當 Microsoft 365 無法透過連接器傳遞這些郵件時，他們就會在 Microsoft 365 中佇列。 Microsoft 365 會繼續重試每封郵件24小時的傳遞。 24小時後，佇列中的郵件會到期，而且郵件會傳回未傳遞回報的原始寄件者 (也稱為 NDR 或退回郵件) 。

當無法使用連接器傳遞郵件時，Microsoft 365 會產生錯誤。 本文說明最常見的錯誤及其解決方案。 透過連接器傳送的未傳遞郵件的排隊和通知錯誤，稱為「 _郵件流程智慧_」。

## <a name="error-code-450-44312-dns-query-failed"></a>錯誤碼： 450 4.4.312 DNS 查詢失敗

一般來說，此錯誤表示 Microsoft 365 嘗試連線至連接器中指定的智慧主機，但 DNS 查詢可尋找智慧主機的 IP 位址失敗。 這種錯誤的可能原因如下：

- 您網域的 DNS 主機服務會有問題， (維護網域) 之授權名稱伺服器的一方。

- 您的網域最近到期，所以無法檢索 MX 記錄。

- 您的網域的 MX 記錄最近已變更，而且 DNS 伺服器仍會為您的網域預先快取 DNS 資訊。

### <a name="how-do-i-fix-error-code-450-44312"></a>如何修正錯誤碼 450 4.4.312？

- 請與您的 DNS 主機服務合作，以找出並修正您網域的問題。

- 如果錯誤來自您的夥伴組織 (例如，協力廠商雲端服務提供者) ，請與您的合作夥伴聯繫以修正此問題。

## <a name="error-code-450-44315-connection-timed-out"></a>錯誤碼： 450 4.4.315 Connection 超時

一般來說，這表示 Microsoft 365 無法連線至目的地電子郵件伺服器。 錯誤詳細資料會說明問題。 例如：

- 您的內部部署電子郵件伺服器已停機。

- 連接器的智慧主機設定中有錯誤，因此 Microsoft 365 會嘗試連接至錯誤的 IP 位址。

### <a name="how-do-i-fix-error-code-450-44315"></a>如何修正錯誤碼 450 4.4.315？

- 找出哪個案例適用于您，並進行必要的更正。 例如，如果郵件流程運作正常，但尚未變更連接器設定，則需要檢查您的內部部署電子郵件環境，以查看伺服器是否已關機，或網路基礎結構是否有任何變更 (例如，您已變更 internet 服務提供者，所以您現在有不同的 IP 位址) 。

- 如果錯誤來自您的夥伴組織 (例如，協力廠商雲端服務提供者) ，請與您的合作夥伴聯繫以修正此問題。

## <a name="error-code-450-44316-connection-refused"></a>錯誤碼： 450 4.4.316 連接被拒絕

一般來說，此錯誤表示 Microsoft 365 嘗試連線至目的地電子郵件伺服器時，發生連線錯誤。 這種錯誤的可能原因是，您的防火牆封鎖的是 Microsoft 365 IP 位址的連線。 或者，如果您已完全將內部部署電子郵件系統移轉至 Microsoft 365 並關閉您的內部部署電子郵件環境，則設計可能會發生此錯誤。

### <a name="how-do-i-fix-error-code-450-44316"></a>如何修正錯誤碼 450 4.4.316？

- 如果您的內部部署環境中有信箱，您必須修改防火牆設定，以允許 TCP 埠25上來自 Microsoft 365 IP 位址的連線到您的內部部署電子郵件伺服器。 如需 Microsoft 365 IP 位址的清單，請參閱 [microsoft 365 URLs 和 IP 位址範圍](https://docs.microsoft.com/microsoft-365/enterprise/urls-and-ip-address-ranges)。

- 若您的內部部署環境中未傳遞任何郵件，請按一下警示中的 [ **立即修正** ]，讓 Microsoft 365 可以立即拒絕具有無效收件者的郵件。 這會降低超出組織的配額以取得無效收件者的風險，這可能會影響一般郵件傳遞。 或者，您可以使用下列指示以手動修正問題：

  - 在 [Exchange 系統管理中心中 (EAC) ](https://docs.microsoft.com/Exchange/exchange-admin-center)中，停用或刪除將電子郵件從 Microsoft 365 傳送至您的內部部署電子郵件環境的連接器：

    1. 在 EAC 中，移至 [ **郵件流程** \> **連接器**]。

    2. 選取 [**寄件者**] 值為 **Office 365** 的連接器，並選取 **您組織的電子郵件伺服器** 的 [**到**] 值，然後執行下列其中一個步驟：

       - 按一下 [**刪除** 移除圖示] 以刪除連接器 ![](../../media/adf01106-cc79-475c-8673-065371c1897b.gif)

       - 按一下 [ **編輯** ![ 編輯圖示] ](../../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) 並清除 [ **關閉**] 以停用連接器。

  - 將與您的內部部署電子郵件環境關聯的 Microsoft 365 中公認的網域從 **內部轉送** 變更為 **權威性**。 如需相關指示，請參閱 [管理 Exchange Online 中公認的網域](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)。

  **附注**：一般會有30分鐘到1小時的變更才會生效。 一小時後，請確認您不再收到錯誤。

- 如果錯誤來自您的夥伴組織 (例如，協力廠商雲端服務提供者) ，您必須聯繫您的合作夥伴以修正此問題。

## <a name="error-code-450-44317-cannot-connect-to-remote-server"></a>錯誤碼： 450 4.4.317 無法連接至遠端伺服器

此錯誤通常是指 Microsoft 365 連接至目的地電子郵件伺服器，但伺服器會以立即錯誤回應，或不符合連線需求。 錯誤詳細資料會說明問題。 例如：

- 目的地電子郵件伺服器會以「服務無法使用」的錯誤回應，這表示伺服器無法與 Microsoft 365 保持通訊。

- 連接器設定為需要 TLS，但目的地電子郵件伺服器不支援 TLS。

### <a name="how-do-i-fix-error-code-450-44317"></a>如何修正錯誤碼 450 4.4.317？

- 確認您的內部部署電子郵件伺服器上的 TLS 設定和憑證，以及連接器上的 TLS 設定。

- 如果錯誤來自您的夥伴組織 (例如，協力廠商雲端服務提供者) ，您必須聯繫您的合作夥伴以修正此問題。

## <a name="error-code-450-44318-connection-was-closed-abruptly"></a>錯誤碼： 450 4.4.318 Connection 突然關閉

一般來說，此錯誤表示 Microsoft 365 在與您的內部部署電子郵件環境通訊時有困難，所以連線已中斷。 這種錯誤的可能原因如下：

- 您的防火牆使用 SMTP 封包檢查規則，而這些規則不會正常運作。

- 您的內部部署電子郵件伺服器無法正常運作 (例如，「服務懸掛」、「系統資源不足」或「低系統資源」) ，這會導致伺服器超時並關閉 Microsoft 365 的連線。

- 您的內部部署環境與 Microsoft 365 之間有網路問題。

### <a name="how-do-i-fix-error-code-450-44318"></a>如何修正錯誤碼 450 4.4.318？

- 找出哪個案例適用于您，並進行必要的更正。

- 如果問題是由您的內部部署環境和 Microsoft 365 之間的網路問題所造成，請與您的網路小組聯繫以進行問題的疑難排解。

- 如果錯誤來自您的夥伴組織 (例如，協力廠商雲端服務提供者) ，您必須聯繫您的合作夥伴以修正此問題。

## <a name="error-code-450-47320-certificate-validation-failed"></a>錯誤碼： 450 4.7.320 憑證驗證失敗

一般來說，此錯誤表示 Microsoft 365 在嘗試驗證目的地電子郵件伺服器的憑證時，發生錯誤。 錯誤詳細資料會說明錯誤。 例如：

- 憑證已到期

- 憑證主體不符

- 憑證已不再有效

### <a name="how-do-i-fix-error-code-450-47320"></a>如何修正錯誤碼 450 4.7.320？

- 修正連接器上的憑證或設定，讓 Microsoft 365 中的排隊郵件可以傳遞。

- 如果錯誤來自您的夥伴組織 (例如，協力廠商雲端服務提供者) ，您必須聯繫您的合作夥伴以修正此問題。

## <a name="other-error-codes"></a>其他錯誤碼

Microsoft 365 在將郵件傳遞至您的內部部署或夥伴電子郵件伺服器時遇到問題。 請使用錯誤中的 **目的伺服器** 資訊檢查您環境中的問題，或在發生設定錯誤時修改連接器。

如果錯誤來自您的夥伴組織 (例如，協力廠商雲端服務提供者) ，您必須聯繫您的合作夥伴以修正此問題。
