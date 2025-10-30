# darkly

## Darkly VM Setup Guide

### Goal

Download the Darkly ISO, create a VirtualBox VM, attach the ISO, and configure a bridged network so the VM and your host appear on the same LAN (same subnet) and can reach each other directly.

To download Darkly iso, <a href="https://cdn.intra.42.fr/isos/Darkly_i386.iso">click here</a>.

### Configuring a Bridged Network (VirtualBox) — Quick Instructions

Follow these steps to place the VM and host on the same LAN/subnet.

#### Configuration Steps

1. **Open VirtualBox → Settings** (for your VM where you installed darkly.iso image) → **Network**

2. **Adapter 1** → Enable Network Adapter
   - **Attached to:** Bridged Adapter
   - **Name:** Select your host's physical interface (e.g., eth0, enp3s0, Wi-Fi)
   - **Promiscuous Mode:** Deny (or Allow VMs if needed)
   - **Cable Connected:** Checked

3. **Click OK/Save**

4. **Start the VM**

5. **Access the darkly_IP_Adress in your web browser**

<p align="center">
  <img src="prerequisites/darkly_img.png" width="800">
</p>

#### Network Configuration

- If the VM uses DHCP, it should obtain an IP from the same network as the host.
- If necessary, configure a static IP in the VM (gateway and netmask must match the host network).

> [!TIP]
> Use the exact same network for the local machine and the VM. Don't use a VPN. <br>
> Access the site in **HTTP**.

## Flag 01 - Parameter Tampering - I forgot my password
Refs:<br>
[Web_Parameter_Tampering](https://owasp.org/www-community/attacks/Web_Parameter_Tampering)

[Test_Integrity_Checks](https://owasp.org/www-project-web-security-testing-guide/latest/4-Web_Application_Security_Testing/10-Business_Logic_Testing/03-Test_Integrity_Checks)

## Flag 02 - Exposure of sensitive files - /robots.txt & /admin panel
Refs:<br>
[Review_Webserver_Metafiles_for_Information_Leakage](https://owasp.org/www-project-web-security-testing-guide/latest/4-Web_Application_Security_Testing/01-Information_Gathering/03-Review_Webserver_Metafiles_for_Information_Leakage)

[Insecure_Direct_Object_References](https://owasp.org/www-project-web-security-testing-guide/latest/4-Web_Application_Security_Testing/05-Authorization_Testing/04-Testing_for_Insecure_Direct_Object_References)

## Flag 03 - Cookie Tampering - I_am_admin
Refs:<br>
[Session_Management_Cheat_Sheet](https://cheatsheetseries.owasp.org/cheatsheets/Session_Management_Cheat_Sheet.html#cookies)

[Cookie_Theft_Mitigation_Cheat_Sheet](https://cheatsheetseries.owasp.org/cheatsheets/Cookie_Theft_Mitigation_Cheat_Sheet.html)

## Flag 04 - UNION-based SQL Injection - Image number
Refs:<br>
[examining-the-database](https://portswigger.net/web-security/sql-injection/examining-the-database)

[union-based-injection](https://hackviser.com/tactics/pentesting/web/sql-injection#union-based-injection)

[SQL_Injection_Prevention_Cheat_Sheet](https://cheatsheetseries.owasp.org/cheatsheets/SQL_Injection_Prevention_Cheat_Sheet.html)

## Flag 05 - UNION-based SQL Injection - Search Member by ID
Refs:<br>
[examining-the-database](https://portswigger.net/web-security/sql-injection/examining-the-database)

[union-based-injection](https://hackviser.com/tactics/pentesting/web/sql-injection#union-based-injection)

[SQL_Injection_Prevention_Cheat_Sheet](https://cheatsheetseries.owasp.org/cheatsheets/SQL_Injection_Prevention_Cheat_Sheet.html)

## Flag 06 - Directory Traversal - URL Route http://darklyIPaddress/../../
Refs:<br>
[Path_Traversal](https://owasp.org/www-community/attacks/Path_Traversal)

[file-path-traversal](https://portswigger.net/web-security/file-path-traversal)

[01-Testing_Directory_Traversal_File_Include](https://owasp.org/www-project-web-security-testing-guide/latest/4-Web_Application_Security_Testing/05-Authorization_Testing/01-Testing_Directory_Traversal_File_Include)

## Flag 07 - Unrestricted file upload - Submit Image with php code integrated
Refs:<br>
[File_Upload_Cheat_Sheet](https://cheatsheetseries.owasp.org/cheatsheets/File_Upload_Cheat_Sheet.html)

[file-upload](https://portswigger.net/web-security/file-upload)

[Unrestricted_File_Upload](https://owasp.org/www-community/vulnerabilities/Unrestricted_File_Upload)

## Flag 08 - Login page BruteForce
## Flag 09 - Leave a feedback -> script XSS
## Flag 10 - Open Redirect - Check Homepage source Code
Refs:<br>
[Testing_for_Client_Side_URL_Redirect](https://owasp.org/www-project-web-security-testing-guide/v41/4-Web_Application_Security_Testing/Client_Side_Testing/04-Testing_for_Client_Side_URL_Redirect)

[Unvalidated_Redirects_and_Forwards_Cheat_Sheet](https://cheatsheetseries.owasp.org/cheatsheets/Unvalidated_Redirects_and_Forwards_Cheat_Sheet.html)
