---
title: 安装和配置AEM文档 Security Extension for Microsoft Office
description: 本文档将指导您安装和配置Adobe Experience Manager文档Security Extension 6.2 for Microsoft Office。
uuid: 9d7eb6bb-4780-4d82-8657-7c6c6d523af0
content-type: reference
topic-tags: installing
discoiquuid: f1cdf344-efe4-4cb5-9fc3-47ee4ba5faf4
translation-type: tm+mt
source-git-commit: ac385c538cdd7d3bb4772b92ee7a94b003595f56
workflow-type: tm+mt
source-wordcount: '2796'
ht-degree: 0%

---


# 安装和配置AEM文档 Security Extension for Microsoft Office{#installing-and-configuring-aem-document-security-extension-for-microsoft-office}

此文档可指导您安装和配置Adobe Experience Manager文档Security Extension for Microsoft Office。

此文档包括以下任务的相关信息：

* 安装文档Security Extension for Microsoft Office
* 将安装程序预配置为指向AEM 6.0Forms或更高版本的LiveCycle Rights Management ES2或文档安全插件。
* 配置默认策略的自动应用

## 安装之前 {#before-you-install}

安装文档Security Extension for Microsoft Office之前，请确保：

* 您已阅读[发行说明](document-security-extension-release-notes.md)。
* Microsoft Office已激活。 激活对话框在打开Microsoft Office应用程序时不显示。
* 已安装Microsoft Windows和Microsoft Office的最新服务包。
* 如果您正在为不支持的语言安装Microsoft Office文档安全，请至少打开一次Office应用程序。

>[!NOTE]
>
>请勿将软件安装在名称包含多次字节字符的文件夹中。 如果这样做，AEM文档安全菜单不会显示在Microsoft Office中。

>[!NOTE]
>
>支持在64位操作系统上安装32位版本的文档安全扩展，但不支持相反的方式。 无法在32位操作系统上安装64位版本的Microsoft Office文档安全扩展。

### 禁用McAfee VirusScan和{#disable-mcafee-virusscan}

要确保在装有文档安全扩展和已启用“按访问扫描程序”的McAfee VirusScan的计算机上顺利开始Office应用程序，请禁用McAfee VirusScan控制台中的“缓冲区溢出保护”选项。

### 卸载第三方插件{#uninstall-third-party-plug-ins}

AEM文档 Security Extension for Microsoft Office不支持Microsoft Office应用程序的第三方插件。 由于此扩展与第三方插件冲突，请先卸载所有非AdobeMicrosoft Office插件，然后再安装文档Security for Microsoft Office。 Adobe不支持安装了第三方插件的Microsoft Office应用程序的文档安全。

## 系统要求{#system-requirements}

### 文档安全扩展客户端{#document-security-extension-client}

确保要安装文档安全扩展的以下最低配置：

* 32位或64位版本的Microsoft Windows 7或Windows 10，英语、法语、德语、日语、意大利语、西班牙语、巴西葡萄牙语、韩语、简体中文或繁体中文。
   **注意：** *文档安全扩展的Microsoft Office也可在Microsoft Surface设备上使用。*

* 32位或64位版本的Microsoft Office 2013、2016、2019和Microsoft Office桌面应用程序作为Office 365的一部分安装，其英语、法语、德语、日语、意大利语、西班牙语、巴西葡萄牙语、韩语、简体中文或繁体中文。

   **注意**: *AEM文档 Security Extension for Microsoft Office不支持Microsoft Office应用程序的第三方插件。由于此扩展可能与第三方插件冲突，因此必须先卸载用于Microsoft Office应用程序的任何非Adobe插件，然后才能安装用于Microsoft Office的文档安全扩展。 Adobe不支持安装第三方插件的Microsoft Office应用程序的文档安全扩展。*

* 1.3 GHz处理器或更高
* 2 GB内存
* 100 MB可用硬盘空间

### 文档安全 {#document-security}

要使用文档安全扩展，请确保您能够连接到Adobe LiveCycle Rights ManagementES2及更高版本，或连接到AEM 6.0表单或更高版本的文档安全插件。

## 正在安装文档Security Extension for Microsoft Office {#installing-document-security-extension-for-microsoft-office}

可以从[下载页面](download-installer.md)下载安装程序。 无法直接自定义安装程序可执行文件，但可以以交互方式或在静默模式下安装它。 要安装软件，请以管理员身份登录到Windows。

32位和64位版本的Microsoft Office可使用单独的安装程序。 对于32位版本的Microsoft Office，请下载DocumentSecurityExtensionforMicrosoftOffice.exe。 对于64位版本的Microsoft Office，请下载DocumentSecurityExtensionforMicrosoftOffice64.exe。

>[!NOTE]
>
>此文档使用32位安装程序文件(DocumentSecurityExtensionforMicrosoftOffice.exe)解释各种命令和选项。 如果您使用64位版本的Microsoft Office，请使用64位安装程序文件(DocumentSecurityExtensionforMicrosoftOffice64.exe)执行本文档中列出的操作。

### 以静默模式安装{#install-in-silent-mode}

使用文件解压工具（如WinZip）从安装程序文件解压`DocumentSecurityExtensionforMicrosoftOffice.exe`。 打开命令提示符，转到包含安装文件的文件夹，然后键入以下文本：

`DocumentSecurityExtensionforMicrosoftOffice.exe -s -a -s -v" /qn"`

安装程序也以MSI文件形式提供，可用于自定义。

### 以静默模式{#install-an-msi-file-in-silent-mode}安装MSI文件

1. 使用文件解压工具（如WinZip）从ZIP文件解压`DocumentSecurityExtensionforMicrosoftOffice.msi`文件。

1. 打开命令提示符，转至包含MSI文件的文件夹，然后键入以下文本：

   `msiexec /I DocumentSecurityExtensionforMicrosoftOffice.msi /qn`

## 预配置安装程序以连接到文档安全{#preconfiguring-the-installer-to-connect-to-document-security}

您可以预配置Microsoft Office文档安全扩展安装程序以指向LiveCycle或AEM服务器，这样，安装Microsoft Office文档安全扩展的用户无需配置连接即可使用这些功能。 因此，用户可以打开受保护的文档，而无需配置。 但是，在将客户端配置为使用特定服务器之前，他们无法保护新文档。

以下步骤描述了如何创建和配置MSI文件。 此MSI文件包含将文档Security Extension for Microsoft Office安装程序预配置到企业中安装的LiveCycle或AEM服务器所需的注册表值。

### 自定义安装程序{#prerequisites-for-customizing-the-installer}的先决条件

使用Orca数据库编辑器自定义安装程序。 以下步骤描述了如何使用Orca数据库编辑器修改MSI安装文件副本，从而创建自定义MSI文件。 Orca可作为Windows SDK for Windows Server 2008和。NET Framework 3.5的一部分提供。有关如何使用Orca编辑Microsoft Windows® Installer文件的详细信息，请参阅[Microsoft Support](http://support.microsoft.com/kb/255905/EN-US/)。

>[!NOTE]
>
>建议在创建自定义MSI文件之前完整备份所有安装程序文件。

#### 安装Orca {#install-orca}

1. 从[Microsoft下载中心](http://www.microsoft.com/download/en/details.aspx?displaylang=en&amp;id=11310)下载适用于Windows Server 2008和。NET Framework 3.5的Windows SDK。
1. 多次单击\Microsoft SDK\bin文件夹中的Orca.msi文件。

   您还需要安装程序文件的MSI变体。 与Adobe支持联系，获取最新版MSI安装程序。

   >[!NOTE]
   >
   >运行安装程序前，请始终关闭DocumentSecurityExtensionforMicrosoftOffice.msi文件。 如果Orca正在使用MSI文件，则无法运行安装程序。

### 创建和配置MSI文件{#create-and-configure-the-msi-file}

1. 单击&#x200B;**[!UICONTROL 开始>项目> Orca]**。

1. 单击&#x200B;**[!UICONTROL 文件>打开]**，然后浏览至`DocumentSecurityExtensionforMicrosoftOffice.msi`文件。

1. 从表列表（左侧）中选择属性。

1. 根据企业安装的Rights Management或文档安全，编辑以下键名值。

<table>
 <tbody>
  <tr>
   <td><p><strong>密</strong><strong></strong><strong>钥名称</strong></p> </td>
   <td><p><strong>描述</strong></p> </td>
   <td><p><strong>键</strong><strong></strong><strong>值默认值</strong></p> </td>
  </tr>
  <tr>
   <td><p><code>APS_SERVER_NAME</code></p> </td>
   <td><p>显示名称。</p> </td>
   <td><p>默认服务器</p> </td>
  </tr>
  <tr>
   <td><p><code>APS_SERVER_URL</code></p> </td>
   <td><p>主机服务器URL。</p> </td>
   <td><p>https://default.corp.com:1234</p> </td>
  </tr>
 </tbody>
</table>

1. 从表的列表（左侧）中选择“注册表”。

1. 编辑以下键名值。

   | **密钥名称** | **描述** | **默认值** |
   |---|---|---|
   | `IsDefault` | 默认APS服务器。 | 默认服务器 |

1. 将修改后的文件保存到包含原始MSI安装程序的同一目录。

   >[!NOTE]
   >
   >通常的做法是使用与原始MSI文件相同的文件名（例如`DocumentSecurityExtensionforMicrosoftOffice.msi`）。

## 配置默认策略{#configuring-automatic-application-of-a-default-policy}的自动应用

作为配置的一部分，您可以配置默认策略的自动应用程序，以便文档Security Extension for Microsoft Office保护保存的每个文档。

您可以指定以下选项之一：

* Protect所有文档都有默认政策。
* 当用户无法连接到服务器时，允许用户选择以不受保护的格式保存文件。 这种灵活性允许您解释用户在与网络断开连接（例如，在飞机上）时创建文档的情况。

启用“自动应用策略”功能后，文档在以下情况下将受默认策略的保护：

* 用户编辑和保存新创建的文档
* 用户编辑和保存不受保护的文档
* 用户打开一个应用程序，它以默认文档打开、编辑，然后保存文档

### 在MSI文件中配置自动应用策略功能  {#configure-the-auto-apply-policy-feature-in-the-msi-file}

在开始之前，请按照本文前面所述，预配置安装程序以指向LiveCycle或AEM表单服务器。

1. 单击&#x200B;**[!UICONTROL 开始>项目> Orca]**。

1. 单击&#x200B;**[!UICONTROL 文件>打开]**，然后浏览至`DocumentSecurityExtensionforMicrosoftOffice.msi`文件。

1. 从表列表（左侧）中选择属性。

1. 根据企业安装的Rights Management或文档安全，编辑以下键名值。

<table>
 <tbody>
  <tr>
   <td><p><strong>密钥名称</strong></p> </td>
   <td><p><strong>描述</strong></p> </td>
   <td><p><strong>键</strong><strong></strong><strong>值默认值</strong></p> </td>
  </tr>
  <tr>
   <td><p><code>AUTO_APPLY_POLICY_IS_AUTO_ APPLY</code></p> </td>
   <td><p>启用或禁用自动应用策略功能。</p> <p><code>1</code>: 启用</p> <p>0:禁用</p> </td>
   <td><p>0</p> </td>
  </tr>
  <tr>
   <td><p><code>AUTO_APPLY_POLICY_POLICY_I D</code></p> </td>
   <td><p>保存新文档时要使用的策略GUID。 应用于自动应用策略功能。</p> </td>
   <td><p>RM服务器上显示的十六进制策略ID</p> </td>
  </tr>
  <tr>
   <td><p><code>AUTO_APPLY_POLICY_SERVER_U RL</code></p> </td>
   <td><p>服务器 URL.</p> </td>
   <td><p>default.corp.com</p> </td>
  </tr>
  <tr>
   <td><p><code>AUTO_APPLY_POLICY_SERVER_P ORT_NO</code></p> </td>
   <td><p>服务器端口号。</p> </td>
   <td><p>1234</p> </td>
  </tr>
  <tr>
   <td><p><code>AUTO_APPLY_POLICY_ALLOW_UN PROTECTED_SAVE</code></p> </td>
   <td><p>确定如果客户端无法联系服务器以在第一次保存时保护文档，是否可以在不进行文档安全保护的情况下创建文档。</p> <p>1:允许保存不受保护的内容 </p> <p>0:当客户端无法联系服务器以保存文档时，阻止创建新文档。</p> </td>
   <td><p>0</p> </td>
  </tr>
 </tbody>
</table>

>[!NOTE]
>
>`AUTO_APPLY_POLICY_ALLOW_UN PROTECTED_SAVE` 选项在您希望提醒客户保护所有文档而不强制他们这样做时很有用。当您知道用户在与网络断开连接时创建文档时，该功能也很有用。 您不希望阻止他们创建和保存文档。

1. 将修改后的文件保存到包含原始MSI文件的同一目录。

   >[!NOTE]
   >
   >通常的做法是使用与原始MSI文件相同的文件名（例如`DocumentSecurityExtensionforMicrosoftOffice.msi`）。

## 启用对新文档{#enabling-automatic-protection-of-new-documents}的自动保护

管理员可以启用自动保护用户保存的任何文档的功能。 管理员在Microsoft Office的文档安全扩展安装项目中配置“自动应用策略”功能。

如果启用“自动应用策略”，则用户保存的所有文档都将使用默认策略进行保护。 此操作适用于以下情况：

* 当用户创建新文档、编辑和保存它时。
* 当用户打开不受保护的文档、编辑和保存它时。

有关配置自动应用策略的信息，请参阅[配置默认策略的自动应用程序](installing-configuring-aemdsext.md#p-configuring-automatic-application-of-a-default-policy-p)。

## 启用无功能区用户界面{#enable-ribbon-less-user-interface}

您可以通过修改Windows注册表中的设置来启用／禁用无功能区用户界面。 请执行以下步骤更新注册表并启用无功能区用户界面：

1. 在对Windows注册表进行更改之前备份它。 有关详细说明，请参阅[如何修改Windows注册表](https://support.microsoft.com/en-us/kb/136393)。
1. 在注册表编辑器中，导航到HKEY_CURRENT_USER\Software\Adobe\LiveCycle Rights Management ES4\11.0.0或HKEY_LOCAL_MACHINE\Software\Adobe\LiveCycle Rights Management ES4\11.0.0
1. 新建一个名为&#x200B;**HidePluginUI**&#x200B;的Dword（32位）值。

1. 将**HidePluginUI **属性的值设置为1以启用无功能区用户界面。

1. 关闭注册表编辑器。

## 在Microsoft Excel {#enable-watermark-for-printing-in-microsoft-excel}中启用用于打印的水印

您可以更改Windows注册表设置，使动态水印与现有页眉和页脚共存。 注册表设置仅在打印期间使水印可用。 执行以下步骤以在打印过程中更新注册表并启用水印：

1. 在对Windows注册表进行更改之前备份它。 有关详细说明，请参阅[如何修改Windows注册表](https://support.microsoft.com/en-us/kb/136393)。
1. 在注册表编辑器中，导航到HKEY_CURRENT_USER\Software\Adobe\LiveCycle Rights Management ES4\11.0.0或HKEY_LOCAL_MACHINE\WOW6432NODE\Software\Adobe\LiveCycle Rights Management ES4\11.0.0
1. 创建新的注册表项&#x200B;**WatermarkMode**。
1. 在WatermarkMode注册表项中，创建DWORD **WatermarkMode**，并将DWORD **WatermarkMode**&#x200B;的值设置为&#x200B;**1**。

1. 关闭注册表编辑器。

>[!NOTE]
>
>在Windows资源管理器中，可以使用“文件”菜单或上下文菜单创建Microsoft Excel文档。 对于使用指定方法创建的文档，无法检索或更改打印日期。 这是Microsoft Excel的限制。 AEM文档安全水印依赖于文档的打印日期。 因此，对于此类文档，水印将恢复为之前的日期。 此外，页眉和页脚也不会保留。

## 向文档{#coverpage}添加自定义封面

用户可以尝试在未安装AEM Security for Microsoft Office插件的计算机上打开受保护的文档。 此类计算机无法打开文档。 在此类计算机上，可显示封面，其中包含下载AEM Security for Microsoft Office插件的说明和其他信息。

### 在配置封面{#before-you-configure-a-cover-page}之前

* 备份CommonResources.dll文件。 默认路径为：

   * **（适用于32位计算机上的32位办公室）** C:\Program Files\Adobe\Adobe Experience Manager Forms\Document Security Extension

   * **（适用于64位计算机上的32位办公室）** C:\Program Files (x86)\Adobe\Adobe Experience Manager Forms\Document Security Extension

   * **（适用于64位计算机上的64位办公室）** C:\Program Files\Adobe\Adobe Experience Manager Forms\Document Security Extension

* 确保已安装Microsoft Visual Studio 2008或更高版本。 您还可以使用任何其他实用程序来编辑DLL文件。
* 解压templates.zip存档。 存档包含封面的。xlsx、.docx和。pptx模板。 仅对文件类型。xlsx、.docx和。pptx使用提供的模板。 您可以为其他文件类型创建自己的模板。 自定义模板以包含自定义消息和说明。 您可以在以下位置找到template.zip:

[获取文件](assets/templates.zip)

### CommonResources.dll文件{#structure-of-the-commonresources-dll-file}的结构

CommonResources.dll文件包含有关资源模板的信息。 它包含两个名称标识符TEMPLATE_FILE和RT_MANIFEST。 要启用自定义封面，将修改TEMPLATE_FILE名称标识符。 TEMPLATE_FILE名称标识符有六个资源：

<table>
 <tbody>
  <tr>
   <td><p><strong>资源</strong></p> </td>
   <td><p><strong>表示 </strong></p> </td>
  </tr>
  <tr>
   <td><p>101 </p> </td>
   <td><p>.xls</p> </td>
  </tr>
  <tr>
   <td><p>102</p> </td>
   <td><p>.doc</p> </td>
  </tr>
  <tr>
   <td><p>103 </p> </td>
   <td><p>.ppt</p> </td>
  </tr>
  <tr>
   <td><p>104 </p> </td>
   <td><p>.xlsx</p> </td>
  </tr>
  <tr>
   <td><p>105</p> </td>
   <td><p>.docx</p> </td>
  </tr>
  <tr>
   <td><p>106</p> </td>
   <td><p>.pptx</p> </td>
  </tr>
 </tbody>
</table>

#### 将模板配置为封面{#configure-the-template-as-a-cover-page}

1. 打开Microsoft Visual Studio。 浏览并打开CommonResources.dll文件进行编辑。

   >[!NOTE]
   >
   >如果文件未出现在“解决方案资源管理器”窗口中，请使用“打开方式”选项重新打开文件。 选择资源编辑器作为编辑器。

1. 在“解决方案资源管理器”窗口中，展开TEMPLATE_FILE目录，并删除资源101。

1. 添加资源：

   1. 在“解决方案资源管理器”中选择项目后，在“项目”菜单上，单击“属性”。
   1. 选择“资源”选项卡。
   1. 在“资源设计器”工具栏中，指向“添加资源”，单击箭头。 对于资源类型，选择TEMPLATE_FILE，然后单击“import”。
   1. 在“将现有文件添加到资源”对话框中，浏览至Resource.xlsx文件，然后单击“打开”。 文件将添加到TEMPLATE_FILE目录。

   >[!NOTE]
   >
   >确保语言设置正确。 使用中性语言删除资源。

1. 对所有资源类型重复步骤2和3。

   >[!NOTE]
   >
   >请勿按随机顺序删除和添加资源类型。 在101之后，配置102等。

### 使用AEM Security Extension for Microsoft Office {#package-custom-commonresources-dll-file-with-the-installer-of-aem-document-security-extension-for-microsoft-office}的安装程序打包自定义CommonResources.dll文件

可以自定义CommonResources.dll文件以添加自定义封面。 自定义文件后，您可以在所有工作站上用自定义文件手动替换原始文件，也可以选择自动方法替换文件。

在大型环境中，用自定义`CommonResources.dll`文件手动替换默认`CommonResources.dll file`很繁琐。 您可以使用自解压和打包工具（例如，WinZip Self-Extractor）将自定义CommonResources.dll文件与AEM Security Extension for Microsoft Office安装程序一起打包。 以后，您可以将自定义安装程序分发到所有工作站。 此方法可缩短将默认`CommonResources.dll`文件替换为自定义文件所需的时间。 它还确保所有工作站都具有所需的CommonResources.dll文件。 自解压和打包工具只是自动替换文件的众多可能方法之一。 您可以选择任何适合您的环境的方法。

可以执行以下步骤，使用AEM Security Extension for Microsoft Office的安装程序打包自定义`CommonResources.dll`文件：

1. 安装自解压器和包装工具。 例如，WinZip Self-Extractor。
1. 创建新文件夹。 例如，YOUR_FOLDER_NAME
1. 将AEM文档安全扩展的原始安装程序和自定义CommonResources.dll文件放在新创建的文件夹中。
1. 在文件夹中创建批处理文件。 例如，YOUR_FOLDER_NAME\Installer.bat
1. 打开要编辑的批处理文件，并向批处理文件添加以下代码：

   ```shell
    @echo off
   
    setlocal EnableDelayedExpansion
   
    msiexec /i YOUR_FOLDER_NAME\MSI_NAME.exe
   
   
    FOR /F "tokens=2,*" %%A IN ('REG query "HKLM\HARDWARE\DESCRIPTION\System\CentralProcessor\0" /v "Identifier"') DO set "IDENTIFIER=%%B"
   
    set IDENTIFIER= %IDENTIFIER: =%
   
    if not %IDENTIFIER:x86=%==%IDENTIFIER% (
   
    REM Fetching install path for 32 bit machine.
   
    FOR /F "tokens=2,*" %%A IN ('REG query "HKLM\SOFTWARE\Adobe\LiveCycle Rights Management ES4\11.0.0" /v "InstallPath"') DO set "INSTALLPATH=%%B"
   
    ) else (
   
        REM Fetching install path for 64 bit machine.
   
            FOR /F "tokens=2,*" %%A IN ('REG query "HKLM\SOFTWARE\Wow6432Node\Adobe\LiveCycle Rights Management ES4\11.0.0" /v "InstallPath"') DO set "INSTALLPATH=%%B"
   
        )
   
    COPY "YOUR_FOLDER_NAME\CommonResources.dll" "%INSTALLPATH%"
   
    endlocal
   ```

   如果您在JEE上使用除LiveCycle Rights Management ES4和版本11.0.0之外的任何其他版本的LiveCycle或AEM Forms，请按如下方式替换注册表项的路径：

   * (LivecycleRights ManagementES2和9.0版):*HKLM\SOFTWARE\Adobe/LiveCycle* *Rights ManagementES2\9.0 *
   * (LivecycleRights ManagementES3和10.0版)
   * (LivecycleRights ManagementES4和11.0版)HKLM\SOFTWARE\Adobe\LiveCycle Rights Management ES4\11.0.0
   * (AEM 6.0Forms关于JEE和更高版本)HKLM\SOFTWARE\Adobe\LiveCycle Rights Management ES4\11.0.0

1. 在以上代码中，将YOUR_FOLDER_NAME的所有实例替换为您在步骤2中创建的文件夹的名称。
1. **(仅适用于具有。exe扩展名的AEM文档 Security Extension for Microsoft Office安装程** 序)替换以下代码行：

   `msiexec /i YOUR_FOLDER_NAME\MSI_NAME.msi`
with

   `START /w YOUR_FOLDER_NAME\APPLICATION_NAME.exe`

1. 保存并关闭批处理文件。
1. 使用自解压器和打包程序工具打包文件夹，其中包含自定义CommonResources.dll文件、AEM Security Extension for Microsoft Office的原始安装程序以及批处理文件。

   >[!NOTE]
   >
   >确保自解压包设置为以管理员身份运行并自动
   >完成提取时运行批处理文件。

现在，针对Microsoft Office的AEM文档 Security Extension的自解压安装程序将自定义CommonResources.dll文件打包并准备分发。
