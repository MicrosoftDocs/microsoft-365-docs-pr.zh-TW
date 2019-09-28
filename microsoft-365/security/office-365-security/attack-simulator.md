---
title: Office 365 中的攻擊模擬器
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: da5845db-c578-4a41-b2cb-5a09689a551b
ms.collection:
- M365-security-compliance
description: 身為 Office 365 全域管理員，您可以使用的攻擊模擬器在組織中執行真實的攻擊案例。 這可協助您找出並之前真實的攻擊拜訪人次貴公司，找出受到使用者。
ms.openlocfilehash: bb68850587647f7e96c940de10e3da23cd5e83de
ms.sourcegitcommit: 84d88a857e82b1a8a0d466057a2e330e8b1692e4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/27/2019
ms.locfileid: "37306177"
---
# <a name="attack-simulator-in-office-365"></a><span data-ttu-id="6ce1a-104">Office 365 中的攻擊模擬器</span><span class="sxs-lookup"><span data-stu-id="6ce1a-104">Attack Simulator in Office 365</span></span>

<span data-ttu-id="6ce1a-105">**摘要**如果您是 Office 365 全域系統管理員或安全性系統管理員，而且您的組織有 Office 365 進階威脅防護計劃 2，其中包含[威脅調查及回應功能](office-365-ti.md)，您可以使用的攻擊模擬器來執行在您的組織中的真實的攻擊案例。</span><span class="sxs-lookup"><span data-stu-id="6ce1a-105">**Summary** If you are an Office 365 global administrator or a security administrator and your organization has Office 365 Advanced Threat Protection Plan 2, which includes [Threat Investigation and Response capabilities](office-365-ti.md), you can use Attack Simulator to run realistic attack scenarios in your organization.</span></span> <span data-ttu-id="6ce1a-106">這可協助您找出並尋找容易遭受使用者之前真實的攻擊影響底部線條。</span><span class="sxs-lookup"><span data-stu-id="6ce1a-106">This can help you identify and find vulnerable users before a real attack impacts your bottom line.</span></span> <span data-ttu-id="6ce1a-107">閱讀本篇文章以了解更多。</span><span class="sxs-lookup"><span data-stu-id="6ce1a-107">Read this article to learn more.</span></span>

## <a name="the-attacks"></a><span data-ttu-id="6ce1a-108">攻擊</span><span class="sxs-lookup"><span data-stu-id="6ce1a-108">The Attacks</span></span>

<span data-ttu-id="6ce1a-109">目前可用的三種類型的攻擊模擬如下：</span><span class="sxs-lookup"><span data-stu-id="6ce1a-109">Three kinds of attack simulations are currently available:</span></span>

- [<span data-ttu-id="6ce1a-110">顯示名稱矛網路釣魚攻擊</span><span class="sxs-lookup"><span data-stu-id="6ce1a-110">Display name spear-phishing attack</span></span>](#display-name-spear-phishing-attack)

- [<span data-ttu-id="6ce1a-111">密碼噴灑攻擊</span><span class="sxs-lookup"><span data-stu-id="6ce1a-111">Password-spray attack</span></span>](#password-spray-attack)

- [<span data-ttu-id="6ce1a-112">暴力密碼攻擊</span><span class="sxs-lookup"><span data-stu-id="6ce1a-112">Brute-force password attack</span></span>](#brute-force-password-attack)

<span data-ttu-id="6ce1a-113">若要順利啟動攻擊，請確定您用來執行模擬的攻擊的帳戶使用多重要素驗證。</span><span class="sxs-lookup"><span data-stu-id="6ce1a-113">For an attack to be successfully launched, make sure that the account you are using to run simulated attacks is using multi-factor authentication.</span></span> <span data-ttu-id="6ce1a-114">此外，您必須是 Office 365 全域系統管理員或安全性系統管理員。</span><span class="sxs-lookup"><span data-stu-id="6ce1a-114">In addition, you must be an Office 365 global administrator or a security administrator.</span></span> <span data-ttu-id="6ce1a-115">（若要深入了解角色和權限，請參閱[Office 365 安全性 & 合規性中心的權限](permissions-in-the-security-and-compliance-center.md)）。</span><span class="sxs-lookup"><span data-stu-id="6ce1a-115">(To learn more about roles and permissions, see [Permissions in the Office 365 Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).)</span></span>

<span data-ttu-id="6ce1a-116">若要存取安全性的攻擊模擬器&amp;合規性中心，選擇 [**威脅管理** \> **攻擊模擬器**。</span><span class="sxs-lookup"><span data-stu-id="6ce1a-116">To access Attack Simulator, in the Security &amp; Compliance Center, choose **Threat management** \> **Attack simulator**.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="6ce1a-117">開始之前...]</span><span class="sxs-lookup"><span data-stu-id="6ce1a-117">Before you begin...</span></span>

<span data-ttu-id="6ce1a-118">請確定您和您的組織符合的攻擊模擬器需求如下：</span><span class="sxs-lookup"><span data-stu-id="6ce1a-118">Make sure that you and your organization meet the following requirements for Attack Simulator:</span></span>

- <span data-ttu-id="6ce1a-119">貴組織的電子郵件會託管於 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="6ce1a-119">Your organization's email is hosted in Exchange Online.</span></span> <span data-ttu-id="6ce1a-120">（攻擊模擬器不適用於內部部署電子郵件伺服器。）</span><span class="sxs-lookup"><span data-stu-id="6ce1a-120">(Attack Simulator is not available for on-premises email servers.)</span></span>

- <span data-ttu-id="6ce1a-121">您是 Office 365 全域系統管理員或安全性系統管理員</span><span class="sxs-lookup"><span data-stu-id="6ce1a-121">You are an Office 365 global administrator or security administrator</span></span>

- <span data-ttu-id="6ce1a-122">[多重要素驗證/條件式存取](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication?view=o365-worldwide)已關閉，如在最低之 Office 365 全域系統管理員帳戶和安全性系統管理員將使用的攻擊模擬器。</span><span class="sxs-lookup"><span data-stu-id="6ce1a-122">[Multi-factor authentication/Conditional Access](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication?view=o365-worldwide) is turned on, for at least the Office 365 global administrator account and security administrators who will be using Attack Simulator.</span></span> <span data-ttu-id="6ce1a-123">（理想狀況下，多重要素驗證條件式存取已為您組織中的所有使用者。）</span><span class="sxs-lookup"><span data-stu-id="6ce1a-123">(Ideally, multi-factor authentication/conditional access is turned on for all users in your organization.)</span></span>

- <span data-ttu-id="6ce1a-124">您的組織有[Office 365 進階威脅防護計劃 2](office-365-atp.md)，與安全性可見的攻擊模擬器&amp;合規性中心 (前往**威脅管理** \> **攻擊模擬器**)</span><span class="sxs-lookup"><span data-stu-id="6ce1a-124">Your organization has [Office 365 Advanced Threat Protection Plan 2](office-365-atp.md), with Attack Simulator visible in the Security &amp; Compliance Center (go to **Threat management** \> **Attack simulator**)</span></span>

    ![威脅管理-攻擊模擬器](../media/ThreatMgmt-AttackSimulator.png)

## <a name="display-name-spear-phishing-attack"></a><span data-ttu-id="6ce1a-126">顯示名稱矛網路釣魚攻擊</span><span class="sxs-lookup"><span data-stu-id="6ce1a-126">Display name spear-phishing attack</span></span>

<span data-ttu-id="6ce1a-127">網路釣魚是通稱歸類為社交樣式攻擊的攻擊廣泛套件。</span><span class="sxs-lookup"><span data-stu-id="6ce1a-127">Phishing is a generic term for a broad suite of attacks classed as a social engineering style attack.</span></span> <span data-ttu-id="6ce1a-128">此類攻擊著重於矛網路釣魚，針對特定群組的個人或組織在多目標攻擊。</span><span class="sxs-lookup"><span data-stu-id="6ce1a-128">This attack is focused on spear phishing, a more targeted attack that is aimed at a specific group of individuals or an organization.</span></span> <span data-ttu-id="6ce1a-129">一般而言，自訂的攻擊與某些偵察執行，並使用會產生收件者，例如看起來像來自組織內的高階主管的電子郵件訊息中的信任的顯示名稱。</span><span class="sxs-lookup"><span data-stu-id="6ce1a-129">Typically, a customized attack with some reconnaissance performed and using a display name that will generate trust in the recipient, such as an email message that looks like it came from an executive within your organization.</span></span>

<span data-ttu-id="6ce1a-130">此類攻擊著重於給您，讓您管理誰會顯示訊息，有來自藉由變更顯示名稱和來源地址。</span><span class="sxs-lookup"><span data-stu-id="6ce1a-130">This attack focuses on letting you manipulate who the message appears to have originated from by changing the display name and source address.</span></span> <span data-ttu-id="6ce1a-131">矛網路釣魚攻擊成功時，cyberattackers 存取使用者的認證。</span><span class="sxs-lookup"><span data-stu-id="6ce1a-131">When spear-phishing attacks are successful, cyberattackers gain access to users' credentials.</span></span>

### <a name="to-simulate-a-spear-phishing-attack"></a><span data-ttu-id="6ce1a-132">若要模擬矛網路釣魚攻擊</span><span class="sxs-lookup"><span data-stu-id="6ce1a-132">To simulate a spear-phishing attack</span></span>

![撰寫電子郵件內文](../media/9bd65af4-1f9d-45c1-8c06-796d7ccfd425.jpg)

<span data-ttu-id="6ce1a-134">您可以製作豐富的 HTML 編輯器，直接在**電子郵件內文**欄位本身或與 HTML 來源搭配使用。</span><span class="sxs-lookup"><span data-stu-id="6ce1a-134">You can craft the rich HTML editor directly in the **Email body** field itself or work with HTML source.</span></span>

1. <span data-ttu-id="6ce1a-135">在[安全性&amp;合規性中心](https://protection.office.com)，選擇 [**威脅管理** \> **攻擊模擬器**。</span><span class="sxs-lookup"><span data-stu-id="6ce1a-135">In the [Security &amp; Compliance Center](https://protection.office.com), choose **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="6ce1a-136">指定攻擊的有意義的活動名稱，或者選取範本。</span><span class="sxs-lookup"><span data-stu-id="6ce1a-136">Specify a meaningful campaign name for the attack or select a template.</span></span>

   ![網路釣魚起始頁面](../media/5e93b3cc-5981-462f-8b45-bdf85d97f1b8.jpg)

3. <span data-ttu-id="6ce1a-138">指定目標收件者。</span><span class="sxs-lookup"><span data-stu-id="6ce1a-138">Specify the target recipients.</span></span> <span data-ttu-id="6ce1a-139">這可以是個人或組織中的群組。</span><span class="sxs-lookup"><span data-stu-id="6ce1a-139">This can be individuals or groups in your organization.</span></span> <span data-ttu-id="6ce1a-140">每個目標收件者必須擁有 Exchange Online 信箱攻擊的順序才會成功。</span><span class="sxs-lookup"><span data-stu-id="6ce1a-140">Each targeted recipient must have an Exchange Online Mailbox in order for the attack to be successful.</span></span>

   ![收件者的選取範圍](../media/faf8c2e0-6175-4cd7-8265-0c8e727f4d0f.jpg)

4. <span data-ttu-id="6ce1a-142">設定網路釣魚電子郵件的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="6ce1a-142">Configure the Phishing email details.</span></span>

   ![設定電子郵件的詳細資訊](../media/f043608f-f8ce-4aae-be28-86e8ecc524a9.jpg)

   <span data-ttu-id="6ce1a-144">HTML 格式可以為複雜或基本與您的行銷活動需求。</span><span class="sxs-lookup"><span data-stu-id="6ce1a-144">The HTML formatting can be as complex or basic as your campaign needs.</span></span> <span data-ttu-id="6ce1a-145">為電子郵件格式是 HTML，您可以插入影像和以增強 believability 的文字。</span><span class="sxs-lookup"><span data-stu-id="6ce1a-145">As the email format is HTML, you can insert images and text to enhance believability.</span></span> <span data-ttu-id="6ce1a-146">您可以在所收到的訊息中接收電子郵件用戶端外觀的控制。</span><span class="sxs-lookup"><span data-stu-id="6ce1a-146">You have control on what the received message will look like in the receiving email client.</span></span>

5. <span data-ttu-id="6ce1a-147">指定文字**從 （名稱）** ] 欄位。</span><span class="sxs-lookup"><span data-stu-id="6ce1a-147">Specify text for the **From (Name)** field.</span></span> <span data-ttu-id="6ce1a-148">這是顯示在接收的電子郵件用戶端中的**顯示名稱**] 欄位。</span><span class="sxs-lookup"><span data-stu-id="6ce1a-148">This is the field that shows in the **Display Name** in the receiving email client.</span></span>

6. <span data-ttu-id="6ce1a-149">指定的文字或 [**從**] 欄位。</span><span class="sxs-lookup"><span data-stu-id="6ce1a-149">Specify text or the **From** field.</span></span> <span data-ttu-id="6ce1a-150">這是顯示為接收電子郵件用戶端的寄件者的電子郵件地址] 欄位。</span><span class="sxs-lookup"><span data-stu-id="6ce1a-150">This is the field that shows as the email address of the sender in the receiving email client.</span></span>

   <span data-ttu-id="6ce1a-151">您可以在組織內輸入現有的電子郵件命名空間 （這樣會使實際解決接收用戶端，促進非常高信任模型中的電子郵件地址），或您可以輸入的外部電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="6ce1a-151">You can enter an existing email namespace within your organization (doing this will make the email address actually resolve in the receiving client, facilitating a very high trust model), or you can enter an external email address.</span></span> <span data-ttu-id="6ce1a-152">您指定的電子郵件地址並沒有實際存在，但仍必須以下列格式為有效的 SMTP 地址，例如`user@domainname.extension`。</span><span class="sxs-lookup"><span data-stu-id="6ce1a-152">The email address that you specify does not have to actually exist, but it does need to following the format of a valid SMTP address, such as `user@domainname.extension`.</span></span>

7. <span data-ttu-id="6ce1a-153">使用下拉式清單選取器，請選取 [反映您必須在您攻擊內的內容類型的網路釣魚登入伺服器 URL。</span><span class="sxs-lookup"><span data-stu-id="6ce1a-153">Using the drop-down selector, select a Phishing Login server URL that reflects the type of content you will have within your attack.</span></span> <span data-ttu-id="6ce1a-154">多個已設佈景主題的 Url 被提供給您從中選擇，例如文件傳遞、 技術、 薪資等。這實際上是目標的使用者上當系統要您按一下 [URL。</span><span class="sxs-lookup"><span data-stu-id="6ce1a-154">Several themed URLs are provided for you to choose from, such as document delivery, technical, payroll etc. This is effectively the URL that targeted users are asked to click.</span></span>

8. <span data-ttu-id="6ce1a-155">指定自訂的登陸頁面 URL。</span><span class="sxs-lookup"><span data-stu-id="6ce1a-155">Specify a custom landing page URL.</span></span> <span data-ttu-id="6ce1a-156">使用這將使用者重新導向至您指定的攻擊成功結尾的 URL。</span><span class="sxs-lookup"><span data-stu-id="6ce1a-156">Using this will redirect users to a URL you specify at the end of a successful attack.</span></span> <span data-ttu-id="6ce1a-157">如果您有內部認知訓練，例如，您可以指定，這裡。</span><span class="sxs-lookup"><span data-stu-id="6ce1a-157">If you have internal awareness training, for example, you can specify that here.</span></span>

9. <span data-ttu-id="6ce1a-158">指定文字的 [**主旨**] 欄位。</span><span class="sxs-lookup"><span data-stu-id="6ce1a-158">Specify text for the **Subject** field.</span></span> <span data-ttu-id="6ce1a-159">這是顯示為中接收電子郵件用戶端的**主體名稱**] 欄位。</span><span class="sxs-lookup"><span data-stu-id="6ce1a-159">This is the field that shows as the **Subject Name** in the receiving email client.</span></span>

10. <span data-ttu-id="6ce1a-160">撰寫目標會收到**電子郵件內文**。</span><span class="sxs-lookup"><span data-stu-id="6ce1a-160">Compose the **Email body** that the target will receive.</span></span>

    <span data-ttu-id="6ce1a-161">`${username}`電子郵件本文中插入的目標名稱。</span><span class="sxs-lookup"><span data-stu-id="6ce1a-161">`${username}` inserts the targets name into the Email body.</span></span>

    <span data-ttu-id="6ce1a-162">`${loginserverurl}`會插入我們想要目標使用者按一下的 URL</span><span class="sxs-lookup"><span data-stu-id="6ce1a-162">`${loginserverurl}` inserts the URL we want target users to click</span></span>

11. <span data-ttu-id="6ce1a-163">選擇 [**下一步]** ，然後**完成]** 來啟動攻擊。</span><span class="sxs-lookup"><span data-stu-id="6ce1a-163">Choose **Next,** then **Finish** to launch the attack.</span></span> <span data-ttu-id="6ce1a-164">矛網路釣魚電子郵件會傳遞至您目標收件者的信箱。</span><span class="sxs-lookup"><span data-stu-id="6ce1a-164">The spear phishing email message is delivered to your target recipients' mailboxes.</span></span>

## <a name="password-spray-attack"></a><span data-ttu-id="6ce1a-165">密碼噴灑攻擊</span><span class="sxs-lookup"><span data-stu-id="6ce1a-165">Password-spray attack</span></span>

<span data-ttu-id="6ce1a-166">壞動作項目已成功取得從租用戶的有效使用者的清單之後，通常會使用組織的密碼噴灑攻擊。</span><span class="sxs-lookup"><span data-stu-id="6ce1a-166">A password spray attack against an organization is typically used after a bad actor has successfully acquired a list of valid users from the tenant.</span></span> <span data-ttu-id="6ce1a-167">壞動作項目所知的人員使用常見密碼。</span><span class="sxs-lookup"><span data-stu-id="6ce1a-167">The bad actor knows about common passwords that people use.</span></span> <span data-ttu-id="6ce1a-168">此為廣泛使用的攻擊，來執行，且更難偵測比暴力方法便宜攻擊。</span><span class="sxs-lookup"><span data-stu-id="6ce1a-168">This is a widely used attack, as it is a cheap attack to run, and harder to detect than brute force approaches.</span></span>

<span data-ttu-id="6ce1a-169">此類攻擊著重於讓您指定要對使用者的大型目標基底常見的密碼。</span><span class="sxs-lookup"><span data-stu-id="6ce1a-169">This attack focuses on letting you specify a common password against a large target base of users.</span></span>

### <a name="to-simulate-a-password-spray-attack"></a><span data-ttu-id="6ce1a-170">若要模擬密碼噴灑攻擊</span><span class="sxs-lookup"><span data-stu-id="6ce1a-170">To simulate a password-spray attack</span></span>

1. <span data-ttu-id="6ce1a-171">在[安全性&amp;合規性中心](https://protection.office.com)，選擇 [**威脅管理** \> **攻擊模擬器**。</span><span class="sxs-lookup"><span data-stu-id="6ce1a-171">In the [Security &amp; Compliance Center](https://protection.office.com), choose **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="6ce1a-172">指定攻擊的有意義的活動名稱。</span><span class="sxs-lookup"><span data-stu-id="6ce1a-172">Specify a meaningful campaign name for the attack.</span></span>

3. <span data-ttu-id="6ce1a-173">指定目標收件者。</span><span class="sxs-lookup"><span data-stu-id="6ce1a-173">Specify the target recipients.</span></span> <span data-ttu-id="6ce1a-174">這可以是個人或組織中的群組。</span><span class="sxs-lookup"><span data-stu-id="6ce1a-174">This can be individuals or groups in your organization.</span></span> <span data-ttu-id="6ce1a-175">目標收件者必須在才能成功攻擊的順序中的 Exchange Online 信箱。</span><span class="sxs-lookup"><span data-stu-id="6ce1a-175">A targeted recipient must have an Exchange Online mailbox in order for the attack to be successful.</span></span>

4. <span data-ttu-id="6ce1a-176">指定要用於攻擊的密碼。</span><span class="sxs-lookup"><span data-stu-id="6ce1a-176">Specify a password to use for the attack.</span></span> <span data-ttu-id="6ce1a-177">例如，您可以嘗試的一個常見、 相關密碼是`Summer2019`。</span><span class="sxs-lookup"><span data-stu-id="6ce1a-177">For example, one common, relevant password you could try is `Summer2019`.</span></span> <span data-ttu-id="6ce1a-178">另一個可能是`Fall2019`，或`Password1`。</span><span class="sxs-lookup"><span data-stu-id="6ce1a-178">Another might be `Fall2019`, or `Password1`.</span></span>

5. <span data-ttu-id="6ce1a-179">選擇 [**完成**] 以啟動攻擊。</span><span class="sxs-lookup"><span data-stu-id="6ce1a-179">Choose **Finish** to launch the attack.</span></span>

## <a name="brute-force-password-attack"></a><span data-ttu-id="6ce1a-180">暴力密碼攻擊</span><span class="sxs-lookup"><span data-stu-id="6ce1a-180">Brute-force password attack</span></span>

<span data-ttu-id="6ce1a-181">壞動作項目已成功取得從租用戶的關鍵使用者的清單之後，通常會使用組織暴力密碼攻擊。</span><span class="sxs-lookup"><span data-stu-id="6ce1a-181">A brute-force password attack against an organization is typically used after a bad actor has successfully acquired a list of key users from the tenant.</span></span> <span data-ttu-id="6ce1a-182">此類攻擊著重在嘗試一組單一使用者的帳戶的密碼。</span><span class="sxs-lookup"><span data-stu-id="6ce1a-182">This attack focuses on trying a set of passwords on a single user's account.</span></span>

### <a name="to-simulate-a-brute-force-password-attack"></a><span data-ttu-id="6ce1a-183">若要模擬暴力密碼攻擊</span><span class="sxs-lookup"><span data-stu-id="6ce1a-183">To simulate a brute-force password attack</span></span>

1. <span data-ttu-id="6ce1a-184">在[安全性&amp;合規性中心](https://protection.office.com)，選擇 [**威脅管理** \> **攻擊模擬器**。</span><span class="sxs-lookup"><span data-stu-id="6ce1a-184">In the [Security &amp; Compliance Center](https://protection.office.com), choose **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="6ce1a-185">指定攻擊的有意義的活動名稱。</span><span class="sxs-lookup"><span data-stu-id="6ce1a-185">Specify a meaningful campaign name for the attack.</span></span>

3. <span data-ttu-id="6ce1a-186">指定目標收件者。</span><span class="sxs-lookup"><span data-stu-id="6ce1a-186">Specify the target recipient.</span></span> <span data-ttu-id="6ce1a-187">目標收件者必須在才能成功攻擊的順序中的 Exchange Online 信箱。</span><span class="sxs-lookup"><span data-stu-id="6ce1a-187">A targeted recipient must have an Exchange Online mailbox in order for the attack to be successful.</span></span>

4. <span data-ttu-id="6ce1a-188">指定一組用於攻擊的密碼。</span><span class="sxs-lookup"><span data-stu-id="6ce1a-188">Specify a set of passwords to use for the attack.</span></span> <span data-ttu-id="6ce1a-189">若要這麼做，您可以使用文字檔 (.txt) 的清單中的密碼。</span><span class="sxs-lookup"><span data-stu-id="6ce1a-189">To do this, you can use a text (.txt) file for your list of passwords.</span></span> <span data-ttu-id="6ce1a-190">將文字檔不可超過 10 MB 的檔案大小。</span><span class="sxs-lookup"><span data-stu-id="6ce1a-190">The text file cannot exceed 10 MB in file size.</span></span> <span data-ttu-id="6ce1a-191">使用一個密碼每一行，並確定要包含在清單中的最後一個密碼之後硬式傳回。</span><span class="sxs-lookup"><span data-stu-id="6ce1a-191">Use one password per line, and make sure to include a hard return after the last password in your list.</span></span>

5. <span data-ttu-id="6ce1a-192">選擇 [**完成**] 以啟動攻擊。</span><span class="sxs-lookup"><span data-stu-id="6ce1a-192">Choose **Finish** to launch the attack.</span></span>

## <a name="new-features-in-attack-simulator"></a><span data-ttu-id="6ce1a-193">攻擊模擬器中的新功能</span><span class="sxs-lookup"><span data-stu-id="6ce1a-193">New features in Attack Simulator</span></span>

<span data-ttu-id="6ce1a-194">新功能最近已新增至攻擊模擬器。</span><span class="sxs-lookup"><span data-stu-id="6ce1a-194">New features have recently been added to Attack Simulator.</span></span> <span data-ttu-id="6ce1a-195">這些包括：</span><span class="sxs-lookup"><span data-stu-id="6ce1a-195">These include:</span></span>

- <span data-ttu-id="6ce1a-196">進階的報告功能。</span><span class="sxs-lookup"><span data-stu-id="6ce1a-196">Advanced reporting capabilities.</span></span> <span data-ttu-id="6ce1a-197">查看資料，例如速度最快 （或速度最慢） 時間按一下 [郵件被覆寫且更多的視覺效果中的連結，以開啟攻擊模擬電子郵件訊息，最快 （或速度最慢） 時間的能力。</span><span class="sxs-lookup"><span data-stu-id="6ce1a-197">The ability to see data such as the fastest (or slowest) time to open an attack simulation email message, the fastest (or slowest) time to click a link in the message, and more visualizations.</span></span>

- <span data-ttu-id="6ce1a-198">電子郵件範本編輯器]。</span><span class="sxs-lookup"><span data-stu-id="6ce1a-198">Email template editor.</span></span> <span data-ttu-id="6ce1a-199">若要建立自訂、 可重複使用的電子郵件範本可供未來的攻擊模擬的能力。</span><span class="sxs-lookup"><span data-stu-id="6ce1a-199">The ability to create a custom, reusable email template's that you can use for future attack simulations.</span></span>

- <span data-ttu-id="6ce1a-200">CSV 匯入收件者。</span><span class="sxs-lookup"><span data-stu-id="6ce1a-200">CSV Recipient Import.</span></span> <span data-ttu-id="6ce1a-201">若要匯入您的目標收件者清單，而不是使用 address book 選擇使用.csv 檔案的能力。</span><span class="sxs-lookup"><span data-stu-id="6ce1a-201">The ability to use a .csv file to import your target recipient list instead of using the address book picker.</span></span>

<span data-ttu-id="6ce1a-202">更多的新功能即將推出的攻擊模擬器。</span><span class="sxs-lookup"><span data-stu-id="6ce1a-202">More new features are coming soon to Attack Simulator.</span></span> <span data-ttu-id="6ce1a-203">這些包括：</span><span class="sxs-lookup"><span data-stu-id="6ce1a-203">These include:</span></span>

- <span data-ttu-id="6ce1a-204">附件承載網路釣魚模擬。</span><span class="sxs-lookup"><span data-stu-id="6ce1a-204">Attachment payload phishing simulation.</span></span> <span data-ttu-id="6ce1a-205">作為附件承載網路釣魚模擬 URL 取代功能。</span><span class="sxs-lookup"><span data-stu-id="6ce1a-205">The ability to use an attachment as the payload for phishing simulation in place of a URL.</span></span>

<span data-ttu-id="6ce1a-206">請造訪[Microsoft 365 藍圖](https://www.microsoft.com/microsoft-365/roadmap)請參閱什麼是在開發中、 什麼推行和功能已啟動。</span><span class="sxs-lookup"><span data-stu-id="6ce1a-206">Visit the [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap) to see what's in development, what's rolling out, and what's already launched.</span></span>

## <a name="see-also"></a><span data-ttu-id="6ce1a-207">請參閱</span><span class="sxs-lookup"><span data-stu-id="6ce1a-207">See also</span></span>

[<span data-ttu-id="6ce1a-208">Office 365 進階威脅防護服務說明</span><span class="sxs-lookup"><span data-stu-id="6ce1a-208">Office 365 Advanced Threat Protection Service Description</span></span>](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)

[<span data-ttu-id="6ce1a-209">Office 365 進階威脅防護</span><span class="sxs-lookup"><span data-stu-id="6ce1a-209">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)
