---
title: 從其他保護服務切換至 EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
ms.assetid: 81b75194-3b04-48da-8b81-951afbabedde
ms.custom:
- seo-marvel-apr2020
description: 在本文中，您將瞭解如何從內部部署電子郵件清潔裝置或雲端式保護服務切換至 Exchange Online Protection (EOP) 。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: dfbbc44ebfed6cafb97e36b18a4fc34c91840d9b
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/24/2021
ms.locfileid: "52624010"
---
# <a name="switch-to-eop-from-google-postini-the-barracuda-spam-and-virus-firewall-or-cisco-ironport"></a>從 Google Postini、Barracuda Spam and Virus Firewall 或 Cisco IronPort 切換到 EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用於**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

 本主題的目的在於協助您了解從內部部署電子郵件檢疫裝置或雲端保護服務切換到 Exchange Online Protection (EOP) 的程序，然後提供給您開始使用的說明資源。有許多垃圾郵件篩選解決方案，但在大多數情況下，切換到 EOP 的程序類型很類似。

如果您是初次使用 EOP 而且想要在決定切換前閱讀其功能概觀，請從[Exchange Online Protection 概觀](exchange-online-protection-overview.md)主題開始。

在您切換到 EOP 之前，請思考要在雲端 (使用 Exchange Online)、內部部署或在混合案例中託管 EOP 保護的信箱 (「混合」的意思是，有些信箱裝載於內部部署，有些信箱裝載於 Exchange Online)。每個託管案例：雲端、內部部署和混合式部署都可行，但設定步驟有所不同。下列考量可協助您選擇適當的部署：

- **內部部署信箱的 EOP 保護**：如果有想要使用的現有郵件託管基礎結構，或有將信箱保留在內部部署的業務需求，而且想要使用 EOP 做為您雲端電子郵件的保護，則適合使用此案例。 [切換至 Exchange Online](#switch-to-eop-standalone) 詳細說明此案例。

- **Exchange Online 信箱的 EOP 保護**：如果您想要 EOP 保護而所有信箱都裝載在雲端，則適合使用此案例。 這可協助您降低複雜度，因為您不需維護內部部署的郵件伺服器。 [切換至 Exchange Online](#switch-to-exchange-online) 說明此案例。

- **混合信箱的 EOP 保護**：也許您想要雲端信箱，但您必須將某些使用者的信箱保留在內部部署。 如果您希望有些信箱裝載於內部部署，而有些信箱裝載於 Exchange Online，則選擇此案例。 [切換至混合解決方案](#switch-to-a-hybrid-solution)說明此案例。

## <a name="switch-to-eop-standalone"></a>切換至獨立式 EOP

如果您目前將信箱託管於內部部署，而且使用內部部署保護裝置或雲端郵件保護服務，即可切換至 EOP，充分利用其保護功能和可用性。若要在獨立環境中設定 EOP (這表示您將信箱託管於內部部署並使用 EOP 提供郵件保護)，可以遵循[設定 EOP 服務](/exchange/standalone-eop/set-up-your-eop-service)中簡述的步驟。本主題檢視設定 EOP 保護的步驟，包含註冊、新增網域以及設定郵件流程與連接器。

## <a name="switch-to-exchange-online"></a>切換至 Exchange Online

您的內部部署信箱可能具有內部部署的裝置，而且您想要 Exchange Online 雲端裝載的信箱和 EOP protection，以利用 Microsoft 365 雲端郵件和保護功能。 若要開始，您可以註冊 Microsoft 365 並新增您的網域。 此案例不需要您設定連接器，因為沒有任何路由傳送至內部部署信箱。 請從[Microsoft 365 取得最新的高級功能](https://www.microsoft.com/microsoft-365/business/compare-more-office-365-for-business-plans)，以進行註冊，並熟悉其功能。

在 Microsoft 365 安裝程式過程中，您將建立雲端架構信箱使用者。

## <a name="switch-to-a-hybrid-solution"></a>切換至混合解決方案

您可能因為業務需求或法規考量，只想要將部分信箱移至雲端。當您部署混合案例時，可根據業務需求將信箱移至雲端。遷移至具有 EOP 保護的混合案例，比移至全雲端案例更加複雜，但 Microsoft 提供了完整的混合支援和豐富的資源，讓您能更加輕鬆地移至混合案例。

如果考慮採用混合式部署，[Exchange Server 混合式部署](/exchange/exchange-hybrid)是最佳起點。 此外，還有幾個不同且重要的方式，可讓您在混合案例中路由郵件。 [在 Exchange 混合式部署傳輸路由](/exchange/transport-routing)說明每種類型，以便您根據業務需求來選擇最佳路由案例。

## <a name="migration-planning"></a>移轉規劃

當您決定切換至 EOP 時，請務必提供下列方面的特殊考量：

- **自訂篩選規則**：如果您有自訂篩選或商務原則規則來找出特定的垃圾郵件，我們建議您在遷移規則之前，先嘗試使用預設設定 EOP 一段時間。 EOP 提供具有預設設定的企業級垃圾郵件保護，結果可能是您不需要將部分規則遷移至 EOP。 當然，如果現有的規則會強制執行特定自訂業務原則，即可建立這些原則。 如需詳細資訊，請參閱[Mail flow rules (transport rules) in Exchange Online](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)。

- **IP 允許清單和 IP 封鎖清單**：如果您有每一使用者的允許清單和封鎖清單，請在設定過程中留出一些時間將這些清單複製到 EOP。 如需 IP 允許清單和 IP 封鎖清單的詳細資訊，請參閱 [Configure the connection filter policy](configure-the-connection-filter-policy.md)。

- **安全通訊**：如果合作夥伴要求郵件必須加密，建議您在 Exchange 系統管理中心設定此案例。 如要設定此案例，請查閱[設定連接器以保護與合作夥伴間的郵件流程安全](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-for-secure-mail-flow-with-a-partner)。

> [!TIP]
> 當您從內部部署裝置切換至 EOP 時，有可能將裝置或伺服器保留在原地，以執行業務規則檢查。 例如，若裝置對輸出郵件執行自訂篩選，而且希望繼續這麼做，您可以設定 EOP，在郵件路由傳送至網際網路之前，直接傳送至此裝置進行額外篩選。
