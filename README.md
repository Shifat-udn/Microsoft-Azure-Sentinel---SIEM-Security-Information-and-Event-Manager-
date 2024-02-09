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

