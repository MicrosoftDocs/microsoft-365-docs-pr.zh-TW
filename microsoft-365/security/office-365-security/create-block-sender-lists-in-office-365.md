---
title: 在 Office 365 中建立封鎖寄件者清單
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 5/6/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150s
description: 封鎖寄件者清單選項包括 Outlook 封鎖寄件者、 反垃圾郵件寄件者/網域封鎖清單、 IP 封鎖清單，以及 Exchange 傳輸規則 (Etr) 也稱為郵件流程規則。
ms.openlocfilehash: f4fab732a92df2a2500212c9825d2b3e710b0a07
ms.sourcegitcommit: 5710ce729c55d95b8b452d99ffb7ea92b5cb254a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/11/2019
ms.locfileid: "39970889"
---
# <a name="create-block-sender-lists-in-office-365"></a><span data-ttu-id="65df3-103">在 Office 365 中建立封鎖寄件者清單</span><span class="sxs-lookup"><span data-stu-id="65df3-103">Create block sender lists in Office 365</span></span>

<span data-ttu-id="65df3-104">有時會需要封鎖寄件者的垃圾電子郵件。</span><span class="sxs-lookup"><span data-stu-id="65df3-104">Sometimes it’s necessary to block unwanted email from senders.</span></span> <span data-ttu-id="65df3-105">有數種方法可從選擇。</span><span class="sxs-lookup"><span data-stu-id="65df3-105">There are several methods available to choose from.</span></span> <span data-ttu-id="65df3-106">這些選項包括 Outlook 封鎖寄件者、 反垃圾郵件寄件者/網域封鎖清單、 IP 封鎖清單，以及 Exchange 傳輸規則 (Etr，也就是也稱為郵件流程規則)。</span><span class="sxs-lookup"><span data-stu-id="65df3-106">These options include Outlook Blocked Senders, Anti-Spam Sender/Domain Block Lists, IP Block Lists, and Exchange Transport Rules (ETRs, which are also known as mail flow rules).</span></span>

> [!NOTE]
> <span data-ttu-id="65df3-107">雖然可用於組織封鎖清單地址 false 負號 （未接的垃圾郵件），這些應徵者應也要送出給 Microsoft 進行分析。</span><span class="sxs-lookup"><span data-stu-id="65df3-107">While organization block lists can be used to address false negatives (missed spam), those candidates should also be submitted to Microsoft for analysis.</span></span> <span data-ttu-id="65df3-108">誤判使用管理的封鎖清單會大幅增加您管理的額外負荷。</span><span class="sxs-lookup"><span data-stu-id="65df3-108">Managing false negatives by using block lists significantly increases your administrative overhead.</span></span> <span data-ttu-id="65df3-109">如果您將會使用封鎖清單達到此目的，您必須同時保留文章[提交垃圾郵件、 非垃圾郵件和網路釣魚詐騙郵件提交給 Microsoft 進行分析](https://docs.microsoft.com/office365/SecurityCompliance/submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis)，在準備。</span><span class="sxs-lookup"><span data-stu-id="65df3-109">If you will use a block list for this purpose, you will need to also keep the article for [submitting spam, non-spam, and phishing scam messages to Microsoft for analysis](https://docs.microsoft.com/office365/SecurityCompliance/submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis), at the ready.</span></span>

<span data-ttu-id="65df3-110">若要設定封鎖的寄件者清單的適當方法影響的範圍而有所不同。</span><span class="sxs-lookup"><span data-stu-id="65df3-110">The proper method to configure blocked sender lists varies depending on the scope of the impact.</span></span> <span data-ttu-id="65df3-111">單一使用者的影響，右解決方案可能是使用 Outlook 封鎖寄件者，但如果多個使用者或所有使用者正在受影響，其中一個其他選項會更合適。</span><span class="sxs-lookup"><span data-stu-id="65df3-111">For single user impact, the right solution could be to use Outlook Blocked Senders, but if multiple users or all users are being impacted, one of the other options would be more appropriate.</span></span>

## <a name="options-from-least-to-broadest-scope"></a><span data-ttu-id="65df3-112">從最小到最大範圍的選項</span><span class="sxs-lookup"><span data-stu-id="65df3-112">Options from least to broadest scope</span></span>

<span data-ttu-id="65df3-113">建立封鎖清單時很重要挑選適合的方法，根據 （會影響多少人） 的影響，範圍，使其符合封鎖方法的廣度。</span><span class="sxs-lookup"><span data-stu-id="65df3-113">When creating a Block list it's important to pick the appropriate method based on the scope of the impact (how many people will be impacted), so that it matches the breadth of the blocking method.</span></span> <span data-ttu-id="65df3-114">下面所列的選項會透過範圍和廣度排名。</span><span class="sxs-lookup"><span data-stu-id="65df3-114">The options listed below are ranked by both scope and breadth.</span></span> <span data-ttu-id="65df3-115">清單會從窄到廣泛，但*讀取特定內容*的完整的建議。</span><span class="sxs-lookup"><span data-stu-id="65df3-115">The list goes from narrow to broad, but *read the specifics* for full recommendations.</span></span>

- <span data-ttu-id="65df3-116">Outlook 封鎖的寄件者</span><span class="sxs-lookup"><span data-stu-id="65df3-116">Outlook Blocked Senders</span></span>
- <span data-ttu-id="65df3-117">反垃圾郵件原則： 寄件者/網域封鎖清單</span><span class="sxs-lookup"><span data-stu-id="65df3-117">Anti-Spam policy: Sender/Domain Block lists</span></span>
- <span data-ttu-id="65df3-118">Exchange 傳輸規則 （Etr 也稱為的郵件流程規則）</span><span class="sxs-lookup"><span data-stu-id="65df3-118">Exchange Transport Rules (ETRs also called mail-flow rules)</span></span>
- <span data-ttu-id="65df3-119">反垃圾郵件原則： IP 封鎖清單</span><span class="sxs-lookup"><span data-stu-id="65df3-119">Anti-Spam policy: IP Block Lists</span></span>

## <a name="use-outlook-blocked-senders"></a><span data-ttu-id="65df3-120">使用 Outlook 封鎖的寄件者</span><span class="sxs-lookup"><span data-stu-id="65df3-120">Use Outlook Blocked Senders</span></span>

<span data-ttu-id="65df3-121">只有少數使用者會受到影響，這是時，也應該使用 Outlook 封鎖寄件者，因為這只會影響郵件傳送給它們。</span><span class="sxs-lookup"><span data-stu-id="65df3-121">When only a small number of users are impacted, that's when Outlook Blocked Senders should be used, because this will only impact mail being sent to them.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="65df3-122">如果不想要的郵件新聞稿信譽及辨識的來源，取消訂閱電子郵件中是用來停止從未來取得電子郵件使用者的其他選項。</span><span class="sxs-lookup"><span data-stu-id="65df3-122">If the unwanted messages are newsletters from a reputable and recognizable source, unsubscribing from the email is another option to stop the user from getting the emails in the future.</span></span>

<span data-ttu-id="65df3-123">若要設定此案例的步驟是不同[的網頁型 Outlook](https://support.office.com/article/48c9f6f7-2309-4f95-9a4d-de987e880e46)和[Outlook 用戶端](https://support.office.com/article/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089)之間。</span><span class="sxs-lookup"><span data-stu-id="65df3-123">The steps to set this up are different between [Outlook on the web](https://support.office.com/article/48c9f6f7-2309-4f95-9a4d-de987e880e46) and the [Outlook client](https://support.office.com/article/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089).</span></span> <span data-ttu-id="65df3-124">**郵件已成功封鎖由於封鎖寄件者時您會看到 sfv: X-Forefront-反垃圾郵件的報告**指出郵件會遭到封鎖。</span><span class="sxs-lookup"><span data-stu-id="65df3-124">**When messages are successfully blocked due to Blocked Senders you will see SFV:BLK in the X-Forefront-Antispam-Report** which indicates that the message is being blocked.</span></span>

## <a name="use-anti-spam-policy-senderdomain-block-lists"></a><span data-ttu-id="65df3-125">使用反垃圾郵件原則/網域的寄件者封鎖清單</span><span class="sxs-lookup"><span data-stu-id="65df3-125">Use Anti-Spam Policy Sender/Domain Block lists</span></span>

<span data-ttu-id="65df3-126">時所受影響多個使用者，範圍更廣，且您需要使用全公司的寄件者/網域 」 封鎖清單反垃圾郵件原則。</span><span class="sxs-lookup"><span data-stu-id="65df3-126">When multiple users are being impacted, the scope is wider, and you need to use a company-wide sender/domain block list Anti-Spam policy.</span></span> <span data-ttu-id="65df3-127">詳細的步驟可以[設定您的垃圾郵件篩選原則](https://docs.microsoft.com/office365/securitycompliance/configure-your-spam-filter-policies)的文件中找到。</span><span class="sxs-lookup"><span data-stu-id="65df3-127">The detailed steps can be found in [Configure your spam filter policies](https://docs.microsoft.com/office365/securitycompliance/configure-your-spam-filter-policies) document.</span></span> <span data-ttu-id="65df3-128">已封鎖透過此方法的任何訊息會遵循 [垃圾郵件] 動作，該原則中設定的一樣。</span><span class="sxs-lookup"><span data-stu-id="65df3-128">Any messages blocked through this method will follow the spam action as configured in the policy.</span></span>

<span data-ttu-id="65df3-129">這些清單的最大限制是大約 1000年項目;雖然您只能夠輸入入入口網站的 30 個項目。</span><span class="sxs-lookup"><span data-stu-id="65df3-129">The maximum limit for these lists is approximately 1000 entries; although, you will only be able to enter 30 entries into the portal.</span></span> <span data-ttu-id="65df3-130">您必須使用 PowerShell 來新增 30 個以上的項目。</span><span class="sxs-lookup"><span data-stu-id="65df3-130">You must use PowerShell to add more than 30 entries.</span></span>

## <a name="use-exchange-transport-rules-etrs-to-block-specific-senders"></a><span data-ttu-id="65df3-131">使用 Exchange 傳輸規則 (Etr) 來封鎖特定寄件者</span><span class="sxs-lookup"><span data-stu-id="65df3-131">Use Exchange Transport Rules (ETRs) to Block specific senders</span></span>

<span data-ttu-id="65df3-132">必要時要傳送給特定使用者或整個組織的封鎖郵件，可以使用 Etr （也稱為郵件流程規則）。</span><span class="sxs-lookup"><span data-stu-id="65df3-132">If it's necessary to block messages being sent to specific users or across the entire organization, ETRs (also called mail flow rules) can be used.</span></span> <span data-ttu-id="65df3-133">Etr 是更有彈性，因為他們可以觸發關閉寄件者電子郵件地址或網域，以及關鍵字和訊息中的其他屬性。</span><span class="sxs-lookup"><span data-stu-id="65df3-133">ETRs are more flexible because they can trigger off the sender Email Address or Domain as well as key words and other properties  in the message.</span></span> <span data-ttu-id="65df3-134">這種彈性可讓您建立或部分-完整區塊。</span><span class="sxs-lookup"><span data-stu-id="65df3-134">This flexibility will let you create partial- to complete blocks.</span></span> <span data-ttu-id="65df3-135">[請按一下 [建立 ETR，也稱為郵件流程規則的步驟](https://docs.microsoft.com/office365/SecurityCompliance/use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages)。</span><span class="sxs-lookup"><span data-stu-id="65df3-135">[Please click for the steps to create an ETR, also known as a mail-flow rules](https://docs.microsoft.com/office365/SecurityCompliance/use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="65df3-136">很容易建立*過度*積極的規則，因此請務必正在使用的準則會儘可能指定特定。</span><span class="sxs-lookup"><span data-stu-id="65df3-136">It's easy to create rules that are *overly* aggressive, as a result it's important the criteria being used is as specific as possible.</span></span> <span data-ttu-id="65df3-137">此外，請務必啟用稽核規則建立並執行測試，以確保每個項目如預期般運作。</span><span class="sxs-lookup"><span data-stu-id="65df3-137">Also, be sure that you enable auditing on the rule you create and do testing to ensure everything works as expected.</span></span>

## <a name="use-anti-spam-policy-ip-block-lists"></a><span data-ttu-id="65df3-138">使用反垃圾郵件原則 IP 封鎖清單</span><span class="sxs-lookup"><span data-stu-id="65df3-138">Use Anti-Spam Policy IP Block lists</span></span>

<span data-ttu-id="65df3-139">*然後*反垃圾郵件原則 IP 封鎖清單時不能使用下列其中一個其他選項來封鎖寄件者，都可以使用。</span><span class="sxs-lookup"><span data-stu-id="65df3-139">When it’s not possible to use one of the other options to block a sender, *then* the Anti-Spam Policy IP Block List can be used.</span></span> <span data-ttu-id="65df3-140">[可以在文章 Configure the connection filter policy > 中找到的詳細的步驟](https://docs.microsoft.com/office365/securitycompliance/configure-the-connection-filter-policy)。</span><span class="sxs-lookup"><span data-stu-id="65df3-140">[Detailed steps can be found in the article Configure the connection filter policy](https://docs.microsoft.com/office365/securitycompliance/configure-the-connection-filter-policy).</span></span> <span data-ttu-id="65df3-141">請務必保留到*最小*的 Ip 封鎖清單，並*不*建議在這裡使用的 IP 位址範圍。</span><span class="sxs-lookup"><span data-stu-id="65df3-141">It's important to keep the list of blocked IPs to a *minimum* and using IP address ranges here is *not* recommended.</span></span>

<span data-ttu-id="65df3-142">您應該*特別*避免新增 IP 位址範圍，屬於消費者服務或共用的基礎結構，也請務必定期維護的一部分檢閱允許的 IP 位址清單。</span><span class="sxs-lookup"><span data-stu-id="65df3-142">You should *especially* avoid adding IP address ranges that belong to consumer services or shared infrastructures, and also ensure that you review the list of allowed IP addresses as part of regular maintenance.</span></span> <span data-ttu-id="65df3-143">**因為可讓項目可以開啟攻擊的路由，您必須密切管理這份清單，並定期移除允許的項目，但不再需要。**</span><span class="sxs-lookup"><span data-stu-id="65df3-143">**Because allows-entries can open up routes for attack, you must closely manage this list and regularly remove the allows-entries that are no longer needed.**</span></span> <span data-ttu-id="65df3-144">此外，如果您將會讓使用者在 [安全寄件者清單中請務必閱讀並瞭解的風險和預防措施來*[建立安全的寄件者列出 Office 365 中](create-safe-sender-lists-in-office-365.md)*。</span><span class="sxs-lookup"><span data-stu-id="65df3-144">Also, if you will make allows in a Safe-Sender list be sure to read and understand the risks and precautions in *[Create Safe-Sender lists in Office 365](create-safe-sender-lists-in-office-365.md)*.</span></span>
