若需身分識別基礎架構的其他建議，另請參閱「[先決條件](https://docs.microsoft.com/microsoft-365-enterprise/identity-access-policies#prerequisites)」(機器翻譯)。

<a name="crit-identity-user-groups"></a>
### <a name="required-all-users-groups-and-group-memberships-have-been-created"></a>必要：所有的使用者、群組和群組成員資格均已建立

您已建立使用者帳戶和群組，因此：

- 貴組織的員工和與貴組織合作的廠商、承包商及合作夥伴擁有在 Azure Active Directory (AD) 中相對應的使用者帳戶。
- Azure AD 群組和其成員包含適用於各種目的使用者帳戶和其他群組 (例如 Microsoft 雲端服務的安全性設定佈建、自動授權，與其他使用)。

如有需要，[步驟 1](../identity-plan-users-groups.md) 可協助您符合這項要求。

<a name="crit-identity-sync"></a>
### <a name="required-users-and-groups-are-synchronized-with-azure-ad"></a>必要：使用者和群組會與 Azure AD 同步處理

如果您有現有內部部署身分識別提供者 (例如 Windows Server Active Directory (AD))，您已使用 Azure AD Connect 以將從內部部署身分識別提供者的使用者帳戶和群組同步處理到 Azure AD 租用戶。

隨著將目錄同步處理，使用者可以使用他們用來登入電腦和存取內部部署資源所用的相同認證來登入 Office 365 和其他 Microsoft 雲端服務。

如有需要，[步驟 7](../identity-azure-ad-connect.md) 可協助您符合這項要求。

如果您略過這項要求，您將有兩組使用者帳戶和群組：

- 在您內部部署身分識別提供者中存在的使用者帳戶和群組
- Azure AD 租用戶中存在的使用者帳戶和群組

在此狀態中，IT 系統管理員和使用者都必須以手動方式維護這兩組使用者帳戶和群組。這難免會導致帳戶、密碼及群組不同步。

#### <a name="how-to-test"></a>如何測試
若要確認與內部部署認證的驗證運作正常，使用您的內部部署認證登入 Office 365 入口網站。

若要確認目錄同步處理是否運作正常，請執行以下動作：

1.  在 Windows Server AD 中建立新測試群組。
2.  等待同步處理的時間。
3.  檢查您的 Azure AD 租用戶以確認新測試群組名稱是否出現。

<a name="crit-identity-global-admin"></a>
### <a name="required-your-global-administrator-accounts-are-protected"></a>必要：全域系統管理員帳戶會受到保護 

您已[保護 Office 365 全域系統管理員帳戶](https://support.office.com/article/Protect-your-Office-365-global-administrator-accounts-6b4ded77-ac8d-42ed-8606-c014fd947560)，以避免可能會導致違反 Office 365 訂閱規定的洩露認證。

如果您略過這項要求，全域系統管理員帳戶可能會受到攻擊和洩露，讓攻擊者可以取得對您資料的系統範圍存取權，來進行蒐集、損毀，或要求贖金。

如有需要，[步驟 2](../identity-designate-protect-admin-accounts.md) 可協助您符合這項要求。

#### <a name="how-to-test"></a>如何測試

使用這些步驟來確認您已受保護全域系統管理員帳戶：

1. 在 PowerShell 命令提示字元執行下列 Azure AD V2 命令。您應該會看到僅專用全域系統管理員帳戶的清單。
   ```
   Get-AzureADDirectoryRole | where { $_.DisplayName -eq "Company Administrator" } | Get-AzureADDirectoryRoleMember | Ft DisplayName
   ```
2. 使用步驟 1 中的每個帳戶登入Office 365。每個登入必須要求多重要素驗證和您組織中可用的最強型次要驗證。

> [!Note]
> 請參閱[連線到 Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell) 以了解安裝 Azure AD V2 PowerShell 模組與登入 Office 365 的指示。

<a name="crit-identity-custom-sign-in"></a>
### <a name="optional-the-office-365-sign-in-screen-is-personalized-for-your-organization"></a>選用：已個人化您組織的 Office 365 登入畫面

您已使用「[將公司商標新增至登入及存取面板頁面](http://aka.ms/aadpaddbranding)」來將貴組織的商標新增至 Office 365 登入頁面。

如果您略過此選項，使用者會看到一般的 Office 365 登入畫面，並且可能無法確定它們登入的是貴組織的網站。

如有需要，[步驟 11](../identity-customize-office-365-sign-in.md) 可協助您使用此選項。

#### <a name="how-to-test"></a>如何測試

透過使用者帳戶名稱與多重要素驗證登入 Office 365 入口網站。您應會在登入頁面上看到您自訂的商標元素。

<a name="crit-identity-mfa"></a>
### <a name="optional-multi-factor-authentication-is-enabled-for-your-users"></a>選用：已為使用者啟用多重要素驗證

您已使用「[Office 365 部署多重要素驗證方案](https://support.office.com/article/Plan-for-multifactor-authentication-for-Office-365-Deployments-043807b2-21db-4d5c-b430-c8a6dee0e6ba)」與「[為 Office 365 使用者設定多重要素驗證](https://support.office.com/article/Set-up-multi-factor-authentication-for-Office-365-users-8f0454b2-f51a-4d9c-bcde-2c48e41621c6)」來啟用使用者帳戶的多重要素驗證 (MFA)。

如果您略過此選項，使用者帳戶會容易遭到網路攻擊所引起的認證洩露。若使用者帳戶的密碼洩露時，帳戶的所有資源和功能 (例如系統管理員角色) 皆可供攻擊者使用。這可讓攻擊者複製、損毀，或保留內部文件和其他資料以勒索贖金。

如有需要，[步驟 5](../identity-multi-factor-authentication.md) 可協助您使用此選項。

#### <a name="how-to-test"></a>如何測試

1.  在 Office 365 系統管理員入口網站中建立測試使用者帳戶並為它們指派授權。 
2.  使用您為實際使用者帳戶使用的其他驗證方法 (例如將郵件傳送給您的電話)，來為測試使用者帳戶設定多重要素驗證。 
3.  以測試使用者帳戶登入 Office 365 或 Azure 入口網站。
4.  請確認 MFA 會提示您輸入其他的驗證資訊，且結果為驗證成功。 
5.  刪除測試使用者帳戶。

<a name="crit-identity-sync-health"></a>
### <a name="optional-directory-synchronization-is-monitored"></a>選用：目錄同步處理已受到監控

您已使用 [Azure AD Connect Health 同步處理](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-sync) (適用於密碼同步處理) 或[使用 Azure AD Connect Health 搭配 AD FS](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs) (適用於同盟驗證) 並已部署 Azure AD Connect Health，其中包括：

- 在每個內部部署身分識別伺服器上安裝 Azure AD Connect Health 代理程式。
- 使用 Azure AD Connect Health 入口網站來監控正在進行的同步處理狀態。

如果您略過此選項時，則可以更精確地評估以雲端為基礎的身分識別基礎結構之狀態。

如有需要，[步驟 8](../identity-azure-ad-connect-health.md) 可協助您使用此選項。

#### <a name="how-to-test"></a>如何測試
Azure AD Connect Health 入口網站會顯示內部部署身分識別伺服器和進行中同步處理的目前和正確狀態。

<a name="crit-identity-pw-reset"></a>
### <a name="optional-users-can-reset-their-own-passwords"></a>選用：使用者可以重設自己的密碼

您已使用 [Azure AD 自助密碼重設快速部署](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-getting-started)來為您的使用者設定密碼重設。

如果您不符合此條件，使用者將依賴使用者帳戶的系統管理員重設密碼，造成其他 IT 系統管理員的負擔。

如有需要，[步驟 4](../identity-password-reset.md) 可協助您使用此選項。

#### <a name="how-to-test"></a>如何測試

1. 使用初始密碼建立測試使用者帳戶。
2. 使用「[讓使用者在 Office 365 中重設其自身密碼](https://support.office.com/article/Let-users-reset-their-own-passwords-in-Office-365-5bc3f460-13cc-48c0-abd6-b80bae72d04a)」中的步驟來重設對測試使用者帳戶的密碼。
3. 登出，然後再使用重設密碼登入測試使用者帳戶。
4. 刪除測試使用者帳戶。

<a name="crit-identity-pw-writeback"></a>
### <a name="optional-password-writeback-is-enabled-for-your-users"></a>選用：已為您的使用者啟用密碼回寫

您已使用在「[具密碼回寫的 Azure AD SSPR](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-getting-started)」中的指示，為您 Microsoft 365 企業版訂閱的 Azure AD 租用戶啟用密碼回寫。

如果您略過此選項，未連線到內部部署網路的使用者必須透過 IT 系統管理員重設或解除鎖定 Windows Server AD 密碼。

如有需要，[步驟 9](../identity-password-writeback.md) 可協助您使用此選項。

>[!Note]
>若要充分利用 Azure AD Identity Protection 功能 (例如當 Azure AD 已偵測到高風險的帳戶洩露時，要求使用者變更其內部部署密碼)，則需要密碼回寫。
>

#### <a name="how-to-test"></a>如何測試

您可以藉由在 Office 365 中變更密碼以測試密碼回寫。您應可使用自己的帳戶與新密碼，以存取內部部署 Windows Server AD 資源。

1. 在內部部署 Windows Server AD 中建立測試使用者帳戶，允許發生目錄同步處理，然後在 Office 365 系統管理員入口網站中授與該帳戶 Office 365 授權。
2. 透過加入您內部部署 Windows 伺服器 AD 網域的遠端電腦，使用測試使用者帳戶的認證來登入電腦與 Office 365 入口網站。
3. 選取 [設定] > [Office 365 設定] > [密碼] > [變更密碼]****。
4. 輸入目前的密碼並輸入新密碼，然後加以確認。
5. 登出 Office 365 入口網站與遠端電腦，然後以測試使用者帳戶與新密碼登入電腦。這證明您可以使用 Azure AD 租用戶變更內部部署 Windows 伺服器 AD 使用者帳戶的密碼。

<a name="crit-identity-sso"></a>
### <a name="optional-users-can-sign-in-using-single-sign-on"></a>選用：使用者可以使用單一登入來進行登入

您可以為您組織啟用 [Azure AD Connect：隨選即用單一登入](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start)，以簡化使用者登入以雲端為基礎之應用程式 (例如 Office 365) 的方式。

如果您略過此選項時，使用者存取其他使用 Azure AD 的應用程式時可能會收到提示，要求他們提供認證。

如有需要，[步驟 10](../identity-single-sign-on.md) 可協助您使用此選項。


<a name="crit-identity-group-license"></a>
### <a name="optional-group-based-licensing-to-automatically-assign-and-remove-licenses-to-user-accounts-based-on-group-membership"></a>選用：以群組為基礎的授權會根據群組成員資格，自動將授權指派至使用者帳戶和將其移除

您已為適當的 Azure AD 的安全性群組[啟用以群組為基礎的授權](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-group-assignment-azure-portal)，以便自動指派或移除 Office 365 和 EMS 的授權。

若您略過此選項，您必須手動進行以下動作：

- 將授權指派給您想要將 Office 365 和 EMS 存取權提供給其中的新使用者。
- 將授權從不再存在於您組織中或不需要存取 Office 365 和 EMS 的使用者中移除。

如有需要，[步驟 12](../identity-group-based-licensing.md) 可協助您使用此選項。

#### <a name="how-to-test"></a>如何測試

1. 在 Azure AD 中使用 Azure 入口網站建立測試安全性群組，並將以群組為基礎的授權設定為指派 Office 365 和 EMS 授權。
2. 在 Azure AD 中建立測試使用者帳戶，並將它新增到測試安全性群組。
3. 檢查 Office 365 系統管理員入口網站中的使用者帳戶內容，以確保其已指派至 Office 365 和 EMS 授權。
4. 從測試安全性群組移除測試使用者帳戶。
5. 檢查使用者帳戶內容，以確保其不再指派至 Office 365 和 EMS 授權。
6. 刪除測試安全性群組和測試使用者帳戶。

<a name="crit-identity-dyn-groups"></a>
### <a name="optional-dynamic-group-membership-settings-automatically-add-user-accounts-to-groups-based-on-user-account-attributes"></a>選用：動態群組成員資格設定會根據使用者帳戶屬性，自動將使用者帳戶新增至群組

您已決定一組 Azure AD 動態群組，並使用「[Azure Active Directory 中的以屬性為基礎的動態群組成員資格](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal)」中的指示來建立群組與規則，以便判斷適用於群組成員資格的一組使用者帳戶屬性和值。

如果您略過此選項時，必須以手動方式完成群組成員資格，因為已新增數個帳戶或使用者帳戶屬性隨著時間而變更。比方說，如果有人從銷售部門調到會計部門時，您必須：

- 更新該使用者帳戶的部門屬性值。
- 手動將它們從銷售群組中移除。
- 手動將它們新增至會計群組。

如果銷售和會計群組是動態的，您只需要變更使用者帳戶的部門值。

如有需要，[步驟 15](../identity-automatic-group-membership.md) 可協助您使用此選項。

#### <a name="how-to-test"></a>如何測試

1. 使用 Azure 入口網站在 Azure AD 中建立測試動態群組並設定部門等於「test1」的規則。
2. 在 Azure AD 中建立測試使用者帳戶，並將部門屬性設定為「test1」。
3. 檢查使用者帳戶的內容，以確定它成為測試動態群組的成員。
4. 將測試使用者帳戶的部門屬性值變為「test2」。
5. 檢查使用者帳戶的內容，以確定它不再是測試動態群組的成員。
6. 刪除測試動態群組和測試使用者帳戶。

<a name="crit-identity-self-service-groups"></a>
### <a name="optional-self-service-group-management-is-enabled-for-specific-azure-ad-security-and-office-365-groups"></a>選用：已啟用特定 Azure AD 的安全性和 Office 365 群組的自助群組管理

您已決定哪些群組適用於自助管理，指示其擁有者關於群組管理工作流程和責任，並為這些群組[設定 Azure AD 中的自助管理](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-self-service-group-management)。

如果您略過此選項時，所有 Azure AD 群組管理工作必須由 IT 系統管理員執行。

如有需要，[步驟 14](../identity-self-service-group-management.md) 可協助您使用此選項。

#### <a name="how-to-test"></a>如何測試
1.  使用 Azure 入口網站在 Azure AD 中建立測試使用者帳戶。
2.  使用測試使用者帳戶登入並建立測試 Azure AD 安全性群組。
3.  登出，然後使用您的 IT 系統管理員帳戶登入。
4.  為測試使用者帳戶設定自助管理的測試安全性群組。
5.  登出，然後使用您的測試使用者帳戶登入。
6.  使用 Azure 入口網站以將成員新增至測試安全性群組。
7.  刪除測試安全性群組和測試使用者帳戶。

<a name="crit-identity-ident-prot"></a>
### <a name="optional-azure-ad-identity-protection-is-enabled-to-protect-against-credential-compromise"></a>選用：已啟用 Azure AD Identity Protection 來防護認證洩露

您已啟用 Azure AD Identity Protection 來：

- 解決潛在的身分識別弱點。
- 偵測可能的認證洩露嘗試。
- 調查並解決持續的可疑身分識別事件。

如果您略過此選項，您將無法偵測或自動抵禦認證洩露嘗試或調查與身分識別相關的安全性事件。這可能會使您的組織憑證洩露並對貴組織的機密資料產生威脅。

如有需要，[步驟 6](../identity-azure-ad-identity-protection.md) 可協助您使用此選項。

<a name="crit-identity-pim"></a>
### <a name="optional-you-have-set-up-privileged-identity-management-to-support-on-demand-assignment-of-the-global-administrator-role"></a>選用：您已設定特殊權限的身分識別管理來支援全域系統管理員角色的隨選指派

您已使用「[設定 Azure AD Privileged Identity Management](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure)」中的指示，以啟用 Azure AD 租用戶中的 PIM 並將您的全域系統管理員帳戶設定為合格的系統管理員。

您也使用「[保護 Azure AD 中混合式和雲端部署的特殊存取權](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices)」中的建議，以開發可保護特殊存取權避免受到網路攻擊的藍圖。

如果您略過此選項時，全域系統管理員帳戶可能會受到持續線上攻擊，且機密資訊洩露時，可能會讓攻擊者蒐集、損毀，或保留您的機密資訊，以勒索贖金。

如有需要，[步驟 3](../identity-azure-ad-identity-protection.md) 可協助您使用此選項。
