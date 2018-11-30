---
title: 部署 Microsoft 365 企業版
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 11/01/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: 了解可用來在組織中部署 Microsoft 365 企業版的資源。
ms.openlocfilehash: ba0dd4d8af9f647b5368fdaa55837d3fe482fb55
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/28/2018
ms.locfileid: "26866657"
---
# <a name="deploy-microsoft-365-enterprise"></a><span data-ttu-id="4fbdb-103">部署 Microsoft 365 企業版</span><span class="sxs-lookup"><span data-stu-id="4fbdb-103">Deploy Microsoft 365 Enterprise</span></span>

<span data-ttu-id="4fbdb-104">Microsoft 365 企業版是 Office 365、Enterprise Mobility + Security (EMS) 和 Windows 10 企業版的組合，其中：</span><span class="sxs-lookup"><span data-stu-id="4fbdb-104">Microsoft 365 Enterprise is a combination of Office 365, Enterprise Mobility + Security (EMS), and Windows 10 Enterprise that:</span></span> 

- <span data-ttu-id="4fbdb-105">提供智慧安全性。</span><span class="sxs-lookup"><span data-stu-id="4fbdb-105">Has intelligent security.</span></span>
- <span data-ttu-id="4fbdb-106">已整合，讓您容易使用。</span><span class="sxs-lookup"><span data-stu-id="4fbdb-106">Is integrated for simplicity.</span></span>
- <span data-ttu-id="4fbdb-107">盡情發揮創意。</span><span class="sxs-lookup"><span data-stu-id="4fbdb-107">Unlocks creativity.</span></span>
- <span data-ttu-id="4fbdb-108">為團隊合作而建置。</span><span class="sxs-lookup"><span data-stu-id="4fbdb-108">Is built for teamwork.</span></span>

<span data-ttu-id="4fbdb-p101">這些優點不只是透過取得這三個產品的授權，也透過以特定的方式部署這些產品以及其功能而實現。這份文件組會逐步引導您執行這些產品和其功能的部署與正確和所需的設定。</span><span class="sxs-lookup"><span data-stu-id="4fbdb-p101">These benefits are not realized just by obtaining the licenses for these three products, but by deploying them and their features in a specific way. This documentation set guides you through that deployment and the correct and required configuration of these products and their features.</span></span>

<span data-ttu-id="4fbdb-111">部署 Microsoft 365 企業版有兩個主要階段：</span><span class="sxs-lookup"><span data-stu-id="4fbdb-111">There are two main phases to deploying Microsoft 365 Enterprise:</span></span>

1. <span data-ttu-id="4fbdb-112">首先，為內建安全性與整合部署所需的[基礎結構](deploy-foundation-infrastructure.md)來簡化管理，此可讓您更輕鬆確保用戶端軟體已更新，具備最新的生產力和安全性增強功能。</span><span class="sxs-lookup"><span data-stu-id="4fbdb-112">First, deploy the required [foundation infrastructure](deploy-foundation-infrastructure.md) for built-in security and integration for simplified management, which makes it easier to ensure your client software is updated with the latest productivity and security enhancements.</span></span>
2. <span data-ttu-id="4fbdb-113">接下來，除了基礎結構，部署一組選用[工作負載和案例](deploy-workloads.md)，以在組織中盡情發揮創意並實現團隊合作。</span><span class="sxs-lookup"><span data-stu-id="4fbdb-113">Next, deploy a set of optional [workloads and scenarios](deploy-workloads.md) on top of the foundation infrastructure, to unlock creativity and teamwork in your organization.</span></span>

<span data-ttu-id="4fbdb-114">下圖顯示基礎結構與工作負載和案例之間的關係和實現內容的路徑。</span><span class="sxs-lookup"><span data-stu-id="4fbdb-114">The following figure shows the relationship between the foundation infrastructure and the workloads and scenarios and your path through the content.</span></span>

![](./media/deploy-microsoft-365-enterprise/m365-deploy-content-arch.png)

<span data-ttu-id="4fbdb-115">已在基礎結構的所有階段中建置安全性。</span><span class="sxs-lookup"><span data-stu-id="4fbdb-115">Security is built into all phases of the foundation infrastructure.</span></span>

## <a name="fasttrack"></a><span data-ttu-id="4fbdb-116">FastTrack</span><span class="sxs-lookup"><span data-stu-id="4fbdb-116">FastTrack</span></span>

<span data-ttu-id="4fbdb-p102">FastTrack 是由 Microsoft 工程師提供的持續且可重複的好處，作為訂閱的一部分供您使用，可協助您以自己的步調移轉到雲端。FastTrack 也可在您有需要時，讓您存取合格合作夥伴的其他服務。至今隨著超過 40000 位啟用此服務的客戶，FastTrack 可協助最大化 ROI、加速部署，以及提高整個組織中的採用率。請參閱[適用於 Microsoft 365 的 FastTrack](https://fasttrack.microsoft.com/microsoft365)。</span><span class="sxs-lookup"><span data-stu-id="4fbdb-p102">FastTrack is an ongoing and repeatable benefit—available as part of your subscription—that is delivered by Microsoft engineers to help you move to the cloud at your own pace. FastTrack also gives you access to qualified partners for additional services, as needed. With over 40,000 customers enabled to date, FastTrack helps maximize ROI, accelerate deployment, and increase adoption across your organization. See [FastTrack for Microsoft 365](https://fasttrack.microsoft.com/microsoft365).</span></span>

<span data-ttu-id="4fbdb-p103">如果您想要利用 FastTrack 來部署 Microsoft 365 企業版，您可以使用 FastTrack [Microsoft 365 部署建議程式](https://aka.ms/microsoft365setupguide)，以了解有關部署及設定基礎結構的指導方針。您必須以全域管理員身分登入 Office 365 或 Microsoft 365 租用戶，以便存取此頁面。</span><span class="sxs-lookup"><span data-stu-id="4fbdb-p103">If you want to take advantage of FastTrack to deploy Microsoft 365 Enterprise, you can use the FastTrack [Microsoft 365 deployment advisor](https://aka.ms/microsoft365setupguide) for guidance on how to deploy and set up your foundation infrastructure. You must be signed on as a global administrator in an Office 365 or Microsoft 365 tenant in order to access this page.</span></span>

## <a name="take-a-test-drive"></a><span data-ttu-id="4fbdb-123">採用測試磁碟機</span><span class="sxs-lookup"><span data-stu-id="4fbdb-123">Take a test drive</span></span>

<span data-ttu-id="4fbdb-p104">在生產部署或利用測試實驗室指南 (TLG) 進行特定選項的部署之前，使用 Microsoft 365 企業版。TLG 是模組化、規範性文章，可逐步引導您在簡化但具代表性環境中，使用試用版或付費訂用帳戶設定基礎結構或某項功能。</span><span class="sxs-lookup"><span data-stu-id="4fbdb-p104">Play with Microsoft 365 Enterprise prior to production deployment or the deployment of specific options with Test Lab Guides (TLGs). TLGs are modular, prescriptive articles that step you through the configuration of infrastructure or a feature in a simplified but representative environment using trial or paid subscriptions.</span></span> 

<span data-ttu-id="4fbdb-126">使用 TLG，您可以示範、自訂或建立複雜組態、工作負載或端對端案例的概念證明。</span><span class="sxs-lookup"><span data-stu-id="4fbdb-126">With TLGs, you can demonstrate, customize, or build a proof of concept of a complex configuration, workload, or end-to-end scenario.</span></span>

<span data-ttu-id="4fbdb-127">如需詳細資訊，請參閱 [Microsoft 365 企業版測試實驗室指南](m365-enterprise-test-lab-guides.md)。</span><span class="sxs-lookup"><span data-stu-id="4fbdb-127">For more information, see [Microsoft 365 Enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md).</span></span>

![Microsoft Cloud 的測試實驗室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

## <a name="how-customers-use-microsoft-365-enterprise"></a><span data-ttu-id="4fbdb-129">客戶如何使用 Microsoft 365 企業版</span><span class="sxs-lookup"><span data-stu-id="4fbdb-129">How customers use Microsoft 365 Enterprise</span></span>

<span data-ttu-id="4fbdb-130">請參閱這些資源，以了解客戶如何使用 Microsoft 365 企業版作為其完整的智慧型解決方案，讓所有人可以發揮創意並且安全地共同作業：</span><span class="sxs-lookup"><span data-stu-id="4fbdb-130">See these resources to learn how customers are using Microsoft 365 Enterprise as their complete, intelligent solution that empowers everyone to be creative and work together securely:</span></span>

- <span data-ttu-id="4fbdb-131">健康服務</span><span class="sxs-lookup"><span data-stu-id="4fbdb-131">Health services</span></span>
  - [<span data-ttu-id="4fbdb-132">Lilly 設想這會是一個內部和外部協同合作的工作場所，有助於創新並加快新藥的上市時間。</span><span class="sxs-lookup"><span data-stu-id="4fbdb-132">Lilly envisions a workplace where internal and external collaboration help enable innovation and accelerate time-to-market for new medicines</span></span>](https://aka.ms/Eli_CLS)
  - <span data-ttu-id="4fbdb-133">[醫療保建技術創新加速在雲端中的糖尿病預防](https://aka.ms/Soleracasestudy) (英文)</span><span class="sxs-lookup"><span data-stu-id="4fbdb-133">[Healthcare technology innovator accelerates diabetes prevention in the cloud ](https://aka.ms/Soleracasestudy)</span></span>
  - <span data-ttu-id="4fbdb-134">[Adventist 醫療系統使用 Microsoft 365 加強提供醫療保健](https://aka.ms/adventisthealth) (英文)</span><span class="sxs-lookup"><span data-stu-id="4fbdb-134">[Adventist Health System is enhancing healthcare delivery using Microsoft 365](https://aka.ms/adventisthealth)</span></span>
  - <span data-ttu-id="4fbdb-135">[Abrona 使用 Microsoft 365 加速 GDPR 合規性並且增加生產力](https://aka.ms/Abrona) (英文)</span><span class="sxs-lookup"><span data-stu-id="4fbdb-135">[Abrona accelerates GDPR compliance and increases productivity with Microsoft 365](https://aka.ms/Abrona)</span></span>
  - <span data-ttu-id="4fbdb-136">[Centra 樂於轉換，使用 Microsoft 365 智慧型商務工具來改善病患照護](https://aka.ms/Centra_Health) (英文)</span><span class="sxs-lookup"><span data-stu-id="4fbdb-136">[Centra embraces transformation, improves patient care with Microsoft 365 intelligent business tools](https://aka.ms/Centra_Health)</span></span>
  - <span data-ttu-id="4fbdb-137">[Advoraate Aurora Health 使用 Microsoft 醫療照護協作解決方案，協助患者擁有更好的生活品質以加強合作](https://aka.ms/Advocate_) (英文)</span><span class="sxs-lookup"><span data-stu-id="4fbdb-137">[Advocate Aurora Health helps patients live well using Microsoft care coordination solution to enhance collaboration](https://aka.ms/Advocate_)</span></span>
- <span data-ttu-id="4fbdb-138">財務服務</span><span class="sxs-lookup"><span data-stu-id="4fbdb-138">Financial services</span></span>
  - <span data-ttu-id="4fbdb-139">[TD Bank 讓員工使用 Office 365 和 Windows 10 中的輔助技術](https://aka.ms/tdbankgroup) (英文)</span><span class="sxs-lookup"><span data-stu-id="4fbdb-139">[TD Bank empowers employees with assistive technology in Office 365 and Windows 10](https://aka.ms/tdbankgroup)</span></span>
  - <span data-ttu-id="4fbdb-140">[家庭報稅開始選擇一體解決方案來協助增加收益](https://aka.ms/SOSCaseStudy) (英文)</span><span class="sxs-lookup"><span data-stu-id="4fbdb-140">[Family tax preparation startup chooses all-in-one solution to help grow business](https://aka.ms/SOSCaseStudy)</span></span>
- <span data-ttu-id="4fbdb-141">交通</span><span class="sxs-lookup"><span data-stu-id="4fbdb-141">Transportation</span></span>
  - <span data-ttu-id="4fbdb-142">[Qantas 讓員工能夠利用 Microsoft 365 讓工作盡善盡美，並提升客戶體驗](https://aka.ms/Qantas_CS) (英文)</span><span class="sxs-lookup"><span data-stu-id="4fbdb-142">[Qantas empowers employees to do their best work with Microsoft 365, enhancing customer experience](https://aka.ms/Qantas_CS)</span></span>
  - <span data-ttu-id="4fbdb-143">[Amtrak 利用 Microsoft 365 使其行動企業迎頭領先](https://aka.ms/Amtrak_) (英文)</span><span class="sxs-lookup"><span data-stu-id="4fbdb-143">[Amtrak keeps its mobile enterprise running ahead of schedule with Microsoft 365](https://aka.ms/Amtrak_)</span></span>
- <span data-ttu-id="4fbdb-144">製造</span><span class="sxs-lookup"><span data-stu-id="4fbdb-144">Manufacturing</span></span>
  - <span data-ttu-id="4fbdb-145">[鋼鐵業公司透過雲端減少硬體成本、簡化 IT，並且獲得行動生產力](https://aka.ms/Steeledalecasestudy) (英文)</span><span class="sxs-lookup"><span data-stu-id="4fbdb-145">[Steel company eliminates hardware costs, streamlines IT, and gains mobile productivity in the cloud](https://aka.ms/Steeledalecasestudy)</span></span>
  - <span data-ttu-id="4fbdb-146">[刺繡設備供應商透過雲端型服務來增強其業務能力，讓名聲散播到其他小型企業](https://aka.ms/PriorityLLCCaseStudy) (英文)</span><span class="sxs-lookup"><span data-stu-id="4fbdb-146">[Embroidery equipment supplier empowers its business with cloud-based services, spreads word to other small businesses](https://aka.ms/PriorityLLCCaseStudy)</span></span>
  - <span data-ttu-id="4fbdb-147">[父子企業向全世界展示了行動不便的員工可以實現的目標](https://aka.ms/JCSCaseStudy) (英文)</span><span class="sxs-lookup"><span data-stu-id="4fbdb-147">[Father and son business shows the world what employees with disabilities can achieve](https://aka.ms/JCSCaseStudy)</span></span>
  - <span data-ttu-id="4fbdb-148">[通過現代化的協作工具，椰子公司可以改善移動性、更好的指標並提高生產力](https://aka.ms/SilvermillCS) (英文)</span><span class="sxs-lookup"><span data-stu-id="4fbdb-148">[Coconut company gains improved mobility, better metrics, and increased productivity by modernizing collaboration tools](https://aka.ms/SilvermillCS)</span></span>
  - <span data-ttu-id="4fbdb-149">[蓬勃發展的日本創新者透過 Microsoft 365 Business 發現了不會過時的彈性和增強的安全性](https://aka.ms/DreamFactoryCaseStudy) (英文)</span><span class="sxs-lookup"><span data-stu-id="4fbdb-149">[Thriving Japanese innovator finds future-proof flexibility and enhanced security with Microsoft 365 Business](https://aka.ms/DreamFactoryCaseStudy)</span></span>
- <span data-ttu-id="4fbdb-150">工程</span><span class="sxs-lookup"><span data-stu-id="4fbdb-150">Engineering</span></span>
   - [<span data-ttu-id="4fbdb-151">Cadence 利用行動協同作業工具加快業務步調</span><span class="sxs-lookup"><span data-stu-id="4fbdb-151">Cadence increases the pace of business with mobile collaboration tools</span></span>](https://customers.microsoft.com/story/cadence-partner-professional-services-microsoft-365)
- <span data-ttu-id="4fbdb-152">專業服務</span><span class="sxs-lookup"><span data-stu-id="4fbdb-152">Professional services</span></span>
  - <span data-ttu-id="4fbdb-153">[精品業和不動產法律事務所支援透過全面性的雲端型平台進行擴展](https://aka.ms/Lieserskaffcasestudy) (英文)</span><span class="sxs-lookup"><span data-stu-id="4fbdb-153">[Boutique business and real estate law firm supports expansion with comprehensive cloud-based platform ](https://aka.ms/Lieserskaffcasestudy)</span></span>
  - <span data-ttu-id="4fbdb-154">[運動科技公司透過生物反饋和分析協助運動員達到巔峰](https://aka.ms/KMOTIONCasestudy) (英文)</span><span class="sxs-lookup"><span data-stu-id="4fbdb-154">[Sports technology company helps athletes reach their peak through biofeedback and analytics ](https://aka.ms/KMOTIONCasestudy)</span></span>
  - <span data-ttu-id="4fbdb-155">[數位轉換和雲端讓商業協會為其成員提供更好的服務](https://aka.ms/AIMCS) (英文)</span><span class="sxs-lookup"><span data-stu-id="4fbdb-155">[Digital transformation and the cloud empower business association to serve its members better ](https://aka.ms/AIMCS)</span></span>
- <span data-ttu-id="4fbdb-156">能源服務</span><span class="sxs-lookup"><span data-stu-id="4fbdb-156">Energy services</span></span>
  - <span data-ttu-id="4fbdb-157">[Schlumberger 透過 Microsoft 365 讓全球團隊合作更加精煉](https://aka.ms/Schlumberger_) (英文)</span><span class="sxs-lookup"><span data-stu-id="4fbdb-157">[Schlumberger refines global teamwork with Microsoft 365](https://aka.ms/Schlumberger_)</span></span>
- <span data-ttu-id="4fbdb-158">營造</span><span class="sxs-lookup"><span data-stu-id="4fbdb-158">Construction</span></span>
  - <span data-ttu-id="4fbdb-159">[搜尋資料安全性解決方案，發掘一般承包公司的 Microsoft 365 共同作業功能](https://aka.ms/Transbluecasestudy) (英文)</span><span class="sxs-lookup"><span data-stu-id="4fbdb-159">[Search for data security solution unearths collaborative capabilities of Microsoft 365 at general contracting company](https://aka.ms/Transbluecasestudy)</span></span>
- <span data-ttu-id="4fbdb-160">顧問</span><span class="sxs-lookup"><span data-stu-id="4fbdb-160">Consulting</span></span>
  - <span data-ttu-id="4fbdb-161">[ERM 使用 Microsoft 365 為可靠的未來持續做出貢獻](https://aka.ms/ERM_CS) (英文)</span><span class="sxs-lookup"><span data-stu-id="4fbdb-161">[ERM contributes to a more sustainable future with Microsoft 365](https://aka.ms/ERM_CS)</span></span>
- <span data-ttu-id="4fbdb-162">非營利機構</span><span class="sxs-lookup"><span data-stu-id="4fbdb-162">Non-profit</span></span>
  - <span data-ttu-id="4fbdb-163">[移轉到雲端的技術可讓非營利組織節省 50 萬美元，同時提高安全性、移動性和協作性](https://aka.ms/MOWCaseStudy) (英文)</span><span class="sxs-lookup"><span data-stu-id="4fbdb-163">[Move to the cloud saves nonprofit $500,000 while improving security, mobility, and collaboration ](https://aka.ms/MOWCaseStudy)</span></span>
  
## <a name="how-microsoft-uses-microsoft-365-enterprise"></a><span data-ttu-id="4fbdb-164">Microsoft 如何使用 Microsoft 365 企業版</span><span class="sxs-lookup"><span data-stu-id="4fbdb-164">How Microsoft uses Microsoft 365 Enterprise</span></span>

<span data-ttu-id="4fbdb-165">一窺 Microsoft IT 內部，並且了解他們如何部署 Microsoft 365 企業版，以及 Microsoft 員工如何每天使用。</span><span class="sxs-lookup"><span data-stu-id="4fbdb-165">Take a peek inside Microsoft IT and learn how they deployed Microsoft 365 Enterprise and how Microsoft employees use it every day.</span></span>

### <a name="networking"></a><span data-ttu-id="4fbdb-166">網路功能</span><span class="sxs-lookup"><span data-stu-id="4fbdb-166">Networking</span></span>

- [<span data-ttu-id="4fbdb-167">最佳化 Microsoft Office 365 的網路效能</span><span class="sxs-lookup"><span data-stu-id="4fbdb-167">Optimizing network performance for Microsoft Office 365</span></span>](https://www.microsoft.com/itshowcase/Article/Content/631/Optimizing-network-performance-for-Microsoft-Office-365)

### <a name="identity"></a><span data-ttu-id="4fbdb-168">身分識別</span><span class="sxs-lookup"><span data-stu-id="4fbdb-168">Identity</span></span>

- [<span data-ttu-id="4fbdb-169">在 Microsoft 管理使用者身分識別並且保護存取權</span><span class="sxs-lookup"><span data-stu-id="4fbdb-169">Managing user identities and secure access at Microsoft</span></span>](https://www.microsoft.com/itshowcase/Article/Content/931/Managing-user-identities-and-secure-access-at-Microsoft)
- [<span data-ttu-id="4fbdb-170">針對提升權限的存取使用 Azure AD Privileged Identity Management</span><span class="sxs-lookup"><span data-stu-id="4fbdb-170">Using Azure AD Privileged Identity Management for elevated access</span></span>](https://www.microsoft.com/itshowcase/Article/Content/887/Using-Azure-AD-Privileged-Identity-Management-for-elevated-access)

### <a name="windows-10-enterprise"></a><span data-ttu-id="4fbdb-171">Windows 10 企業版</span><span class="sxs-lookup"><span data-stu-id="4fbdb-171">Windows 10 Enterprise</span></span>

- [<span data-ttu-id="4fbdb-172">準備您的組織以便進行完美的 Windows 10 部署</span><span class="sxs-lookup"><span data-stu-id="4fbdb-172">Preparing your organization for a seamless Windows 10 deployment</span></span>](https://www.microsoft.com/itshowcase/windows10deployment?wt.mc_id=bmkg_itsc)
- [<span data-ttu-id="4fbdb-173">採用 Microsoft 的 Windows 即服務</span><span class="sxs-lookup"><span data-stu-id="4fbdb-173">Adopting Windows as a service at Microsoft</span></span>](https://www.microsoft.com/itshowcase/Article/Content/851/Adopting-Windows-as-a-service-at-Microsoft)
- [<span data-ttu-id="4fbdb-174">在 Microsoft 以就地升級方式部署 Windows 10</span><span class="sxs-lookup"><span data-stu-id="4fbdb-174">Deploying Windows 10 at Microsoft as an in-place upgrade</span></span>](https://www.microsoft.com/itshowcase/Article/Content/668/Deploying-Windows-10-at-Microsoft-as-an-inplace-upgrade)
- [<span data-ttu-id="4fbdb-175">使用 Windows Hello 企業版實作強大的使用者驗證</span><span class="sxs-lookup"><span data-stu-id="4fbdb-175">Implementing strong user authentication with Windows Hello for Business</span></span>](https://www.microsoft.com/itshowcase/Article/Content/756/Implementing-strong-user-authentication-with-Windows-Hello-for-Business)
- <span data-ttu-id="4fbdb-176">[Windows 10 部署：Microsoft IT 的秘訣與技巧](https://www.microsoft.com/itshowcase/Article/Content/951/Windows-10-deployment-tips-and-tricks-from-Microsoft-IT) (影片)</span><span class="sxs-lookup"><span data-stu-id="4fbdb-176">[Windows 10 deployment: tips and tricks from Microsoft IT](https://www.microsoft.com/itshowcase/Article/Content/951/Windows-10-deployment-tips-and-tricks-from-Microsoft-IT) (video)</span></span>
- [<span data-ttu-id="4fbdb-177">Windows Defender ATP 可協助偵測複雜的威脅</span><span class="sxs-lookup"><span data-stu-id="4fbdb-177">Windows Defender ATP helps detect sophisticated threats</span></span>](https://www.microsoft.com/itshowcase/Article/Content/854/Windows-Defender-ATP-helps-detect-sophisticated-threats)
- <span data-ttu-id="4fbdb-178">[使用 Windows Defender 和 Windows Defender ATP 保護現代的企業](https://www.microsoft.com/itshowcase/Article/Content/903/Securing-the-modern-enterprise-with-Windows-Defender-and-Windows-Defender-ATP) (影片)</span><span class="sxs-lookup"><span data-stu-id="4fbdb-178">[Securing the modern enterprise with Windows Defender and Windows Defender ATP](https://www.microsoft.com/itshowcase/Article/Content/903/Securing-the-modern-enterprise-with-Windows-Defender-and-Windows-Defender-ATP) (video)</span></span>

### <a name="office-365-proplus"></a><span data-ttu-id="4fbdb-179">Office 365 專業增強版</span><span class="sxs-lookup"><span data-stu-id="4fbdb-179">Office 365 ProPlus</span></span>

- [<span data-ttu-id="4fbdb-180">準備您的組織以便進行完美的 Office 365 專業增強版 2016 部署</span><span class="sxs-lookup"><span data-stu-id="4fbdb-180">Preparing your organization for a seamless Office 365 ProPlus 2016 deployment</span></span>](https://www.microsoft.com/itshowcase/Office365adoption)
- [<span data-ttu-id="4fbdb-181">部署及更新 Microsoft Office 365 專業增強版</span><span class="sxs-lookup"><span data-stu-id="4fbdb-181">Deploying and updating Microsoft Office 365 ProPlus</span></span>](https://www.microsoft.com/itshowcase/Article/Content/757/Deploying-and-updating-Microsoft-Office-365-ProPlus)
- <span data-ttu-id="4fbdb-182">[自動化和更新通道有助於部署 Microsoft Office 365 專業增強版](https://www.microsoft.com/itshowcase/Article/Content/794/Automation-and-update-channels-help-deploy-Microsoft-Office-365-ProPlus) (影片)</span><span class="sxs-lookup"><span data-stu-id="4fbdb-182">[Automation and update channels help deploy Microsoft Office 365 ProPlus](https://www.microsoft.com/itshowcase/Article/Content/794/Automation-and-update-channels-help-deploy-Microsoft-Office-365-ProPlus) (video)</span></span>

### <a name="mobility-and-device-management"></a><span data-ttu-id="4fbdb-183">行動力和裝置管理</span><span class="sxs-lookup"><span data-stu-id="4fbdb-183">Mobility and device management</span></span>

- <span data-ttu-id="4fbdb-184">[使用企業行動力 + 安全性管理現代行動生產力](https://www.microsoft.com/itshowcase/Article/Content/972/Managing-modern-mobile-productivity-with-Enterprise-Mobility--Security) (英文)</span><span class="sxs-lookup"><span data-stu-id="4fbdb-184">[Managing modern mobile productivity with Enterprise Mobility + Security](https://www.microsoft.com/itshowcase/Article/Content/972/Managing-modern-mobile-productivity-with-Enterprise-Mobility--Security)</span></span>
- <span data-ttu-id="4fbdb-185">[使用 Microsoft Intune 連線到公司的 Windows 10 裝置](https://www.microsoft.com/itshowcase/Article/Content/783/Connecting-to-work-on-your-Windows-10-device-with-Microsoft-Intune) (英文)</span><span class="sxs-lookup"><span data-stu-id="4fbdb-185">[Connecting to work on your Windows 10 device with Microsoft Intune](https://www.microsoft.com/itshowcase/Article/Content/783/Connecting-to-work-on-your-Windows-10-device-with-Microsoft-Intune)</span></span>
- <span data-ttu-id="4fbdb-186">[為 Microsoft 的 iOS、OS X 和 Android 設備啟用移動生產力](https://www.microsoft.com/itshowcase/Article/Content/773/Enabling-mobile-productivity-for-iOS-OS-X-and-Android-devices-at-Microsoft) (英文)</span><span class="sxs-lookup"><span data-stu-id="4fbdb-186">[Enabling mobile productivity for iOS, OS X, and Android devices at Microsoft](https://www.microsoft.com/itshowcase/Article/Content/773/Enabling-mobile-productivity-for-iOS-OS-X-and-Android-devices-at-Microsoft)</span></span>

### <a name="security-and-information-protection"></a><span data-ttu-id="4fbdb-187">安全性和資訊保護</span><span class="sxs-lookup"><span data-stu-id="4fbdb-187">Security and information protection</span></span>

- [<span data-ttu-id="4fbdb-188">使用 Azure 資訊保護來保護雲端的檔案</span><span class="sxs-lookup"><span data-stu-id="4fbdb-188">Protecting files in the cloud with Azure Information Protection</span></span>](https://www.microsoft.com/itshowcase/Article/Content/924/Protecting-files-in-the-cloud-with-Azure-Information-Protection)
- [<span data-ttu-id="4fbdb-189">Microsoft 會使用威脅情報來保護、偵測及回應威脅</span><span class="sxs-lookup"><span data-stu-id="4fbdb-189">Microsoft uses threat intelligence to protect, detect, and respond to threats</span></span>](https://www.microsoft.com/itshowcase/Article/Content/934/Microsoft-uses-threat-intelligence-to-protect-detect-and-respond-to-threats)
- [<span data-ttu-id="4fbdb-190">Microsoft 會使用 Office 365 來阻撓網路釣魚嘗試</span><span class="sxs-lookup"><span data-stu-id="4fbdb-190">Microsoft thwarts phishing attempts with Office 365</span></span>](https://www.microsoft.com/itshowcase/Article/Content/956/Microsoft-thwarts-phishing-attempts-with-Office-365)

### <a name="microsoft-teams"></a><span data-ttu-id="4fbdb-191">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4fbdb-191">Microsoft Teams</span></span>

- [<span data-ttu-id="4fbdb-192">部署 Microsoft Teams 可簡化共同作業並提升團隊合作</span><span class="sxs-lookup"><span data-stu-id="4fbdb-192">Deploying Microsoft Teams streamlines collaboration and improves teamwork</span></span>](https://www.microsoft.com/itshowcase/Article/Content/1013/Deploying-Microsoft-Teams-streamlines-collaboration-and-improves-teamwork)
- [<span data-ttu-id="4fbdb-193">Microsoft Teams 可在 Microsoft 的現代化工作場所增進共同作業</span><span class="sxs-lookup"><span data-stu-id="4fbdb-193">Microsoft Teams increases collaboration in the modern workplace at Microsoft</span></span>](https://www.microsoft.com/itshowcase/Article/Content/1012/Microsoft-Teams-increases-collaboration-in-the-modern-workplace-at-Microsoft)

### <a name="data-migration"></a><span data-ttu-id="4fbdb-194">資料移轉</span><span class="sxs-lookup"><span data-stu-id="4fbdb-194">Data migration</span></span>

- [<span data-ttu-id="4fbdb-195">Microsoft 會將 150000 個信箱移轉到 Exchange Online</span><span class="sxs-lookup"><span data-stu-id="4fbdb-195">Microsoft migrates 150,000 mailboxes to Exchange Online</span></span>](https://www.microsoft.com/itshowcase/Article/Content/577/Microsoft-migrates-150000-mailboxes-to-Exchange-Online)
- [<span data-ttu-id="4fbdb-196">SharePoint 至雲端：深入了解 Microsoft 如何執行自己的移轉</span><span class="sxs-lookup"><span data-stu-id="4fbdb-196">SharePoint to the cloud: Learn how Microsoft ran its own migration</span></span>](https://www.microsoft.com/itshowcase/Article/Content/691/SharePoint-to-the-cloud-Learn-how-Microsoft-ran-its-own-migration)

## <a name="how-the-contoso-corporation-deployed-microsoft-365-enterprise"></a><span data-ttu-id="4fbdb-197">Contoso Corporation 如何部署 Microsoft 365 企業版</span><span class="sxs-lookup"><span data-stu-id="4fbdb-197">How the Contoso Corporation deployed Microsoft 365 Enterprise</span></span>

<span data-ttu-id="4fbdb-p105">Contoso Corporation 是虛構但有代表性的全球製造集團，總部位於巴黎。請參閱 [Contoso 已部署 Microsoft 365 企業版](contoso-case-study.md)，並且針對網路、身分識別、Windows 10 企業版、Office 365 專業增強版、行動裝置管理、資訊保護和安全性，訂定主要設計決策和實作詳細資料。</span><span class="sxs-lookup"><span data-stu-id="4fbdb-p105">The Contoso Corporation is a fictional but representative global manufacturing conglomerate with its headquarters in Paris. See how [Contoso deployed Microsoft 365 Enterprise](contoso-case-study.md) and addressed major design decisions and implementation details for networking, identity, Windows 10 Enterprise, Office 365 ProPlus, mobile device management, information protection, and security.</span></span> 

![](./media/contoso-overview/contoso-icon.png)

## <a name="additional-microsoft-365-solutions"></a><span data-ttu-id="4fbdb-200">其他 Microsoft 365 解決方案</span><span class="sxs-lookup"><span data-stu-id="4fbdb-200">Additional Microsoft 365 solutions</span></span>

- [<span data-ttu-id="4fbdb-201">Microsoft 365 商務版 </span><span class="sxs-lookup"><span data-stu-id="4fbdb-201">Microsoft 365 Business</span></span>](https://docs.microsoft.com/microsoft-365/business/)
 
  <span data-ttu-id="4fbdb-202">將 Office 365 的同等級最佳生產力和共同作業能力與裝置管理和安全性解決方案整合在一起，以保護中小型企業 (SMB) 的商務資料。</span><span class="sxs-lookup"><span data-stu-id="4fbdb-202">Bring together the best-in-class productivity and collaboration capabilities of Office 365 with device management and security solutions to safeguard business data for small and midsize businesses (SMB).</span></span>

- [<span data-ttu-id="4fbdb-203">Microsoft 365 教育版</span><span class="sxs-lookup"><span data-stu-id="4fbdb-203">Microsoft 365 Education</span></span>](https://docs.microsoft.com/education)
 
  <span data-ttu-id="4fbdb-204">可讓授課者解放創意、提升團隊合作，並在專為教育打造且價格合理的單一解決方案中提供簡單且安全的體驗。</span><span class="sxs-lookup"><span data-stu-id="4fbdb-204">Empower educators to unlock creativity, promote teamwork, and provide a simple and safe experience in a single, affordable solution built for education.</span></span>

## <a name="next-step"></a><span data-ttu-id="4fbdb-205">下一步</span><span class="sxs-lookup"><span data-stu-id="4fbdb-205">Next step</span></span>

<span data-ttu-id="4fbdb-206">使用 [FastTrack](https://fasttrack.microsoft.com/microsoft365) 或[基礎結構](deploy-foundation-infrastructure.md)入門。</span><span class="sxs-lookup"><span data-stu-id="4fbdb-206">Use [FastTrack](https://fasttrack.microsoft.com/microsoft365) or get started with the [foundation infrastructure](deploy-foundation-infrastructure.md).</span></span>
