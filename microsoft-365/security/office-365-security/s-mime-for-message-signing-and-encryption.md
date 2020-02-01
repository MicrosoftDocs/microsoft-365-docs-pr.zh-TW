---
title: 可用於 Exchange Online 中訊息簽署和加密的 S/MIME
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
search.appverid:
- MET150
ms.assetid: 887c710b-0ec6-4ff0-8065-5f05f74afef3
description: 系統管理員可以在 Exchange Online 中瞭解如何使用 S/MIME。
ms.openlocfilehash: b135a9dc2c5ad8fbf190b38f9fe10161b95a7531
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/29/2020
ms.locfileid: "41598530"
---
# <a name="smime-for-message-signing-and-encryption-in-exchange-online"></a><span data-ttu-id="70d86-103">可用於 Exchange Online 中訊息簽署和加密的 S/MIME</span><span class="sxs-lookup"><span data-stu-id="70d86-103">S/MIME for message signing and encryption in Exchange Online</span></span>

<span data-ttu-id="70d86-104">S/MIME (安全多用途網際網路郵件延伸) 是一種被廣為接受的方法 (更具體來說是通訊協定) 可用來傳送已數位簽署和加密的郵件。</span><span class="sxs-lookup"><span data-stu-id="70d86-104">S/MIME (Secure/Multipurpose Internet Mail Extensions) is a widely accepted method (or more precisely, a protocol) for sending digitally signed and encrypted messages.</span></span> <span data-ttu-id="70d86-105">S/MIME 可讓您將電子郵件加密和進行數位簽署。</span><span class="sxs-lookup"><span data-stu-id="70d86-105">S/MIME allows you to encrypt emails and digitally sign them.</span></span> <span data-ttu-id="70d86-106">對電子郵件使用 S/MIME 時，可讓收件者確定收件匣裡的郵件確實為寄件者所寄出。</span><span class="sxs-lookup"><span data-stu-id="70d86-106">When you use S/MIME with an email message, it helps the people who receive that message to be certain that what they see in their inbox is the exact message that started with the sender.</span></span> <span data-ttu-id="70d86-107">也可讓收件者確定郵件來自特定的寄件者，而不是由其他人假冒寄件者。</span><span class="sxs-lookup"><span data-stu-id="70d86-107">It will also help people who receive messages to be certain that the message came from the specific sender and not from someone pretending to be the sender.</span></span> <span data-ttu-id="70d86-108">為了達到此目的，S/MIME 提供密碼編譯的安全性服務，例如驗證、訊息完整性和來源不可否認性 (使用數位簽章)。</span><span class="sxs-lookup"><span data-stu-id="70d86-108">To do this, S/MIME provides for cryptographic security services such as authentication, message integrity, and non-repudiation of origin (using digital signatures).</span></span> <span data-ttu-id="70d86-109">另外還可加強電子郵件通訊的隱私性和資料安全性 (使用加密)。</span><span class="sxs-lookup"><span data-stu-id="70d86-109">It also helps enhance privacy and data security (using encryption) for electronic messaging.</span></span> <span data-ttu-id="70d86-110">如需 S/MIME 在電子郵件方面的歷史和架構的完整背景資訊，請參閱＜[瞭解 S/MIME](https://docs.microsoft.com/previous-versions/tn-archive/aa995740(v=exchg.65))＞。</span><span class="sxs-lookup"><span data-stu-id="70d86-110">For a more complete background about the history and architecture of S/MIME in the context of email, see [Understanding S/MIME](https://docs.microsoft.com/previous-versions/tn-archive/aa995740(v=exchg.65)).</span></span>

<span data-ttu-id="70d86-111">如果您是 Exchange Online 系統管理員，您可以針對組織中的信箱啟用 S/MIME 安全性。</span><span class="sxs-lookup"><span data-stu-id="70d86-111">As an Exchange Online admin, you can enable S/MIME-based security for the mailboxes in your organization.</span></span> <span data-ttu-id="70d86-112">請使用 Exchange Online PowerShell 並參考以下各連結主題的指引來設定 S/MIME。</span><span class="sxs-lookup"><span data-stu-id="70d86-112">Use the guidance in the topics linked here along with Exchange Online PowerShell to set up S/MIME.</span></span> <span data-ttu-id="70d86-113">若要在支援的電子郵件用戶端中使用 S/MIME，則組織中的使用者必須有針對簽署和加密用途所發出的憑證，以及發佈至內部部署 Active Directory 網域服務 (AD DS) 的資料。</span><span class="sxs-lookup"><span data-stu-id="70d86-113">To use S/MIME in supported email clients, the users in your organization must have certificates issued for signing and encryption purposes and data published to your on-premises Active Directory Domain Service (AD DS).</span></span> <span data-ttu-id="70d86-114">AD DS 必須位於您可掌控的實際位置上的電腦，而不是在遠端設備或網際網路某處的雲端式服務上。</span><span class="sxs-lookup"><span data-stu-id="70d86-114">Your AD DS must be located on computers at a physical location that you control and not at a remote facility or cloud-based service somewhere on the internet.</span></span> <span data-ttu-id="70d86-115">如需 AD DS 的詳細資訊，請參閱 [Active Directory 網域服務概觀](https://docs.microsoft.com/windows-server/identity/ad-ds/get-started/virtual-dc/active-directory-domain-services-overview)。</span><span class="sxs-lookup"><span data-stu-id="70d86-115">For more information about AD DS, see [Active Directory Domain Services Overview](https://docs.microsoft.com/windows-server/identity/ad-ds/get-started/virtual-dc/active-directory-domain-services-overview).</span></span>

## <a name="supported-scenarios-and-technical-considerations"></a><span data-ttu-id="70d86-116">支援的案例和技術考量</span><span class="sxs-lookup"><span data-stu-id="70d86-116">Supported scenarios and technical considerations</span></span>

<span data-ttu-id="70d86-117">您可以設定 S/MIME 供下列任何端點使用：</span><span class="sxs-lookup"><span data-stu-id="70d86-117">You can set up S/MIME to work with any of the following end points:</span></span>

- <span data-ttu-id="70d86-118">Outlook 2010 或更新版本</span><span class="sxs-lookup"><span data-stu-id="70d86-118">Outlook 2010 or later</span></span>

- <span data-ttu-id="70d86-119">Outlook 網頁版 (先前為 Outlook Web App)</span><span class="sxs-lookup"><span data-stu-id="70d86-119">Outlook on the web (formerly known as Outlook Web App)</span></span>

- <span data-ttu-id="70d86-120">Exchange ActiveSync (EAS)</span><span class="sxs-lookup"><span data-stu-id="70d86-120">Exchange ActiveSync (EAS)</span></span>

<span data-ttu-id="70d86-121">對每個端點設定 S/MIME 時所採取的步驟會稍有不同。</span><span class="sxs-lookup"><span data-stu-id="70d86-121">The steps that you follow to set up S/MIME with each of these end points is slightly different.</span></span> <span data-ttu-id="70d86-122">通常需要執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="70d86-122">Generally, you will need to do the following steps:</span></span>

- <span data-ttu-id="70d86-p104">安裝以 Windows 為基礎的憑證授權單位，並且設定公開金鑰基礎結構，來核發 S/MIME 憑證。也支援協力廠商憑證提供者所發出的憑證。如需詳細資訊，請參閱 [Active Directory 憑證服務概觀](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/hh831740(v=ws.11))。</span><span class="sxs-lookup"><span data-stu-id="70d86-p104">Install a Windows-based Certification Authority and set up a public key infrastructure to issue S/MIME certificates. Certificates issued by third-party certificate providers are also supported. For details, see [Active Directory Certificate Services Overview](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/hh831740(v=ws.11)).</span></span>

- <span data-ttu-id="70d86-126">在內部部署 AD DS 帳戶的 **UserSMIMECertificate** 和/或 **UserCertificate** 屬性中發佈使用者憑證。</span><span class="sxs-lookup"><span data-stu-id="70d86-126">Publish the user certificate in an on-premises AD DS account in the **UserSMIMECertificate** and/or **UserCertificate** attributes.</span></span>

- <span data-ttu-id="70d86-p105">在 Exchange Online 組織中，使用適當的 DirSync 版本，將使用者憑證從 AD DS 同步至 Azure Active Directory。這些憑證會從 Azure Active Directory 同步至 Exchange Online 目錄，並於加密寄給收件者的郵件時使用。</span><span class="sxs-lookup"><span data-stu-id="70d86-p105">For Exchange Online organizations, synchronize the user certificates from AD DS to Azure Active Directory by using an appropriate version of DirSync. These certificates will then get synchronized from Azure Active Directory to Exchange Online directory and will be used when encrypting a message to a recipient.</span></span>

- <span data-ttu-id="70d86-129">設定虛擬憑證集合以驗證 S/MIME。</span><span class="sxs-lookup"><span data-stu-id="70d86-129">Set up a virtual certificate collection in order to validate S/MIME.</span></span> <span data-ttu-id="70d86-130">Outlook 網頁版會使用此資訊來驗證電子郵件的簽章，以確保電子郵件是以信任的憑證所簽署。</span><span class="sxs-lookup"><span data-stu-id="70d86-130">This information is used by Outlook on the web when validating the signature of an email and ensuring that it was signed by a trusted certificate.</span></span>

- <span data-ttu-id="70d86-131">設定 Outlook 或 EAS 端點來使用 S/MIME。</span><span class="sxs-lookup"><span data-stu-id="70d86-131">Set up the Outlook or EAS end point to use S/MIME.</span></span>

> [!NOTE]
> <span data-ttu-id="70d86-132">您無法在 Mac、iOS、Android 或其他非 Windows 裝置上的 Outlook 網頁版中安裝 S/MIME 控制。</span><span class="sxs-lookup"><span data-stu-id="70d86-132">You can't install S/MIME control in Outlook on the web on Mac, iOS, Android, or other non-Windows devices.</span></span> <span data-ttu-id="70d86-133">如需詳細資訊，請參閱[在 Outlook 網頁版中使用 S/MIME 將郵件加密](https://support.office.com/article/878c79fc-7088-4b39-966f-14512658f480)。</span><span class="sxs-lookup"><span data-stu-id="70d86-133">For more information, see [Encrypt messages by using S/MIME in Outlook on the web](https://support.office.com/article/878c79fc-7088-4b39-966f-14512658f480).</span></span>

## <a name="setup-smime-with-outlook-on-the-web"></a><span data-ttu-id="70d86-134">使用 Outlook 網頁版設定 S/MIME</span><span class="sxs-lookup"><span data-stu-id="70d86-134">Setup S/MIME with Outlook on the web</span></span>

<span data-ttu-id="70d86-135">設定 Exchange Online 的 Outlook 網頁版來使用 S/MIME 包含下列幾個主要步驟：</span><span class="sxs-lookup"><span data-stu-id="70d86-135">Setting up S/MIME for Exchange Online with Outlook on the web involves the following key steps:</span></span>

1. [<span data-ttu-id="70d86-136">設定 Outlook 網頁版的 S/MIME 設定</span><span class="sxs-lookup"><span data-stu-id="70d86-136">Configure S/MIME settings for Outlook on the web</span></span>](configure-s-mime-settings-for-outlook-web-app.md)

2. [<span data-ttu-id="70d86-137">設定虛擬憑證集合以驗證 S/MIME</span><span class="sxs-lookup"><span data-stu-id="70d86-137">Set up virtual certificate collection to validate S/MIME</span></span>](set-up-virtual-certificate-collection-to-validate-s-mime.md)

3. [<span data-ttu-id="70d86-138">將使用者憑證同步至 Office 365 進行 S/MIME 處理</span><span class="sxs-lookup"><span data-stu-id="70d86-138">Sync user certificates to Office 365 for S/MIME</span></span>](sync-user-certificates-to-office-365-for-s-mime.md)

## <a name="related-message-encryption-technologies"></a><span data-ttu-id="70d86-139">相關郵件加密技術</span><span class="sxs-lookup"><span data-stu-id="70d86-139">Related message encryption technologies</span></span>

<span data-ttu-id="70d86-140">郵件安全性已變得越來越重要，因此系統管理員必須了解安全郵件的原則和概念。</span><span class="sxs-lookup"><span data-stu-id="70d86-140">As message security becomes more important, admins need to understand the principles and concepts of secure messaging.</span></span> <span data-ttu-id="70d86-141">由於有越來越多各式各樣的防護技術 (包括 S/MIME) 問世，所以了解這一方面的資訊再重要不過。</span><span class="sxs-lookup"><span data-stu-id="70d86-141">This understanding is especially important because of the growing variety of protection-related technologies (including S/MIME) that are available.</span></span> <span data-ttu-id="70d86-142">若要深入了解 S/MIME 及其於電子郵件上的運作，請參閱＜[瞭解 S/MIME](https://docs.microsoft.com/previous-versions/tn-archive/aa995740(v=exchg.65))＞。</span><span class="sxs-lookup"><span data-stu-id="70d86-142">To understand more about S/MIME and how it works in context of email, see [Understanding S/MIME](https://docs.microsoft.com/previous-versions/tn-archive/aa995740(v=exchg.65)).</span></span> <span data-ttu-id="70d86-143">各種加密技術可搭配運作，以為靜止和傳輸中的郵件提供保護。</span><span class="sxs-lookup"><span data-stu-id="70d86-143">A variety of encryption technologies work together to provide protection for messages at rest and in-transit.</span></span> <span data-ttu-id="70d86-144">S/MIME 可以與下列技術同時運作，但彼此並不具依存關係：</span><span class="sxs-lookup"><span data-stu-id="70d86-144">S/MIME can work simultaneously with the following technologies but is not dependent on them:</span></span>

- <span data-ttu-id="70d86-145">**傳輸層安全性 (TLS)** 會加密電子郵件伺服器之間的通道或路由，以協助防止側錄和竊聽。</span><span class="sxs-lookup"><span data-stu-id="70d86-145">**Transport Layer Security (TLS)** encrypts the tunnel or the route between email servers in order to help prevent snooping and eavesdropping.</span></span>

- <span data-ttu-id="70d86-146">**安全通訊端層 (SSL)** 會加密電子郵件用戶端與 Office 365 伺服器之間的連線。</span><span class="sxs-lookup"><span data-stu-id="70d86-146">**Secure Sockets Layer (SSL)** encrypts the connection between email clients and Office 365 servers.</span></span>

- <span data-ttu-id="70d86-147">**BitLocker** 會加密資料中心硬碟上的資料，因此如果有人未獲授權就存取，便無法讀取資料。</span><span class="sxs-lookup"><span data-stu-id="70d86-147">**BitLocker** encrypts the data on a hard drive in a datacenter so that if someone gets unauthorized access, they can't read it.</span></span>

### <a name="smime-compared-with-office-365-message-encryption"></a><span data-ttu-id="70d86-148">S/MIME 與 Office 365 郵件加密的比較</span><span class="sxs-lookup"><span data-stu-id="70d86-148">S/MIME compared with Office 365 Message Encryption</span></span>

<span data-ttu-id="70d86-149">S/MIME 需要憑證和發佈基礎結構 (常用於企業對企業及企業對消費者情況)。</span><span class="sxs-lookup"><span data-stu-id="70d86-149">S/MIME requires a certificate and publishing infrastructure that is often used in business-to-business and business-to-consumer situations.</span></span> <span data-ttu-id="70d86-150">在 S/MIME 中，由使用者控制密碼編譯金鑰，且在他們所傳送的每一封郵件上，都可選擇是否使用金鑰。</span><span class="sxs-lookup"><span data-stu-id="70d86-150">The user controls the cryptographic keys in S/MIME and can choose whether to use them for each message they send.</span></span> <span data-ttu-id="70d86-151">電子郵件程式 (例如 Outlook) 會搜尋受信任的根憑證授單位，以進行數位簽署並驗證簽章。</span><span class="sxs-lookup"><span data-stu-id="70d86-151">Email programs such as Outlook search a trusted root certificate authority location to perform digital signing and verification of the signature.</span></span> <span data-ttu-id="70d86-152">Office 365 郵件加密是系統管理員 (而不是個別使用者) 可設定的原則型加密服務，可將傳送給組織內外任何人的郵件加密。</span><span class="sxs-lookup"><span data-stu-id="70d86-152">Office 365 Message Encryption is a policy-based encryption service that can be configured by an administrator, and not an individual user, to encrypt mail sent to anyone inside or outside of the organization.</span></span> <span data-ttu-id="70d86-153">它是以 Azure 版權管理 (RMS) 為基礎的線上服務，且不依賴任何公開金鑰基礎結構。</span><span class="sxs-lookup"><span data-stu-id="70d86-153">It's an online service that's built on Azure Rights Management (RMS) and does not rely on a public key infrastructure.</span></span> <span data-ttu-id="70d86-154">Office 365 郵件加密還提供其他功能，例如以組織的品牌來自訂郵件。</span><span class="sxs-lookup"><span data-stu-id="70d86-154">Office 365 Message Encryption also provides additional capabilities, such as the capability to customize the mail with organization's brand.</span></span> <span data-ttu-id="70d86-155">如需 Office 365 郵件加密的相關資訊，請參閱 [Office 365 加密](https://docs.microsoft.com/microsoft-365/compliance/encryption)。</span><span class="sxs-lookup"><span data-stu-id="70d86-155">For more information about Office 365 Message Encryption, see [Encryption in Office 365](https://docs.microsoft.com/microsoft-365/compliance/encryption).</span></span>

## <a name="more-information"></a><span data-ttu-id="70d86-156">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="70d86-156">More information</span></span>

[<span data-ttu-id="70d86-157">Outlook 網頁版</span><span class="sxs-lookup"><span data-stu-id="70d86-157">Outlook on the web</span></span>](https://docs.microsoft.com/exchange/exchange-admin-center)

<span data-ttu-id="70d86-158">[安全郵件 (2000)](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-2000-server/cc962043(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="70d86-158">[Secure Mail (2000)](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-2000-server/cc962043(v=technet.10))</span></span>
