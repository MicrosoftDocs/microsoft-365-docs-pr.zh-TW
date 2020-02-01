---
title: 將使用者憑證同步至 Office 365 進行 S/MIME 處理
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: 12/09/2016
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 351c932e-99c1-4512-a6e8-788e90b7838f
description: 在設定正確的憑證之前，任何人都無法傳送受 S/MIME 保護的郵件。為了透過 Exchange Online 傳送加密郵件，寄件者的電子郵件程式會使用收件者的公用憑證為郵件加密。這個公用的 X.509 憑證必須發行至 Office 365。
ms.openlocfilehash: a62af3b176f29ec2bd8c97ae02178c87b7a63544
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/29/2020
ms.locfileid: "41598190"
---
# <a name="sync-user-certificates-to-office-365-for-smime"></a><span data-ttu-id="e99fd-105">將使用者憑證同步至 Office 365 進行 S/MIME 處理</span><span class="sxs-lookup"><span data-stu-id="e99fd-105">Sync user certificates to Office 365 for S/MIME</span></span>

<span data-ttu-id="e99fd-106">任何人都可以傳送受 S/MIME 保護的郵件在 Exchange Online 之前，請將適當的憑證必須設定。</span><span class="sxs-lookup"><span data-stu-id="e99fd-106">Before anyone can send S/MIME-protected messages in Exchange Online, the appropriate certificates must be set up.</span></span> <span data-ttu-id="e99fd-107">若要傳送加密的郵件，透過 Exchange Online，寄件者的電子郵件應用程式會使用收件者的公用憑證來加密郵件。</span><span class="sxs-lookup"><span data-stu-id="e99fd-107">To send encrypted messages through Exchange Online, the sender's email app uses the public certificate of the recipient to encrypt the message.</span></span> <span data-ttu-id="e99fd-108">這個公用的 X.509 憑證必須發行至 Office 365。</span><span class="sxs-lookup"><span data-stu-id="e99fd-108">This public X.509 certificate has to be published to Office 365.</span></span>

## <a name="to-sync-certificates-that-support-smime"></a><span data-ttu-id="e99fd-109">同步處理支援 S/MIME 的憑證</span><span class="sxs-lookup"><span data-stu-id="e99fd-109">To Sync certificates that support S/MIME</span></span>

<span data-ttu-id="e99fd-110">設定 S/MIME 的首要步驟，是在您的本機 Active Directory 網域服務中核發憑證並加以發行。</span><span class="sxs-lookup"><span data-stu-id="e99fd-110">Begin setting up S/MIME by issuing certificates and publishing them in your local Active Directory Domain Service.</span></span> <span data-ttu-id="e99fd-111">如需詳細資訊，請參閱 [Active Directory 憑證服務概觀](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831740(v=ws.11))。</span><span class="sxs-lookup"><span data-stu-id="e99fd-111">For more information, see [Active Directory Certificate Services Overview](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831740(v=ws.11)).</span></span>

<span data-ttu-id="e99fd-112">您的憑證發行後，使用 Azure AD Connect 工具來同步處理至 Office 365 的使用者資料從您的內部部署 Exchange 環境。</span><span class="sxs-lookup"><span data-stu-id="e99fd-112">After your certificates are published, use the Azure AD Connect tool to synchronize user data from your on-premises Exchange environment to Office 365.</span></span> <span data-ttu-id="e99fd-113">如需有關此程序的詳細資訊，請參閱[Azure AD Connect 同步處理： 了解及自訂同步處理](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-whatis)。</span><span class="sxs-lookup"><span data-stu-id="e99fd-113">For more information on this process, see [Azure AD Connect sync: Understand and customize synchronization](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-whatis).</span></span>

<span data-ttu-id="e99fd-114">以及其他目錄資料，針對 S/MIME 用途同步處理工具會同步處理每個使用者物件的**userCertificate**和**userSMIMECertificate**屬性，讓資料可用來簽署及加密郵件。</span><span class="sxs-lookup"><span data-stu-id="e99fd-114">Along with synchronizing other directory data, for S/MIME purposes, the tool will synchronize the  **userCertificate** and **userSMIMECertificate** attributes for each user object so the data can be used to sign and encrypt messages.</span></span>

## <a name="more-information"></a><span data-ttu-id="e99fd-115">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="e99fd-115">More Information</span></span>

[<span data-ttu-id="e99fd-116">可用於訊息簽署和加密的 S/MIME</span><span class="sxs-lookup"><span data-stu-id="e99fd-116">S/MIME for message signing and encryption</span></span>](s-mime-for-message-signing-and-encryption.md)

[<span data-ttu-id="e99fd-117">什麼是 Azure AD Connect？</span><span class="sxs-lookup"><span data-stu-id="e99fd-117">What is Azure AD Connect?</span></span>](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-azure-ad-connect)
