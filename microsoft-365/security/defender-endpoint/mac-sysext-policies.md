---
title: macOS Catalina 和更新版本 macOS 的新設定設定檔
description: 本主題說明必須進行的變更，以便從系統擴充（macOS Catalina 上的核心擴充和較新版本的 macOS）中受益。
keywords: microsoft，defender，Microsoft Defender for Endpoint，mac，內核，system，extensions，catalina
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: security
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ROBOTS: noindex,nofollow
ms.technology: mde
ms.openlocfilehash: 28a332cec68521741bdda62aeecd25440552344a
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2021
ms.locfileid: "51932736"
---
# <a name="new-configuration-profiles-for-macos-catalina-and-newer-versions-of-macos"></a><span data-ttu-id="3ac66-104">macOS Catalina 和更新版本 macOS 的新設定設定檔</span><span class="sxs-lookup"><span data-stu-id="3ac66-104">New configuration profiles for macOS Catalina and newer versions of macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="3ac66-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="3ac66-105">**Applies to:**</span></span>
- [<span data-ttu-id="3ac66-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="3ac66-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="3ac66-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3ac66-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="3ac66-108">想要體驗適用於端點的 Microsoft Defender 嗎？</span><span class="sxs-lookup"><span data-stu-id="3ac66-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="3ac66-109">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="3ac66-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="3ac66-110">在 macOS 演變的情況下，我們正在準備使用系統擴充（而不是核心擴充）的 macOS 更新上的 Microsoft Defender for Endpoint。</span><span class="sxs-lookup"><span data-stu-id="3ac66-110">In alignment with macOS evolution, we are preparing a Microsoft Defender for Endpoint on macOS update that leverages system extensions instead of kernel extensions.</span></span> <span data-ttu-id="3ac66-111">此更新只適用于 macOS Catalina (10.15.4) 和更新版本的 macOS。</span><span class="sxs-lookup"><span data-stu-id="3ac66-111">This update will only be applicable to macOS Catalina (10.15.4) and newer versions of macOS.</span></span>

<span data-ttu-id="3ac66-112">如果您已在受管理環境 (透過 JAMF、Intune 或另一個 MDM 方案) 部署 Microsoft Defender for Endpoint macOS，您必須部署新的設定檔。</span><span class="sxs-lookup"><span data-stu-id="3ac66-112">If you have deployed Microsoft Defender for Endpoint on macOS in a managed environment (through JAMF, Intune, or another MDM solution), you must deploy new configuration profiles.</span></span> <span data-ttu-id="3ac66-113">若無法執行這些步驟，將會導致使用者取得核准提示以執行這些新元件。</span><span class="sxs-lookup"><span data-stu-id="3ac66-113">Failure to do these steps will result in users getting approval prompts to run these new components.</span></span>

## <a name="jamf"></a><span data-ttu-id="3ac66-114">JAMF</span><span class="sxs-lookup"><span data-stu-id="3ac66-114">JAMF</span></span>

### <a name="system-extensions-policy"></a><span data-ttu-id="3ac66-115">系統擴充原則</span><span class="sxs-lookup"><span data-stu-id="3ac66-115">System Extensions Policy</span></span>

<span data-ttu-id="3ac66-116">若要核准系統擴充，請建立下列的負載：</span><span class="sxs-lookup"><span data-stu-id="3ac66-116">To approve the system extensions, create the following payload:</span></span>

1. <span data-ttu-id="3ac66-117">在 **> 設定檔的電腦** 中，選取 [ **系統分機] > 的選項**。</span><span class="sxs-lookup"><span data-stu-id="3ac66-117">In **Computers > Configuration Profiles** select **Options > System Extensions**.</span></span>
2. <span data-ttu-id="3ac66-118">從 [**系統擴充類型**] 下拉式清單中選取 [**允許的系統擴充**]。</span><span class="sxs-lookup"><span data-stu-id="3ac66-118">Select **Allowed System Extensions** from the **System Extension Types** drop-down list.</span></span>
3. <span data-ttu-id="3ac66-119">使用 **UBF8T346G9** 做為小組識別碼。</span><span class="sxs-lookup"><span data-stu-id="3ac66-119">Use **UBF8T346G9** for Team Id.</span></span>
4. <span data-ttu-id="3ac66-120">將下列束識別碼新增至 **允許的系統副檔名** 清單：</span><span class="sxs-lookup"><span data-stu-id="3ac66-120">Add the following bundle identifiers to the **Allowed System Extensions** list:</span></span>

    - <span data-ttu-id="3ac66-121">**wdav epsext**</span><span class="sxs-lookup"><span data-stu-id="3ac66-121">**com.microsoft.wdav.epsext**</span></span>
    - <span data-ttu-id="3ac66-122">**wdav netext**</span><span class="sxs-lookup"><span data-stu-id="3ac66-122">**com.microsoft.wdav.netext**</span></span>

    ![核准的系統擴充螢幕擷取畫面](images/mac-approved-system-extensions.png)

### <a name="privacy-preferences-policy-control"></a><span data-ttu-id="3ac66-124">隱私權偏好設定原則控制</span><span class="sxs-lookup"><span data-stu-id="3ac66-124">Privacy Preferences Policy Control</span></span>

<span data-ttu-id="3ac66-125">新增下列 JAMF 負載，以授與 Microsoft Defender for Endpoint Endpoint Security Extension 的完整磁片存取權。</span><span class="sxs-lookup"><span data-stu-id="3ac66-125">Add the following JAMF payload to grant Full Disk Access to the Microsoft Defender for Endpoint Endpoint Security Extension.</span></span> <span data-ttu-id="3ac66-126">這個原則是在您的裝置上執行分機的必要條件。</span><span class="sxs-lookup"><span data-stu-id="3ac66-126">This policy is a pre-requisite for running the extension on your device.</span></span>

1. <span data-ttu-id="3ac66-127">選取[  >  **隱私權偏好設定原則] 控制項** 的選項。</span><span class="sxs-lookup"><span data-stu-id="3ac66-127">Select **Options** > **Privacy Preferences Policy Control**.</span></span>
2. <span data-ttu-id="3ac66-128">`com.microsoft.wdav.epsext`當作 **識別碼** 及 `Bundle ID` **束類型** 使用。</span><span class="sxs-lookup"><span data-stu-id="3ac66-128">Use `com.microsoft.wdav.epsext` as the **Identifier** and `Bundle ID` as **Bundle type**.</span></span>
3. <span data-ttu-id="3ac66-129">將程式碼需求設定為 `identifier "com.microsoft.wdav.epsext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span><span class="sxs-lookup"><span data-stu-id="3ac66-129">Set Code Requirement to `identifier "com.microsoft.wdav.epsext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span></span>
4. <span data-ttu-id="3ac66-130">將 **App 或服務** 設定為 **SystemPolicyAllFiles** ，並存取 **允許**。</span><span class="sxs-lookup"><span data-stu-id="3ac66-130">Set **App or service** to **SystemPolicyAllFiles** and access to **Allow**.</span></span>

    ![隱私權偏好設定原則控制](images/mac-system-extension-privacy.png)

### <a name="network-extension-policy"></a><span data-ttu-id="3ac66-132">網路擴充原則</span><span class="sxs-lookup"><span data-stu-id="3ac66-132">Network Extension Policy</span></span>

<span data-ttu-id="3ac66-133">在端點偵測和回應功能的一部分中，macOS 的 Microsoft Defender for endpoint 會檢查通訊端流量，並將此資訊報告給 Microsoft Defender 資訊安全中心入口網站。</span><span class="sxs-lookup"><span data-stu-id="3ac66-133">As part of the Endpoint Detection and Response capabilities, Microsoft Defender for Endpoint on macOS inspects socket traffic and reports this information to the Microsoft Defender Security Center portal.</span></span> <span data-ttu-id="3ac66-134">下列原則允許網路分機執行這項功能。</span><span class="sxs-lookup"><span data-stu-id="3ac66-134">The following policy allows the network extension to perform this functionality.</span></span>

>[!NOTE]
><span data-ttu-id="3ac66-135">JAMF 不具備內容篩選原則的內建支援，也就是在裝置上安裝 Microsoft Defender for Endpoint for the macOS 的網路分機。</span><span class="sxs-lookup"><span data-stu-id="3ac66-135">JAMF doesn’t have built-in support for content filtering policies, which are a pre-requisite for enabling the network extensions that Microsoft Defender for Endpoint on macOS installs on the device.</span></span> <span data-ttu-id="3ac66-136">此外，JAMF 有時會變更所要部署之原則的內容。</span><span class="sxs-lookup"><span data-stu-id="3ac66-136">Furthermore, JAMF sometimes changes the content of the policies being deployed.</span></span>
><span data-ttu-id="3ac66-137">如此一來，下列步驟會提供對設定設定檔進行簽章的解決方法。</span><span class="sxs-lookup"><span data-stu-id="3ac66-137">As such, the following steps provide a workaround that involve signing the configuration profile.</span></span>

1. <span data-ttu-id="3ac66-138">使用文字編輯器，將下列內容儲存到您的裝置 `com.microsoft.network-extension.mobileconfig` ：</span><span class="sxs-lookup"><span data-stu-id="3ac66-138">Save the following content to your device as `com.microsoft.network-extension.mobileconfig` using a text editor:</span></span>

    ```xml
    <?xml version="1.0" encoding="UTF-8"?><!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
    <plist version="1">
        <dict>
            <key>PayloadUUID</key>
            <string>DA2CC794-488B-4AFF-89F7-6686A7E7B8AB</string>
            <key>PayloadType</key>
            <string>Configuration</string>
            <key>PayloadOrganization</key>
            <string>Microsoft Corporation</string>
            <key>PayloadIdentifier</key>
            <string>DA2CC794-488B-4AFF-89F7-6686A7E7B8AB</string>
            <key>PayloadDisplayName</key>
            <string>Microsoft Defender ATP Network Extension</string>
            <key>PayloadDescription</key>
            <string/>
            <key>PayloadVersion</key>
            <integer>1</integer>
            <key>PayloadEnabled</key>
            <true/>
            <key>PayloadRemovalDisallowed</key>
            <true/>
            <key>PayloadScope</key>
            <string>System</string>
            <key>PayloadContent</key>
            <array>
                <dict>
                    <key>PayloadUUID</key>
                    <string>2BA070D9-2233-4827-AFC1-1F44C8C8E527</string>
                    <key>PayloadType</key>
                    <string>com.apple.webcontent-filter</string>
                    <key>PayloadOrganization</key>
                    <string>Microsoft Corporation</string>
                    <key>PayloadIdentifier</key>
                    <string>CEBF7A71-D9A1-48BD-8CCF-BD9D18EC155A</string>
                    <key>PayloadDisplayName</key>
                    <string>Approved Network Extension</string>
                    <key>PayloadDescription</key>
                    <string/>
                    <key>PayloadVersion</key>
                    <integer>1</integer>
                    <key>PayloadEnabled</key>
                    <true/>
                    <key>FilterType</key>
                    <string>Plugin</string>
                    <key>UserDefinedName</key>
                    <string>Microsoft Defender ATP Network Extension</string>
                    <key>PluginBundleID</key>
                    <string>com.microsoft.wdav</string>
                    <key>FilterSockets</key>
                    <true/>
                    <key>FilterDataProviderBundleIdentifier</key>
                    <string>com.microsoft.wdav.netext</string>
                    <key>FilterDataProviderDesignatedRequirement</key>
                    <string>identifier "com.microsoft.wdav.netext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9</string>
                </dict>
            </array>
        </dict>
    </plist>
    ```

2. <span data-ttu-id="3ac66-139">`plutil`在終端中執行公用程式，確認已正確複製上述檔案。</span><span class="sxs-lookup"><span data-stu-id="3ac66-139">Verify that the above file was copied correctly by running the `plutil` utility in the Terminal:</span></span>

    ```bash
    $ plutil -lint <PathToFile>/com.microsoft.network-extension.mobileconfig
    ```

    <span data-ttu-id="3ac66-140">例如，如果檔案儲存在檔中：</span><span class="sxs-lookup"><span data-stu-id="3ac66-140">For example, if the file was stored in Documents:</span></span>

    ```bash
    $ plutil -lint ~/Documents/com.microsoft.network-extension.mobileconfig
    ```
    
    <span data-ttu-id="3ac66-141">確認命令輸出 `OK` 。</span><span class="sxs-lookup"><span data-stu-id="3ac66-141">Verify that the command outputs `OK`.</span></span>
        
    ```bash
    <PathToFile>/com.microsoft.network-extension.mobileconfig: OK
    ```
    
3. <span data-ttu-id="3ac66-142">遵循 [此頁面](https://www.jamf.com/jamf-nation/articles/649/creating-a-signing-certificate-using-jamf-pro-s-built-in-certificate-authority) 上的指示，使用 JAMF 的內建憑證授權單位建立簽署憑證。</span><span class="sxs-lookup"><span data-stu-id="3ac66-142">Follow the instructions on [this page](https://www.jamf.com/jamf-nation/articles/649/creating-a-signing-certificate-using-jamf-pro-s-built-in-certificate-authority) to create a signing certificate using JAMF’s built-in certificate authority.</span></span>

4. <span data-ttu-id="3ac66-143">建立憑證並將其安裝至裝置後，請從終端執行下列命令以簽署檔案：</span><span class="sxs-lookup"><span data-stu-id="3ac66-143">After the certificate is created and installed to your device, run the following command from the Terminal to sign the file:</span></span>

    ```bash
    $ security cms -S -N "<CertificateName>" -i <PathToFile>/com.microsoft.network-extension.mobileconfig -o <PathToSignedFile>/com.microsoft.network-extension.signed.mobileconfig
    ```
    
    <span data-ttu-id="3ac66-144">例如，如果憑證名稱是 **SigningCertificate** ，且已簽署的檔案將要儲存在檔中：</span><span class="sxs-lookup"><span data-stu-id="3ac66-144">For example, if the certificate name is **SigningCertificate** and the signed file is going to be stored in Documents:</span></span>
    
    ```bash
    $ security cms -S -N "SigningCertificate" -i ~/Documents/com.microsoft.network-extension.mobileconfig -o ~/Documents/com.microsoft.network-extension.signed.mobileconfig
    ```
    
5. <span data-ttu-id="3ac66-145">在 JAMF 入口網站中，流覽至 [設定 **設定檔**]，然後按一下 [ **Upload** ] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="3ac66-145">From the JAMF portal, navigate to **Configuration Profiles** and click the **Upload** button.</span></span> <span data-ttu-id="3ac66-146">`com.microsoft.network-extension.signed.mobileconfig`當系統提示您輸入檔案時，請選取。</span><span class="sxs-lookup"><span data-stu-id="3ac66-146">Select `com.microsoft.network-extension.signed.mobileconfig` when prompted for the file.</span></span>

## <a name="intune"></a><span data-ttu-id="3ac66-147">Intune</span><span class="sxs-lookup"><span data-stu-id="3ac66-147">Intune</span></span>

### <a name="system-extensions-policy"></a><span data-ttu-id="3ac66-148">系統擴充原則</span><span class="sxs-lookup"><span data-stu-id="3ac66-148">System Extensions Policy</span></span>

<span data-ttu-id="3ac66-149">若要核准系統擴充：</span><span class="sxs-lookup"><span data-stu-id="3ac66-149">To approve the system extensions:</span></span>

1. <span data-ttu-id="3ac66-150">在 Intune 中，開啟 [**管理**  >  **裝置** 設定]。</span><span class="sxs-lookup"><span data-stu-id="3ac66-150">In Intune, open **Manage** > **Device configuration**.</span></span> <span data-ttu-id="3ac66-151">選取 [**管理**  >  **設定檔**  >  **建立設定檔**]。</span><span class="sxs-lookup"><span data-stu-id="3ac66-151">Select **Manage** > **Profiles** > **Create Profile**.</span></span>
2. <span data-ttu-id="3ac66-152">選擇設定檔的名稱。</span><span class="sxs-lookup"><span data-stu-id="3ac66-152">Choose a name for the profile.</span></span> <span data-ttu-id="3ac66-153">將 **平臺** 改為 MacOS **配置檔案類型 = 分機**。</span><span class="sxs-lookup"><span data-stu-id="3ac66-153">Change **Platform=macOS** to **Profile type=Extensions**.</span></span> <span data-ttu-id="3ac66-154">選取 [建立 **]**。</span><span class="sxs-lookup"><span data-stu-id="3ac66-154">Select **Create**.</span></span>
3. <span data-ttu-id="3ac66-155">在 [索引標籤 `Basics` ] 中，為此新設定檔指定名稱。</span><span class="sxs-lookup"><span data-stu-id="3ac66-155">In the `Basics` tab, give a name to this new profile.</span></span>
4. <span data-ttu-id="3ac66-156">在 [ `Configuration settings` ] 索引標籤中，在區段中新增下列專案 `Allowed system extensions` ：</span><span class="sxs-lookup"><span data-stu-id="3ac66-156">In the `Configuration settings` tab, add the following entries in the `Allowed system extensions` section:</span></span>

    <span data-ttu-id="3ac66-157">束識別碼</span><span class="sxs-lookup"><span data-stu-id="3ac66-157">Bundle identifier</span></span>         | <span data-ttu-id="3ac66-158">小組識別碼</span><span class="sxs-lookup"><span data-stu-id="3ac66-158">Team identifier</span></span>
    --------------------------|----------------
    <span data-ttu-id="3ac66-159">wdav epsext</span><span class="sxs-lookup"><span data-stu-id="3ac66-159">com.microsoft.wdav.epsext</span></span> | <span data-ttu-id="3ac66-160">UBF8T346G9</span><span class="sxs-lookup"><span data-stu-id="3ac66-160">UBF8T346G9</span></span>
    <span data-ttu-id="3ac66-161">wdav netext</span><span class="sxs-lookup"><span data-stu-id="3ac66-161">com.microsoft.wdav.netext</span></span> | <span data-ttu-id="3ac66-162">UBF8T346G9</span><span class="sxs-lookup"><span data-stu-id="3ac66-162">UBF8T346G9</span></span>

    ![系統設定檔的螢幕擷取畫面](images/mac-system-extension-intune2.png)

5. <span data-ttu-id="3ac66-164">在 [索引標籤 `Assignments` ] 中，將此設定檔指派給所有 **使用者 & 所有裝置**。</span><span class="sxs-lookup"><span data-stu-id="3ac66-164">In the `Assignments` tab, assign this profile to **All Users & All devices**.</span></span>
6. <span data-ttu-id="3ac66-165">複查和建立此設定設定檔。</span><span class="sxs-lookup"><span data-stu-id="3ac66-165">Review and create this configuration profile.</span></span>

### <a name="create-and-deploy-the-custom-configuration-profile"></a><span data-ttu-id="3ac66-166">建立及部署自訂設定檔</span><span class="sxs-lookup"><span data-stu-id="3ac66-166">Create and deploy the Custom Configuration Profile</span></span>

<span data-ttu-id="3ac66-167">下列設定設定檔可啟用網路分機，並授與對端點安全性系統擴充的完整磁片存取權。</span><span class="sxs-lookup"><span data-stu-id="3ac66-167">The following configuration profile enables the network extension and grants Full Disk Access to the Endpoint Security system extension.</span></span> 

<span data-ttu-id="3ac66-168">將下列內容儲存至名為 **sysext.xml** 的檔案：</span><span class="sxs-lookup"><span data-stu-id="3ac66-168">Save the following content to a file named **sysext.xml**:</span></span>

```xml
<?xml version="1.0" encoding="UTF-8"?><!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1">
    <dict>
        <key>PayloadUUID</key>
        <string>7E53AC50-B88D-4132-99B6-29F7974EAA3C</string>
        <key>PayloadType</key>
        <string>Configuration</string>
        <key>PayloadOrganization</key>
        <string>Microsoft Corporation</string>
        <key>PayloadIdentifier</key>
        <string>7E53AC50-B88D-4132-99B6-29F7974EAA3C</string>
        <key>PayloadDisplayName</key>
        <string>Microsoft Defender ATP System Extensions</string>
        <key>PayloadDescription</key>
        <string/>
        <key>PayloadVersion</key>
        <integer>1</integer>
        <key>PayloadEnabled</key>
        <true/>
        <key>PayloadRemovalDisallowed</key>
        <true/>
        <key>PayloadScope</key>
        <string>System</string>
        <key>PayloadContent</key>
        <array>
            <dict>
                <key>PayloadUUID</key>
                <string>2BA070D9-2233-4827-AFC1-1F44C8C8E527</string>
                <key>PayloadType</key>
                <string>com.apple.webcontent-filter</string>
                <key>PayloadOrganization</key>
                <string>Microsoft Corporation</string>
                <key>PayloadIdentifier</key>
                <string>CEBF7A71-D9A1-48BD-8CCF-BD9D18EC155A</string>
                <key>PayloadDisplayName</key>
                <string>Approved Network Extension</string>
                <key>PayloadDescription</key>
                <string/>
                <key>PayloadVersion</key>
                <integer>1</integer>
                <key>PayloadEnabled</key>
                <true/>
                <key>FilterType</key>
                <string>Plugin</string>
                <key>UserDefinedName</key>
                <string>Microsoft Defender ATP Network Extension</string>
                <key>PluginBundleID</key>
                <string>com.microsoft.wdav</string>
                <key>FilterSockets</key>
                <true/>
                <key>FilterDataProviderBundleIdentifier</key>
                <string>com.microsoft.wdav.netext</string>
                <key>FilterDataProviderDesignatedRequirement</key>
                <string>identifier &quot;com.microsoft.wdav.netext&quot; and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9</string>
            </dict>
            <dict>
                <key>PayloadUUID</key>
                <string>56105E89-C7C8-4A95-AEE6-E11B8BEA0366</string>
                <key>PayloadType</key>
                <string>com.apple.TCC.configuration-profile-policy</string>
                <key>PayloadOrganization</key>
                <string>Microsoft Corporation</string>
                <key>PayloadIdentifier</key>
                <string>56105E89-C7C8-4A95-AEE6-E11B8BEA0366</string>
                <key>PayloadDisplayName</key>
                <string>Privacy Preferences Policy Control</string>
                <key>PayloadDescription</key>
                <string/>
                <key>PayloadVersion</key>
                <integer>1</integer>
                <key>PayloadEnabled</key>
                <true/>
                <key>Services</key>
                <dict>
                    <key>SystemPolicyAllFiles</key>
                    <array>
                        <dict>
                            <key>Identifier</key>
                            <string>com.microsoft.wdav.epsext</string>
                            <key>CodeRequirement</key>
                            <string>identifier "com.microsoft.wdav.epsext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9</string>
                            <key>IdentifierType</key>
                            <string>bundleID</string>
                            <key>StaticCode</key>
                            <integer>0</integer>
                            <key>Allowed</key>
                            <integer>1</integer>
                        </dict>
                    </array>
                </dict>
            </dict>
        </array>
    </dict>
</plist>
```

<span data-ttu-id="3ac66-169">確認上述檔案是否已正確複製。</span><span class="sxs-lookup"><span data-stu-id="3ac66-169">Verify that the above file was copied correctly.</span></span> <span data-ttu-id="3ac66-170">從終端執行下列命令，並確認其輸出 `OK` ：</span><span class="sxs-lookup"><span data-stu-id="3ac66-170">From the Terminal, run the following command and verify that it outputs `OK`:</span></span>

```bash
$ plutil -lint sysext.xml
sysext.xml: OK
```

<span data-ttu-id="3ac66-171">若要部署此自訂設定檔：</span><span class="sxs-lookup"><span data-stu-id="3ac66-171">To deploy this custom configuration profile:</span></span>

1.  <span data-ttu-id="3ac66-172">在 Intune 中，開啟 [**管理**  >  **裝置** 設定]。</span><span class="sxs-lookup"><span data-stu-id="3ac66-172">In Intune, open **Manage** > **Device configuration**.</span></span> <span data-ttu-id="3ac66-173">選取 [**管理**  >  **設定檔**  >  **建立設定檔**]。</span><span class="sxs-lookup"><span data-stu-id="3ac66-173">Select **Manage** > **Profiles** > **Create profile**.</span></span>
2. <span data-ttu-id="3ac66-174">選擇設定檔的名稱。</span><span class="sxs-lookup"><span data-stu-id="3ac66-174">Choose a name for the profile.</span></span> <span data-ttu-id="3ac66-175">變更 **平臺 = macOS** 和 **配置檔案類型 = 自訂**。</span><span class="sxs-lookup"><span data-stu-id="3ac66-175">Change **Platform=macOS** and **Profile type=Custom**.</span></span> <span data-ttu-id="3ac66-176">選取 [ **設定**]。</span><span class="sxs-lookup"><span data-stu-id="3ac66-176">Select **Configure**.</span></span>
3.  <span data-ttu-id="3ac66-177">開啟設定設定檔，並上傳 **sysext.xml**。</span><span class="sxs-lookup"><span data-stu-id="3ac66-177">Open the configuration profile and upload **sysext.xml**.</span></span> <span data-ttu-id="3ac66-178">此檔案是在上述步驟中建立的。</span><span class="sxs-lookup"><span data-stu-id="3ac66-178">This file was created in the preceding step.</span></span>
4.  <span data-ttu-id="3ac66-179">選取 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="3ac66-179">Select **OK**.</span></span>

    ![Intune 螢幕擷取畫面中的系統擴充](images/mac-system-extension-intune.png)

5. <span data-ttu-id="3ac66-181">在 [索引標籤 `Assignments` ] 中，將此設定檔指派給所有 **使用者 & 所有裝置**。</span><span class="sxs-lookup"><span data-stu-id="3ac66-181">In the `Assignments` tab, assign this profile to **All Users & All devices**.</span></span>
6. <span data-ttu-id="3ac66-182">複查和建立此設定設定檔。</span><span class="sxs-lookup"><span data-stu-id="3ac66-182">Review and create this configuration profile.</span></span>
