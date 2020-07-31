---
title: 您可以 sail 的安全性障礙（一個架構師的視點）
description: 描述。
ms.author: bcarter
author: brendacarter
manager: bcarter
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-identity-device-management
- M365-security-compliance
ms.custom: ''
f1.keywords: NOCSH
ms.openlocfilehash: cdb6b557bf2f46a2338d929547167cf89a048695
ms.sourcegitcommit: 0f71042edc7c3a7f10a7b92e1943abf51532cbf5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/29/2020
ms.locfileid: "46522273"
---
# <a name="security-hurdles-you-can-sail-over--one-architects-viewpoint"></a>您可以 sail 的安全性障礙（一個架構師的視點）

在本文中，Microsoft 的[Kozeta Garrett](https://www.linkedin.com/in/kozeta-garrett-53013a6/)，Cybersecurity 架構中，會說明她在企業組織中遇到的最大安全性挑戰，並建議 sailing 超過這些障礙的方法。 

## <a name="about-the-author"></a>關於作者

![Kozeta Garrett 相片](../media/solutions-architecture-center/kozeta-garrett-security.jpg) 

在「我的角色」中，我已與多個組織合作，針對遷移至 Microsoft 365 和 Azure 的客戶，設計及實施安全架構提供相關的戰略性和技術指導方針、開發企業安全性解決方案，以及協助轉換安全性架構和文化，以取得商務恢復能力。 我的經驗包括事件偵測和回應、惡意程式碼分析、滲透測試，並建議 IT 安全性與防禦狀態的增強。 我非常 passionate 有關主要轉換的方式，導致安全性成為公司的啟用者，包括現代化工作。

雖然最近的 COVID-19 的情況，但瞭解如何在過去幾年中採用安全性現代化思維的組織，都是最有説明的做法，都是在很大的位置，讓他們能夠繼續以安全的方式遠端運作。 不幸的是，這些情況也為部分客戶提供喚醒呼叫，但尚未準備好進行這項立即的需求。 許多組織意識到他們必須快速現代化、淘汰其累計的 IT 安全性債務，並改善安全性狀態整夜，讓他們可以在這些極不尋常的情況下運作。

好消息是 Microsoft 已策劃一些極佳的資源，可協助組織快速提升其安全性狀況。 除了這些資源之外，我也想要分享我每日在客戶上遇到的最大難題，因為您可以 sail 這些障礙。

我目前居住于北弗吉尼亞州，請接近我們公司的資本（華盛頓）。 我只喜歡每一種形式的戶外活動和運動，如執行、biking、hiking 及 swimming。 若要對付這些，我只會喜歡許多烹飪、gourmet 食物和旅行。 


## <a name="partner-with-the-security-team-from-the-start-of-cloud-adoption"></a>從雲端採用開始，與安全性小組合作

開始時，我無法強調組織中的團隊在開始時的重要性。 在雲端採用和設計的早期階段，安全性小組必須是重要的合作夥伴。 這表示讓安全小組能夠在專家採用雲端採用，而不僅僅是針對企業新增的功能（例如安全行動裝置上的卓越使用者經驗、完整功能應用程式，或是在有限的功能電子郵件和生產力應用程式上建立公司資料的價值），但也可利用儲存、AI 及計算分析功能，協助解決新的和舊的安全性挑戰。 安全小組必須納入管理此班的所有層面，包括人員（文化）、程式（訓練）及技術成功。 這也表示投資進行安全作業中心（SOC）的現代化和連續改進。 請共同合作以將您的安全性原則與業務策略及環境趨勢對應，以確保數位轉換已安全地進行。 當這項工作順利完成時，組織會開發出更快進行變更的功能，包括對業務、IT 及安全性的變更。 

當我看到客戶超過障礙時，最大的情形是作業和 SOC 團隊之間沒有真正的合作關係。 當運作小組遭到 pressured，並要求嚴格的期限來採用雲端時，安全性小組不一定會儘早包含在程式中，以修訂及規劃完整的安全性策略。 這包括整合不同的雲端元件，以及部署中的元件。 這缺乏合作關係進一步 trickles 至不同的小組，其似乎可在思洛群組中運作，以針對其特定元件執行控制項，進而增加實施、疑難排解和整合的複雜性。

Sail 超過這些障礙的客戶都有良好的作業與控管與安全性與風險管理小組之間的合作關係，以 revamp 保護混合雲端工作負載的安全性策略和需求。 他們會專注于終極的安全性目標與成果-資料保護和系統和服務可用性符合 cybersecurity 的控管、風險和合規性需求。 這些組織會在他們的運作與控管小組和 SOC 之間開發早期階段的合作關係，這對於安全性設計方法來說很重要，其投資的價值會最大化。 

## <a name="build-a-modern-identity-based-security-perimeter"></a>建立現代（以身分識別為基礎）安全性周邊環境

接下來，採用零信任架構方法。 這始于建立現代化的身分識別安全性周邊性。 設計一種安全性架構，不論是在部署或雲端上的每次存取嘗試，都是在驗證之前（「永不相信，永遠驗證」）視為不受信任。 這種設計方法不僅能提高安全性和生產力，也可讓使用者從任何裝置類型的任何地方運作。 Microsoft 365 隨附的完善的雲端控制項，可協助您保護使用者的身分識別，同時根據使用者風險層級控制寶貴資源的存取。

如需建議的設定，請參閱[Identity and device access](../enterprise/microsoft-365-policies-configurations.md)configuration。 

## <a name="transition-security-controls-to-the-cloud"></a>將安全性控制轉換為雲端

許多安全性小組仍然使用為所有內部部署世界所建立的傳統安全性最佳作法，包括維護「網路周邊安全性」，並嘗試將部署安全性工具和控制項「強制」為雲端解決方案。 這類控制項不是專為雲端設計，不是低效，也不會妨礙採用新式雲端功能。 可用於網路周邊安全性方法的程式及工具，已證實其效率低下，obstructive 到雲端功能，且不允許利用新式和自動化的安全性功能。

您可以將防護策略移至雲端管理的保護、自動化調查和修正、自動化的鋼筆測試、高級威脅防護，以及事件分析，以 sail 此障礙。 使用新式裝置管理解決方案的客戶已實現所有裝置（不論是 smartphone、個人電腦、膝上型電腦或平板電腦）的自動管理、標準化修補、防病毒、原則強制執行和應用程式保護。 這樣就不需要有 VPN、Microsoft System Center Configuration Manager （SCCM）和 Active Directory 群組原則。 這會結合條件式存取原則，提供強大的控制項和可視性，並可簡化存取資源，不論使用者的運作位置為何。

## <a name="strive-for-best-together-security-tools"></a>盡力搭配「最佳」安全性工具

另一個障礙--我看到客戶 stumble 超過安全性工具的最佳做法。 不斷分層「最佳」點解決方案，以解決新興的安全性需求，造成企業安全性中斷。 即使有最佳的目的，大部分環境中的工具也不會整合，因為它會變得太昂貴而且複雜。 這反過來會在可見度中產生空隙，因為會審的警示超過了小組可以處理的程度。 重新培訓 SecOps 小組的新工具也會變成經常性的挑戰。

「簡單越好」的做法也會運作安全性。 除了採用「最佳」工具之外，您可以將「最佳搭配」策略與預設使用的工具結合使用，以 sail 至此功能。 Microsoft 安全性功能會使用跨應用程式、使用者和雲端的整合威脅防護來保護整個組織。 整合可讓組織在進入和快速補救攻擊的情況中包含攻擊者，以提高彈性能力並降低風險。

## <a name="balance-security-with-functionality"></a>以功能平衡安全性

在我的 cybersecurity 背景和經驗上，我傾向于從現成的最安全設定開始，讓組織根據其運作與安全性需求來放寬安全性設定。 不過，這可能會造成遺失功能和不良使用者體驗的 hefty 價。 隨著許多組織已學到，如果使用者的安全性過於困難，他們就會發現一種解決您問題的方法，包括使用未受管理的雲端服務。 就像我接受的一樣，我已意識到微妙的功能必須達到安全性平衡。

假設使用者完成工作所需的工作，請確認「陰影 IT 工作」沒有任何必要的要求。 他們認識到 IT 員工在將其隱藏，並使用未核准的 SaaS 應用程式進行工作時，是最大的違犯方式。 他們已移動其策略以鼓勵其使用（而不是抑制），並且著重于減輕其可能造成的風險危險性。 這些組織的安全性小組不會堅持透過反向 proxy 或 VPN 來封鎖、記錄及傳送所有專案。 相反地，這些安全小組會加倍努力，以保護重要及敏感性資料，使其不會向錯誤的一方或惡意應用程式公開。 其運作方式是為了保護資料的完整性。 他們完全使用更高級的雲端資訊保護功能，包括加密、安全的多重要素驗證、自動化的風險和合規性，以及雲端應用程式安全性代理（CASB）功能，同時允許甚至鼓勵跨多個平臺的受保護共用。 他們會將其陰影變成 inspiring 的創造力、生產力及共同作業，讓其業務保持在競爭優勢。


## <a name="adopt-a-methodical-approach"></a>採用一種方法 

在不同組織（不論行業）上實施 cloud security 的大部分難題，都非常類似。 首先，雖然有許多有關特定功能及功能的極佳檔，但在組織層級上會有一些對這些專案套用的程度混淆，安全性功能會重迭，以及整合功能的方式。 您也有不確定，哪些安全性功能已預先設定為現成的功能，且需要組織進行設定。 此外，SOC 小組也沒有必要的整體公開、訓練或預算配置，以準備快速的雲端採用，並為其組織所進行的數位轉換進行準備。

為了協助您清除這些障礙，Microsoft 已策劃數個資源，以協助您採取一種安全性原則與實施方式。 


|資源   |詳細資訊  |
|---------|---------|
|[安全性團隊支援在家工作的最常見工作](../security/top-security-tasks-for-remote-work.md)      | 如果您覺得您突然支援大多數工作中的工作力，這篇文章可協助您快速提升安全性。 它包含根據您的授權方案的最大建議工作。    |
|[Microsoft 365 商務決策人的安全性](../security/Microsoft-365-security-for-bdm.md)    | 當您有時間進行更全面的計畫時，本文會包含跨越 Microsoft 365 的建議，並依攻擊面劃分優先順序。 它甚至附帶您可以用來排序授權和區域的試算表（例如身分識別、威脅防護和監視）。  |
|[Microsoft 安全架構建議](https://docs.microsoft.com/security/compass/compass)    | 如果您是安全性架構架構，請務必查看依學科組織的安全性建議，包括身分識別、網路及安全性作業。   |
|[Microsoft 安全性作業建議](https://docs.microsoft.com/security/compass/security-operations-videos-and-decks)|瞭解設定及執行安全性作業中心（SOC）的 Microsoft 建議 |
|[首席資訊安全性監察官（CISO）研討會訓練](https://docs.microsoft.com/security/ciso-workshop/ciso-workshop)   | 如果您是新的雲端安全性，請不要錯過這系列的影片。        |
|[docs.security.com/security](https://docs.microsoft.com/security/)    | 來自 Microsoft 的技術指導，以取得安全性策略和架構。        |
| | |

所有這些資源都是設計用來作為起點，並根據您的組織的需求而改編。 

