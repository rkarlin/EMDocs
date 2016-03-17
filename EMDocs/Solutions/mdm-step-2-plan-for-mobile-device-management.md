---
title: Step 2 - Plan for mobile device management
ms.custom: na
ms.reviewer: na
ms.service: multiple
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 3cdc1318-50a2-4280-b051-1e009620816e
author: robmazz
---
# Step 2 - Plan for mobile device management

>[Note!]
>This topic is part of a larger design considerations guide. If you'd like to start at the beginning of the guide, check out the [main topic](mdm-design-considerations-guide.md). To get a downloadable copy of this entire guide, visit the [TechNet Gallery](https://gallery.technet.microsoft.com/Mobile-Device-Management-7d401582).

Managing mobile devices, both company-owned and user-owned, encompasses several important lifecycle management decisions. After you’ve determined the mobile device platform, application, and user requirements for your organization, you’ll also need to identify how to manage each of these areas in a way that aligns your overall MDM strategy with other management and support policies. In this step, we’ll examine the MDM enrollment, management, monitoring, and reporting lifecycle requirements.



   


</section></sections></section><section>
<title>Task 4: Define your mobile device management lifecycle strategy</title><content><para>In this task, you’ll refine the mobile device management lifecycle strategy to meet the management requirements you identified in Tasks 1-3.</para></content>
<sections><section>


<title>Task 4c: Device management options</title><content><para>Managing mobile devices with <token>Intune</token> and <token>ConfigMgr</token> centers around management policies. Policies define groups of settings for mobile devices and can be either created from templates or customized for specific devices, users, or groups. The best management practice is to create management policies before mobile devices are enrolled in the management solution. This insures that the devices are immediately managed in accordance with the policies and processes defined in your IT strategy. Both solutions allow for configuring the following policy types:</para><list class="bullet"><listItem><para><legacyBold>Configuration policies:</legacyBold> Configuration policies are used to define the general organizational settings for each enrolled mobile device. This may include device password, application, cloud policy, and encryption settings, but can include <externalLink target="_blank"><linkText>many other device settings</linkText><linkUri>https://technet.microsoft.com/library/dn743712.aspx</linkUri></externalLink> for different management areas. Additionally, configuration policies are applied and configured differently for different types of mobile device operating systems by using device enrollment profiles.</para><alert class="note">
 <para>When creating different policies for different types of devices, users, or groups – it’s easy to have conflicting policy settings applied to the same device. Be sure that you understand <externalLink><linkText>how conflicting policy settings are applied</linkText><linkUri>https://technet.microsoft.com/library/dn743712.aspx</linkUri></externalLink>.</para>
</alert></listItem><listItem><para><legacyBold>Compliance policies: </legacyBold>Compliance policies enforce your organization’s requirements for mobile devices to access (or be denied access) to company resources or services. This can also include device password and encryption settings, as well as determining if the mobile device is rooted (“jailbroken”). As with configuration policies, <token>Intune</token> and <externalLink target="_blank"><linkText>ConfigMgr</linkText><linkUri>https://technet.microsoft.com/library/dn376523.aspx</linkUri></externalLink> compliance policy options also vary by mobile device operating system type. If you’re creating compliance policies in <token>ConfigMgr</token>, it’s important to note that increased granularity can be configured as part of a multi-part process: </para><list class="bullet"><listItem><para>Creating <externalLink target="_blank"><linkText>configuration items</linkText><linkUri>https://technet.microsoft.com/library/gg712331.aspx?WT.mc_id=Blog_EntMob_Showcase_PCIT</linkUri></externalLink></para></listItem><listItem><para>Creating <externalLink target="_blank"><linkText>configuration baselines</linkText><linkUri>https://technet.microsoft.com/library/gg712268.aspx?WT.mc_id=Blog_EntMob_Showcase_PCIT</linkUri></externalLink></para></listItem><listItem><para><externalLink target="_blank"><linkText>Deploying the configuration baselines</linkText><linkUri>https://technet.microsoft.com/library/hh219289.aspx?WT.mc_id=Blog_EntMob_Showcase_PCIT</linkUri></externalLink> to <token>ConfigMgr</token> user or device collections</para></listItem></list></listItem><listItem><para><legacyBold>Conditional access policies:</legacyBold> Conditional access policies define how access to email is managed and can be used separately or in conjunction with compliance policies. Connections to your on-premises <token>Exchange Server</token> or <token>Exchange Online</token> service must be configured in <externalLink target="_blank"><linkText>Intune</linkText><linkUri>https://technet.microsoft.com/library/dn818907.aspx</linkUri></externalLink> or in <externalLink target="_blank"><linkText>ConfigMgr</linkText><linkUri>https://technet.microsoft.com/library/dn919655.aspx</linkUri></externalLink> before conditional access policies can be deployed. Conditional access can also be configured for <token>Office 365</token> and <token>SharePoint Online</token> services.</para></listItem></list><para>Your answers the questions in Task 1 can help you determine how you want devices to be enrolled in the mobile device management solution. Table 7 below will help you understand the advantages and disadvantages of each management scenario.</para><para><legacyBold>Table 7</legacyBold></para><table border="1"><thead><tr><TD><para>Management options</para></TD><TD><para>Advantages</para></TD><TD><para>Disadvantages</para></TD></tr></thead><tbody><tr><TD><para><token>Intune</token> (standalone)</para></TD><TD><list class="bullet"><listItem><para>•	Supports simplified policy control for managing users and devices, now separated by device platform. Supports Android, iOS, <externalLink><linkText>Windows 10</linkText><linkUri>https://technet.microsoft.com/library/mt147406.aspx</linkUri></externalLink>, Windows 8.x, and Windows Phone platforms, as well as support for Exchange ActiveSync. </para></listItem><listItem><para>Provides a simple, web-based administration &amp; management console that is accessible from any location</para></listItem><listItem><para>Supports group-based policies, making it easier to manage large numbers and diverse types of mobile devices</para></listItem><listItem><para>Supports advanced mobile device compliance features and functionality, including device root and jailbreak detection</para></listItem><listItem><para>Allows for selective wipe or full factory reset for all mobile devices</para></listItem><listItem><para>Includes a customizable Company portal, allowing the managed and secure distribution of internal and 3rd party mobile applications</para></listItem><listItem><para>Deploy certificates to mobile devices</para></listItem><listItem><para>Allows organizations to prevent cut/copy/paste functions in mobile applications</para></listItem><listItem><para>Supports enforcing the use of managed browsers</para></listItem></list></TD><TD><list class="bullet"><listItem><para>Additional licensing requirements and costs for user accounts enrolling devices in the <token>Intune</token> service </para></listItem></list></TD></tr><tr><TD><para><token>MDM for Office 365</token></para></TD><TD><list class="bullet"><listItem><para>•	Integrated web-based administration and management console within Office 365 tenants</para></listItem><listItem><para>Supports group-based policies, making it easier to manage large numbers and diverse types of mobile devices</para></listItem><listItem><para>•	Supports advanced mobile device compliance features and functionality, including device root and jailbreak detection</para></listItem><listItem><para>•	Allows selective wipe or full factory reset for all mobile devices</para></listItem></list></TD><TD><list class="bullet"><listItem><para>•	Advanced mobile device management features aren’t supported, including:</para><list class="bullet"><listItem><para>Provisioning and managing certificates, email, VPN, wireless profiles</para></listItem><listItem><para>Enrolling and managing collections of devices</para></listItem></list></listItem><listItem><para>Some mobile application management features and functionality aren’t supported:</para><list class="bullet"><listItem><para>Deploying line of business applications to mobile devices</para></listItem><listItem><para>Enabling secure data access to Office mobile applications</para></listItem><listItem><para>Extending corporate data securely to line of business apps for mobile devices</para></listItem><listItem><para>Managed browsers or other content viewing applications</para></listItem></list></listItem></list></TD></tr><tr><TD><para>Hybrid (<token>Intune</token> with <token>ConfigMgr</token>)</para></TD><TD><list class="bullet"><listItem><para>All the advantages of <token>Intune</token> standalone, plus the following:</para><list class="bullet"><listItem><para>Provides a single pane of glass view for managing the corporate estate, including flexibility for role-based administration and scripting (through PowerShell)</para></listItem></list></listItem></list></TD><TD><list class="bullet"><listItem><para>Requires additional configuration to connect <token>Intune</token> with the on-premises <token>ConfigMgr</token> infrastructure</para></listItem><listItem><para>For organizations that don’t have a current <token>ConfigMgr</token> infrastructure configured, it will need to be planned, installed and configured prior to integrating with<token>Intune</token></para></listItem><listItem><para>VPN and email profiles for Android devices aren’t currently supported</para></listItem><listItem><para>Managed browser support isn’t currently supported</para></listItem></list></TD></tr></tbody></table></content>
</section><section>
<title>Task 4d: Device monitoring options</title><content><para>Monitoring and understanding the status and configuration of all mobile devices managed by your organization helps you discover problems and non-compliance, and manage device inventory. Without detailed reports on hardware, software, and compliance status, it’s impossible to make sure that your device policies are actually in place and working correctly. Proactive monitoring helps mitigate small problems before they become larger and more costly.</para><para><externalLink target="_blank"><linkText>Intune</linkText><linkUri>https://technet.microsoft.com/library/dn646951.aspx</linkUri></externalLink>, <externalLink target="_blank"><linkText>MDM for Office 365</linkText><linkUri>https://technet.microsoft.com/library/faa7d8e5-645d-4d59-839c-c8d4c1869e4a(v=technet.10).aspx</linkUri></externalLink>, and a <externalLink target="_blank"><linkText>hybrid deployment</linkText><linkUri>https://technet.microsoft.com/library/gg699377.aspx</linkUri></externalLink> of <token>Intune</token> and <token>ConfigMgr</token> all include monitoring and reporting to help manage devices, users, and compliance with your organization’s policies and procedures. Using built-in reports together with customized reports, you can monitor mobile device management in areas such as:</para><list class="bullet"><listItem><para>Update reports for software</para></listItem><listItem><para>Software inventory reports</para></listItem><listItem><para>Hardware inventory reports</para></listItem><listItem><para>Licensing reports</para></listItem><listItem><para>Non-compliance reports</para></listItem></list><para>Depending on how your infrastructure is set up, you may be able to create a variety of reports to help you monitor your organization. <token>Intune</token>-based monitoring and reporting capabilities are the backbone for reports in <token>MDM for Office 365</token>, as well as <token>Intune</token> standalone deployments. These reports can also be tightly integrated with the reporting capabilities of <token>ConfigMgr</token> when it’s connected to <token>Intune</token> in a hybrid deployment. Each product, as shown below, has different but complementary reporting capabilities. It’s important to explore the nuances of the reporting capabilities of each mobile device management solution to help make sure you choose a solution that has the reports that you need.</para><mediaLink>
<image xlink:href="1047aa81-9c0e-4e4b-8acc-53cc33b33d5a"/>
</mediaLink><para><legacyBold>Figure 5 – Integrated mobile device monitoring and reporting</legacyBold></para><para>The answers you gave to the questions in Task 2 can help you determine your monitoring and reporting needs for your mobile devices. Table 8 below shows the advantages and disadvantages of the monitoring and reporting features in each MDM solution.</para><para><legacyBold>Table 8</legacyBold></para><table border="1"><thead><tr><TD><para>Monitoring options</para></TD><TD><para>Advantages</para></TD><TD><para>Disadvantages</para></TD></tr></thead><tbody><tr><TD><para><token>Intune</token> (standalone)</para></TD><TD><list class="bullet"><listItem><para>Monitoring overview/dashboard</para></listItem><listItem><para>Alerts when errors are detected on direct managed network devices</para></listItem><listItem><para>An <token>Intune</token> service RSS feed can notify you about problems with the service and upcoming maintenance</para></listItem><listItem><para>Three levels of alerts (critical, warning, Informational) with thresholds and email alert notifications</para></listItem><listItem><para>Can filter alerts by device type</para></listItem><listItem><para>Can review the status of any managed device</para></listItem><listItem><para>Can monitor details in the following areas:</para><list class="bullet"><listItem><para>System</para></listItem><listItem><para>OS</para></listItem><listItem><para>Storage</para></listItem><listItem><para><token>Exchange ActiveSync</token></para></listItem><listItem><para>System enclosure</para></listItem><listItem><para>Network</para></listItem><listItem><para>Service</para></listItem></list></listItem></list></TD><TD><list class="bullet"><listItem><para>Email alerts only, no text-based or voice alerts</para></listItem></list></TD></tr><tr><TD><para><token>MDM for Office 365</token></para></TD><TD><list class="bullet"><listItem><para>Monitoring overview/dashboard</para></listItem><listItem><para>Three levels of alerts (critical, warning, Informational) with thresholds and email alert notifications</para></listItem><listItem><para>Can filter alerts by device type</para></listItem><listItem><para>Can review the status of any managed device</para></listItem></list></TD><TD><list class="bullet"><listItem><para>Mobile device compliance status reports only</para></listItem></list></TD></tr><tr><TD><para>Hybrid (<token>Intune</token> with <token>ConfigMgr</token>)</para></TD><TD><list class="bullet"><listItem><para>All the monitoring and reporting features of <token>Intune</token> standalone, plus the following:</para><list class="bullet"><listItem><para>Comprehensive, threshold-based, consolidated monitoring and reporting for all your organization’s devices, including non-mobile and non-<token>Intune</token> enrolled devices</para></listItem><listItem><para>Advanced reporting capabilities of SQL Server Reporting Services (SSRS) and the rich authoring experience provided by Reporting Services Report Builder</para></listItem></list></listItem></list></TD><TD><list class="bullet"><listItem><para>Requires additional configuration to connect <token>Intune</token> with the on-premises <token>ConfigMgr</token> infrastructure</para></listItem><listItem><para>For organizations that don’t have a current <token>ConfigMgr</token> infrastructure configured, it will need to be planned, installed and configured prior to integrating with <token>Intune</token></para></listItem></list></TD></tr></tbody></table><para>Explore the details about mobile device monitoring options by reviewing the following:</para><list class="bullet"><listItem><para><token>Intune</token>: How to <externalLink target="_blank"><linkText>monitor mobile devices</linkText><linkUri>https://technet.microsoft.com/library/jj733634.aspx</linkUri></externalLink> and <externalLink target="_blank"><linkText>manage reporting</linkText><linkUri>https://technet.microsoft.com/library/dn646951.aspx</linkUri></externalLink></para></listItem><listItem><para><token>ConfigMgr</token>: <externalLink target="_blank"><linkText>Monitoring mobile devices</linkText><linkUri>https://technet.microsoft.com/library/gg682128.aspx</linkUri></externalLink> and <externalLink target="_blank"><linkText>manage reporting</linkText><linkUri>https://technet.microsoft.com/library/gg699377.aspx</linkUri></externalLink></para></listItem><listItem><para><token>MDM for Office 365</token>: <externalLink><linkText>Overview and device management tasks</linkText><linkUri>https://technet.microsoft.com/en-us/library/ms.o365.cc.devicepolicy.aspx</linkUri></externalLink></para></listItem></list></content>
</section><section>
<title>Task 4e: Email management options</title><content><para>The main reason for implementing a mobile device management solution is usually to provide managed access to corporate email from mobile devices. For example, in <token>MDM for Office 365</token>, you can create a <externalLink><linkText>security policy</linkText><linkUri>https://technet.microsoft.com/library/ms.o365.cc.newdevicepolicy.aspx</linkUri></externalLink> that provide basic managed access to email mailboxes hosted in <token>Exchange Online</token> or access through Office apps (on iOS and Android). This policy enforces basic mobile device compliance settings, such as requiring a device password and device encryption, before the device is allowed to connect to a user mailbox. </para><para>You follow a similar process to configure email management options in <token>Intune</token>, and hybrid <token>Intune</token> and <token>ConfigMgr</token> deployments. The primary difference is that you can implement more advanced email management options than you can in <token>MDM for Office 365</token>. For example, using <token>Intune</token> standalone, you can configure conditional email access to allow access mailboxes hosted on both <token>Exchange Online</token> and Exchange on-premises, as well as configure customized email profiles. <token>Intune</token> enables these features by using configuration and compliance policies.  Hybrid <token>Intune</token> and <token>ConfigMgr</token> deployments also supports conditional email access, but only for mailboxes hosted on <token>Exchange Online</token>.</para><para>In the scenario shown below in Figure 6, the user has enrolled their device in <token>Intune</token> and is now trying to access their corporate email using <token>Office 365</token> or Exchange on-premises. Based on the settings defined by the IT administrator at their company, <token>Intune</token> runs a policy verification process. In this scenario, the user’s access is granted if the device is encrypted, a passcode is set, and the device isn’t jail broken or rooted. If a user tries to access corporate email and their device is not enrolled, or not compliant based upon settings defined by the IT admin, the user will receive an email explaining why their access has been blocked along with steps for how to resolve the issue. </para><mediaLink>
<image xlink:href="c11419cf-0e78-43f9-a4e1-3c0b1fff0995"/>
</mediaLink><para><legacyBold>Figure 6</legacyBold></para><para>Your answers to the questions in Task 1 can help you determine how you want devices to be managed in the mobile device management solution. Table 9 below lists the advantages and disadvantages of email management in each MDM solution.</para><para><legacyBold>Table 9</legacyBold></para><table border="1"><thead><tr><TD><para>Email management option</para></TD><TD><para>Advantages</para></TD><TD><para>Disadvantages</para></TD></tr></thead><tbody><tr><TD><para><token>Intune</token> (standalone)</para></TD><TD><list class="bullet"><listItem><para>Supports email management for all major mobile device operating systems (Android, iOS, Windows 10, Windows 8.x, and Windows Phone)</para></listItem><listItem><para>Can leverage native mobile device email applications via integration with <token>Exchange ActiveSync</token></para></listItem><listItem><para>Integration with <token>Exchange Online</token> via the Service-to-Service connector to allow cross-platform monitoring and reporting between <token>Intune</token> and <token>Office 365</token></para></listItem><listItem><para>Supports configuration of email profiles for managing <token>Exchange ActiveSync</token>-based settings on mobile devices</para></listItem><listItem><para>Conditional email access to resources</para></listItem></list></TD><TD><list class="bullet"><listItem><para>	Email profiles aren’t supported for Android-based mobile devices</para></listItem></list></TD></tr><tr><TD><para><token>MDM for Office 365</token></para></TD><TD><list class="bullet"><listItem><para>Allows <token>Exchange ActiveSync</token> support for password, encryption, rooted device compliance</para></listItem><listItem><para>Allows device management policies and requiring device enrollment before access is granted to Office and OneDrive for Business apps (iOS and Android)</para></listItem><listItem><para>Conditional email access to resources</para></listItem></list></TD><TD><list class="bullet"><listItem><para>	Some advanced email management options aren’t supported  </para></listItem><listItem><para>Deploying email profiles isn’t supported (except iOS)</para></listItem></list></TD></tr><tr><TD><para>Hybrid (<token>Intune</token> with <token>ConfigMgr</token>)</para></TD><TD><list class="bullet"><listItem><para><token>Intune</token> On-premises Connector for hybrid connectivity with <token>Exchange Online</token></para></listItem><listItem><para>Integration with <token>Exchange ActiveSync</token> (most strict policy setting is enforced)</para></listItem><listItem><para>Email profiles</para></listItem><listItem><para>Conditional access to restrict email access to <token>Exchange Online</token></para></listItem><listItem><para>Compliance policies to define the rules and settings the device must comply with in order to be allowed access to the services</para></listItem><listItem><para>Conditional access policies for each service, define rules for security groups, <token>Intune</token> groups, or how unenrolled devices are managed</para></listItem></list></TD><TD><list class="bullet"><listItem><para>Managed access to email only available for mailboxes hosted on <token>Exchange Online</token>, not mailboxes hosted on Exchange on-premises</para></listItem><listItem><para>Configuring the service-to-service connector should not be configured if you enable conditional access for both <token>Exchange Online</token> and Exchange on-premises</para></listItem></list></TD></tr></tbody></table><para>Explore the details about mobile device email configuration management options by reviewing the following:</para><list class="bullet"><listItem><para><token>Intune</token>: How to <externalLink><linkText>enable email profiles</linkText><linkUri>https://technet.microsoft.com/library/dn800672.aspx</linkUri></externalLink> and <externalLink><linkText>conditional email access</linkText><linkUri>https://technet.microsoft.com/library/dn818907.aspx</linkUri></externalLink></para></listItem><listItem><para><token>ConfigMgr</token>: Enabling <externalLink><linkText>email profiles</linkText><linkUri>https://technet.microsoft.com/library/dn554227.aspx</linkUri></externalLink> and <externalLink><linkText>conditional email access</linkText><linkUri>https://technet.microsoft.com/library/dn919655.aspx</linkUri></externalLink></para></listItem><listItem><para><token>MDM for Office 365</token>: <externalLink><linkText>Capabilities of mobile device management</linkText><linkUri>https://technet.microsoft.com/library/ms.o365.cc.devicepolicysupporteddevice.aspx</linkUri></externalLink></para></listItem></list></content>
</section><section>
<title>Task 4f: Network connectivity management options</title><content><para>Depending on your infrastructure, mobile devices might be able to connect to corporate resources from a variety of Internet connectivity services, which are often secured by VPN-protected endpoints.</para><para>By using <externalLink><linkText>Intune</linkText><linkUri>https://technet.microsoft.com/library/dn818903.aspxv</linkUri></externalLink> or a <externalLink><linkText>hybrid deployment</linkText><linkUri>https://technet.microsoft.com/library/dn261221.aspx</linkUri></externalLink> with <token>ConfigMgr</token>, you can deploy Wi-Fi profiles to provision Wi-Fi networks, so a device can auto-connect to the network when it is in range. For example, mobile devices can be configured to connect to a Wi-Fi network segmented to a conference room, but then switch to connect to a Wi-Fi network segment when roaming to a different location. Users don’t have to enter passwords or choose a network; the connection works automatically.</para><para><externalLink><linkText>Intune</linkText><linkUri>https://technet.microsoft.com/library/dn818905.aspx</linkUri></externalLink> and <externalLink><linkText>ConfigMgr</linkText><linkUri>https://technet.microsoft.com/library/dn261217.aspx</linkUri></externalLink> can also deploy VPN profiles directly to mobile devices, to let user access internal corporate resources without extra configuration or manual work. Additionally, Intune can configure mobile devices to automatically start a VPN connection that is based on the type resource or method of access. Be aware, however, that there are different configuration requirements for doing this for different types of mobile device operating systems.</para><para>Your answers to the questions in Task 3 can help you determine how you want devices to be connect to corporate resources. Be aware that currently, <token>MDM for Office 365</token> doesn’t support managing wireless and VPN network resources for mobile devices.</para><para>Table 10 below lists the advantages and disadvantages of managing wireless and VPN networks using <token>Intune</token> standalone and hybrid <token>Intune</token> with <token>ConfigMgr</token>.</para><para><legacyBold>Table 10</legacyBold></para><table border="1"><thead><tr><TD><para>Network management options</para></TD><TD><para>Advantages</para></TD><TD><para>Disadvantages</para></TD></tr></thead><tbody><tr><TD><para><token>Intune</token> (standalone)</para></TD><TD><list class="bullet"><listItem><para>Supports wireless and VPN profiles on all major mobile device operating systems (Android, iOS, Windows 10, Windows 8.x, and Windows Phone) </para></listItem><listItem><para>Supports industry leading VPN connection types, including Cisco, Juniper, Dell SonicWall, Checkpoint, and others</para></listItem><listItem><para>Wireless and VPN profiles can be integrated with SCEP certificate profiles for increased security</para></listItem><listItem><para>Supports configuring customized wireless and VPN profiles for different types of users, devices, device operating systems, or user groups and roles</para></listItem><listItem><para>DNS name-based initiation support for Windows 10, Windows 8.1, <token>Windows Phone</token> 8.1 and iOS</para></listItem><listItem><para>Application ID based initiation support for Windows 10 and Windows 8.1</para></listItem></list></TD><TD><list class="bullet"><listItem><para>To support VPN profiles, you’ll need to deploy and maintain an on-premises VPN infrastructure</para></listItem></list></TD></tr><tr><TD><para><token>MDM for Office 365</token></para></TD><TD><list class="bullet"><listItem><para>	Not available</para></listItem></list></TD><TD><list class="bullet"><listItem><para>Not available</para></listItem></list></TD></tr><tr><TD><para>Hybrid (<token>Intune</token> with <token>ConfigMgr</token>)</para></TD><TD><list class="bullet"><listItem><para>All the advantages of <token>Intune</token> standalone, plus the following:</para><list class="bullet"><listItem><para>VPN profiles are supported by your existing on-premises enterprise VPN infrastructure</para></listItem></list></listItem></list></TD><TD><list class="bullet"><listItem><para>To support VPN profiles, you’ll need to deploy and maintain an on-premises VPN infrastructure </para></listItem><listItem><para>Specific security permissions must be granted to manage <externalLink target="_blank"><linkText>Wi-Fi profiles</linkText><linkUri>https://technet.microsoft.com/library/dn408646.aspx</linkUri></externalLink> and <externalLink target="_blank"><linkText>VPN profiles</linkText><linkUri>https://technet.microsoft.com/library/dn408643.aspx</linkUri></externalLink> in <token>ConfigMgr</token></para></listItem></list></TD></tr></tbody></table><para>Explore the details about mobile device email configuration management options by reviewing the following:</para><list class="bullet"><listItem><para>Intune: Enable <externalLink><linkText>wireless</linkText><linkUri>https://technet.microsoft.com/library/dn818903.aspx</linkUri></externalLink> and <externalLink><linkText>VPN</linkText><linkUri>https://technet.microsoft.com/library/dn818905.aspx</linkUri></externalLink> profiles</para></listItem><listItem><para>ConfigMgr: Enabling <externalLink><linkText>wireless</linkText><linkUri>https://technet.microsoft.com/library/dn261221.aspx</linkUri></externalLink> and <externalLink><linkText>VPN</linkText><linkUri>https://technet.microsoft.com/library/dn261217.aspx</linkUri></externalLink> profiles</para></listItem></list></content>
</section><section>
<title>Task 4g: Certificate management options</title><content><para>Using digital certificate management and certificate profiles is supported both by <externalLink><linkText>Intune</linkText><linkUri>https://technet.microsoft.com/library/dn818904.aspx</linkUri></externalLink> standalone and <externalLink><linkText>hybrid Intune and ConfigMgr</linkText><linkUri>https://technet.microsoft.com/library/dn261202.aspx</linkUri></externalLink> deployment scenarios. These features allow you to deploy trusted root certificates to mobile devices, as well as Simple Certificate Enrollment Protocol (SCEP) based profiles that instruct mobile devices to get additional certificates from a NDES server in your organization. </para><para>Since SCEP is natively supported by iOS, Windows 10 and 8.1, and Windows Phone 10 and 8.1, and is also supported through the <token>Microsoft Intune Company Portal</token> app for Android, using this enrollment protocol has the advantage of having the private key generated directly on the mobile device. The private key is never generated, cached, or stored by either <token>ConfigMgr</token> or by <token>Intune</token> - which helps to keep the mobile device secure.</para><para>Figure 7 shows how <token>Intune</token> and <token>ConfigMgr</token> use the NDES to provide secure certificate provisioning to mobile devices using SCEP:</para><mediaLink>
<image xlink:href="1f6f2542-eb66-48c0-9988-59c40c1fdead"/>
</mediaLink><para><legacyBold>Figure 7 - Secure certificate provisioning</legacyBold></para><list class="ordered"><listItem><para>A policy that includes the properties of the certificate for SCEP enrollment is created on the <token>Intune</token> service. </para></listItem><listItem><para><token>Intune</token> converts the policy to a platform mobile device management protocol (like OMA-DM for Windows 10 and Windows 8.1) and sends it to the device</para></listItem><listItem><para>The mobile device receives the policy and initiates an enrollment request from NDES</para></listItem><listItem><para>NDES forwards the request to <token>ConfigMgr</token></para></listItem><listItem><para><token>ConfigMgr</token> compares the request attributes of the SCEP request for an authentication match and sends confirmation back to NDES.</para></listItem><listItem><para>NDES sends a certificate issuance request to the CA and it sends the certificate to the NDES role.</para></listItem><listItem><para>NDES role sends the certificate to the device.

</para></listItem></list><para>Depending on how you answered the questions in Task 3, you should be able to determine how you want certificates managed in the mobile device management solution. Currently, <token>MDM for Office 365</token> doesn’t support managing certificate profiles for mobile devices. Table 11 below will help you understand the advantages and disadvantages of the certificate profile management for <token>Intune</token> and the hybrid <token>Intune</token> with <token>ConfigMgr</token> deployment scenario:</para><para><legacyBold>Table 11</legacyBold></para><table border="1"><thead><tr><TD><para>Certificate management options</para></TD><TD><para>Advantages</para></TD><TD><para>Disadvantages</para></TD></tr></thead><tbody><tr><TD><para><token>Intune</token> (standalone)</para></TD><TD><list class="bullet"><listItem><para>Supports certificate profiles on all major mobile device operating systems (Android, iOS, Windows 10, Windows 8.x, and Windows Phone)</para></listItem><listItem><para>Platform supports the Simple Certificate Enrollment Protocol (SCEP)</para></listItem><listItem><para>Certificate profiles can automatically configure mobile devices so that company resources can be accessed without having to install certificates manually or use a non-approved security process</para></listItem><listItem><para>Certificates can be automatically revoked when the device is retired from management, selectively wiped, or block from the management hierarchy</para></listItem></list></TD><TD><list class="bullet"><listItem><para>To use certificate profiles, some existing on-premises infrastructure must be in place. You must integrate the following on-premises infrastructure with <token>Intune</token>:</para><list class="bullet"><listItem><para>A server that runs the Network Device Enrollment Service</para></listItem><listItem><para>An Enterprise Certification Authority</para></listItem><listItem><para>The <token>Intune</token> NDES Connector, which installs on the server that runs NDES</para></listItem></list></listItem></list></TD></tr><tr><TD><para><token>MDM for Office 365</token></para></TD><TD><list class="bullet"><listItem><para>Not available</para></listItem></list></TD><TD><list class="bullet"><listItem><para>Not available</para></listItem></list></TD></tr><tr><TD><para>Hybrid (<token>Intune</token> with <token>ConfigMgr</token>)</para></TD><TD><list class="bullet"><listItem><para>All the advantages of <token>Intune</token> standalone, plus the following:</para><list class="bullet"><listItem><para>Also supports managing certificates for non-mobile devices</para></listItem></list></listItem></list></TD><TD><list class="bullet"><listItem><para>To use certificate profiles, some existing on-premises infrastructure must be in place. You must integrate the following on-premises infrastructure with <token>Intune</token>:</para><list class="bullet"><listItem><para>A server that runs the Network Device Enrollment Service</para></listItem><listItem><para>An Enterprise Certification Authority</para></listItem><listItem><para>The <token>Intune</token> NDES Connector, which installs on the server that runs NDES</para></listItem></list></listItem></list></TD></tr></tbody></table><para>For more details about mobile device certificate management options, read how to <externalLink target="_blank"><linkText>enable certificate profiles</linkText><linkUri>https://technet.microsoft.com/library/dn818904.aspx</linkUri></externalLink> in <token>Intune</token> and compare these requirements and procedures to <externalLink target="_blank"><linkText>enabling certificate profiles</linkText><linkUri>https://technet.microsoft.com/library/dn261202.aspx</linkUri></externalLink> in <token>System Center 2012 R2 Configuration Manager</token>.</para></content>
</section></sections></section><section>
<title>Ready for the next step?</title><content><para>Go to <link xlink:href="5dffb570-dd1a-4beb-aa1e-7c0b51393704">Step 3 - Plan for securing mobile devices</link> for the next step in this guide.</para></content>
</section><relatedTopics/>
</developerConceptualDocument>