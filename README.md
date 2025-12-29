# Google Chrome STIG-Compliant Managed Policy Configuration

## Overview
This policy file implements all required settings from the **DISA STIG Google Chrome Current Windows Security Technical Implementation Guide V2R8** (January 2023).

**Total Controls:** 43  
**Severity Breakdown:**
- High: 1
- Medium: 41
- Low: 1

---

## Deployment Methods

### Windows Group Policy
1. Download Chrome ADMX templates from Google
2. Import policies into Group Policy Management Console
3. Apply settings as documented below

### Chrome Enterprise (Cloud)
1. Upload the JSON file to Google Admin Console
2. Navigate to Devices > Chrome > Settings
3. Import managed browser policies

### Windows Registry (Standalone)
Deploy to: `HKLM\Software\Policies\Google\Chrome\`

### macOS
Place file at: `/Library/Managed Preferences/com.google.Chrome.plist`

### Linux
Place file at: `/etc/opt/chrome/policies/managed/policy.json`

---

## Policy Settings Reference

### HIGH Severity

| STIG ID | Vuln ID | Policy | Value | Description |
|---------|---------|--------|-------|-------------|
| DTBC-0056 | V-234701 | SSLVersionMin | "tls1.2" | Chrome must be configured to allow only TLS 1.2+ |

### MEDIUM Severity

| STIG ID | Vuln ID | Policy | Value | Description |
|---------|---------|--------|-------|-------------|
| DTBC-0001 | V-221558 | RemoteAccessHostFirewallTraversal | false | Firewall traversal from remote host must be disabled |
| DTBC-0002 | V-221559 | DefaultGeolocationSetting | 2 | Site tracking users location must be disabled |
| DTBC-0004 | V-221561 | DefaultPopupsSetting | 2 | Sites ability to show pop-ups must be disabled |
| DTBC-0005 | V-221562 | ExtensionInstallBlocklist | ["*"] | Extensions installation must be blocklisted by default |
| DTBC-0006 | V-221563 | ExtensionInstallAllowlist | [list] | Extensions approved for use must be allowlisted |
| DTBC-0007 | V-221564 | DefaultSearchProviderName | "Google Encrypted" | Default search providers name must be set |
| DTBC-0008 | V-221565 | DefaultSearchProviderSearchURL | https URL | Default search provider URL must use encryption |
| DTBC-0009 | V-221566 | DefaultSearchProviderEnabled | true | Default search provider must be enabled |
| DTBC-0011 | V-221567 | PasswordManagerEnabled | false | The Password Manager must be disabled |
| DTBC-0017 | V-221570 | BackgroundModeEnabled | false | Background processing must be disabled |
| DTBC-0020 | V-221571 | SyncDisabled | true | Google Data Synchronization must be disabled |
| DTBC-0021 | V-221572 | URLBlocklist | ["javascript://*"] | URL protocol schema javascript must be disabled |
| DTBC-0023 | V-221573 | CloudPrintProxyEnabled | false | Cloud print sharing must be disabled |
| DTBC-0025 | V-221574 | NetworkPredictionOptions | 2 | Network prediction must be disabled |
| DTBC-0026 | V-221575 | MetricsReportingEnabled | false | Metrics reporting to Google must be disabled |
| DTBC-0027 | V-221576 | SearchSuggestEnabled | false | Search suggestions must be disabled |
| DTBC-0029 | V-221577 | ImportSavedPasswords | false | Importing of saved passwords must be disabled |
| DTBC-0030 | V-221578 | IncognitoModeAvailability | 1 | Incognito mode must be disabled |
| DTBC-0037 | V-221579 | EnableOnlineRevocationChecks | true | Online revocation checks must be performed |
| DTBC-0038 | V-221580 | SafeBrowsingProtectionLevel | 1 or 2 | Safe Browsing must be enabled |
| DTBC-0039 | V-221581 | SavingBrowserHistoryDisabled | false | Browser history must be saved |
| DTBC-0045 | V-245539 | CookiesSessionOnlyForUrls | [] | Session only based cookies must be disabled |
| DTBC-0052 | V-221586 | AllowDeletingBrowserHistory | false | Deletion of browser history must be disabled |
| DTBC-0053 | V-221587 | PromptForDownloadLocation | true | Prompt for download location must be enabled |
| DTBC-0055 | V-221588 | DownloadRestrictions | 1 or 2 | Download restrictions must be configured |
| DTBC-0057 | V-221590 | SafeBrowsingExtendedReportingEnabled | false | Safe Browsing Extended Reporting must be disabled |
| DTBC-0058 | V-221591 | DefaultWebUsbGuardSetting | 2 | WebUSB must be disabled |
| DTBC-0060 | V-221592 | ChromeCleanupEnabled | false | Chrome Cleanup must be disabled |
| DTBC-0061 | V-221593 | ChromeCleanupReportingEnabled | false | Chrome Cleanup reporting must be disabled |
| DTBC-0063 | V-221594 | EnableMediaRouter | false | Google Cast must be disabled |
| DTBC-0064 | V-221595 | AutoplayAllowed | false | Autoplay must be disabled |
| DTBC-0065 | V-221596 | AutoplayAllowlist | [list] | URLs must be allowlisted for Autoplay use |
| DTBC-0066 | V-221597 | UrlKeyedAnonymizedDataCollectionEnabled | false | Anonymized data collection must be disabled |
| DTBC-0067 | V-221598 | WebRtcEventLogCollectionAllowed | false | Collection of WebRTC event logs must be disabled |
| DTBC-0069 | V-226401 | BrowserGuestModeEnabled | false | Guest Mode must be disabled |
| DTBC-0070 | V-226402 | AutofillCreditCardEnabled | false | AutoFill for credit cards must be disabled |
| DTBC-0071 | V-226403 | AutofillAddressEnabled | false | AutoFill for addresses must be disabled |
| DTBC-0072 | V-226404 | ImportAutofillFormData | false | Import AutoFill form data must be disabled |
| DTBC-0073 | V-241787 | DefaultWebBluetoothGuardSetting | 2 | Web Bluetooth API must be disabled |
| DTBC-0074 | V-245538 | QuicAllowed | false | Use of the QUIC protocol must be disabled |

### LOW Severity

| STIG ID | Vuln ID | Policy | Value | Description |
|---------|---------|--------|-------|-------------|
| DTBC-0068 | V-221599 | DeveloperToolsAvailability | 2 | Chrome development tools must be disabled |

---

## Value Reference

### DefaultGeolocationSetting / DefaultPopupsSetting
- 1 = Allow
- 2 = Do not allow (Block)
- 3 = Ask

### IncognitoModeAvailability
- 0 = Incognito mode available
- 1 = Incognito mode disabled
- 2 = Incognito mode forced

### NetworkPredictionOptions
- 0 = Predict network actions on any connection
- 1 = Predict network actions on non-cellular connections
- 2 = Do not predict network actions on any connection

### SafeBrowsingProtectionLevel
- 0 = No protection (not allowed by STIG)
- 1 = Standard protection
- 2 = Enhanced protection

### DownloadRestrictions
- 0 = No restrictions (not allowed by STIG)
- 1 = Block dangerous downloads
- 2 = Block potentially dangerous downloads
- 3 = Block all downloads

### DeveloperToolsAvailability
- 0 = Allow use of Developer Tools
- 1 = Allow use except for force-installed extensions
- 2 = Disallow use of Developer Tools

### DefaultWebUsbGuardSetting / DefaultWebBluetoothGuardSetting
- 2 = Do not allow any site to request access
- 3 = Allow sites to ask user for access

---

## Customization Notes

### Extension Allowlist
The `ExtensionInstallAllowlist` includes a sample extension ID. Replace with your organization's approved extensions:
```json
"ExtensionInstallAllowlist": [
  "extension_id_1",
    "extension_id_2"
    ]
    ```

    ### Search Provider
    Modify `DefaultSearchProviderName` and `DefaultSearchProviderSearchURL` for your preferred encrypted search provider:
    - Google: `https://www.google.com/search?q={searchTerms}`
    - Bing: `https://www.bing.com/search?q={searchTerms}`
    - DuckDuckGo: `https://duckduckgo.com/?q={searchTerms}`

    ### Autoplay Allowlist
    Customize `AutoplayAllowlist` for your organization's trusted domains:
    ```json
    "AutoplayAllowlist": ["[*.]mil", "[*.]gov", "[*.]yourdomain.com"]
    ```

    ---

    ## Manual Verification

    To verify policies are applied, navigate to `chrome://policy` in the browser and confirm all settings are correctly configured.

    ---

    ## Additional Requirements

    ### DTBC-0050 (V-221584)
    **The version of Google Chrome must be a supported version.**

    This is a manual check - ensure Chrome is updated to a currently supported version. Automate updates through enterprise management tools.

    ---

    ## References
    - DISA STIG: https://public.cyber.mil/stigs/
    - Chrome Enterprise Policy List: https://chromeenterprise.google/policies/
    - NIST 800-53: https://csrc.nist.gov/publications/detail/sp/800-53/rev-5/final
