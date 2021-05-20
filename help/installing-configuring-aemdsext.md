---
title: 安装和配置 AEM Document Security Extension for Microsoft Office
description: 本文档指导您完成安装和配置 Adobe Experience Manager Document Security Extension 6.2 for Microsoft Office。
uuid: 9d7eb6bb-4780-4d82-8657-7c6c6d523af0
content-type: reference
topic-tags: installing
discoiquuid: f1cdf344-efe4-4cb5-9fc3-47ee4ba5faf4
exl-id: 88759737-d57f-4354-951e-ad9f62d0a872
source-git-commit: a15d49cdd21ccb8e6ec6c770a92bf16cb24ffaa1
workflow-type: tm+mt
source-wordcount: '2796'
ht-degree: 100%

---

# 安装和配置 AEM Document Security Extension for Microsoft Office{#installing-and-configuring-aem-document-security-extension-for-microsoft-office}

本文档指导您完成安装和配置 Adobe Experience Manager Document Security Extension for Microsoft Office。

本文档包含有关以下任务的信息：

* 安装 Document Security Extension for Microsoft Office
* 预先配置安装程序以指向 LiveCycle Rights Management ES2 或更高版本或者 AEM 6.0 Forms 或更高版本的 Document Security 插件。
* 配置默认策略的自动应用

## 安装之前 {#before-you-install}

在安装 Document Security Extension for Microsoft Office 之前，请确保：

* 您已阅读[发行说明](document-security-extension-release-notes.md)。
* Microsoft Office 已激活。打开 Microsoft Office 应用程序时未显示激活对话框。
* Microsoft Windows 和 Microsoft Office 的最新服务包已安装。
* 如果您在为不支持的语言安装 Document Security for Microsoft Office，请至少打开 Office 应用程序一次。

>[!NOTE]
>
>不要将软件安装在其名称包含双字节字符的文件夹中。如果这样做，Microsoft Office 中将不显示 AEM Document Security 菜单。

>[!NOTE]
>
>支持在 64 位操作系统上安装 32 位版本的 Document Security Extension，但反之则不支持。无法在 32 位操作系统上安装 64 位版本的 Document Security Extension for Microsoft Office。

### 禁用 McAfee VirusScan {#disable-mcafee-virusscan}

在安装了 Document Security Extension 并为 McAfee VirusScan 启用了 On-Access Scan 的计算机上，为了确保 Office 应用程序顺利启动，请在 McAfee VirusScan 控制台中禁用 Buffer Overflow Protection 选项。

### 卸载第三方插件 {#uninstall-third-party-plug-ins}

AEM Document Security Extension for Microsoft Office 不支持 Microsoft Office 应用程序的第三方插件。由于此扩展与第三方插件冲突，在安装 Document Security for Microsoft Office 之前，请卸载 Microsoft Office 的任意非 Adobe 插件。Adobe 不提供对安装了第三方插件的 Document Security for Microsoft Office 应用程序的支持。

## 系统要求{#system-requirements}

### Document Security Extension 客户端 {#document-security-extension-client}

确保要安装 Document Security Extension 的计算机满足以下最低配置：

* 英语、法语、德语、日语、意大利语、西班牙语、巴西葡萄牙语、朝鲜语、简体中文和繁体中文的 32 位或 64 位版本的 Microsoft Windows 7 或 Windows 10。
   **注意：** *Document Security Extension for Microsoft Office 应该也可以在 Microsoft Surface 设备上使用。*

* 英语、法语、德语、日语、意大利语、西班牙语、巴西葡萄牙语、朝鲜语、简体中文和繁体中文的 32 位或 64 位版本的 Microsoft Office 2013、2016、2019 以及作为 Office 365 一部分安装的 Microsoft Office 桌面应用程序。

   **注意**：*AEM Document Security Extension for Microsoft Office 不支持 Microsoft Office 应用程序的第三方插件。由于此扩展可能与第三方插件冲突，在安装 Document Security Extension for Microsoft Office 之前，必须卸载 Microsoft Office 应用程序的任意非 Adobe 插件。Adobe 不提供对安装了第三方插件的 Document Security Extensions for Microsoft Office 应用程序的支持。*

* 1.3 GHz 处理器或更高
* 2 GB RAM
* 100 MB 可用硬盘空间

### Document Security {#document-security}

要使用 Document Security Extension，请确保您可以连接到 Adobe LiveCycle Rights Management ES2 和更高版本或 AEM 6.0 Forms 或更高版本的 Document Security 插件。

## 安装 Document Security Extension for Microsoft Office {#installing-document-security-extension-for-microsoft-office}

安装程序可以从[下载页面](download-installer.md)下载。无法直接自定义安装程序可执行文件，但它可以在交互模式或静默模式下安装。要安装软件，请以管理员身份登录 Windows。

为 32 位和 64 位版本的 Microsoft Office 提供了单独的安装程序。对于 32 位版本的 Microsoft Office，请下载 DocumentSecurityExtensionforMicrosoftOffice.exe。对于 64 位版本的 Microsoft Office，请下载 DocumentSecurityExtensionforMicrosoftOffice64.exe。

>[!NOTE]
>
>此文档使用 32 位安装程序文件 (DocumentSecurityExtensionforMicrosoftOffice.exe) 来说明各种命令和选项。如果您使用 64 位版本的 Microsoft Office，请使用 64 位安装程序文件 (DocumentSecurityExtensionforMicrosoftOffice64.exe) 来执行本文档中列出的操作。

### 在静默模式下安装 {#install-in-silent-mode}

使用文件提取器实用程序，例如 WinZip，从安装程序文件中提取 `DocumentSecurityExtensionforMicrosoftOffice.exe`。打开命令行提示符，转到包含设置文件的文件夹，然后键入以下文本：

`DocumentSecurityExtensionforMicrosoftOffice.exe -s -a -s -v" /qn"`

安装程序也以 MSI 文件提供，此文件可用于定制。

### 在静默模式下安装 MSI 文件 {#install-an-msi-file-in-silent-mode}

1. 使用文件提取器实用程序，例如 WinZip，从 ZIP 文件中提取 `DocumentSecurityExtensionforMicrosoftOffice.msi` 文件。

1. 打开命令行提示符，转到包含 MSI 文件的文件夹，然后键入以下文本：

   `msiexec /I DocumentSecurityExtensionforMicrosoftOffice.msi /qn`

## 预配置安装程序以连接到 Document Security {#preconfiguring-the-installer-to-connect-to-document-security}

您可以预配置 Document Security Extension for Microsoft Office 安装程序以指向 LiveCycle 或 AEM 服务器，以便安装 Document Security Extension for Microsoft Office 的用户可以使用这些功能而不需要配置连接。这样，用户可以打开受保护文档而无需配置。但是，用户无法保护新文档，除非配置客户端使用特定服务器。

以下步骤描述了如何创建和配置 MSI 文件。此 MSI 文件包含向企业中安装的 LiveCycle 或 AEM 服务器预配置 Document Security Extension for Microsoft Office 安装程序所需的注册表值。

### 自定义安装程序的先决条件 {#prerequisites-for-customizing-the-installer}

使用 Orca 数据库编辑器自定义安装程序。以下步骤描述了如何使用 Orca 数据库编辑器，通过修改 MSI 安装文件的副本来创建自定义 MSI 文件。Orca 作为 Windows SDK for Windows Server 2008 和 .NET Framework 3.5 的一部分提供。有关如何使用 Orca 编辑 Microsoft Windows® 安装程序文件的更多信息，请参阅 [Microsoft 支持](http://support.microsoft.com/kb/255905/EN-US/)。

>[!NOTE]
>
>建议您在创建自定义 MSI 文件之前，对所有安装程序文件进行完全备份。

#### 安装 Orca {#install-orca}

1. 从 [Microsoft 下载中心](http://www.microsoft.com/download/en/details.aspx?displaylang=en&amp;id=11310)下载 Windows SDK for Windows Server 2008 和 .NET Framework 3.5。
1. 双击 \Microsoft SDK\bin 文件夹中的 Orca.msi 文件。

   您还需要安装程序文件的 MSI 变体。联系 Adobe 支持以接收最新版本的 MSI 安装程序。

   >[!NOTE]
   >
   >始终在运行安装程序之前关闭 DocumentSecurityExtensionforMicrosoftOffice.msi 文件。如果 Orca 在使用 MSI 文件，您无法运行安装程序。

### 创建和配置 MSI 文件 {#create-and-configure-the-msi-file}

1. 单击 **[!UICONTROL 开始 > 程序 > Orca]**。

1. 单击 **[!UICONTROL 文件 > 打开]**，然后浏览到 `DocumentSecurityExtensionforMicrosoftOffice.msi` 文件。

1. 从表的列表（左侧）中选择“属性”。

1. 根据企业安装的是 Rights Management 还是 Document Security，相应编辑以下键名和键值。

<table>
 <tbody>
  <tr>
   <td><p><strong>键</strong><strong></strong><strong>名</strong></p> </td>
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
   <td><p>主机服务器 URL。</p> </td>
   <td><p>https://default.corp.com:1234</p> </td>
  </tr>
 </tbody>
</table>

1. 从表的列表（左侧）中选择“注册表”。

1. 输入以下键名和键值。

   | **键名** | **描述** | **键值默认值** |
   |---|---|---|
   | `IsDefault` | 默认 APS 服务器。 | 默认服务器 |

1. 将修改的文件保存到包含原始 MSI 安装程序的同一个目录。

   >[!NOTE]
   >
   >一种常见做法是使用与原始 MSI 文件相同的文件名（例如，`DocumentSecurityExtensionforMicrosoftOffice.msi`）。

## 配置默认策略的自动应用 {#configuring-automatic-application-of-a-default-policy}

作为配置的一部分，您可以配置自动应用默认策略，这样 Document Security Extension for Microsoft Office 可以保护所保存的每个文档。

可以指定下列选项之一：

* 使用默认策略保护所有文档。
* 允许用户在无法连接到服务器时选择以无保护格式保存文件。这种灵活性使得您可以考虑用户在断开网络连接时创建文档的情况（例如，在飞机上时）。

在启用自动应用策略功能之后，以下情况中使用默认策略保护文档：

* 用户编辑并保存新创建的文档
* 用户编辑并保存无保护的文档
* 用户打开应用程序并打开默认文档，编辑，然后保存文档

### 在 MSI 文件中配置自动应用策略功能 {#configure-the-auto-apply-policy-feature-in-the-msi-file}

在开始之前，请预配置安装程序指向 LiveCycle 或 AEM Forms 服务器，如本文中前面所述。

1. 单击 **[!UICONTROL 开始 > 程序 > Orca]**。

1. 单击 **[!UICONTROL 文件 > 打开]**，然后浏览到 `DocumentSecurityExtensionforMicrosoftOffice.msi` 文件。

1. 从表的列表（左侧）中选择“属性”。

1. 根据企业安装的是 Rights Management 还是 Document Security，相应编辑以下键名和键值。

<table>
 <tbody>
  <tr>
   <td><p><strong>键名</strong></p> </td>
   <td><p><strong>描述</strong></p> </td>
   <td><p><strong>键</strong><strong></strong><strong>值默认值</strong></p> </td>
  </tr>
  <tr>
   <td><p><code>AUTO_APPLY_POLICY_IS_AUTO_ APPLY</code></p> </td>
   <td><p>启用或禁用自动应用策略功能。</p> <p><code>1</code>：启用</p> <p>0：禁用</p> </td>
   <td><p>0</p> </td>
  </tr>
  <tr>
   <td><p><code>AUTO_APPLY_POLICY_POLICY_I D</code></p> </td>
   <td><p>保存新文档时使用的策略 GUID。适用于自动应用策略功能。</p> </td>
   <td><p>在 RM 服务器上显示的十六进制策略 ID</p> </td>
  </tr>
  <tr>
   <td><p><code>AUTO_APPLY_POLICY_SERVER_U RL</code></p> </td>
   <td><p>服务器 URL。</p> </td>
   <td><p>default.corp.com</p> </td>
  </tr>
  <tr>
   <td><p><code>AUTO_APPLY_POLICY_SERVER_P ORT_NO</code></p> </td>
   <td><p>服务器端口号。</p> </td>
   <td><p>1234</p> </td>
  </tr>
  <tr>
   <td><p><code>AUTO_APPLY_POLICY_ALLOW_UN PROTECTED_SAVE</code></p> </td>
   <td><p>确定在首次保存时如果客户端无法连接到服务器来保护文档，是否创建文档而不使用 Document Security 保护。</p> <p>1：允许无保护保存 </p> <p>0：在客户端无法连接到服务器来保存文档时阻止创建新文档。</p> </td>
   <td><p>0</p> </td>
  </tr>
 </tbody>
</table>

>[!NOTE]
>
>`AUTO_APPLY_POLICY_ALLOW_UN PROTECTED_SAVE` 选项在要提醒客户保存所有文档而不强制他们这样做时很有用。当您知道客户在网络连接断开的情况下创建文档时，这也很有用。您不希望阻止他们创建和保存文档。

1. 将修改的文件保存到包含原始 MSI 文件的同一个目录。

   >[!NOTE]
   >
   >一种常见做法是使用与原始 MSI 文件相同的文件名（例如，`DocumentSecurityExtensionforMicrosoftOffice.msi`）。

## 启用新文档的自动保护 {#enabling-automatic-protection-of-new-documents}

管理员可以启用自动保护用户保存的任何文档的功能。管理员在 Document Security Extension for Microsoft Office 的安装程序中配置自动应用策略功能。

如果启用了自动应用策略，则用户保存的所有文档将受默认策略保护。此操作适用于以下情况：

* 用户创建新文档、编辑并保存它时。
* 用户打开无保护文档、编辑并保存它时。

有关配置自动应用策略的信息，请参阅[配置默认策略的自动应用](installing-configuring-aemdsext.md#p-configuring-automatic-application-of-a-default-policy-p)。

## 启用无功能区用户界面 {#enable-ribbon-less-user-interface}

您可通过在 Windows 注册表中修改设置来启用/禁用无功能区界面。执行以下步骤来更新注册表并启用无功能区用户界面：

1. 在进行更改之前获取 Windows 注册表的备份。有关详细说明，请参阅[如何修改 Windows 注册表](https://support.microsoft.com/en-us/kb/136393)。
1. 在注册表编辑器中，导航到 HKEY_CURRENT_USER\Software\Adobe\LiveCycle Rights Management ES4\11.0.0 或 HKEY_LOCAL_MACHINE\Software\Adobe\LiveCycle Rights Management ES4\11.0.0
1. 创建名为 **HidePluginUI** 的新 Dword（32 位）值。

1. 将 **HidePluginUI** 属性的值设置为 1 以启用无功能区用户界面。

1. 关闭注册表编辑器。

## 为 Microsoft Excel 中的打印启用水印 {#enable-watermark-for-printing-in-microsoft-excel}

您可以更改 Windows 注册表设置以使动态水印与现有页眉和页脚共存。注册表设置使水印仅在打印期间可用。执行以下步骤来更新注册表并在打印期间启用水印：

1. 在进行更改之前获取 Windows 注册表的备份。有关详细说明，请参阅[如何修改 Windows 注册表](https://support.microsoft.com/en-us/kb/136393)。
1. 在注册表编辑器中，导航到 HKEY_CURRENT_USER\Software\Adobe\LiveCycle Rights Management ES4\11.0.0 或 HKEY_LOCAL_MACHINE\WOW6432NODE\Software\Adobe\LiveCycle Rights Management ES4\11.0.0
1. 创建新的注册表项 **WatermarkMode**。
1. 在 WatermarkMode 注册表项下，创建 DWORD **WatermarkMode**，并将 DWORD **WatermarkMode** 的值设置为 **1**。

1. 关闭注册表编辑器。

>[!NOTE]
>
>在 Windows 资源管理器中，可以使用“文件”菜单或上下文菜单来创建 Microsoft Excel 文档。对于使用所述方法创建的文档，无法检索或更改打印日期。这是 Microsoft Excel 的限制。AEM Document Security 水印依赖于文档的打印日期。因此，对于此类文档，水印将恢复到之前的日期。此外，页眉和页脚也不保留。

## 向文档添加自定义封面页 {#coverpage}

用户尝试在未安装 AEM Document Security for Microsoft Office 插件的计算机上打开受保护的文档。此类计算机无法打开文档。在此类计算机上，您可以显示包含下载 AEM Document Security for Microsoft Office 插件和其他信息的封面页。

### 配置封面页之前 {#before-you-configure-a-cover-page}

* 对 CommonResources.dll 文件进行备份。默认路径为：

   * **（对于 32 位计算机上的 32 位 Office）** C:\Program Files\Adobe\Adobe Experience Manager Forms\Document Security Extension

   * **（对于 32 位计算机上的 64 位 Office）** C:\Program Files (x86)\Adobe\Adobe Experience Manager Forms\Document Security Extension

   * **（对于 64 位计算机上的 64 位 Office）** C:\Program Files\Adobe\Adobe Experience Manager Forms\Document Security Extension

* 确保您安装了 Microsoft Visual Studio 2008 或更高版本。您也可以使用任何其他实用程序编辑 DLL 文件。
* 提取 templates.zip 存档。存档包含封面页的 .xlsx、.docx 和 .pptx 模板。仅为文件类型 .xlsx、.docx 和 .pptx 使用提供的模板。可以为其他文件类型创建自己的模板。自定义模板以包含自定义消息和说明。在以下位置可以找到 template.zip：

[获取文件](assets/templates.zip)

### CommonResources.dll 文件的结构{#structure-of-the-commonresources-dll-file}

CommonResources.dll 文件包含有关资源模板的信息。它包含两个名称标识符 TEMPLATE_FILE 和 RT_MANIFEST。要启用自定义封面页，需要修改 TEMPLATE_FILE 名称标识符。TEMPLATE_FILE 名称标识符有六个资源：

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

#### 配置模板作为封面页 {#configure-the-template-as-a-cover-page}

1. 打开 Microsoft Visual Studio。浏览并打开 CommonResources.dll 文件进行编辑。

   >[!NOTE]
   >
   >如果文件未显示在 Solution Explorer 窗口中，请使用“打开方式”选项重新打开文件。选择资源编辑器作为编辑器。

1. 在 Solution Explorer 窗口中，展开 TEMPLATE_FILE 目录并删除资源 101。

1. 添加资源：

   1. 在 Solution Explorer 中选定一个项目，在“项目”菜单中，单击“属性”。
   1. 选择“资源”选项卡。
   1. 打开“资源设计器”工具栏，指向“添加资源”，单击箭头。对于资源类型，选择“TEMPLATE_FILE”，然后单击“导入”。
   1. 在“将现有文件添加到资源”对话框中，浏览到 Resource.xlsx 文件，然后单击“打开”。文件添加到 TEMPLATE_FILE 目录。

   >[!NOTE]
   >
   >确保语言设置正确。使用中性语言删除资源。

1. 对所有资源类型重复步骤 2 和 3。

   >[!NOTE]
   >
   >不要以随机顺序删除和添加资源类型。在 101 之后，配置 102，以此类推。

### 将自定义 CommonResources.dll 文件打包到 AEM Document Security Extension for Microsoft Office 的安装程序中 {#package-custom-commonresources-dll-file-with-the-installer-of-aem-document-security-extension-for-microsoft-office}

可以自定义 CommonResources.dll 文件以添加自定义封面页。自定义文件之后，您可以在所有工作站上使用自定义文件手动替换原始文件，或者选择自动方法来替换文件。

在大型环境中，手动将默认 `CommonResources.dll file` 替换为自定义 `CommonResources.dll` 文件不仅困难，而且繁琐。您可以使用自行提取和打包工具（例如，WinZip Self-Extractor）来将自定义 CommonResources.dll 文件打包到 AEM Document Security Extension for Microsoft Office 安装程序。以后，您可以将自定义安装程序分发到所有工作站。此方法可减少使用自定义文件替换默认 `CommonResources.dll` 文件所需的时间。它还可以确保所有工作站具有所需的 CommonResources.dll 文件。自行提取和打包工具只不过是自动替换文件的众多可行方法之一。您可以选择适合您环境的任意方法。

您可以执行以下步骤，将自定义 `CommonResources.dll` 文件打包到 AEM Document Security Extension for Microsoft Office 的安装程序中：

1. 安装自行提取和打包工具。例如，WinZip Self-Extractor。
1. 创建新文件夹。例如，YOUR_FOLDER_NAME
1. 将 AEM Document Security Extension 的原始安装程序和自定义 CommonResources.dll 文件放在新创建的文件夹中。
1. 在文件夹中创建批处理文件。例如 YOUR_FOLDER_NAME\Installer.bat
1. 打开批处理文件进行编辑，添加以下代码到批处理文件中：

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

   如果您在 JEE 上使用除了 LiveCycle Rights Management ES4 以及版本 11.0.0 之外的任何其他版本的 LiveCycle 或 AEM Forms，请更换注册表项的路径如下所示：

   * （Livecycle Rights Management ES2 和版本 9.0）：*HKLM\SOFTWARE\Adobe/LiveCycle* *Rights Management ES2\9.0 *
   * （Livecycle Rights Management ES3 和版本 10.0）
   * （Livecycle Rights Management ES4 和版本 11.0）HKLM\SOFTWARE\Adobe\LiveCycle Rights Management ES4\11.0.0
   * （JEE 上的 AEM 6.0 Forms 及更高版本）HKLM\SOFTWARE\Adobe\LiveCycle Rights Management ES4\11.0.0

1. 在上述代码中，将出现的所有 YOUR_FOLDER_NAME 替换为您在第 2 步中创建的文件夹的名称。
1. **（仅适用于 AEM Document Security Extension for Microsoft Office 安装程序及 .exe 扩展名）** 替换以下代码行：

   `msiexec /i YOUR_FOLDER_NAME\MSI_NAME.msi`
替换为

   `START /w YOUR_FOLDER_NAME\APPLICATION_NAME.exe`

1. 保存并关闭批处理文件。
1. 使用自行提取和打包工具，将包含自定义 CommonResources.dll 文件、AEM Document Security Extension for Microsoft Office 原始安装程序和批处理文件的文件夹打包。

   >[!NOTE]
   >
   >确保自行提取程序包设置为自动以管理员身份运行。
   >在提取完成时运行批处理文件。

现在，自行提取的 AEM Document Security Extension for Microsoft Office 安装程序打包了自定义 CommonResources.dll 文件，并且可供分发。
