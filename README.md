# Microsoft-Azure-Sentinel-SIEM-Security-Information-and-Event-Manager-
Microsoft Azure Sentinel - SIEM (Security Information and Event Manager)

Designed and implemented Sentinel, a cybersecurity project leveraging Microsoft Azure and Azure Sentinel. Employed PowerShell to call APIs for IP-to-geolocation conversion, creating a decoy honeypot that captures real-time attack data. Integrated Azure Sentinel to store and analyze logs with KQL, enabling the visualization of cyber threats on a map. It greatly enhance firewall policy adjustment mechanism based on a constantly updated list of abusing IPs, enhancing proactive cybersecurity measures

![image](https://github.com/Shifat-udn/Microsoft-Azure-Sentinel---SIEM-Security-Information-and-Event-Manager-/assets/141313925/847179a0-09c1-40fa-b012-406458e6f02b)
<hr/>
<h3>1.	Technology Used </h3>
<ul>
  <li>Exposed Virtual machine</li>
  <li>Log Analytics Workspace</li> 
  <li>Azure Sentinel (SIEM)</li>
  <li>Powershell </li>
  <li>Kusto Query Language (KQL)</li> 
</ul>


<h3>2. Enviroment Setup</h3>
<ul>
  <li>Setup and log on Azure Account and visit https://portal.azure.com/</li>
  <li>Go to create resource > Virtual machine
  <table>
  <tr><td><img src="https://github.com/Shifat-udn/Microsoft-Azure-Sentinel---SIEM-Security-Information-and-Event-Manager-/assets/141313925/21b52823-993b-46c3-8d3d-952710c0e777"></td>
  <td><img src="https://github.com/Shifat-udn/Microsoft-Azure-Sentinel---SIEM-Security-Information-and-Event-Manager-/assets/141313925/da35a590-492e-42df-bee8-f9fa01d5f273"></td></tr>
  </table>
 </li>
  <li>Create new resource group
  <table>
  <tr><td> <img src="https://github.com/Shifat-udn/Microsoft-Azure-Sentinel---SIEM-Security-Information-and-Event-Manager-/assets/141313925/7950ac21-a54e-4761-9c62-90118234262f"></td>
  <td><img src="https://github.com/Shifat-udn/Microsoft-Azure-Sentinel---SIEM-Security-Information-and-Event-Manager-/assets/141313925/a522aa62-f749-4daa-9c21-332c06515303"></td></tr>
  </table>
  </li>
    <li>Set user & disk
  <table>
  <tr><td> <img src="https://github.com/Shifat-udn/Microsoft-Azure-Sentinel---SIEM-Security-Information-and-Event-Manager-/assets/141313925/a252e350-c2ea-4ca9-96db-da1b7e72f52f"></td>
  <td><img src="https://github.com/Shifat-udn/Microsoft-Azure-Sentinel---SIEM-Security-Information-and-Event-Manager-/assets/141313925/c7f8b012-5044-4cdd-806e-7587e9f80d8f"></td></tr>
  </table>
  </li>
      <li>Create New Network Security Group and allow all traffic 
  <table>
  <tr><td> <img src="https://github.com/Shifat-udn/Microsoft-Azure-Sentinel---SIEM-Security-Information-and-Event-Manager-/assets/141313925/74a6896d-0132-47c7-bc5e-97df456d21f8"></td>
  <td><img src="https://github.com/Shifat-udn/Microsoft-Azure-Sentinel---SIEM-Security-Information-and-Event-Manager-/assets/141313925/eacdfd35-6eea-4c24-8e8a-f8fa97ec9800"></td>
  <td><img src="https://github.com/Shifat-udn/Microsoft-Azure-Sentinel---SIEM-Security-Information-and-Event-Manager-/assets/141313925/26af24b0-9466-4f0f-8a54-a90fa6c765e4"></td>
  <td><img src="https://github.com/Shifat-udn/Microsoft-Azure-Sentinel---SIEM-Security-Information-and-Event-Manager-/assets/141313925/8ee9beef-39df-42d9-b6a7-65e001b1b79a"></td></tr>
  </table>
  </li>
  <li>Review and Create New Virtual Mechine 
  <table>
  <tr><td> <img src="https://github.com/Shifat-udn/Microsoft-Azure-Sentinel---SIEM-Security-Information-and-Event-Manager-/assets/141313925/b60b34e1-3edf-43f8-85be-cee643c3ed8b"></td>
  <td><img src="https://github.com/Shifat-udn/Microsoft-Azure-Sentinel---SIEM-Security-Information-and-Event-Manager-/assets/141313925/a8db4eba-5677-45a3-a972-b0bfe2a39792"></td>
 </tr>
  </table>
  </li>
</ul>
<hr/>
<h2>2. Log analytics workspace </h2>
<ul>
    <li>Create a Log analytics workspace under same resource group
  <table>
  <tr><td> <img src="https://github.com/Shifat-udn/Microsoft-Azure-Sentinel---SIEM-Security-Information-and-Event-Manager-/assets/141313925/6d654778-df9f-41dc-8f08-d33843034216"></td>
  <td><img src="https://github.com/Shifat-udn/Microsoft-Azure-Sentinel---SIEM-Security-Information-and-Event-Manager-/assets/141313925/96dc409e-5548-4b7a-98db-9800ec40e728"></td></tr>
  <tr><td> <img src="https://github.com/Shifat-udn/Microsoft-Azure-Sentinel---SIEM-Security-Information-and-Event-Manager-/assets/141313925/6d1c7bc0-85bb-405d-80c0-f92b3086fe88"></td>
  <td><img src="https://github.com/Shifat-udn/Microsoft-Azure-Sentinel---SIEM-Security-Information-and-Event-Manager-/assets/141313925/ca74df7d-35ad-46c5-bfd4-70eed94a8001"></td></tr>
  </table>
  </li>
   <li> Turn on Microsoft Defender for Cloud, Select Log analytics (rules-honeypot) from Enviroment Settings. also turn off SQL server on machines from defender plans and select "All Events from Data collection" 
  <table>
  <tr><td> <img src="https://github.com/Shifat-udn/Microsoft-Azure-Sentinel---SIEM-Security-Information-and-Event-Manager-/assets/141313925/4058aea9-0db8-4c96-ba02-12cded462070"></td>
  <td><img src="https://github.com/Shifat-udn/Microsoft-Azure-Sentinel---SIEM-Security-Information-and-Event-Manager-/assets/141313925/4d0542cb-0573-46e2-935d-c719e2cc1434"></td></tr>
  <tr><td> <img src="https://github.com/Shifat-udn/Microsoft-Azure-Sentinel---SIEM-Security-Information-and-Event-Manager-/assets/141313925/200d5f55-53a1-4523-aa8e-1ea5c3553669"></td>
  <td><img src="https://github.com/Shifat-udn/Microsoft-Azure-Sentinel---SIEM-Security-Information-and-Event-Manager-/assets/141313925/e2a57087-9f58-4f03-9e1d-c875bbc4b08c"></td></tr>
  </table>
  </li>
     <li> Now go back to Log analytics workspace and connect the VM
  <table>
  <tr><td> <img src="https://github.com/Shifat-udn/Microsoft-Azure-Sentinel---SIEM-Security-Information-and-Event-Manager-/assets/141313925/0d6eb42e-2403-49bd-b3c3-650114220521"></td>
  <td><img src="https://github.com/Shifat-udn/Microsoft-Azure-Sentinel---SIEM-Security-Information-and-Event-Manager-/assets/141313925/c3c3db8d-4900-4e8f-81b1-8a2866f1c7e1"></td></tr>
  </table>
  </li>
</ul>
<hr/>
<h2>3. Connect everything with Microsoft Sentinel </h2>
<ul>
    <li>Open Microsoft Sentinel and add Log analytics workspace to it
  <table>
  <tr><td> <img src="https://github.com/Shifat-udn/Microsoft-Azure-Sentinel---SIEM-Security-Information-and-Event-Manager-/assets/141313925/87585556-6bcf-466d-8cdf-e7257c6e380e"></td>
  <td><img src="https://github.com/Shifat-udn/Microsoft-Azure-Sentinel---SIEM-Security-Information-and-Event-Manager-/assets/141313925/9921d7c1-3f9c-4fe6-a817-05017f63ed62"></td>
  <td> <img src="https://github.com/Shifat-udn/Microsoft-Azure-Sentinel---SIEM-Security-Information-and-Event-Manager-/assets/141313925/bd7df04f-aae7-48a7-b82f-697bdcc3701f"></td>
  <td><img src="https://github.com/Shifat-udn/Microsoft-Azure-Sentinel---SIEM-Security-Information-and-Event-Manager-/assets/141313925/5c24c5aa-0475-4cf5-98c4-2ef60900f08d"></td></tr>
  </table>
  </li>
</ul>
<hr/>
<h2>4. Configur Endpoint Honeypot for colleting logs </h2>
<ul>
    <li>Collect API Key from https://app.ipgeolocation.io/dashboard and edit the powershell based on the <a href="https://github.com/Shifat-udn/Microsoft-Azure-Sentinel---SIEM-Security-Information-and-Event-Manager-/blob/main/Log_Exporter.ps1">file</a>. Then connect the VM with Remote desktop, open Power Shell ISE and run the powershell code. A log file will be created with ip location.
  <table>
  <tr><td> <img src="https://github.com/Shifat-udn/Microsoft-Azure-Sentinel---SIEM-Security-Information-and-Event-Manager-/assets/141313925/f8e1c422-25bd-4e58-a706-69286658c3de"></td>
  <td><img src="https://github.com/Shifat-udn/Microsoft-Azure-Sentinel---SIEM-Security-Information-and-Event-Manager-/assets/141313925/88424df9-e9f3-404d-b418-30621cdf4cc4"></td>
</tr>
  </table>
  </li>
      <li> Copy the sample data to the work station. Then go to Log analytics workspace > Tables > Create Table > New Custom logs-MMA based . 
  <table>
  <tr><td> <img src="https://github.com/Shifat-udn/Microsoft-Azure-Sentinel---SIEM-Security-Information-and-Event-Manager-/assets/141313925/5db7f4ec-beb5-48bb-83c2-09633a6e1c32"></td>
  <td><img src="https://github.com/Shifat-udn/Microsoft-Azure-Sentinel---SIEM-Security-Information-and-Event-Manager-/assets/141313925/9fbb4404-7a9e-44d2-8881-6deb12ae7be3"></td>
</tr>
  </table>
  </li>
   <li> Create custom log with collection path  
  <table>
  <tr><td> <img src="https://github.com/Shifat-udn/Microsoft-Azure-Sentinel---SIEM-Security-Information-and-Event-Manager-/assets/141313925/067e19e0-25b6-454e-bb05-33802049864b"></td>
  <td><img src="https://github.com/Shifat-udn/Microsoft-Azure-Sentinel---SIEM-Security-Information-and-Event-Manager-/assets/141313925/afd3c540-511f-4ad3-8f45-df38d2d09b7e"></td></tr>
  <tr><td> <img src="https://github.com/Shifat-udn/Microsoft-Azure-Sentinel---SIEM-Security-Information-and-Event-Manager-/assets/141313925/a364d7bf-508b-4d43-9ad2-fa162197199c"></td>
  <td><img src="https://github.com/Shifat-udn/Microsoft-Azure-Sentinel---SIEM-Security-Information-and-Event-Manager-/assets/141313925/88fc55b1-6168-47e8-9976-3570748cd7fb"></td>
</tr>
  </table>
  </li>
</ul>
