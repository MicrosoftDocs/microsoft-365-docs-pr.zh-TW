---
title: 輸出和輸入郵件流程
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: 8/7/2018
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: f2738dec-41b0-43c4-b814-84c0a4e45c6d
description: 系統管理員可以在安全性與合規性中心中的郵件流程儀表板了解輸出和輸入郵件流程小工具。
ms.openlocfilehash: 5c86db8e33ff3ee1dc4d9d126239465b3c84bde5
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42088428"
---
# <a name="outbound-and-inbound-mail-flow"></a>輸出和輸入郵件流程

**輸出和輸入郵件流程**小工具會將**連接器報告**和先前的 **TLS 概觀報告**集中在一個位置。

![安全性與合規性中心內郵件流程儀表板的輸出和輸入郵件流程報告](../../media/2c591d1c-bad6-4b72-890e-f8fdfd4f447a.png)

小工具中的資訊會與 Office 365 中的連接器和 TLS 郵件保護相關。 如需相關資訊，請參閱這些主題：

- [使用 Office 365 中的連接器設定郵件流程](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)

- [Exchange Online 如何使用 TLS 來保護 Office 365 中的電子郵件連線](https://docs.microsoft.com/microsoft-365/compliance/exchange-online-uses-tls-to-secure-email-connections)

## <a name="message-protected-in-transit-by-tls"></a>傳輸中郵件保護 (使用 TLS)

當您在 Office 365 組織中接收及傳送郵件時，**輸出和輸入郵件流程**小工具會顯示用於連線的 TLS 加密。 與其他電子郵件服務建立的連線，若兩端都提供 TLS，則會由 TLS 進行加密。 小工具會提供上一週的郵件流程快照。 當您按一下 [檢視詳細資料]**** 時，**傳輸中郵件保護 (使用 TLS)** 彈出頁面會針對進入和離開您組織的郵件顯示 TLS 保護。

![安全性與合規性中心內的傳輸中郵件保護 (使用 TLS) 彈出畫面](../../media/825aa74c-413d-4141-8e3c-dfe68ae78eed.png)

目前，TLS 1.2 是 Office 365 提供的最安全 TLS 版本。 通常，您必須知道用於合規性稽核的 TLS 加密為何。 您可能與來源和目的地電子郵件伺服器都沒有直接關係 (您沒有，Microsoft 也沒有)，因此您沒有許多選項可改善那些伺服器使用的 TLS 加密。

不過，您可以使用 [連接器](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)，以確保在您電子郵件伺服器與 Office 365 之間傳送的郵件是使用最適合的 TLS 保護。 在 Office 365 和您自有電子郵件伺服器或屬於您合作夥伴的伺服器之間，電子郵件流程通常比一般郵件還要重要且敏感，因此您必須針對這些郵件套用額外的安全性和警覺性。 您可以升級或修正您自己的電子郵件伺服器，以改善正在使用的 TLS 加密，或連絡合作夥伴來執行此相同動作。 **連接器報告**會針對使用您 Office 365 連接器的郵件顯示郵件流程量和 TLS 加密。

## <a name="connector-report"></a>連接器報告

當您在 [傳輸中郵件保護 (使用 TLS)]**** 彈出畫面中按一下 [連接器報告]**** 時，報告會顯示使用連接器在 Office 365 組織接受和傳送的郵件相關資訊。 您可以在自己的電子郵件伺服器與 Office 365 之間，或您夥伴的伺服器與 Office 365 之間使用連接器。 這會提供每個連接器的郵件量，以及用於連線的 TLS 加密。 此外，您也可以在不使用連接器的情況下，檢視在 Office 365 中傳送或接收的郵件資料。

[郵件流程]**** 檢視會顯示過去一周內透過連接器進行的郵件量。 若要變更日期範圍，請選取 [篩選]****，您可以在此將範圍增加到最多 30 天。 [所有郵件流程]**** 檢視會顯示透過所有連接器在您 Office 365 組織中傳送及接收的所有郵件流程。 您可以按照名稱在下拉式功能表中選取特定的連接器。

您可以從下拉式清單中選取 [TLS 使用狀況]**** 檢視，以查看透過連接器進行的 TLS 郵件保護細項。 就像 **TLS 概觀報告**一樣，此檢視會顯示不同 TLS 版本的百分比。 在 TLS 1.0 連線中，您必須先將電子郵件伺服器或合作夥伴的伺服器升級或修正，以避免 Office 365 終將不支援 TLS 1.0 的問題。 如需詳細資訊，請參閱[關於 Office 365 中加密的技術參考細節](https://docs.microsoft.com/microsoft-365/compliance/technical-reference-details-about-encryption)。

深入解析會指向連接器，協助您注意到連接器的潛在 TLS 加密問題。 這些深入解析為：**沒有 TLS 超過 25%**，或 **TLS 1.0 高於 50%**。 如果您看到這些深入見解，您需要調查與連接器相關聯的電子郵件伺服器，或與合作夥伴組織聯繫。

## <a name="see-also"></a>另請參閱

如需郵件流量儀表板中其他郵件流程深入解析之詳細資訊，請參閱[安全性與合規性中心中郵件流程深入解析](mail-flow-insights-v2.md)。
