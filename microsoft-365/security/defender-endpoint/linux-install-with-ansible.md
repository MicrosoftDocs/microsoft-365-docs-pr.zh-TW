---
title: 使用 Ansible 在 Linux 上部署 Microsoft Defender for Endpoint
ms.reviewer: ''
description: 說明如何使用 Ansible 在 Linux 上部署 Microsoft Defender for Endpoint。
keywords: microsoft，defender，Microsoft Defender for Endpoint，linux，安裝，部署，卸載，puppet，ansible，linux，redhat，ubuntu，debian，sles，suse，centos
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 12ff9834e2853c1745c20847f869bc2cba4e082e
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/30/2021
ms.locfileid: "52114267"
---
# <a name="deploy-microsoft-defender-for-endpoint-on-linux-with-ansible"></a><span data-ttu-id="a00f5-104">使用 Ansible 在 Linux 上部署 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="a00f5-104">Deploy Microsoft Defender for Endpoint on Linux with Ansible</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="a00f5-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="a00f5-105">**Applies to:**</span></span>
- [<span data-ttu-id="a00f5-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="a00f5-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="a00f5-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a00f5-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="a00f5-108">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="a00f5-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="a00f5-109">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="a00f5-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="a00f5-110">本文說明如何使用 Ansible 在 Linux 上部署 Defender for Endpoint。</span><span class="sxs-lookup"><span data-stu-id="a00f5-110">This article describes how to deploy Defender for Endpoint on Linux using Ansible.</span></span> <span data-ttu-id="a00f5-111">成功的部署需要完成下列所有工作：</span><span class="sxs-lookup"><span data-stu-id="a00f5-111">A successful deployment requires the completion of all of the following tasks:</span></span>

- [<span data-ttu-id="a00f5-112">下載上架套件</span><span class="sxs-lookup"><span data-stu-id="a00f5-112">Download the onboarding package</span></span>](#download-the-onboarding-package)
- [<span data-ttu-id="a00f5-113">建立 Ansible YAML 檔案</span><span class="sxs-lookup"><span data-stu-id="a00f5-113">Create Ansible YAML files</span></span>](#create-ansible-yaml-files)
- [<span data-ttu-id="a00f5-114">部署</span><span class="sxs-lookup"><span data-stu-id="a00f5-114">Deployment</span></span>](#deployment)
- [<span data-ttu-id="a00f5-115">參考資料</span><span class="sxs-lookup"><span data-stu-id="a00f5-115">References</span></span>](#references)

## <a name="prerequisites-and-system-requirements"></a><span data-ttu-id="a00f5-116">必要條件和系統需求</span><span class="sxs-lookup"><span data-stu-id="a00f5-116">Prerequisites and system requirements</span></span>

<span data-ttu-id="a00f5-117">開始之前，請參閱 [適用于 Linux 頁面的主要 Defender for The Endpoint](microsoft-defender-endpoint-linux.md) ，以取得目前軟體版本的必要條件和系統需求的描述。</span><span class="sxs-lookup"><span data-stu-id="a00f5-117">Before you get started, see [the main Defender for Endpoint on Linux page](microsoft-defender-endpoint-linux.md) for a description of prerequisites and system requirements for the current software version.</span></span>

<span data-ttu-id="a00f5-118">此外，針對 Ansible 部署，您必須熟悉 Ansible 管理工作、Ansible 設定，以及瞭解如何部署行動手冊和工作。</span><span class="sxs-lookup"><span data-stu-id="a00f5-118">In addition, for Ansible deployment, you need to be familiar with Ansible administration tasks, have Ansible configured, and know how to deploy playbooks and tasks.</span></span> <span data-ttu-id="a00f5-119">Ansible 有許多方式可完成相同的工作。</span><span class="sxs-lookup"><span data-stu-id="a00f5-119">Ansible has many ways to complete the same task.</span></span> <span data-ttu-id="a00f5-120">這些指示假設支援的 Ansible 模組（如 *apt* 和 *unarchive* ）可用，以協助部署套件。</span><span class="sxs-lookup"><span data-stu-id="a00f5-120">These instructions assume availability of supported Ansible modules, such as *apt* and *unarchive* to help deploy the package.</span></span> <span data-ttu-id="a00f5-121">您的組織可能會使用不同的工作流程。</span><span class="sxs-lookup"><span data-stu-id="a00f5-121">Your organization might use a different workflow.</span></span> <span data-ttu-id="a00f5-122">如需詳細資訊，請參閱 [Ansible 檔](https://docs.ansible.com/) 。</span><span class="sxs-lookup"><span data-stu-id="a00f5-122">Refer to the [Ansible documentation](https://docs.ansible.com/) for details.</span></span>

- <span data-ttu-id="a00f5-123">Ansible 必須安裝在至少一部電腦上 (Ansible 呼叫此控制項節點) 。</span><span class="sxs-lookup"><span data-stu-id="a00f5-123">Ansible needs to be installed on at least one computer (Ansible calls this the control node).</span></span>
- <span data-ttu-id="a00f5-124">您必須為系統管理員帳戶設定 SSH，以供在其上安裝 (已安裝 Defender 端點的裝置) ，並且建議使用公開金鑰驗證加以設定。</span><span class="sxs-lookup"><span data-stu-id="a00f5-124">SSH must be configured for an administrator account between the control node and all managed nodes (devices that will have Defender for Endpoint installed on them), and it is recommended to be configured with public key authentication.</span></span>
- <span data-ttu-id="a00f5-125">您必須在所有受管理的節點上安裝下列軟體：</span><span class="sxs-lookup"><span data-stu-id="a00f5-125">The following software must be installed on all managed nodes:</span></span>
  - <span data-ttu-id="a00f5-126">捲曲</span><span class="sxs-lookup"><span data-stu-id="a00f5-126">curl</span></span>
  - <span data-ttu-id="a00f5-127">python-apt</span><span class="sxs-lookup"><span data-stu-id="a00f5-127">python-apt</span></span>

- <span data-ttu-id="a00f5-128">所有受管理的節點都必須在或相關檔案中以下列格式列出 `/etc/ansible/hosts` ：</span><span class="sxs-lookup"><span data-stu-id="a00f5-128">All managed nodes must be listed in the following format in the `/etc/ansible/hosts` or relevant file:</span></span>

    ```bash
    [servers]
    host1 ansible_ssh_host=10.171.134.39
    host2 ansible_ssh_host=51.143.50.51
    ```

- <span data-ttu-id="a00f5-129">Ping 測試：</span><span class="sxs-lookup"><span data-stu-id="a00f5-129">Ping test:</span></span>

    ```bash
    ansible -m ping all
    ```

## <a name="download-the-onboarding-package"></a><span data-ttu-id="a00f5-130">下載上架套件</span><span class="sxs-lookup"><span data-stu-id="a00f5-130">Download the onboarding package</span></span>

<span data-ttu-id="a00f5-131">從 Microsoft Defender 資訊安全中心下載上架套件：</span><span class="sxs-lookup"><span data-stu-id="a00f5-131">Download the onboarding package from Microsoft Defender Security Center:</span></span>

1. <span data-ttu-id="a00f5-132">在 Microsoft Defender 資訊安全中心中，移至 **設定 > 裝置管理 > 上架**。</span><span class="sxs-lookup"><span data-stu-id="a00f5-132">In Microsoft Defender Security Center, go to **Settings > Device Management > Onboarding**.</span></span>
2. <span data-ttu-id="a00f5-133">在第一個下拉式功能表中，選取 [ **Linux 伺服器** ] 做為作業系統。</span><span class="sxs-lookup"><span data-stu-id="a00f5-133">In the first drop-down menu, select **Linux Server** as the operating system.</span></span> <span data-ttu-id="a00f5-134">在第二個下拉式功能表中，選取 **您偏好的 Linux 設定管理工具** 做為部署方法。</span><span class="sxs-lookup"><span data-stu-id="a00f5-134">In the second drop-down menu, select **Your preferred Linux configuration management tool** as the deployment method.</span></span>
3. <span data-ttu-id="a00f5-135">選取 [ **下載上架] 套件**。</span><span class="sxs-lookup"><span data-stu-id="a00f5-135">Select **Download onboarding package**.</span></span> <span data-ttu-id="a00f5-136">將檔案儲存為 WindowsDefenderATPOnboardingPackage.zip。</span><span class="sxs-lookup"><span data-stu-id="a00f5-136">Save the file as WindowsDefenderATPOnboardingPackage.zip.</span></span>

    ![Microsoft Defender 資訊安全中心螢幕擷取畫面](images/atp-portal-onboarding-linux-2.png)

4. <span data-ttu-id="a00f5-138">在命令提示字元中，確認您有檔案。</span><span class="sxs-lookup"><span data-stu-id="a00f5-138">From a command prompt, verify that you have the file.</span></span> <span data-ttu-id="a00f5-139">解壓縮封存的內容：</span><span class="sxs-lookup"><span data-stu-id="a00f5-139">Extract the contents of the archive:</span></span>

    ```bash
    ls -l
    ```
    ```Output
    total 8
    -rw-r--r-- 1 test  staff  4984 Feb 18 11:22 WindowsDefenderATPOnboardingPackage.zip
    ```
    ```bash
    unzip WindowsDefenderATPOnboardingPackage.zip
    ```
    ```Output
    Archive:  WindowsDefenderATPOnboardingPackage.zip
    inflating: mdatp_onboard.json
    ```

## <a name="create-ansible-yaml-files"></a><span data-ttu-id="a00f5-140">建立 Ansible YAML 檔案</span><span class="sxs-lookup"><span data-stu-id="a00f5-140">Create Ansible YAML files</span></span>

<span data-ttu-id="a00f5-141">建立加入行動手冊或工作的子任務或角色檔案。</span><span class="sxs-lookup"><span data-stu-id="a00f5-141">Create a subtask or role files that contribute to an playbook or task.</span></span>

- <span data-ttu-id="a00f5-142">建立上架任務 `onboarding_setup.yml` ：</span><span class="sxs-lookup"><span data-stu-id="a00f5-142">Create the onboarding task, `onboarding_setup.yml`:</span></span>

    ```bash
    - name: Create MDATP directories
      file:
        path: /etc/opt/microsoft/mdatp/
        recurse: true
        state: directory
        mode: 0755
        owner: root
        group: root

    - name: Register mdatp_onboard.json
      stat:
        path: /etc/opt/microsoft/mdatp/mdatp_onboard.json
      register: mdatp_onboard

    - name: Extract WindowsDefenderATPOnboardingPackage.zip into /etc/opt/microsoft/mdatp
      unarchive:
        src: WindowsDefenderATPOnboardingPackage.zip
        dest: /etc/opt/microsoft/mdatp
        mode: 0600
        owner: root
        group: root
      when: not mdatp_onboard.stat.exists
    ```

- <span data-ttu-id="a00f5-143">新增適用于端點存放庫和金鑰的 Defender。</span><span class="sxs-lookup"><span data-stu-id="a00f5-143">Add the Defender for Endpoint repository and key.</span></span>

    <span data-ttu-id="a00f5-144">您可以從下列其中一個 (通道部署在 Linux 上的 Defender： *[通道]*) ：「內部人員 *-快*」、「 *預覽人員-緩慢*」或「 *生產*」。每個通道都會對應至 Linux 軟體存放庫。</span><span class="sxs-lookup"><span data-stu-id="a00f5-144">Defender for Endpoint on Linux can be deployed from one of the following channels (denoted below as *[channel]*): *insiders-fast*, *insiders-slow*, or *prod*. Each of these channels corresponds to a Linux software repository.</span></span>

    <span data-ttu-id="a00f5-145">通道選擇會決定提供給裝置的更新類型及頻率。</span><span class="sxs-lookup"><span data-stu-id="a00f5-145">The choice of the channel determines the type and frequency of updates that are offered to your device.</span></span> <span data-ttu-id="a00f5-146">在內部版本中的裝置 *快* 用的第一種方法是接收更新及新功能，然後是上一個程式 *-速度慢* ，最後透過 *生產*。</span><span class="sxs-lookup"><span data-stu-id="a00f5-146">Devices in *insiders-fast* are the first ones to receive updates and new features, followed later by *insiders-slow* and lastly by *prod*.</span></span>

    <span data-ttu-id="a00f5-147">為了預覽新功能並提供及早的意見反應，建議您將企業中的部分裝置設定為使用 *預覽人員-快* 或內部的 *速度緩慢*。</span><span class="sxs-lookup"><span data-stu-id="a00f5-147">In order to preview new features and provide early feedback, it is recommended that you configure some devices in your enterprise to use either *insiders-fast* or *insiders-slow*.</span></span>

    > [!WARNING]
    > <span data-ttu-id="a00f5-148">初次安裝後切換通道需要重新安裝產品。</span><span class="sxs-lookup"><span data-stu-id="a00f5-148">Switching the channel after the initial installation requires the product to be reinstalled.</span></span> <span data-ttu-id="a00f5-149">若要切換產品通道，請執行下列動作：卸載現有的套件、重新設定裝置以使用新通道，然後依照此檔中的步驟，從新位置安裝套件。</span><span class="sxs-lookup"><span data-stu-id="a00f5-149">To switch the product channel: uninstall the existing package, re-configure your device to use the new channel, and follow the steps in this document to install the package from the new location.</span></span>

    <span data-ttu-id="a00f5-150">請記下您的發行及版本，並為其指定最接近的專案 `https://packages.microsoft.com/config/` 。</span><span class="sxs-lookup"><span data-stu-id="a00f5-150">Note your distribution and version and identify the closest entry for it under `https://packages.microsoft.com/config/`.</span></span>

    <span data-ttu-id="a00f5-151">在下列命令中，將 *[distro]* 和 *[version]* 取代為您識別的資訊。</span><span class="sxs-lookup"><span data-stu-id="a00f5-151">In the following commands, replace *[distro]* and *[version]* with the information you've identified.</span></span>

    > [!NOTE]
    > <span data-ttu-id="a00f5-152">如果是 Oracle Linux，請將 *[distro]* 取代為 "rhel"。</span><span class="sxs-lookup"><span data-stu-id="a00f5-152">In case of Oracle Linux, replace *[distro]* with “rhel”.</span></span>

  ```bash
  - name: Add Microsoft APT key
    apt_key:
      keyserver: https://packages.microsoft.com/
      id: BC528686B50D79E339D3721CEB3E94ADBE1229CF
    when: ansible_os_family == "Debian"

  - name: Add Microsoft apt repository for MDATP
    apt_repository:
      repo: deb [arch=arm64,armhf,amd64] https://packages.microsoft.com/[distro]/[version]/prod [channel] main
      update_cache: yes
      state: present
      filename: microsoft-[channel].list
    when: ansible_os_family == "Debian"

  - name: Add Microsoft DNF/YUM key
    rpm_key:
      state: present
      key: https://packages.microsoft.com/keys/microsoft.asc
    when: ansible_os_family == "RedHat"

  - name: Add  Microsoft yum repository for MDATP
    yum_repository:
      name: packages-microsoft-com-prod-[channel]
      description: Microsoft Defender for Endpoint
      file: microsoft-[channel]
      baseurl: https://packages.microsoft.com/[distro]/[version]/[channel]/
      gpgcheck: yes
      enabled: Yes
    when: ansible_os_family == "RedHat"
  ```

- <span data-ttu-id="a00f5-153">建立 Ansible 安裝和卸載 YAML 檔案。</span><span class="sxs-lookup"><span data-stu-id="a00f5-153">Create the Ansible install and uninstall YAML files.</span></span>

    - <span data-ttu-id="a00f5-154">針對 apt 發行使用下列 YAML 檔案：</span><span class="sxs-lookup"><span data-stu-id="a00f5-154">For apt-based distributions use the following YAML file:</span></span>

        ```bash
        cat install_mdatp.yml
        ```
        ```Output
        - hosts: servers
          tasks:
            - include: ../roles/onboarding_setup.yml
            - include: ../roles/add_apt_repo.yml
            - name: Install MDATP
              apt:
                name: mdatp
                state: latest
                update_cache: yes
        ```

        ```bash
        cat uninstall_mdatp.yml
        ```
        ```Output
        - hosts: servers
          tasks:
            - name: Uninstall MDATP
              apt:
                name: mdatp
                state: absent
        ```

    - <span data-ttu-id="a00f5-155">針對 dnf 發行使用下列 YAML 檔案：</span><span class="sxs-lookup"><span data-stu-id="a00f5-155">For dnf-based distributions use the following YAML file:</span></span>

        ```bash
        cat install_mdatp_dnf.yml
        ```
        ```Output
        - hosts: servers
          tasks:
            - include: ../roles/onboarding_setup.yml
            - include: ../roles/add_yum_repo.yml
            - name: Install MDATP
              dnf:
                name: mdatp
                state: latest
                enablerepo: packages-microsoft-com-prod-[channel]
        ```

        ```bash
        cat uninstall_mdatp_dnf.yml
        ```
        ```Output
        - hosts: servers
          tasks:
            - name: Uninstall MDATP
              dnf:
                name: mdatp
                state: absent
        ```

## <a name="deployment"></a><span data-ttu-id="a00f5-156">部署</span><span class="sxs-lookup"><span data-stu-id="a00f5-156">Deployment</span></span>

<span data-ttu-id="a00f5-157">現在執行任務檔案 `/etc/ansible/playbooks/` 或相關目錄。</span><span class="sxs-lookup"><span data-stu-id="a00f5-157">Now run the tasks files under `/etc/ansible/playbooks/` or relevant directory.</span></span>

- <span data-ttu-id="a00f5-158">安裝：</span><span class="sxs-lookup"><span data-stu-id="a00f5-158">Installation:</span></span>

    ```bash
    ansible-playbook /etc/ansible/playbooks/install_mdatp.yml -i /etc/ansible/hosts
    ```

> [!IMPORTANT]
> <span data-ttu-id="a00f5-159">產品第一次啟動時，會下載最新的反惡意程式碼定義。</span><span class="sxs-lookup"><span data-stu-id="a00f5-159">When the product starts for the first time, it downloads the latest antimalware definitions.</span></span> <span data-ttu-id="a00f5-160">視您的網際網路連線而定，這可能需要幾分鐘的時間。</span><span class="sxs-lookup"><span data-stu-id="a00f5-160">Depending on your Internet connection, this can take up to a few minutes.</span></span>

- <span data-ttu-id="a00f5-161">驗證/設定：</span><span class="sxs-lookup"><span data-stu-id="a00f5-161">Validation/configuration:</span></span>

    ```bash
    ansible -m shell -a 'mdatp connectivity test' all
    ```
    ```bash
    ansible -m shell -a 'mdatp health' all
    ```

- <span data-ttu-id="a00f5-162">卸載：</span><span class="sxs-lookup"><span data-stu-id="a00f5-162">Uninstallation:</span></span>

    ```bash
    ansible-playbook /etc/ansible/playbooks/uninstall_mdatp.yml -i /etc/ansible/hosts
    ```

## <a name="log-installation-issues"></a><span data-ttu-id="a00f5-163">記錄安裝問題</span><span class="sxs-lookup"><span data-stu-id="a00f5-163">Log installation issues</span></span>

<span data-ttu-id="a00f5-164">如需如何找到錯誤發生時所建立的自動產生記錄，請參閱 [記錄安裝的問題](linux-resources.md#log-installation-issues) 。</span><span class="sxs-lookup"><span data-stu-id="a00f5-164">See [Log installation issues](linux-resources.md#log-installation-issues) for more information on how to find the automatically generated log that is created by the installer when an error occurs.</span></span>

## <a name="operating-system-upgrades"></a><span data-ttu-id="a00f5-165">作業系統升級</span><span class="sxs-lookup"><span data-stu-id="a00f5-165">Operating system upgrades</span></span>

<span data-ttu-id="a00f5-166">將作業系統升級為新的主要版本時，您必須先在 Linux 上卸載適用于 Endpoint 的 Defender，安裝升級，最後在裝置上重新設定 Linux 上的 Endpoint 的 Defender。</span><span class="sxs-lookup"><span data-stu-id="a00f5-166">When upgrading your operating system to a new major version, you must first uninstall Defender for Endpoint on Linux, install the upgrade, and finally reconfigure Defender for Endpoint on Linux on your device.</span></span>

## <a name="references"></a><span data-ttu-id="a00f5-167">參考</span><span class="sxs-lookup"><span data-stu-id="a00f5-167">References</span></span>

- [<span data-ttu-id="a00f5-168">新增或移除 YUM 存放庫</span><span class="sxs-lookup"><span data-stu-id="a00f5-168">Add or remove YUM repositories</span></span>](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/yum_repository_module.html)

- [<span data-ttu-id="a00f5-169">使用 dnf 套件管理員管理套件</span><span class="sxs-lookup"><span data-stu-id="a00f5-169">Manage packages with the dnf package manager</span></span>](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/dnf_module.html)

- [<span data-ttu-id="a00f5-170">新增和移除 APT 存放庫</span><span class="sxs-lookup"><span data-stu-id="a00f5-170">Add and remove APT repositories</span></span>](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/apt_repository_module.html)

- [<span data-ttu-id="a00f5-171">管理 apt-套件</span><span class="sxs-lookup"><span data-stu-id="a00f5-171">Manage apt-packages</span></span>](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/apt_module.html)
