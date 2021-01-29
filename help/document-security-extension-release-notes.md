---
title: AEM文档 Security for Microsoft Office —— 发行说明
description: 在安装AEM Security 6.2 Extension for Microsoft Office前，请阅读发行说明。
uuid: f6ab73d4-ac4e-4fff-9bb8-917b75401653
content-type: reference
topic-tags: installing
discoiquuid: c9342c28-8289-4831-a613-4bc03431f557
translation-type: tm+mt
source-git-commit: 403b800eab086d131beb65a496836158778954ee
workflow-type: tm+mt
source-wordcount: '1030'
ht-degree: 0%

---


# AEM文档 Security for Microsoft Office —— 发行说明{#aem-document-security-for-microsoft-office-release-notes}

## AEM文档 Security for Microsoft Office {#whats-new-in-aem-document-security-for-microsoft-office}的新增功能

* **支持Office 2019**:文档安全扩展(Microsoft Office)增加了对Microsoft Office 2019的支持。它还应与作为Office 365的一部分安装的Microsoft Office 2019桌面应用程序配合使用。

>[!NOTE]
>
>该文档可以交替使用“Adobe Experience Manager文档安全”(Microsoft Office)、“Adobe Experience Manager文档安全扩展”(Microsoft Office)和“文档安全扩展”(Microsoft Office)。

## 安装和配置AEM文档 Security Extension for Microsoft Office {#installing-and-configuring-aem-document-security-extension-for-microsoft-office}

此版本的文档Security Extension for Microsoft Office与Adobe LiveCycle Rights ManagementES2及更高版本以及AEM表单的文档Security加载项兼容。

在安装AEM文档 Security Extension for Microsoft Office之前，请查看此文档中的信息。 有关详细的安装说明，请参阅[安装和配置AEM Security Extension for Microsoft Office](installing-configuring-aemdsext.md)文章。

## 修复的问题 {#fixed-issues}

* 字符串垂直显示，而将错误的换行符添加到内容中。 (Ref# CQ-4201054)

## 已知问题 {#known-issues}

### 不支持第三方插件{#third-party-plug-ins-not-supported}

AEM文档 Security Extension for Microsoft Office不支持第三方插件。 在安装Microsoft Office文档安全扩展之前，请卸载Microsoft Office的任何第三方插件。

### Microsoft Word、Excel和PowerPoint {#disabled-menu-options-in-microsoft-word-excel-and-powerpoint}中禁用的菜单选项

AEM文档 Security Extension for Microsoft Office使用内置保护功能保护文档、工作表和演示文稿。 它禁用一些Excel、Word和PowerPoint菜单选项。

### Microsoft Office 2013、2016和2019的限制{#restrictions-for-microsoft-office}

在Microsoft Office中，以下选项在受保护的会话期间不可用：

* Microsoft Office 2016或Microsoft Office 2019

   * “文件”>“另存为”
   * “文件”>“历史记录”
   * “文件”>“共享”
   * “文件”>“导出”
   * “文件”>“发布”
   * “文件”>“帐户”
   * “文件”>“信息”>“Protect文档”/“工作簿”/“演示文稿”>“使用口令加密”
   * “文件”>“信息”>“Protect文档”>“添加数字签名”
   * “文件”>“信息”>“Protect文档”>“标记为最终状态”
   * 右上角的共享选项

* Microsoft Office 2013

   * “文件”>“另存为”
   * “文件”>“共享”
   * “文件”>“导出”
   * “文件”>“帐户”
   * “文件”>“信息”>“Protect文档”/“工作簿”/“演示文稿”>“使用口令加密”
   * “文件”>“信息”>“Protect文档”>“添加数字签名”
   * “文件”>“信息”>“Protect文档”>“标记为最终状态”

### 从SharePoint Server {#opening-a-protected-document-from-sharepoint-server}打开受保护的文档

打开受保护的文档:如果尝试从SharePoint Server在Microsoft Office的文档安全扩展中打开受保护的文档，而未先打开与文件类型（如Microsoft Word、Microsoft Excel或Microsoft PowerPoint）关联的Microsoft Office项目，则文档可能无法打开。 将显示一条错误消息，指示您安装适用的插件。 因此，建议先打开关联的Microsoft Office项目，然后再在SharePoint Server的Microsoft Office文档安全扩展中打开受保护的文档。

（可选）建议先清除缓存文件夹，然后再在SharePoint Server中Microsoft Office文档安全扩展中打开受保护的文档。

从SharePoint Server打开受保护的文档时，将禁用该文档的所有权限，而不管所应用的策略。

### 在未安装打印机的情况下，将包含动态水印的策略应用于Microsoft Excel 2013、Microsoft Excel 2016和Microsoft Excel 2019文件{#apply-a-policy-with-a-dynamic-watermark-to-microsoft-excel-microsoft-excel-and-microsoft-excel-file-with-no-printer-installed}

在未安装打印机的计算机上，将包含动态水印的策略应用于Microsoft Excel 2013、Microsoft Excel 2016和Microsoft Excel 2019文件，然后保存该文件时，将出现以下错误：&quot;应用动态水印时出现内部错误。&quot; 重新打开受保护的文件时也会显示此错误。 水印不会应用，也不会从“视图”>“页面布局”中显示。

### 禁用支持的Office应用程序{#disable-windows-data-execution-prevention-for-supported-office-applications}的Windows数据执行预防

建议在使用Microsoft Office应用程序的文档安全扩展时禁用Windows Data Execution Prevention(DEP)设置。

### 无法使用文档安全扩展{#shared-microsoft-office-files-cannot-be-protected-using-document-security-extension}保护共享的Microsoft Office文件

使用文档安全扩展保护任何共享的Microsoft Office文件时，将发生错误，共享文件也不受保护。

### 在包含Microsoft Office和McAfee VirusScan的文档Security Extension {#starting-office-applications-on-a-machine-containing-document-security-extension-for-microsoft-office-and-mcafee-virusscan}的计算机上启动Office应用程序

要确保在已安装文档安全和已启用“按访问扫描程序”的McAfee VirusScan的计算机上顺利开始Office应用程序，请禁用McAfee VirusScan控制台中的“缓冲区溢出保护”选项。

### 在具有不支持的Microsoft Office语言{#installing-document-security-extension-for-microsoft-office-on-a-machine-with-an-unsupported-microsoft-office-language}的计算机上安装文档Security Extension for Microsoft Office

在具有不支持语言的Microsoft Office应用程序的计算机上安装文档Security Extension for Microsoft Office之前，请至少打开一次Office应用程序。

### 即使用户没有脱机权限{#synchronize-offline-button-is-enabled-even-when-a-user-does-not-have-offline-permissions}，也会启用“同步脱机”按钮

即使用户没有该文档的脱机权限，也可以使用“脱机同步”按钮。 但是，选择该按钮不会执行任何操作。

### 不支持试用版Microsoft Office {#no-support-for-trial-versions-of-microsoft-office}

文档Security Extension for Microsoft Office不支持Microsoft Office的试用版。 安装扩展之前，请确保已安装Microsoft Office的许可副本并已激活它。

### 无法打开受保护的Microsoft Office文件{#unable-to-open-a-protected-microsoft-office-files}

如果启用Microsoft Office的受保护视图，则Right Management Extension无法从远程位置打开受保护的Microsoft Excel文件(XLS、XLSX)和受保护的Microsoft PowerPoint(PPT)文件。

### 包含图像或背景颜色的Microsoft Excel文档的单元格显示在水印{#cells-of-microsoft-excel-document-containing-an-image-or-background-color-appear-on-top-of-watermark}的顶部

如果Microsoft Excel文档的某个单元格包含图像或已填充背景颜色，且动态水印策略已应用于该文档，则填充该单元格的图像或背景颜色将显示在水印的顶部并覆盖水印。

### 多个证书{#usability-issue-with-multiple-certificates}的可用性问题

如果客户端计算机上存在多个证书，并且用户取消证书选择对话框，则再次显示该对话框，用户必须取消该对话框两次。

### Microsoft PowerPoint允许编辑受保护的文档{#microsoft-powerpoint-allows-editing-protected-documents}

在尝试编辑受保护的文档时，Microsoft PowerPoint会显示一条消息，“您不允许修改此文档。 您将无法保存更改。” 关闭消息后，用户可以继续添加文本或编辑文档。 但是，对受保护文档所做的更改不会保存。

上述行为在PowerPoint 2013、PowerPoint 2016和PowerPoint 2019中如预期。
