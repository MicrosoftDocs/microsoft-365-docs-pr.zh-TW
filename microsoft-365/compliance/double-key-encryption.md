---
title: 雙金鑰加密（DKE）
description: DKE 可讓您保護高度機密的資料，同時維持機碼的完整控制權。
author: kccross
ms.author: krowley
manager: laurawi
ms.date: 07/21/2020
ms.topic: conceptual
ms.service: information-protection
audience: Admin
ms.reviewer: esaggese
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.openlocfilehash: 7f54832001f80418ffb09bc45da8f32c79f3df53
ms.sourcegitcommit: 1b83b6bcacb997324bc4be355deba6daf319591d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/28/2020
ms.locfileid: "46503034"
---
# <a name="double-key-encryption-dke"></a><span data-ttu-id="98ab8-103">雙金鑰加密（DKE）</span><span class="sxs-lookup"><span data-stu-id="98ab8-103">Double Key Encryption (DKE)</span></span>

> <span data-ttu-id="98ab8-104">*適用于： Microsoft 365 公開預覽的雙金鑰加密， [microsoft 365 合規性](https://www.microsoft.com/microsoft-365/business/compliance-management)， [Azure 資訊保護](https://azure.microsoft.com/pricing/details/information-protection)*</span><span class="sxs-lookup"><span data-stu-id="98ab8-104">*Applies to: Double Key Encryption for Microsoft 365 public preview, [Microsoft 365 Compliance](https://www.microsoft.com/microsoft-365/business/compliance-management), [Azure Information Protection](https://azure.microsoft.com/pricing/details/information-protection)*</span></span>
>
> <span data-ttu-id="98ab8-105">*相關指示： [Azure 資訊保護統一標籤用戶端 For Windows](https://docs.microsoft.com/azure/information-protection/faqs.md#whats-the-difference-between-the-azure-information-protection-classic-and-unified-labeling-clients)*</span><span class="sxs-lookup"><span data-stu-id="98ab8-105">*Instructions for: [Azure Information Protection unified labeling client for Windows](https://docs.microsoft.com/azure/information-protection/faqs.md#whats-the-difference-between-the-azure-information-protection-classic-and-unified-labeling-clients)*</span></span>
>
> <span data-ttu-id="98ab8-106">*服務說明： [Microsoft 365 合規性](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)*</span><span class="sxs-lookup"><span data-stu-id="98ab8-106">*Service description for: [Microsoft 365 Compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)*</span></span>

<span data-ttu-id="98ab8-107">雙金鑰加密（DKE）搭配兩個按鍵來存取受保護的內容。</span><span class="sxs-lookup"><span data-stu-id="98ab8-107">Double Key Encryption (DKE) uses two keys together to access protected content.</span></span> <span data-ttu-id="98ab8-108">您可以在 Microsoft Azure 中儲存一個金鑰，並保留另一個金鑰。</span><span class="sxs-lookup"><span data-stu-id="98ab8-108">You store one key in Microsoft Azure, and you hold the other key.</span></span> <span data-ttu-id="98ab8-109">Azure 資訊保護統一的標籤用戶端會保護高度機密的內容，同時維持對其中一個索引鍵的完整控制權。</span><span class="sxs-lookup"><span data-stu-id="98ab8-109">The Azure Information Protection unified labeling client protects highly sensitive content while you maintain full control of one of your keys.</span></span>

<span data-ttu-id="98ab8-110">雙金鑰加密可同時支援雲端和內部部署。</span><span class="sxs-lookup"><span data-stu-id="98ab8-110">Double Key Encryption supports both cloud and on-premises deployments.</span></span> <span data-ttu-id="98ab8-111">這些部署可協助確保在任何儲存受保護的資料時，加密的資料都保持不透明。</span><span class="sxs-lookup"><span data-stu-id="98ab8-111">These deployments help to ensure that encrypted data remains opaque wherever you store the protected data.</span></span>

<span data-ttu-id="98ab8-112">如需預設的雲端型租使用者超級機碼的詳細資訊，請參閱[規劃及執行 Azure 資訊保護租使用者金鑰](https://docs.microsoft.com/azure/information-protection/plan-implement-tenant-key)。</span><span class="sxs-lookup"><span data-stu-id="98ab8-112">For more information about the default, cloud-based tenant root keys, see [Planning and implementing your Azure Information Protection tenant key](https://docs.microsoft.com/azure/information-protection/plan-implement-tenant-key).</span></span>

<!--
The following video shows how Double Key Encryption works to secure your content.

> [!VIDEO https://msit.microsoftstream.com/embed/video/f466a1ff-0400-a936-221c-f1eab45dc756]
-->

<span data-ttu-id="98ab8-113">如果您的組織有下列任何一個需求，您可以使用 DKE 來保護您的內容：</span><span class="sxs-lookup"><span data-stu-id="98ab8-113">If your organizations have any of the following requirements, you can use DKE to help secure your content:</span></span>

- <span data-ttu-id="98ab8-114">您想要確保*只有您*在所有情況下都能解密受保護的內容。</span><span class="sxs-lookup"><span data-stu-id="98ab8-114">You want to ensure that *only you* can ever decrypt protected content, under all circumstances.</span></span>
- <span data-ttu-id="98ab8-115">您不想讓 Microsoft 自行存取受保護的資料。</span><span class="sxs-lookup"><span data-stu-id="98ab8-115">You don't want Microsoft to have access to protected data on its own.</span></span>
- <span data-ttu-id="98ab8-116">您有法規需求，可在地理界限內保留金鑰。</span><span class="sxs-lookup"><span data-stu-id="98ab8-116">You have regulatory requirements to hold keys within a geographical boundary.</span></span> <span data-ttu-id="98ab8-117">您在資料中心維護所有保留用於資料加密和解密的機碼。</span><span class="sxs-lookup"><span data-stu-id="98ab8-117">All of the keys that you hold for data encryption and decryption are maintained in your data center.</span></span>

## <a name="system-and-licensing-requirements-for-dke"></a><span data-ttu-id="98ab8-118">DKE 的系統和授權需求</span><span class="sxs-lookup"><span data-stu-id="98ab8-118">System and licensing requirements for DKE</span></span>

<span data-ttu-id="98ab8-119">與 Microsoft 365 E5 和 Office 365 E5 搭配使用，適用于 Microsoft 365 的雙金鑰加密。</span><span class="sxs-lookup"><span data-stu-id="98ab8-119">Double Key Encryption for Microsoft 365 comes with Microsoft 365 E5 and Office 365 E5.</span></span> <span data-ttu-id="98ab8-120">如果您沒有 Microsoft 365 E5 授權，您可以註冊[試用版](https://aka.ms/M365E5ComplianceTrial)。</span><span class="sxs-lookup"><span data-stu-id="98ab8-120">If you don’t have a Microsoft 365 E5 license, you can sign up for a [trial](https://aka.ms/M365E5ComplianceTrial).</span></span> <span data-ttu-id="98ab8-121">如需這些授權的相關資訊，請參閱[Microsoft 365 授權指南以取得安全性 & 合規性](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。</span><span class="sxs-lookup"><span data-stu-id="98ab8-121">For more information about these licenses, see [Microsoft 365 licensing guidance for security & compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).</span></span>

<span data-ttu-id="98ab8-122">**Office 有問必答**若要使用公開預覽，您必須是 Office 預覽人員計畫的成員。</span><span class="sxs-lookup"><span data-stu-id="98ab8-122">**Office Insider** To use the public preview, you must be a member of the Office Insider program.</span></span> <span data-ttu-id="98ab8-123">若要加入 Office 有問必答，請前往 [https://insider.office.com](https://insider.office.com) 。</span><span class="sxs-lookup"><span data-stu-id="98ab8-123">To join Office Insider, go to [https://insider.office.com](https://insider.office.com).</span></span> <span data-ttu-id="98ab8-124">一旦您是成員，請為您的組織選擇適當的部署方法，以準備您的環境以部署 Office 有問必答組建。</span><span class="sxs-lookup"><span data-stu-id="98ab8-124">Once you're a member, prepare your environment to deploy Office Insider builds by choosing the right deployment method for your organization.</span></span> <span data-ttu-id="98ab8-125">如需相關指示，請參閱[部署 Office 有問必答組建的快速入門](https://insider.office.com/business/deploy)。</span><span class="sxs-lookup"><span data-stu-id="98ab8-125">For instructions, see [Getting started on deploying Office Insider builds](https://insider.office.com/business/deploy).</span></span>

<span data-ttu-id="98ab8-126">**Azure 資訊保護**。</span><span class="sxs-lookup"><span data-stu-id="98ab8-126">**Azure Information Protection**.</span></span> <span data-ttu-id="98ab8-127">DKE 與敏感度標籤搭配運作，需要 Azure 資訊保護。</span><span class="sxs-lookup"><span data-stu-id="98ab8-127">DKE works with sensitivity labels and requires Azure Information Protection.</span></span>

## <a name="supported-environments-for-storing-and-viewing-dke-protected-content"></a><span data-ttu-id="98ab8-128">支援儲存及查看 DKE 保護內容的環境</span><span class="sxs-lookup"><span data-stu-id="98ab8-128">Supported environments for storing and viewing DKE-protected content</span></span>

<span data-ttu-id="98ab8-129">**支援的應用程式**。</span><span class="sxs-lookup"><span data-stu-id="98ab8-129">**Supported applications**.</span></span> <span data-ttu-id="98ab8-130">Windows 上[的 Microsoft 365 應用程式](https://www.microsoft.com/microsoft-365/business/microsoft-365-apps-for-enterprise-product)（包括 Word、Excel 及 PowerPoint）。</span><span class="sxs-lookup"><span data-stu-id="98ab8-130">[Microsoft 365 Apps for enterprise](https://www.microsoft.com/microsoft-365/business/microsoft-365-apps-for-enterprise-product) clients on Windows, including Word, Excel, and PowerPoint.</span></span>

<span data-ttu-id="98ab8-131">**線上內容支援**。</span><span class="sxs-lookup"><span data-stu-id="98ab8-131">**Online content support**.</span></span> <span data-ttu-id="98ab8-132">支援在 Microsoft SharePoint 和商務 OneDrive 中線上儲存的檔和檔案。</span><span class="sxs-lookup"><span data-stu-id="98ab8-132">Documents and files stored online in both Microsoft SharePoint and OneDrive for Business are supported.</span></span> <span data-ttu-id="98ab8-133">您可以透過電子郵件共用加密內容，但無法在線上查看加密的檔和檔案。</span><span class="sxs-lookup"><span data-stu-id="98ab8-133">You can share encrypted content by email, but you can't view encrypted documents and files online.</span></span> <span data-ttu-id="98ab8-134">相反地，您必須使用本機電腦上的桌面應用程式來查看受保護的內容。</span><span class="sxs-lookup"><span data-stu-id="98ab8-134">Instead, you must view protected content using the desktop apps on your local computer.</span></span>

## <a name="about-this-public-preview-article"></a><span data-ttu-id="98ab8-135">關於此公開預覽文章</span><span class="sxs-lookup"><span data-stu-id="98ab8-135">About this public preview article</span></span>

<span data-ttu-id="98ab8-136">您可以透過幾種方式完成一些部署雙按鍵加密的步驟。</span><span class="sxs-lookup"><span data-stu-id="98ab8-136">There are several ways you can complete some of the steps to deploy Double Key Encryption.</span></span> <span data-ttu-id="98ab8-137">本文提供詳細指示，使系統管理員無法順利部署服務。</span><span class="sxs-lookup"><span data-stu-id="98ab8-137">This article provides detailed instructions so that less experienced admins successfully deploy the service.</span></span> <span data-ttu-id="98ab8-138">如果您很舒適，可以選擇使用您自己的方法。</span><span class="sxs-lookup"><span data-stu-id="98ab8-138">If you're comfortable doing so, you can choose to use your own methods.</span></span>

<span data-ttu-id="98ab8-139">本文包含如何在 Azure 中部署雙金鑰加密服務的逐步指示。</span><span class="sxs-lookup"><span data-stu-id="98ab8-139">This article includes step-by-step instructions on how to deploy the Double Key Encryption service to Azure.</span></span> <span data-ttu-id="98ab8-140">這種案例不是您在生產環境中的問題。</span><span class="sxs-lookup"><span data-stu-id="98ab8-140">This scenario isn't something you'd likely do in production.</span></span> <span data-ttu-id="98ab8-141">針對公開預覽，使用 Azure 是部署 DKE 的快速方法。</span><span class="sxs-lookup"><span data-stu-id="98ab8-141">For public preview, using Azure is a quick way to deploy DKE.</span></span> <span data-ttu-id="98ab8-142">部署至 Azure 可讓您立即開始使用雙金鑰加密。</span><span class="sxs-lookup"><span data-stu-id="98ab8-142">Deploying to Azure lets you get started using Double Key Encryption right away.</span></span>

<span data-ttu-id="98ab8-143">您可以在您的網路上或使用其他提供者，在本機上部署服務。</span><span class="sxs-lookup"><span data-stu-id="98ab8-143">You can deploy the service locally on your network or with another provider.</span></span> <span data-ttu-id="98ab8-144">您必須使用適合該位置的方法來發佈金鑰存放區。</span><span class="sxs-lookup"><span data-stu-id="98ab8-144">You'll need to publish the key store using methods that are appropriate for that location.</span></span>

## <a name="deploy-double-key-encryption"></a><span data-ttu-id="98ab8-145">部署雙重金鑰加密</span><span class="sxs-lookup"><span data-stu-id="98ab8-145">Deploy Double Key Encryption</span></span>

<span data-ttu-id="98ab8-146">本文和部署影片使用 Azure 作為 DKE 服務的部署目的地。</span><span class="sxs-lookup"><span data-stu-id="98ab8-146">This article and the deployment video use Azure as the deployment destination for the DKE service.</span></span> <span data-ttu-id="98ab8-147">如果您要部署至其他位置，您必須提供您自己的值。</span><span class="sxs-lookup"><span data-stu-id="98ab8-147">If you're deploying to another location, you'll need to provide your own values.</span></span>

<span data-ttu-id="98ab8-148">觀賞[雙重金鑰加密部署影片](https://youtu.be/vDWfHN_kygg)，以查看文章中概念的逐步綜述。</span><span class="sxs-lookup"><span data-stu-id="98ab8-148">Watch the [Double Key Encryption deployment video](https://youtu.be/vDWfHN_kygg) to see step-by-step overview of concepts in the article.</span></span> <span data-ttu-id="98ab8-149">影片大約需要18分鐘才能完成。</span><span class="sxs-lookup"><span data-stu-id="98ab8-149">The video takes about 18 minutes to complete.</span></span>

<span data-ttu-id="98ab8-150">您將遵循下列一般步驟為您的組織設定雙金鑰加密。</span><span class="sxs-lookup"><span data-stu-id="98ab8-150">You'll follow these general steps to set up Double Key Encryption for your organization.</span></span>

1. [<span data-ttu-id="98ab8-151">安裝軟體必要條件</span><span class="sxs-lookup"><span data-stu-id="98ab8-151">Install software prerequisites</span></span>](#install-software-prerequisites)
1. [<span data-ttu-id="98ab8-152">複製雙金鑰加密 GitHub 存放庫</span><span class="sxs-lookup"><span data-stu-id="98ab8-152">Clone the Double Key Encryption GitHub repository</span></span>](#clone-the-dke-github-repository)
1. [<span data-ttu-id="98ab8-153">修改應用程式設定</span><span class="sxs-lookup"><span data-stu-id="98ab8-153">Modify application settings</span></span>](#modify-application-settings)
1. [<span data-ttu-id="98ab8-154">產生測試機碼</span><span class="sxs-lookup"><span data-stu-id="98ab8-154">Generate test keys</span></span>](#generate-test-keys)
1. [<span data-ttu-id="98ab8-155">建立專案</span><span class="sxs-lookup"><span data-stu-id="98ab8-155">Build the project</span></span>](#build-the-project)
1. [<span data-ttu-id="98ab8-156">發佈金鑰存放區</span><span class="sxs-lookup"><span data-stu-id="98ab8-156">Publish the key store</span></span>](#publish-the-key-store)
1. [<span data-ttu-id="98ab8-157">驗證您的部署</span><span class="sxs-lookup"><span data-stu-id="98ab8-157">Validate your deployment</span></span>](#validate-your-deployment)
1. [<span data-ttu-id="98ab8-158">註冊金鑰存放區</span><span class="sxs-lookup"><span data-stu-id="98ab8-158">Register your key store</span></span>](#register-your-key-store)
1. [<span data-ttu-id="98ab8-159">建立敏感度標籤</span><span class="sxs-lookup"><span data-stu-id="98ab8-159">Create sensitivity labels</span></span>](#create-labels-using-dke)

<span data-ttu-id="98ab8-160">完成後，您可以使用 DKE 加密檔和檔案。</span><span class="sxs-lookup"><span data-stu-id="98ab8-160">When you're done, you can encrypt documents and files using DKE.</span></span> <span data-ttu-id="98ab8-161">如需詳細資訊，請參閱[將敏感度標籤套用至檔案和 Office 中的電子郵件](https://support.microsoft.com/office/2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)。</span><span class="sxs-lookup"><span data-stu-id="98ab8-161">For information, see [Apply sensitivity labels to your files and email in Office](https://support.microsoft.com/office/2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9).</span></span>

### <a name="install-software-prerequisites"></a><span data-ttu-id="98ab8-162">安裝軟體必要條件</span><span class="sxs-lookup"><span data-stu-id="98ab8-162">Install software prerequisites</span></span>

<span data-ttu-id="98ab8-163">有兩種類型的軟體必要條件可用於雙金鑰加密</span><span class="sxs-lookup"><span data-stu-id="98ab8-163">There are two types of software prerequisites for Double Key Encryption</span></span>

- [<span data-ttu-id="98ab8-164">雙金鑰加密服務必要條件</span><span class="sxs-lookup"><span data-stu-id="98ab8-164">Double Key Encryption service prerequisites</span></span>](#double-key-encryption-service-prerequisites)
- [<span data-ttu-id="98ab8-165">用戶端電腦的雙金鑰加密必要條件</span><span class="sxs-lookup"><span data-stu-id="98ab8-165">Double Key Encryption prerequisites for client computers</span></span>](#double-key-encryption-prerequisites-for-client-computers)

#### <a name="double-key-encryption-service-prerequisites"></a><span data-ttu-id="98ab8-166">雙金鑰加密服務必要條件</span><span class="sxs-lookup"><span data-stu-id="98ab8-166">Double Key Encryption service prerequisites</span></span>

<span data-ttu-id="98ab8-167">在您想要安裝 DKE 服務的電腦上安裝這些必要條件。</span><span class="sxs-lookup"><span data-stu-id="98ab8-167">Install these prerequisites on the computer where you want to install the DKE service.</span></span>

<span data-ttu-id="98ab8-168">**.Net Core 3.1 SDK**。</span><span class="sxs-lookup"><span data-stu-id="98ab8-168">**.NET Core 3.1 SDK**.</span></span> <span data-ttu-id="98ab8-169">從[下載 .Net Core 3.1](https://dotnet.microsoft.com/download/dotnet-core/3.1)下載並安裝 SDK。</span><span class="sxs-lookup"><span data-stu-id="98ab8-169">Download and install the SDK from [Download .NET Core 3.1](https://dotnet.microsoft.com/download/dotnet-core/3.1).</span></span>

<span data-ttu-id="98ab8-170">**Visual Studio 程式碼**。</span><span class="sxs-lookup"><span data-stu-id="98ab8-170">**Visual Studio Code**.</span></span> <span data-ttu-id="98ab8-171">從下載 Visual Studio 程式碼 [https://code.visualstudio.com/](https://code.visualstudio.com) 。</span><span class="sxs-lookup"><span data-stu-id="98ab8-171">Download Visual Studio Code from [https://code.visualstudio.com/](https://code.visualstudio.com).</span></span> <span data-ttu-id="98ab8-172">安裝之後，請執行 Visual Studio 程式碼並選取 [ **View** \> **extension**]。</span><span class="sxs-lookup"><span data-stu-id="98ab8-172">Once installed, run Visual Studio Code and select **View** \> **Extensions**.</span></span> <span data-ttu-id="98ab8-173">安裝這些分機號碼。</span><span class="sxs-lookup"><span data-stu-id="98ab8-173">Install these extensions.</span></span>

- <span data-ttu-id="98ab8-174">Visual Studio 程式碼的 c #</span><span class="sxs-lookup"><span data-stu-id="98ab8-174">C# for Visual Studio Code</span></span>

- <span data-ttu-id="98ab8-175">NuGet 套件管理員</span><span class="sxs-lookup"><span data-stu-id="98ab8-175">NuGet Package Manager</span></span>

<span data-ttu-id="98ab8-176">**Microsoft Office 有問必答**。</span><span class="sxs-lookup"><span data-stu-id="98ab8-176">**Microsoft Office Insider**.</span></span> <span data-ttu-id="98ab8-177">設定至少一個[部署方法](https://insider.office.com/business/deploy)。</span><span class="sxs-lookup"><span data-stu-id="98ab8-177">Set up at least one [deployment method](https://insider.office.com/business/deploy).</span></span>

<span data-ttu-id="98ab8-178">**Git 資源**。</span><span class="sxs-lookup"><span data-stu-id="98ab8-178">**Git resources**.</span></span> <span data-ttu-id="98ab8-179">下載並安裝下列其中一個。</span><span class="sxs-lookup"><span data-stu-id="98ab8-179">Download and install one of the following.</span></span>

- [<span data-ttu-id="98ab8-180">Git</span><span class="sxs-lookup"><span data-stu-id="98ab8-180">Git</span></span>](https://git-scm.com/downloads)

- [<span data-ttu-id="98ab8-181">GitHub 桌面</span><span class="sxs-lookup"><span data-stu-id="98ab8-181">GitHub Desktop</span></span>](https://desktop.github.com/)

- [<span data-ttu-id="98ab8-182">GitHub 企業版</span><span class="sxs-lookup"><span data-stu-id="98ab8-182">GitHub Enterprise</span></span>](https://github.com/enterprise)

<span data-ttu-id="98ab8-183">**OpenSSL**您必須安裝[OpenSSL](https://slproweb.com/products/Win32OpenSSL.html) ，才可在部署 DKE 之後[產生測試機碼](#generate-test-keys)。</span><span class="sxs-lookup"><span data-stu-id="98ab8-183">**OpenSSL** You must have [OpenSSL](https://slproweb.com/products/Win32OpenSSL.html) installed to [generate test keys](#generate-test-keys) after you deploy DKE.</span></span> <span data-ttu-id="98ab8-184">請確認您已從環境變數路徑正確呼叫它。</span><span class="sxs-lookup"><span data-stu-id="98ab8-184">Make sure you're invoking it correctly from your environment variables path.</span></span> <span data-ttu-id="98ab8-185">例如，如需詳細資訊，請參閱「將安裝目錄新增至路徑」 https://www.osradar.com/install-openssl-windows/ 。</span><span class="sxs-lookup"><span data-stu-id="98ab8-185">For example, see "Add the installation directory to PATH" at https://www.osradar.com/install-openssl-windows/ for details.</span></span>

#### <a name="double-key-encryption-prerequisites-for-client-computers"></a><span data-ttu-id="98ab8-186">用戶端電腦的雙金鑰加密必要條件</span><span class="sxs-lookup"><span data-stu-id="98ab8-186">Double Key Encryption prerequisites for client computers</span></span>

<span data-ttu-id="98ab8-187">在您要保護和使用受保護檔的每一部用戶端電腦上安裝這些必要條件。</span><span class="sxs-lookup"><span data-stu-id="98ab8-187">Install these prerequisites on each client computer where you want to protect and consume protected documents.</span></span>

<span data-ttu-id="98ab8-188">**Microsoft Office**版本12711或更新版本。</span><span class="sxs-lookup"><span data-stu-id="98ab8-188">**Microsoft Office** version \*.12711 or later.</span></span>

<span data-ttu-id="98ab8-189">**Azure 資訊保護統一標籤用戶端**版本2.7.93.0 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="98ab8-189">**Azure Information Protection Unified Labeling Client** versions 2.7.93.0 or later.</span></span> <span data-ttu-id="98ab8-190">從[Microsoft](https://www.microsoft.com/download/details.aspx?id=53018)下載及安裝統一的標記用戶端。</span><span class="sxs-lookup"><span data-stu-id="98ab8-190">Download and install the Unified Labeling client from [Microsoft](https://www.microsoft.com/download/details.aspx?id=53018).</span></span>

### <a name="clone-the-dke-github-repository"></a><span data-ttu-id="98ab8-191">複製 DKE GitHub 存放庫</span><span class="sxs-lookup"><span data-stu-id="98ab8-191">Clone the DKE GitHub repository</span></span>

<span data-ttu-id="98ab8-192">Microsoft 會在 GitHub 存放庫中提供 DKE 來源檔案。</span><span class="sxs-lookup"><span data-stu-id="98ab8-192">Microsoft supplies the DKE source files in a GitHub repository.</span></span> <span data-ttu-id="98ab8-193">您可以複製存放庫，以在本機為組織使用建立專案。</span><span class="sxs-lookup"><span data-stu-id="98ab8-193">You clone the repository to build the project locally for your organization's use.</span></span> <span data-ttu-id="98ab8-194">DKE GitHub 存放庫位於 [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService) 。</span><span class="sxs-lookup"><span data-stu-id="98ab8-194">The DKE GitHub repository is located at [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService).</span></span>

<span data-ttu-id="98ab8-195">下列指示適用于未經驗的 git 或 Visual Studio 程式碼使用者：</span><span class="sxs-lookup"><span data-stu-id="98ab8-195">The following instructions are intended for inexperienced git or Visual Studio Code users:</span></span>

1. <span data-ttu-id="98ab8-196">在您的瀏覽器中，移至：[https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService)</span><span class="sxs-lookup"><span data-stu-id="98ab8-196">In your browser, go to: [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService)</span></span>

1. <span data-ttu-id="98ab8-197">在螢幕右側，選取 [程式**代碼**]。</span><span class="sxs-lookup"><span data-stu-id="98ab8-197">Towards the right side of the screen, select **Code**.</span></span> <span data-ttu-id="98ab8-198">您的 UI 版本可能會顯示 [**複製] 或 [下載**] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="98ab8-198">Your version of the UI might show a **Clone or download** button.</span></span> <span data-ttu-id="98ab8-199">然後，在出現的下拉式清單中，選取複製圖示，將 URL 複製到您的剪貼簿。</span><span class="sxs-lookup"><span data-stu-id="98ab8-199">Then, in the dropdown that appears, select the copy icon to copy the URL to your clipboard.</span></span>

    <span data-ttu-id="98ab8-200">例如：</span><span class="sxs-lookup"><span data-stu-id="98ab8-200">For example:</span></span>

    :::image type="content" source="../media/dke-clone.png" alt-text="從 GitHub 複製 Double 金鑰加密服務存放庫":::

3. <span data-ttu-id="98ab8-202">在 Visual Studio 程式碼中，選取 [ **View** \> **Command 調板**]，然後選取 [ **Git：複本**]。</span><span class="sxs-lookup"><span data-stu-id="98ab8-202">In Visual Studio Code, select **View** \> **Command Palette** and select **Git: Clone**.</span></span> <span data-ttu-id="98ab8-203">若要跳到清單中的選項，請開始輸入 `git: clone` 以篩選項目，然後從下拉式清單中選取。</span><span class="sxs-lookup"><span data-stu-id="98ab8-203">To jump to the option in the list, start typing `git: clone` to filter the entries and then select it from the drop-down.</span></span> <span data-ttu-id="98ab8-204">例如：</span><span class="sxs-lookup"><span data-stu-id="98ab8-204">For example:</span></span>

    :::image type="content" source="../media/dke-vscode-clone.png" alt-text="Visual Studio 程式碼 GIT：仿製選項":::

4. <span data-ttu-id="98ab8-206">在文字方塊中，粘貼您從 Git 複製的 URL，並**從 GitHub**選取 [複製]。</span><span class="sxs-lookup"><span data-stu-id="98ab8-206">In the text box, paste the URL that you copied from Git and select **Clone from GitHub**.</span></span>

5. <span data-ttu-id="98ab8-207">在出現的 [**選取資料夾**] 對話方塊中，流覽至儲存存放庫的位置並加以選取。</span><span class="sxs-lookup"><span data-stu-id="98ab8-207">In the **Select Folder** dialog that appears, browse to and select a location to store the repository.</span></span> <span data-ttu-id="98ab8-208">在提示中，選取 [**開啟**]。</span><span class="sxs-lookup"><span data-stu-id="98ab8-208">At the prompt, select **Open**.</span></span>

    <span data-ttu-id="98ab8-209">會在 Visual Studio 程式碼中開啟存放庫，並在左下方顯示目前的 Git 分支。</span><span class="sxs-lookup"><span data-stu-id="98ab8-209">The repository is opened in Visual Studio Code, and displays the current Git branch at the bottom left.</span></span> <span data-ttu-id="98ab8-210">分支應為**master**。</span><span class="sxs-lookup"><span data-stu-id="98ab8-210">The branch should be **master**.</span></span>

    <span data-ttu-id="98ab8-211">例如：</span><span class="sxs-lookup"><span data-stu-id="98ab8-211">For example:</span></span>

    :::image type="content" source="../media/dke-vscode-master.png" alt-text="Visual Studio 程式碼主分支":::

6. <span data-ttu-id="98ab8-213">選取 [word**主**圖形]，然後選取分支清單中的 [ **public_preview** ]。</span><span class="sxs-lookup"><span data-stu-id="98ab8-213">Select the word **master,** and then select **public_preview** from the list of branches.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="98ab8-214">選取 [public_preview] 分支可確保您具有正確的檔案來建立專案。</span><span class="sxs-lookup"><span data-stu-id="98ab8-214">Selecting the public_preview branch ensures that you have the correct files to build the project.</span></span> <span data-ttu-id="98ab8-215">如果您未選擇正確的分支，您的部署將會失敗。</span><span class="sxs-lookup"><span data-stu-id="98ab8-215">If you do not choose the correct branch your deployment will fail.</span></span>

<span data-ttu-id="98ab8-216">您現在已設定本機的 DKE 來源存放庫。</span><span class="sxs-lookup"><span data-stu-id="98ab8-216">You now have your DKE source repository set up locally.</span></span> <span data-ttu-id="98ab8-217">接下來，修改組織的[應用程式設定](#modify-application-settings)。</span><span class="sxs-lookup"><span data-stu-id="98ab8-217">Next, [modify application settings](#modify-application-settings) for your organization.</span></span>

### <a name="modify-application-settings"></a><span data-ttu-id="98ab8-218">修改應用程式設定</span><span class="sxs-lookup"><span data-stu-id="98ab8-218">Modify application settings</span></span>

<span data-ttu-id="98ab8-219">若要部署 DKE 服務，您必須修改下列類型的應用程式設定：</span><span class="sxs-lookup"><span data-stu-id="98ab8-219">To deploy the DKE service, you must modify the following types of application settings:</span></span>

- [<span data-ttu-id="98ab8-220">主要存取設定</span><span class="sxs-lookup"><span data-stu-id="98ab8-220">Key access settings</span></span>](#key-access-settings)
- [<span data-ttu-id="98ab8-221">租使用者和主要設定</span><span class="sxs-lookup"><span data-stu-id="98ab8-221">Tenant and key settings</span></span>](#tenant-and-key-settings)

<span data-ttu-id="98ab8-222">您可以在 [檔案] 中的 [appsettings.js修改應用程式設定。</span><span class="sxs-lookup"><span data-stu-id="98ab8-222">You modify application settings in the appsettings.json file.</span></span> <span data-ttu-id="98ab8-223">此檔案位於您在本機上複製的 DoubleKeyEncryptionService 存放庫中 DoubleKeyEncryptionService\src\customer-key-store。</span><span class="sxs-lookup"><span data-stu-id="98ab8-223">This file is located in the DoubleKeyEncryptionService repo you cloned locally under DoubleKeyEncryptionService\src\customer-key-store.</span></span> <span data-ttu-id="98ab8-224">例如，在 Visual Studio 程式碼中，您可以流覽至檔案，如下圖所示。</span><span class="sxs-lookup"><span data-stu-id="98ab8-224">For example, in Visual Studio Code, you can browse to the file as shown in the following picture.</span></span>

:::image type="content" source="../media/dke-appsettingsjson.png" alt-text="在 DKE 的檔案中尋找 appsettings.js。":::

#### <a name="key-access-settings"></a><span data-ttu-id="98ab8-226">主要存取設定</span><span class="sxs-lookup"><span data-stu-id="98ab8-226">Key access settings</span></span>

<span data-ttu-id="98ab8-227">選擇是否要使用電子郵件或角色授權。</span><span class="sxs-lookup"><span data-stu-id="98ab8-227">Choose whether to use email or role authorization.</span></span> <span data-ttu-id="98ab8-228">DKE 一次只支援其中一種驗證方法。</span><span class="sxs-lookup"><span data-stu-id="98ab8-228">DKE supports only one of these authentication methods at a time.</span></span>

- <span data-ttu-id="98ab8-229">**電子郵件授權**。</span><span class="sxs-lookup"><span data-stu-id="98ab8-229">**Email authorization**.</span></span> <span data-ttu-id="98ab8-230">可讓您的組織僅根據電子郵件地址來授權存取機碼。</span><span class="sxs-lookup"><span data-stu-id="98ab8-230">Allows your organization to authorize access to keys based on email addresses only.</span></span>

- <span data-ttu-id="98ab8-231">**角色授權**。</span><span class="sxs-lookup"><span data-stu-id="98ab8-231">**Role authorization**.</span></span> <span data-ttu-id="98ab8-232">可讓您的組織授權以 Active Directory 群組為基礎的金鑰存取權，且要求 web 服務可以查詢 LDAP。</span><span class="sxs-lookup"><span data-stu-id="98ab8-232">Allows your organization to authorize access to keys based on Active Directory groups, and requires that the web service can query LDAP.</span></span>

<span data-ttu-id="98ab8-233">**使用電子郵件授權設定 DKE 的主要存取設定**</span><span class="sxs-lookup"><span data-stu-id="98ab8-233">**To set key access settings for DKE using email authorization**</span></span>

1. <span data-ttu-id="98ab8-234">開啟檔案**上的appsettings.js** ，並找到 `AuthorizedEmailAddress` 設定。</span><span class="sxs-lookup"><span data-stu-id="98ab8-234">Open the **appsettings.json** file and locate the `AuthorizedEmailAddress` setting.</span></span>

2. <span data-ttu-id="98ab8-235">新增您要授權的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="98ab8-235">Add the email address or addresses that you want to authorize.</span></span> <span data-ttu-id="98ab8-236">使用雙引號和逗號來分隔多個電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="98ab8-236">Separate multiple email addresses with double quotes and commas.</span></span> <span data-ttu-id="98ab8-237">例如：</span><span class="sxs-lookup"><span data-stu-id="98ab8-237">For example:</span></span>

   ```json
   "AuthorizedEmailAddress": ["email1@company.com", "email2@company.com ", "email3@company.com"]
   ```

3. <span data-ttu-id="98ab8-238">找到 `LDAPPath` 設定，然後 `If role authorization is used then this is the LDAP path` 在雙引號之間移除文字。</span><span class="sxs-lookup"><span data-stu-id="98ab8-238">Locate the `LDAPPath` setting and remove the text `If role authorization is used then this is the LDAP path` between the double quotes.</span></span> <span data-ttu-id="98ab8-239">將雙引號保留在原處。</span><span class="sxs-lookup"><span data-stu-id="98ab8-239">Leave the double quotes in place.</span></span> <span data-ttu-id="98ab8-240">當您完成時，此設定應該如下所示。</span><span class="sxs-lookup"><span data-stu-id="98ab8-240">When you're finished, the setting should look like this.</span></span>

   ```json
   "LDAPPath": ""
   ```

4. <span data-ttu-id="98ab8-241">找到 `AuthorizedRoles` 設定，並刪除整行。</span><span class="sxs-lookup"><span data-stu-id="98ab8-241">Locate the `AuthorizedRoles` setting and delete the entire line.</span></span>

<span data-ttu-id="98ab8-242">此影像顯示檔的**appsettings.js**的電子郵件授權格式設定正確。</span><span class="sxs-lookup"><span data-stu-id="98ab8-242">This image shows the **appsettings.json** file correctly formatted for email authorization.</span></span>

   :::image type="content" source="../media/dke-email-accesssetting.png" alt-text="檔上顯示電子郵件授權方法的 appsettings.js":::

<span data-ttu-id="98ab8-244">**使用角色授權設定 DKE 的主要存取設定**</span><span class="sxs-lookup"><span data-stu-id="98ab8-244">**To set key access settings for DKE using role authorization**</span></span>

1. <span data-ttu-id="98ab8-245">開啟檔案**上的appsettings.js** ，並找到 `AuthorizedRoles` 設定。</span><span class="sxs-lookup"><span data-stu-id="98ab8-245">Open the **appsettings.json** file and locate the `AuthorizedRoles` setting.</span></span>

2. <span data-ttu-id="98ab8-246">新增您要授權的 Active Directory 群組名稱。</span><span class="sxs-lookup"><span data-stu-id="98ab8-246">Add the Active Directory group names you want to authorize.</span></span> <span data-ttu-id="98ab8-247">使用雙引號和逗號來分隔多個組名。</span><span class="sxs-lookup"><span data-stu-id="98ab8-247">Separate multiple group names with double quotes and commas.</span></span> <span data-ttu-id="98ab8-248">例如：</span><span class="sxs-lookup"><span data-stu-id="98ab8-248">For example:</span></span>

   ```json
   "AuthorizedRoles": ["group1", "group2", "group3"]
   ```

3. <span data-ttu-id="98ab8-249">找到 `LDAPPath` 設定並新增 Active Directory 網域。</span><span class="sxs-lookup"><span data-stu-id="98ab8-249">Locate the `LDAPPath` setting and add the Active Directory domain.</span></span> <span data-ttu-id="98ab8-250">例如：</span><span class="sxs-lookup"><span data-stu-id="98ab8-250">For example:</span></span>

   ```json
   "LDAPPath": "contoso.com"
   ```

4. <span data-ttu-id="98ab8-251">找到 `AuthorizedEmailAddress` 設定，並刪除整行。</span><span class="sxs-lookup"><span data-stu-id="98ab8-251">Locate the `AuthorizedEmailAddress` setting and delete the entire line.</span></span>

<span data-ttu-id="98ab8-252">此影像顯示針對角色授權，正確設定檔案格式的**appsettings.js** 。</span><span class="sxs-lookup"><span data-stu-id="98ab8-252">This image shows the **appsettings.json** file correctly formatted for role authorization.</span></span>

   :::image type="content" source="../media/dke-role-accesssetting.png" alt-text="檔顯示角色授權方法的appsettings.js":::

#### <a name="tenant-and-key-settings"></a><span data-ttu-id="98ab8-254">租使用者和主要設定</span><span class="sxs-lookup"><span data-stu-id="98ab8-254">Tenant and key settings</span></span>

<span data-ttu-id="98ab8-255">DKE 租使用者和 key settings 位於檔案中的**appsettings.js** 。</span><span class="sxs-lookup"><span data-stu-id="98ab8-255">DKE tenant and key settings are located in the **appsettings.json** file.</span></span>

<span data-ttu-id="98ab8-256">**設定 DKE 的承租人和主要設定**</span><span class="sxs-lookup"><span data-stu-id="98ab8-256">**To configure tenant and key settings for DKE**</span></span>

1. <span data-ttu-id="98ab8-257">開啟檔**上的appsettings.js** 。</span><span class="sxs-lookup"><span data-stu-id="98ab8-257">Open the **appsettings.json** file.</span></span>

2. <span data-ttu-id="98ab8-258">找到 `ValidIssuers` 設定，並 `<tenantid>` 將其取代為您的租使用者識別碼。</span><span class="sxs-lookup"><span data-stu-id="98ab8-258">Locate the `ValidIssuers` setting and replace `<tenantid>` with your tenant ID.</span></span> <span data-ttu-id="98ab8-259">您可以移至 Azure 入口網站並查看[租使用者屬性](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties)，以找出您的租使用者識別碼。</span><span class="sxs-lookup"><span data-stu-id="98ab8-259">You can locate your tenant ID by going to the Azure portal and viewing the [tenant properties](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span> <span data-ttu-id="98ab8-260">例如：</span><span class="sxs-lookup"><span data-stu-id="98ab8-260">For example:</span></span>

   ```json
   "ValidIssuers": [
     "https://sts.windows.net/9c99431e-b513-44be-a7d9-e7b500002d4b/"
   ]
   ```

<span data-ttu-id="98ab8-261">找到 `JwtAudience` 。</span><span class="sxs-lookup"><span data-stu-id="98ab8-261">Locate the `JwtAudience`.</span></span> <span data-ttu-id="98ab8-262">取代 `<yourhostname>` DKE 服務將執行的機器的主機名稱。</span><span class="sxs-lookup"><span data-stu-id="98ab8-262">Replace `<yourhostname>` with the hostname of the machine where the DKE service will run.</span></span> <span data-ttu-id="98ab8-263">例如：</span><span class="sxs-lookup"><span data-stu-id="98ab8-263">For example:</span></span>



  > [!IMPORTANT]
  > <span data-ttu-id="98ab8-264">的值 `JwtAudience` 必須與您的主機名稱稱*完全*相符。</span><span class="sxs-lookup"><span data-stu-id="98ab8-264">The value for `JwtAudience` must match the name of your host *exactly*.</span></span> <span data-ttu-id="98ab8-265">您可以在調試時使用**localhost： 5001** 。</span><span class="sxs-lookup"><span data-stu-id="98ab8-265">You may use **localhost:5001** while debugging.</span></span> <span data-ttu-id="98ab8-266">不過，當您完成調試時，請務必將此值更新為伺服器的主機名稱。</span><span class="sxs-lookup"><span data-stu-id="98ab8-266">However, When you're done debugging, make sure to update this value to the server's hostname.</span></span>

- <span data-ttu-id="98ab8-267">`TestKeys:Name`.</span><span class="sxs-lookup"><span data-stu-id="98ab8-267">`TestKeys:Name`.</span></span> <span data-ttu-id="98ab8-268">輸入機碼的名稱。</span><span class="sxs-lookup"><span data-stu-id="98ab8-268">Enter a name for your key.</span></span> <span data-ttu-id="98ab8-269">例如：`TestKey1`</span><span class="sxs-lookup"><span data-stu-id="98ab8-269">For example: `TestKey1`</span></span>
- <span data-ttu-id="98ab8-270">`TestKeys:Id`.</span><span class="sxs-lookup"><span data-stu-id="98ab8-270">`TestKeys:Id`.</span></span> <span data-ttu-id="98ab8-271">建立 GUID 並輸入為 `TestKeys:ID` 值。</span><span class="sxs-lookup"><span data-stu-id="98ab8-271">Create a GUID and enter it as the `TestKeys:ID` value.</span></span> <span data-ttu-id="98ab8-272">例如，`DCE1CC21-FF9B-4424-8FF4-9914BD19A1BE`。</span><span class="sxs-lookup"><span data-stu-id="98ab8-272">For example, `DCE1CC21-FF9B-4424-8FF4-9914BD19A1BE`.</span></span> <span data-ttu-id="98ab8-273">您可以使用像是[線上 GUID 發生器](https://guidgenerator.com/)的網站，以隨機產生 GUID。</span><span class="sxs-lookup"><span data-stu-id="98ab8-273">You can use a site like [Online GUID Generator](https://guidgenerator.com/) to randomly generate a GUID.</span></span>

<span data-ttu-id="98ab8-274">這個圖像會顯示**appsettings.js**中的承租人和機碼設定的正確格式。</span><span class="sxs-lookup"><span data-stu-id="98ab8-274">This image shows the correct format for tenant and keys settings in **appsettings.json**.</span></span> <span data-ttu-id="98ab8-275">`LDAPPath`設定角色授權。</span><span class="sxs-lookup"><span data-stu-id="98ab8-275">`LDAPPath` is configured for role authorization.</span></span>

:::image type="content" source="../media/dke-appsettingsjson-tenantkeysettings.png" alt-text="在檔案 appsettings.js中顯示 DKE 的正確租使用者和重要設定。":::

### <a name="generate-test-keys"></a><span data-ttu-id="98ab8-277">產生測試機碼</span><span class="sxs-lookup"><span data-stu-id="98ab8-277">Generate test keys</span></span>

<span data-ttu-id="98ab8-278">定義應用程式設定之後，即可開始產生公用和私人測試金鑰。</span><span class="sxs-lookup"><span data-stu-id="98ab8-278">Once you have your application settings defined, you're ready to generate public and private test keys.</span></span>

<span data-ttu-id="98ab8-279">若要產生機碼：</span><span class="sxs-lookup"><span data-stu-id="98ab8-279">To generate keys:</span></span>

1. <span data-ttu-id="98ab8-280">在 Windows [開始] 功能表中，執行 OpenSSL 命令提示字元。</span><span class="sxs-lookup"><span data-stu-id="98ab8-280">From the Windows Start menu, run the OpenSSL Command Prompt.</span></span>

1. <span data-ttu-id="98ab8-281">變更至您要儲存測試機碼的資料夾。</span><span class="sxs-lookup"><span data-stu-id="98ab8-281">Change to the folder where you want to save the test keys.</span></span> <span data-ttu-id="98ab8-282">您完成此工作中的步驟所建立的檔案會儲存在相同的資料夾中。</span><span class="sxs-lookup"><span data-stu-id="98ab8-282">The files you create by completing the steps in this task are stored in the same folder.</span></span>

1. <span data-ttu-id="98ab8-283">產生新的測試機碼。</span><span class="sxs-lookup"><span data-stu-id="98ab8-283">Generate the new test key.</span></span>

   ```dos
   openssl req -x509 -newkey rsa:2048 -keyout key.pem -out cert.pem -days 365
   ```

2. <span data-ttu-id="98ab8-284">產生私密金鑰。</span><span class="sxs-lookup"><span data-stu-id="98ab8-284">Generate the private key.</span></span>

   ```dos
   openssl rsa -in key.pem -out privkeynopass.pem
   ```

1. <span data-ttu-id="98ab8-285">產生公開金鑰。</span><span class="sxs-lookup"><span data-stu-id="98ab8-285">Generate the public key.</span></span>

   ```dos
   openssl rsa -in key.pem -pubout > pubkeyonly.pem
   ```

1. <span data-ttu-id="98ab8-286">在文字編輯器中，開啟**pubkeyonly**。</span><span class="sxs-lookup"><span data-stu-id="98ab8-286">In a text editor, open **pubkeyonly.pem**.</span></span> <span data-ttu-id="98ab8-287">將**pubkeyonly**檔案中的所有內容（第一行及最後一列除外）複製到檔案中 `PublicPem` **appsettings.js**區段。</span><span class="sxs-lookup"><span data-stu-id="98ab8-287">Copy all of the content in the **pubkeyonly.pem** file, except the first and last lines, into the `PublicPem` section of the **appsettings.json** file.</span></span>

1. <span data-ttu-id="98ab8-288">在文字編輯器中，開啟**privkeynopass**。</span><span class="sxs-lookup"><span data-stu-id="98ab8-288">In a text editor, open **privkeynopass.pem**.</span></span> <span data-ttu-id="98ab8-289">將**privkeynopass**檔案中的所有內容（第一行及最後一列除外）複製到檔案中 `PrivatePem` **appsettings.js**區段。</span><span class="sxs-lookup"><span data-stu-id="98ab8-289">Copy all of the content in the **privkeynopass.pem** file, except the first and last lines, into the `PrivatePem` section of the **appsettings.json** file.</span></span>

1. <span data-ttu-id="98ab8-290">移除及區段中的所有空格和分行符號 `PublicPem` `PrivatePem` 。</span><span class="sxs-lookup"><span data-stu-id="98ab8-290">Remove all blank spaces and newlines in both the `PublicPem` and `PrivatePem` sections.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="98ab8-291">當您複製此內容時，請勿刪除任何 PEM 資料。</span><span class="sxs-lookup"><span data-stu-id="98ab8-291">When you copy this content, do not delete any of the PEM data.</span></span>

1. <span data-ttu-id="98ab8-292">在 Visual Studio 程式碼中，流覽至**Startup.cs**檔案。</span><span class="sxs-lookup"><span data-stu-id="98ab8-292">In Visual Studio Code, browse to the **Startup.cs** file.</span></span> <span data-ttu-id="98ab8-293">此檔案位於您在本機上複製的 DoubleKeyEncryptionService 存放庫中 DoubleKeyEncryptionService\src\customer-key-store\。</span><span class="sxs-lookup"><span data-stu-id="98ab8-293">This file is located in the DoubleKeyEncryptionService repo you cloned locally under DoubleKeyEncryptionService\src\customer-key-store\.</span></span>

2. <span data-ttu-id="98ab8-294">找到下列行：</span><span class="sxs-lookup"><span data-stu-id="98ab8-294">Locate the following lines:</span></span>

   ```c#
        #if USE_TEST_KEYS
        #error !!!!!!!!!!!!!!!!!!!!!! Use of test keys is only supported for testing,
        DO NOT USE  FOR PRODUCTION !!!!!!!!!!!!!!!!!!!!!!!!!!!!!
        services.AddSingleton<ippw.IKeyStore, ippw.TestKeyStore>();
        #endif
   ```

3. <span data-ttu-id="98ab8-295">請使用下列文字取代這些行：</span><span class="sxs-lookup"><span data-stu-id="98ab8-295">Replace these lines with the following text:</span></span>

   ```csharp
   services.AddSingleton<ippw.IKeyStore, ippw.TestKeyStore>();
   ```

   <span data-ttu-id="98ab8-296">結束結果應如下所示。</span><span class="sxs-lookup"><span data-stu-id="98ab8-296">The end results should look similar to the following.</span></span>

   :::image type="content" source="../media/dke-startupcs-usetestkeys.png" alt-text="公開預覽的 startup.cs 檔案":::

<span data-ttu-id="98ab8-298">現在您已經準備好[建立 DKE 專案](#build-the-project)。</span><span class="sxs-lookup"><span data-stu-id="98ab8-298">Now you're ready to [build your DKE project](#build-the-project).</span></span>

### <a name="build-the-project"></a><span data-ttu-id="98ab8-299">建立專案</span><span class="sxs-lookup"><span data-stu-id="98ab8-299">Build the project</span></span>

<span data-ttu-id="98ab8-300">使用下列指示在本機建立 DKE 專案：</span><span class="sxs-lookup"><span data-stu-id="98ab8-300">Use the following instructions to build the DKE project locally:</span></span>

1. <span data-ttu-id="98ab8-301">在 Visual Studio 程式碼的 DKE 服務存放庫中，選取 [ **View** \> **Command 調板**]，然後在提示中輸入**build** 。</span><span class="sxs-lookup"><span data-stu-id="98ab8-301">In Visual Studio Code, in the DKE service repository, select **View** \> **Command Palette** and then type **build** at the prompt.</span></span>

1. <span data-ttu-id="98ab8-302">從清單中選擇 [**任務：執行建立任務**]。</span><span class="sxs-lookup"><span data-stu-id="98ab8-302">From the list, choose **Tasks: Run build task**.</span></span>

   <span data-ttu-id="98ab8-303">如果找不到任何建立工作，請選取 [**設定建立**工作] 並為 .net core 建立一個工作，如下所示。</span><span class="sxs-lookup"><span data-stu-id="98ab8-303">If there are no build tasks found, select **Configure Build Task** and create one for .NET core as follows.</span></span>

   :::image type="content" source="../media/dke-configurebuildtask.png" alt-text="設定 .NET 的遺失組建工作":::

   1. <span data-ttu-id="98ab8-305">選擇 [**從範本建立 tasks.js**]。</span><span class="sxs-lookup"><span data-stu-id="98ab8-305">Choose **Create tasks.json from template**.</span></span>

   :::image type="content" source="../media/dke-createtasksjsonfromtemplate.png" alt-text="在 DKE 的檔案從範本建立 tasks.js":::

   2. <span data-ttu-id="98ab8-307">從範本類型清單中，選取 [ **.Net Core**]。</span><span class="sxs-lookup"><span data-stu-id="98ab8-307">From the list of template types, select **.NET Core**.</span></span>

   :::image type="content" source="../media/dke-tasksjsontemplate.png" alt-text="在 DKE 的檔案從範本建立 tasks.js":::

   3. <span data-ttu-id="98ab8-309">在 [建立] 區段中，找到 customerkeystore 之 **.csproj**檔案的路徑。</span><span class="sxs-lookup"><span data-stu-id="98ab8-309">In the build section, locate the path to the **customerkeystore.csproj** file.</span></span> <span data-ttu-id="98ab8-310">如果沒有的話，請新增下列一行：</span><span class="sxs-lookup"><span data-stu-id="98ab8-310">If it's not there, add the following line:</span></span>

      ```json
      "${workspaceFolder}/src/customer-key-store/customerkeystore.csproj",
      ```

  4. <span data-ttu-id="98ab8-311">再次執行組建。</span><span class="sxs-lookup"><span data-stu-id="98ab8-311">Run the build again.</span></span>

1. <span data-ttu-id="98ab8-312">確認 [輸出] 視窗中沒有紅色的錯誤。</span><span class="sxs-lookup"><span data-stu-id="98ab8-312">Verify that there are no red errors in the output window.</span></span>

   <span data-ttu-id="98ab8-313">如果有紅色錯誤，請檢查主控台輸出。</span><span class="sxs-lookup"><span data-stu-id="98ab8-313">If there are red errors, check the console output.</span></span> <span data-ttu-id="98ab8-314">確定您已正確完成上述所有步驟，且有正確的版本。</span><span class="sxs-lookup"><span data-stu-id="98ab8-314">Ensure that you completed all the previous steps correctly and the correct build versions are present.</span></span>

2. <span data-ttu-id="98ab8-315">選取 [**執行** \> **開始調試**] 以調試處理常式。</span><span class="sxs-lookup"><span data-stu-id="98ab8-315">Select **Run** \> **Start Debugging** to debug the process.</span></span> <span data-ttu-id="98ab8-316">如果系統提示您選取環境，請選取 [ **.net core**]。</span><span class="sxs-lookup"><span data-stu-id="98ab8-316">If you're prompted to select an environment, select **.NET core**.</span></span>

<span data-ttu-id="98ab8-317">.Net core 偵錯工具通常會啟動至 ' ' ' https://localhost:5001 `. To view your test key, go to ` https://localhost:5001 ，並附加一個正斜線（/）和您的金鑰名稱。</span><span class="sxs-lookup"><span data-stu-id="98ab8-317">The .NET core debugger typically launches to \`\`https://localhost:5001`. To view your test key, go to `https://localhost:5001\` and append a forward slash (/) and the name of your key.</span></span> <span data-ttu-id="98ab8-318">例如：</span><span class="sxs-lookup"><span data-stu-id="98ab8-318">For example:</span></span>

```https
https://localhost:5001/TestKey1
```

<span data-ttu-id="98ab8-319">該項應該會以 JSON 格式顯示。</span><span class="sxs-lookup"><span data-stu-id="98ab8-319">The key should display in JSON format.</span></span>

<span data-ttu-id="98ab8-320">您的設定現在已完成。</span><span class="sxs-lookup"><span data-stu-id="98ab8-320">Your setup is now complete.</span></span> <span data-ttu-id="98ab8-321">在您發佈金鑰庫之前 appsettings.js開啟] 中的 JwtAudience 設定，請確定主機名稱的值完全符合您的應用程式服務主機名稱。</span><span class="sxs-lookup"><span data-stu-id="98ab8-321">Before you publish the keystore, in appsettings.json, for the JwtAudience setting, ensure the value for hostname exactly matches your App Service host name.</span></span> <span data-ttu-id="98ab8-322">您可能已將其變更為 localhost 以進行組建疑難排解。</span><span class="sxs-lookup"><span data-stu-id="98ab8-322">You may have changed it to localhost to troubleshoot the build.</span></span>

### <a name="publish-the-key-store"></a><span data-ttu-id="98ab8-323">發佈金鑰存放區</span><span class="sxs-lookup"><span data-stu-id="98ab8-323">Publish the key store</span></span>

<span data-ttu-id="98ab8-324">若要發佈機碼存放區，您將會建立 Azure 應用程式服務實例，以裝載您的 DKE 部署。</span><span class="sxs-lookup"><span data-stu-id="98ab8-324">To publish the key store, you'll create an Azure App Service instance to host your DKE deployment.</span></span> <span data-ttu-id="98ab8-325">接下來，您會將所產生的金鑰發佈到 Azure。</span><span class="sxs-lookup"><span data-stu-id="98ab8-325">Next, you'll publish your generated keys to Azure.</span></span>

<span data-ttu-id="98ab8-326">**建立 Azure Web 應用程式實例以主控您的 DKE 部署**</span><span class="sxs-lookup"><span data-stu-id="98ab8-326">**To create an Azure Web App instance to host your DKE deployment**</span></span>

1. <span data-ttu-id="98ab8-327">在您的瀏覽器中，登入[Microsoft Azure 入口網站](https://ms.portal.azure.com)，然後移至 [**應用程式服務**] [  >  **新增**]。</span><span class="sxs-lookup"><span data-stu-id="98ab8-327">In your browser, sign in to the [Microsoft Azure portal](https://ms.portal.azure.com), and go to **App Services** > **Add**.</span></span>

1. <span data-ttu-id="98ab8-328">選取您的訂閱和資源群組，然後定義您的實例詳細資料。</span><span class="sxs-lookup"><span data-stu-id="98ab8-328">Select your subscription and resource group and define your instance details.</span></span>

    - <span data-ttu-id="98ab8-329">輸入您要安裝 DKE 服務之電腦的主機名稱。</span><span class="sxs-lookup"><span data-stu-id="98ab8-329">Enter the hostname of the computer where you want to install the DKE service.</span></span> <span data-ttu-id="98ab8-330">請確定其名稱與[**appsettings.json**](#tenant-and-key-settings) file 中的 JwtAudience 設定所定義的名稱相同。</span><span class="sxs-lookup"><span data-stu-id="98ab8-330">Make sure it's the same name as the one defined for the JwtAudience setting in the [**appsettings.json**](#tenant-and-key-settings) file.</span></span> <span data-ttu-id="98ab8-331">您為此名稱提供的值也是 WebAppInstanceName。</span><span class="sxs-lookup"><span data-stu-id="98ab8-331">The value you provide for the name is also the WebAppInstanceName.</span></span>

    - <span data-ttu-id="98ab8-332">在 [**發佈**]、[程式**代碼**] 及 [**執行時間堆疊**] 中，選取 [ **.net Core 3.1**]。</span><span class="sxs-lookup"><span data-stu-id="98ab8-332">For **Publish**, select **code**, and for **Runtime stack**, select **.NET Core 3.1**.</span></span>

    <span data-ttu-id="98ab8-333">例如：</span><span class="sxs-lookup"><span data-stu-id="98ab8-333">For example:</span></span>

    :::image type="content" source="../media/dke-azure-add-app-service.png" alt-text="新增應用程式服務":::

1. <span data-ttu-id="98ab8-335">在頁面底部，選取 [**複查 + 建立**]，然後選取 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="98ab8-335">At the bottom of the page, select **Review + create**, and then select **Add**.</span></span>

1. <span data-ttu-id="98ab8-336">執行下列其中一項作業，將您產生的機碼發佈到 Azure：</span><span class="sxs-lookup"><span data-stu-id="98ab8-336">Do one of the following to publish your generated keys to Azure:</span></span>

    - [<span data-ttu-id="98ab8-337">透過 ZipDeployUI 發佈</span><span class="sxs-lookup"><span data-stu-id="98ab8-337">Publish via ZipDeployUI</span></span>](#publish-via-zipdeployui)
    - [<span data-ttu-id="98ab8-338">透過 FTP 發佈</span><span class="sxs-lookup"><span data-stu-id="98ab8-338">Publish via FTP</span></span>](#publish-via-ftp)
    - [<span data-ttu-id="98ab8-339">透過 Visual Studio 2019 或更新版本發行</span><span class="sxs-lookup"><span data-stu-id="98ab8-339">Publish via Visual Studio 2019 or later</span></span>](https://docs.microsoft.com/aspnet/core/tutorials/)
    - [<span data-ttu-id="98ab8-340">發佈至內部部署系統</span><span class="sxs-lookup"><span data-stu-id="98ab8-340">Publish to an on-premises system</span></span>](https://docs.microsoft.com/aspnet/core/tutorials/publish-to-iis?view=aspnetcore-3.1&tabs=netcore-cli)

    > [!NOTE]
    > <span data-ttu-id="98ab8-341">您可以選擇使用其他方法來部署金鑰。</span><span class="sxs-lookup"><span data-stu-id="98ab8-341">You may prefer other methods to deploy your keys.</span></span> <span data-ttu-id="98ab8-342">選取最適合您組織的方法。</span><span class="sxs-lookup"><span data-stu-id="98ab8-342">Select the method that works best for your organization.</span></span>

    > [!TIP]
    > <span data-ttu-id="98ab8-343">使用[Visual Studio](https://docs.microsoft.com/aspnet/core/tutorials/)和[內部部署系統](https://docs.microsoft.com/aspnet/core/tutorials/publish-to-iis?view=aspnetcore-3.1&tabs=netcore-cli)進行發佈會在[ASP .net 檔](https://docs.microsoft.com/aspnet/core/)中說明。</span><span class="sxs-lookup"><span data-stu-id="98ab8-343">[Publishing via Visual Studio](https://docs.microsoft.com/aspnet/core/tutorials/) and to an [on-premises system](https://docs.microsoft.com/aspnet/core/tutorials/publish-to-iis?view=aspnetcore-3.1&tabs=netcore-cli) is described in the [ASP .NET documentation](https://docs.microsoft.com/aspnet/core/).</span></span> <span data-ttu-id="98ab8-344">如果您使用其中一種方法，請在個別的索引標籤中開啟指示，這樣您就可以在完成時輕鬆回到這裡。</span><span class="sxs-lookup"><span data-stu-id="98ab8-344">If you use one of these methods, open the instructions in a separate tab so that you can return here easily when you're done.</span></span>

#### <a name="publish-via-zipdeployui"></a><span data-ttu-id="98ab8-345">透過 ZipDeployUI 發佈</span><span class="sxs-lookup"><span data-stu-id="98ab8-345">Publish via ZipDeployUI</span></span>

1. <span data-ttu-id="98ab8-346">請移至 `https://<WebAppInstanceName>.scm.azurewebsites.net/ZipDeployUI`。</span><span class="sxs-lookup"><span data-stu-id="98ab8-346">Go to `https://<WebAppInstanceName>.scm.azurewebsites.net/ZipDeployUI`.</span></span>

    <span data-ttu-id="98ab8-347">例如：https://customerkeystoreforpublicpreview.scm.azurewebsites.net/ZipDeployUI</span><span class="sxs-lookup"><span data-stu-id="98ab8-347">For example: https://customerkeystoreforpublicpreview.scm.azurewebsites.net/ZipDeployUI</span></span>

1. <span data-ttu-id="98ab8-348">在金鑰存放區的基本代碼中，移至 [ **customer-key-store\src\customer-key-store** ] 資料夾，然後確認此資料夾包含**customerkeystore 的 .csproj**檔案。</span><span class="sxs-lookup"><span data-stu-id="98ab8-348">In the codebase for the key store, go to the **customer-key-store\src\customer-key-store** folder, and verify that this folder contains the **customerkeystore.csproj** file.</span></span>

1. <span data-ttu-id="98ab8-349">執行： **dotnet 發佈**</span><span class="sxs-lookup"><span data-stu-id="98ab8-349">Run: **dotnet publish**</span></span>

     <span data-ttu-id="98ab8-350">[輸出] 視窗會顯示部署發佈所在的目錄。</span><span class="sxs-lookup"><span data-stu-id="98ab8-350">The output window displays the directory where the publish was deployed.</span></span>

    <span data-ttu-id="98ab8-351">例如：`customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`</span><span class="sxs-lookup"><span data-stu-id="98ab8-351">For example: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`</span></span>

1. <span data-ttu-id="98ab8-352">將發行目錄中的所有檔案傳送至 .zip 檔案。</span><span class="sxs-lookup"><span data-stu-id="98ab8-352">Send all files in the publish directory to a .zip file.</span></span> <span data-ttu-id="98ab8-353">建立 .zip 檔時，請確定目錄中的所有檔案都位於 .zip 檔案的根層級。</span><span class="sxs-lookup"><span data-stu-id="98ab8-353">When creating the .zip file, make sure that all files in the directory are at the root level of the .zip file.</span></span>

1. <span data-ttu-id="98ab8-354">將您建立的 .zip 檔案拖放至您在上面開啟的 ZipDeployUI 網站。</span><span class="sxs-lookup"><span data-stu-id="98ab8-354">Drag and drop the .zip file you create to the ZipDeployUI site you opened above.</span></span> <span data-ttu-id="98ab8-355">例如：https://customerkeystoreforpublicpreview.scm.azurewebsites.net/ZipDeployUI</span><span class="sxs-lookup"><span data-stu-id="98ab8-355">For example: https://customerkeystoreforpublicpreview.scm.azurewebsites.net/ZipDeployUI</span></span>

<span data-ttu-id="98ab8-356">已部署 DKE，您可以流覽至您建立的測試機碼。</span><span class="sxs-lookup"><span data-stu-id="98ab8-356">DKE is deployed and you can browse to the test keys you've created.</span></span> <span data-ttu-id="98ab8-357">繼續[驗證您的部署](#validate-your-deployment)。</span><span class="sxs-lookup"><span data-stu-id="98ab8-357">Continue to [Validate your deployment](#validate-your-deployment) below.</span></span>

#### <a name="publish-via-ftp"></a><span data-ttu-id="98ab8-358">透過 FTP 發佈</span><span class="sxs-lookup"><span data-stu-id="98ab8-358">Publish via FTP</span></span>

1. <span data-ttu-id="98ab8-359">連線至您在[上述](#publish-the-key-store)建立的 App 服務。</span><span class="sxs-lookup"><span data-stu-id="98ab8-359">Connect to the App Service you created [above](#publish-the-key-store).</span></span>

    <span data-ttu-id="98ab8-360">在您的瀏覽器中，移至： **Azure 入口**網站  >  **應用程式服務**  >  **部署中心**  >  **手動部署**  >  **FTP**  >  **儀表板**。</span><span class="sxs-lookup"><span data-stu-id="98ab8-360">In your browser, go to: **Azure portal** > **App Service** > **Deployment Center** > **Manual Deployment** > **FTP** > **Dashboard**.</span></span>

1. <span data-ttu-id="98ab8-361">複製顯示至本機檔案的連接字串。</span><span class="sxs-lookup"><span data-stu-id="98ab8-361">Copy the connection strings displayed to a local file.</span></span> <span data-ttu-id="98ab8-362">您將使用這些字串連線到 Web App 服務，並透過 FTP 上傳檔案。</span><span class="sxs-lookup"><span data-stu-id="98ab8-362">You'll use these strings to connect to the Web App Service and upload files via FTP.</span></span>

    <span data-ttu-id="98ab8-363">例如：</span><span class="sxs-lookup"><span data-stu-id="98ab8-363">For example:</span></span>

    :::image type="content" source="../media/dke-ftp-dashboard.png" alt-text="從 FTP 儀表板複製連接字串":::

1. <span data-ttu-id="98ab8-365">在金鑰儲存的基本代碼中，移至**customer-key-store\src\customer-key-store 目錄**。</span><span class="sxs-lookup"><span data-stu-id="98ab8-365">In the codebase for the key storage, go to the **customer-key-store\src\customer-key-store directory**.</span></span>

1. <span data-ttu-id="98ab8-366">請確認此目錄包含**customerkeystore （.csproj** ）檔案。</span><span class="sxs-lookup"><span data-stu-id="98ab8-366">Verify that this directory contains the **customerkeystore.csproj** file.</span></span>

1. <span data-ttu-id="98ab8-367">執行： **dotnet 發佈**</span><span class="sxs-lookup"><span data-stu-id="98ab8-367">Run: **dotnet publish**</span></span>

    <span data-ttu-id="98ab8-368">輸出包含部署發佈所在的目錄。</span><span class="sxs-lookup"><span data-stu-id="98ab8-368">The output contains the directory where the publish was deployed.</span></span>

    <span data-ttu-id="98ab8-369">例如：`customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`</span><span class="sxs-lookup"><span data-stu-id="98ab8-369">For example: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`</span></span>

1. <span data-ttu-id="98ab8-370">將發行目錄中的所有檔案傳送至 zip 檔案。</span><span class="sxs-lookup"><span data-stu-id="98ab8-370">Send all files in the publish directory to a zip file.</span></span> <span data-ttu-id="98ab8-371">建立 .zip 檔時，請確定目錄中的所有檔案都位於 .zip 檔案的根層級。</span><span class="sxs-lookup"><span data-stu-id="98ab8-371">When creating the .zip file, make sure that all files in the directory are at the root level of the .zip file.</span></span>

1. <span data-ttu-id="98ab8-372">您可以從您的 FTP 用戶端，使用複製的連線資訊連線至應用程式服務。</span><span class="sxs-lookup"><span data-stu-id="98ab8-372">From your FTP client, use the connection information you copied to connect to your App Service.</span></span> <span data-ttu-id="98ab8-373">將您在上一個步驟中建立的 .zip 檔案上傳至 Web 應用程式的根目錄。</span><span class="sxs-lookup"><span data-stu-id="98ab8-373">Upload the .zip file you created in the previous step to the root directory of your Web App.</span></span>

<span data-ttu-id="98ab8-374">已部署 DKE，您可以流覽至您所建立的測試機碼。</span><span class="sxs-lookup"><span data-stu-id="98ab8-374">DKE is deployed and you can browse to the test keys you'd created.</span></span> <span data-ttu-id="98ab8-375">接下來，[驗證您的部署](#validate-your-deployment)。</span><span class="sxs-lookup"><span data-stu-id="98ab8-375">Next, [Validate your deployment](#validate-your-deployment).</span></span>

### <a name="validate-your-deployment"></a><span data-ttu-id="98ab8-376">驗證您的部署</span><span class="sxs-lookup"><span data-stu-id="98ab8-376">Validate your deployment</span></span>

<span data-ttu-id="98ab8-377">使用上述其中一種方法來部署 DKE 之後，請驗證部署及主要儲存區設定。</span><span class="sxs-lookup"><span data-stu-id="98ab8-377">After deploying DKE using one of the methods described above, validate the deployment and the key store settings.</span></span>

<span data-ttu-id="98ab8-378">運行：</span><span class="sxs-lookup"><span data-stu-id="98ab8-378">Run:</span></span>

<span data-ttu-id="98ab8-379">src\customer-key-store\scripts\key_store_tester.ps1 mykeystoreurl/mykey</span><span class="sxs-lookup"><span data-stu-id="98ab8-379">src\customer-key-store\scripts\key_store_tester.ps1 mykeystoreurl/mykey</span></span>

<span data-ttu-id="98ab8-380">例如：</span><span class="sxs-lookup"><span data-stu-id="98ab8-380">For example:</span></span>

<span data-ttu-id="98ab8-381">key_store_tester.ps1https://mycustomerkeystore.com/mykey</span><span class="sxs-lookup"><span data-stu-id="98ab8-381">key_store_tester.ps1 https://mycustomerkeystore.com/mykey</span></span>

<span data-ttu-id="98ab8-382">確定輸出中未顯示任何錯誤。</span><span class="sxs-lookup"><span data-stu-id="98ab8-382">Ensure that no errors appear in the output.</span></span> <span data-ttu-id="98ab8-383">當您準備好時，請[註冊金鑰存放區](#register-your-key-store)。</span><span class="sxs-lookup"><span data-stu-id="98ab8-383">When you're ready, [register your key store](#register-your-key-store).</span></span>

## <a name="register-your-key-store"></a><span data-ttu-id="98ab8-384">註冊金鑰存放區</span><span class="sxs-lookup"><span data-stu-id="98ab8-384">Register your key store</span></span>

<span data-ttu-id="98ab8-385">下列步驟可讓您註冊金鑰存放區。</span><span class="sxs-lookup"><span data-stu-id="98ab8-385">The following steps enable you to register your key store.</span></span> <span data-ttu-id="98ab8-386">註冊金鑰存放區是部署 DKE 之前的最後一個步驟，可以開始建立標籤。</span><span class="sxs-lookup"><span data-stu-id="98ab8-386">Registering your key store is the last step in deploying DKE before you can start creating labels.</span></span>

<span data-ttu-id="98ab8-387">若要註冊金鑰存放區：</span><span class="sxs-lookup"><span data-stu-id="98ab8-387">To register your key store:</span></span>

1. <span data-ttu-id="98ab8-388">在您的瀏覽器中，開啟[Microsoft Azure 入口網站](https://ms.portal.azure.com/)，然後移至**所有服務**身分 \> **識別** \> **應用程式註冊**。</span><span class="sxs-lookup"><span data-stu-id="98ab8-388">In your browser, open the [Microsoft Azure portal](https://ms.portal.azure.com/), and go to **All Services** \> **Identity** \> **App Registrations**.</span></span>

2. <span data-ttu-id="98ab8-389">選取 [**新增註冊**]，然後輸入有意義的名稱。</span><span class="sxs-lookup"><span data-stu-id="98ab8-389">Select **New registration**, and enter a meaningful name.</span></span>

3. <span data-ttu-id="98ab8-390">從顯示的選項中選取帳戶類型。</span><span class="sxs-lookup"><span data-stu-id="98ab8-390">Select an account type from the options displayed.</span></span>

    <span data-ttu-id="98ab8-391">如果您使用的是非自訂網域（例如**onmicrosoft.com**）的 Microsoft Azure，請選取 **[僅限 Microsoft 單一租使用者] 中的 [帳戶]。**</span><span class="sxs-lookup"><span data-stu-id="98ab8-391">If you're using Microsoft Azure with a non-custom domain, such as **onmicrosoft.com**, select **Accounts in this organizational directory only (Microsoft only - Single tenant).**</span></span>

    <span data-ttu-id="98ab8-392">例如：</span><span class="sxs-lookup"><span data-stu-id="98ab8-392">For example:</span></span>

    :::image type="content" source="../media/dke-app-registration.png" alt-text="新的應用程式註冊":::

4. <span data-ttu-id="98ab8-394">在頁面底部，選取 [**註冊**] 以建立新的應用程式註冊。</span><span class="sxs-lookup"><span data-stu-id="98ab8-394">At the bottom of the page, select **Register** to create the new App Registration.</span></span>

5. <span data-ttu-id="98ab8-395">在新的應用程式註冊的左窗格中，按一下 [**管理**] 下的 [**驗證**]。</span><span class="sxs-lookup"><span data-stu-id="98ab8-395">In your new App Registration, in the left pane, under **Manage**, select **Authentication**.</span></span>

6. <span data-ttu-id="98ab8-396">選取 [**新增平臺**]。</span><span class="sxs-lookup"><span data-stu-id="98ab8-396">Select **Add a platform**.</span></span>
 
7. <span data-ttu-id="98ab8-397">在 [**設定平臺**] 快顯功能表上，選取 [ **Web**]。</span><span class="sxs-lookup"><span data-stu-id="98ab8-397">On the **Configure platforms** popup, select **Web**.</span></span>
 
8. <span data-ttu-id="98ab8-398">在 [重新**導向 URIs**] 底下，輸入您的雙金鑰加密服務 URI。</span><span class="sxs-lookup"><span data-stu-id="98ab8-398">Under **Redirect URIs**, enter the URI of your double key encryption service.</span></span> <span data-ttu-id="98ab8-399">輸入應用程式服務 URL，包括主機名稱和網域。</span><span class="sxs-lookup"><span data-stu-id="98ab8-399">Enter the App Service URL, including both the hostname and domain.</span></span>

    <span data-ttu-id="98ab8-400">例如：https://mycustomerkeystoretest.com</span><span class="sxs-lookup"><span data-stu-id="98ab8-400">For example: https://mycustomerkeystoretest.com</span></span>

    - <span data-ttu-id="98ab8-401">您輸入的 URL 必須符合部署金鑰存放區的主機名稱。</span><span class="sxs-lookup"><span data-stu-id="98ab8-401">The URL you enter must match the hostname where your key store is deployed.</span></span>
    - <span data-ttu-id="98ab8-402">如果您要在本機上使用 Visual Studio 進行測試，請使用 **https://localhost:5001** 。</span><span class="sxs-lookup"><span data-stu-id="98ab8-402">If you're testing locally with Visual Studio, use **https://localhost:5001**.</span></span>
    - <span data-ttu-id="98ab8-403">在所有情況下，此配置必須是**HTTPs**。</span><span class="sxs-lookup"><span data-stu-id="98ab8-403">In all cases, the scheme must be **https**.</span></span>

    <span data-ttu-id="98ab8-404">確定主機名稱完全符合您的應用程式服務主機名稱。</span><span class="sxs-lookup"><span data-stu-id="98ab8-404">Ensure the hostname exactly matches your App Service host name.</span></span> <span data-ttu-id="98ab8-405">您可能已經將其變更為 `localhost` 疑難排解組建。</span><span class="sxs-lookup"><span data-stu-id="98ab8-405">You may have changed it to `localhost` to troubleshoot the build.</span></span> <span data-ttu-id="98ab8-406">在**appsettings.js開啟**] 中，這個值是您為設定的主機名稱 `JwtAudience` 。</span><span class="sxs-lookup"><span data-stu-id="98ab8-406">In **appsettings.json**, this value is the hostname you set for `JwtAudience`.</span></span>

6. <span data-ttu-id="98ab8-407">在 **[隱含授**與] 底下，選取 [**識別碼標記**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="98ab8-407">Under **Implicit grant**, select the **ID tokens** checkbox.</span></span>

1. <span data-ttu-id="98ab8-408">選取 **[儲存]** 以儲存變更。</span><span class="sxs-lookup"><span data-stu-id="98ab8-408">Select **Save** to save your changes.</span></span>

7. <span data-ttu-id="98ab8-409">在左窗格中，選取 [**公開 API**]，然後選取 [應用程式識別碼 URI] 旁的 [**設定**]。</span><span class="sxs-lookup"><span data-stu-id="98ab8-409">On the left pane, select **Expose an API**, then next to Application ID URI, select **Set**.</span></span>

9. <span data-ttu-id="98ab8-410">在 [**公開 API** ] 頁面上，選取 [**此 api**區域所定義的範圍] 中的 [**新增範圍**]。</span><span class="sxs-lookup"><span data-stu-id="98ab8-410">Still on the **Expose an API** page, in the **Scopes defined by this API** area, select **Add a scope**.</span></span> <span data-ttu-id="98ab8-411">在 [新增] 範圍中：</span><span class="sxs-lookup"><span data-stu-id="98ab8-411">In the new scope:</span></span>

    1. <span data-ttu-id="98ab8-412">將範圍名稱定義為**user_impersonation**。</span><span class="sxs-lookup"><span data-stu-id="98ab8-412">Define the scope name as **user_impersonation**.</span></span>

    2. <span data-ttu-id="98ab8-413">選取可同意的系統管理員和使用者。</span><span class="sxs-lookup"><span data-stu-id="98ab8-413">Select the administrators and users who can consent.</span></span>

    3. <span data-ttu-id="98ab8-414">定義任何其他必要的值。</span><span class="sxs-lookup"><span data-stu-id="98ab8-414">Define any remaining values required.</span></span>

    4. <span data-ttu-id="98ab8-415">選取 [**新增範圍]。**</span><span class="sxs-lookup"><span data-stu-id="98ab8-415">Select **Add scope.**</span></span>

    <span data-ttu-id="98ab8-416">選取頂端的 [**儲存**] 以儲存變更。</span><span class="sxs-lookup"><span data-stu-id="98ab8-416">Select **Save** at the top to save your changes.</span></span>

10. <span data-ttu-id="98ab8-417">仍在**公開 API**頁面上，選取 [**授權用戶端應用程式**] 區域中的 [**新增用戶端應用程式**]。</span><span class="sxs-lookup"><span data-stu-id="98ab8-417">Still on the **Expose an API** page, in the **Authorized client applications** area, select **Add a client application**.</span></span>

    <span data-ttu-id="98ab8-418">在新的用戶端應用程式中：</span><span class="sxs-lookup"><span data-stu-id="98ab8-418">In the new client application:</span></span>

    1. <span data-ttu-id="98ab8-419">將用戶端識別碼定義為**d3590ed6-52b3-4102-aeff-aad2292ab01c**。</span><span class="sxs-lookup"><span data-stu-id="98ab8-419">Define the Client ID as **d3590ed6-52b3-4102-aeff-aad2292ab01c**.</span></span> <span data-ttu-id="98ab8-420">這個值是 Microsoft Office 用戶端識別碼，可讓 Office 取得金鑰存放區的存取權杖。</span><span class="sxs-lookup"><span data-stu-id="98ab8-420">This value is the Microsoft Office client ID, and enables Office to obtain an access token for your key store.</span></span>

    2. <span data-ttu-id="98ab8-421">在 [**授權範圍**] 底下，選取 [ **user_impersonation** ] 範圍。</span><span class="sxs-lookup"><span data-stu-id="98ab8-421">Under **Authorized scopes**, select the **user_impersonation** scope.</span></span>

    3. <span data-ttu-id="98ab8-422">選取 [**新增應用程式**]。</span><span class="sxs-lookup"><span data-stu-id="98ab8-422">Select **Add application**.</span></span>

    4. <span data-ttu-id="98ab8-423">選取頂端的 [**儲存**] 以儲存變更。</span><span class="sxs-lookup"><span data-stu-id="98ab8-423">Select **Save** at the top to save your changes.</span></span>

<span data-ttu-id="98ab8-424">您的 DKE 金鑰存放區現在已註冊。</span><span class="sxs-lookup"><span data-stu-id="98ab8-424">Your DKE key store is now registered.</span></span> <span data-ttu-id="98ab8-425">[使用 DKE 建立標籤](#create-labels-using-dke)以繼續。</span><span class="sxs-lookup"><span data-stu-id="98ab8-425">Continue by [creating labels using DKE](#create-labels-using-dke).</span></span>

## <a name="create-labels-using-dke"></a><span data-ttu-id="98ab8-426">使用 DKE 建立標籤</span><span class="sxs-lookup"><span data-stu-id="98ab8-426">Create labels using DKE</span></span>

<span data-ttu-id="98ab8-427">在 Microsoft 365 規範中心中，建立新的靈敏度標籤，並依照您的需要套用加密。</span><span class="sxs-lookup"><span data-stu-id="98ab8-427">In the Microsoft 365 compliance center, create a new sensitivity label and apply encryption as you would otherwise.</span></span> <span data-ttu-id="98ab8-428">選取 [**使用雙重金鑰加密**]，然後輸入機碼的端點 URL。</span><span class="sxs-lookup"><span data-stu-id="98ab8-428">Select **Use Double Key Encryption** and enter the endpoint URL for your key.</span></span>

<span data-ttu-id="98ab8-429">例如：</span><span class="sxs-lookup"><span data-stu-id="98ab8-429">For example:</span></span>

:::image type="content" source="../media/dke-use-dke.png" alt-text="選取 [Microsoft 365 規範中心] 中的 [使用雙重金鑰加密]":::

<span data-ttu-id="98ab8-431">在最新版本的 Microsoft 365 應用程式中，您新增的任何 DKE 標籤都會開始顯示給使用者。</span><span class="sxs-lookup"><span data-stu-id="98ab8-431">Any DKE labels you add will start appearing for users in the latest versions of Microsoft 365 Apps for enterprise.</span></span>

> [!NOTE]
> <span data-ttu-id="98ab8-432">最多可能需要24小時的時間，讓用戶端重新整理新的標籤。</span><span class="sxs-lookup"><span data-stu-id="98ab8-432">It may take up to 24 hours for the clients to refresh with the new labels.</span></span>

### <a name="enable-dke-in-your-client"></a><span data-ttu-id="98ab8-433">在用戶端啟用 DKE</span><span class="sxs-lookup"><span data-stu-id="98ab8-433">Enable DKE in your client</span></span>

<span data-ttu-id="98ab8-434">新增下列登錄機碼，為您的用戶端啟用 DKE：</span><span class="sxs-lookup"><span data-stu-id="98ab8-434">Enable DKE for your client by adding the following registry keys:</span></span>

```properties
    [HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIPC\flighting]
    "DoubleKeyProtection"=dword:00000001

    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSIPC\flighting]
    "DoubleKeyProtection"=dword:00000001
```
