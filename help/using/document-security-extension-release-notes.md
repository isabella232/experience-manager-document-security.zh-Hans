---
title: AEM Document Security for Microsoft Office - 发行说明
description: 在安装 AEM Document Security 6.2 Extension for Microsoft Office 之前，请阅读发行说明。
uuid: f6ab73d4-ac4e-4fff-9bb8-917b75401653
content-type: reference
topic-tags: installing
discoiquuid: c9342c28-8289-4831-a613-4bc03431f557
exl-id: 582f10bb-60d2-46ed-b81d-5818a040edc6
source-git-commit: 28137f26afc024d411857d44887bf69fe1ee2b81
workflow-type: ht
source-wordcount: '1051'
ht-degree: 100%

---

# AEM Document Security for Microsoft Office - 发行说明{#aem-document-security-for-microsoft-office-release-notes}

## AEM Document Security for Microsoft Office 中的新增功能 {#whats-new-in-aem-document-security-for-microsoft-office}

* **对 Office 2019 的支持**：Document Security Extension for Microsoft Office 已添加了对 Microsoft Office 2019 的支持。它还应该可以与作为 Office 365 一部分安装的 Microsoft Office 2019 桌面应用程序一起使用。

>[!NOTE]
>
>本文档将互换使用术语 Adobe Experience Manager Document Security for Microsoft Office、Adobe Experience Manager Document Security Extension for Microsoft Office 和 Document Security Extension for Microsoft Office。

## 安装和配置 AEM Document Security Extension for Microsoft Office {#installing-and-configuring-aem-document-security-extension-for-microsoft-office}

此版本的 Document Security Extension for Microsoft Office 与 Adobe LiveCycle Rights Management ES2 和更高版本以及 AEM Forms 的 Document Security 插件兼容。

在安装 AEM Document Security Extension for Microsoft Office 之前，请查看本文档中的信息。有关详细安装说明，请参阅[安装和配置 AEM Document Security Extension for Microsoft Office](installing-configuring-aemdsext.md) 文章。

## 修复的问题 {#fixed-issues}

* 字符串垂直显示，内容中添加了错误的换行符。(Ref# CQ-4201054)

## 已知问题 {#known-issues}

### 不支持第三方插件 {#third-party-plug-ins-not-supported}

AEM Document Security Extension for Microsoft Office 不使用第三方插件。在安装 Document Security Extension for Microsoft Office 之前，请卸载 Microsoft Office 的任意第三方插件。

### 禁用了 Microsoft Word、Excel 和 PowerPoint 中的某些菜单选项 {#disabled-menu-options-in-microsoft-word-excel-and-powerpoint}

AEM Document Security Extension for Microsoft Office 使用内置的保护功能来保护文档、工作表和演示文稿。它禁用了一些 Excel、Word 和 PowerPoint 菜单选项。

### Microsoft Office 2013、2016 和 2019 的限制 {#restrictions-for-microsoft-office}

在 Microsoft Office 中，在受保护的会话中以下选项不可用：

* Microsoft Office 2016 或 Microsoft Office 2019

   * 文件 > 另存为
   * 文件 > 历史记录
   * 文件 > 共享
   * 文件 > 导出
   * 文件 > 发布
   * 文件 > 帐户
   * 文件 > 信息 > 保护文档/工作簿/演示文稿 > 使用密码加密
   * 文件 > 信息 > 保护文档 > 添加数字签名
   * 文件 > 信息 > 保护文档 > 标记为最终状态
   * 右上角的共享选项

* Microsoft Office 2013

   * 文件 > 另存为
   * 文件 > 共享
   * 文件 > 导出
   * 文件 > 帐户
   * 文件 > 信息 > 保护文档/工作簿/演示文稿 > 使用密码加密
   * 文件 > 信息 > 保护文档 > 添加数字签名
   * 文件 > 信息 > 保护文档 > 标记为最终状态

### 从 SharePoint Server 打开受保护的文档 {#opening-a-protected-document-from-sharepoint-server}

打开受保护的文档：如果您尝试从 SharePoint Server 在 Document Security Extension for Microsoft Office 中打开受保护的文档而没有先打开与该文件类型关联的 Microsoft Office 程序，例如 Microsoft Word、Microsoft Excel 或 Microsoft PowerPoint，则文档无法打开。此时会显示一条错误消息，指示您安装适用的插件。因此，建议您先打开关联的 Microsoft Office 程序，然后再从 SharePoint Server 在 Document Security Extension for Microsoft Office 中打开受保护的文档。

（可选）建议在从 SharePoint Server 在 Document Security Extension for Microsoft Office 中打开受保护的文档之前，清除缓存文件夹。

在从 SharePoint Server 打开受保护文档时，文档上的所有权限将禁用，不论应用了什么策略。

### 在未安装打印机的情况下将带有动态水印的策略应用于 Microsoft Excel 2013、Microsoft Excel 2016 和 Microsoft Excel 2019 文件 {#apply-a-policy-with-a-dynamic-watermark-to-microsoft-excel-microsoft-excel-and-microsoft-excel-file-with-no-printer-installed}

在未安装打印机的计算机上，将带有动态水印的策略应用到 Microsoft Excel 2013、Microsoft Excel 2016 和 Microsoft Excel 2019 文件然后保存文件时，将显示以下错误：“应用动态水印时出现内部错误。”在重新打开受保护文件时也会显示此错误。 水印未应用，在“视图”>“页面布局”中不可见。

### 为支持的 Office 应用程序禁用 Windows 数据执行保护 {#disable-windows-data-execution-prevention-for-supported-office-applications}

建议在使用 Document Security Extension for Microsoft Office 应用程序时禁用 Windows 数据执行保护 (DEP) 设置。

### 无法使用 Document Security Extension 保护共享的 Microsoft Office 文件 {#shared-microsoft-office-files-cannot-be-protected-using-document-security-extension}

在使用 Document Security Extension 保护任何共享的 Microsoft Office 文件时出错，共享的文件未受保护。

### 在包含 Document Security Extension for Microsoft Office 和 McAfee VirusScan 的计算机上启动 Office 应用程序 {#starting-office-applications-on-a-machine-containing-document-security-extension-for-microsoft-office-and-mcafee-virusscan}

为了确保 Office 应用程序在装有 Document Security 以及启用了 On-Access Scan 的 McAfee VirusScan 的计算机上可顺畅启动，请禁用 McAfee VirusScan 控制台中禁用“缓冲区溢出保护”选项。

### 在具有不支持的 Microsoft Office 语言的计算机上安装 Document Security Extension for Microsoft Office {#installing-document-security-extension-for-microsoft-office-on-a-machine-with-an-unsupported-microsoft-office-language}

在装有具有不支持的语言的 Microsoft Office 应用程序的计算机上安装 Document Security Extension for Microsoft Office 之前，请打开 Office 应用程序至少一次。

### 即使在用户没有离线权限时也启用了“离线同步”按钮 {#synchronize-offline-button-is-enabled-even-when-a-user-does-not-have-offline-permissions}

“离线同步”按钮可用，即使用户没有文档的离线权限。但是，选择该按钮没有任何效果。

### 不支持 Microsoft Office 的试用版 {#no-support-for-trial-versions-of-microsoft-office}

Document Security Extension for Microsoft Office 不支持 Microsoft Office 的试用版。在安装扩展之前，请确保您已安装了 Microsoft Office 的许可副本并且已激活。

### 无法打开受保护的 Microsoft Office 文件 {#unable-to-open-a-protected-microsoft-office-files}

如果启用了 Microsoft Office 的受保护的视图，则 Right Management Extension 无法从远程位置打开受保护的 Microsoft Excel 文件（XLS、XLSX）和受保护的 Microsoft PowerPoint (PPT) 文件。

### Microsoft Excel 文档中包含图像或背景颜色的单元格出现在水印之上 {#cells-of-microsoft-excel-document-containing-an-image-or-background-color-appear-on-top-of-watermark}

如果 Microsoft Excel 文档的某个单元格包含图像或者填充了背景色，而将动态水印策略应用于该文档，则该单元格中的图像或填充的背景色出现在水印之上并遮住水印。

### 多个证书的可用性问题 {#usability-issue-with-multiple-certificates}

如果客户端计算机上存在多个证书，而用户取消了证书选择对话框，则再次出现该对话框，而用户必须取消该对话框两次。

### Microsoft PowerPoint 允许编辑受保护的文档 {#microsoft-powerpoint-allows-editing-protected-documents}

在尝试编辑受保护文档时，Microsoft PowerPoint 显示消息“不允许您修改此文档。您无法保存更改。”关闭消息后，用户可以继续添加文本或编辑文档。但是，对受保护文档进行的更改不保存。

上述行为预期会在 PowerPoint 2013、PowerPoint 2016 和 PowerPoint 2019 中出现。
