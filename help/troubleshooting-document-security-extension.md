---
title: AEM Document Security Extension for Microsoft Office 疑难解答
description: 如果在安装、配置或使用 AEM Document Security Extension for Microsoft Office 时遇到问题，请按照本文档中列出的说明进行操作。
uuid: 61001ca8-a25a-4879-98ac-563a6eb126e7
contentOwner: khsingh
content-type: reference
topic-tags: using
discoiquuid: bdc3f174-e417-4d3e-b3af-972cdcc10133
exl-id: 98f24032-0774-47f8-bcc5-1ee37b417833
source-git-commit: a15d49cdd21ccb8e6ec6c770a92bf16cb24ffaa1
workflow-type: tm+mt
source-wordcount: '294'
ht-degree: 100%

---

# AEM Document Security Extension for Microsoft Office 疑难解答{#troubleshooting-aem-document-security-extension-for-microsoft-office}

## 安装和配置问题疑难解答 {#troubleshootinginstallationandconfiguration}

如果在安装和配置 AEM Document Security Extension for Microsoft Office 时遇到问题，在安装之前，请确保您认真按照[安装](installing-configuring-aemdsext.md)一文部分中列出的说明进行操作。

如果您根据文档安装和配置了所有内容，请在以下部分中查看与您遇到的问题相似的问题。

### Microsoft Office 应用程序无法加载 Document Security Extension {#document-security-extension-fails-to-load-for-microsoft-office-applications}

Windows 注册表中的 LoadBehavior 属性指定文档安全插件的运行时行为。如果 LoadBehavior 属性设置为 3，则所有插件自动加载。在安装 Document Security Extension for Microsoft Office 之前，请确保 LoadBehavior 属性值设置为 3。

1. 在进行更改之前获取 Windows 注册表的备份。有关详细说明，请参阅[如何修改 Windows 注册表](https://support.microsoft.com/en-us/kb/136393)。
1. 在注册表编辑器中，浏览到 HKEY_CURRENT_USER\Software\Microsoft\Office\Word\Addins\Adobe.DRMIntegration.WordAddin or HKEY_LOCAL_MACHINE\Software\Microsoft\Office\Word\Addins\Adobe.DRM。
1. 将 **LoadBehavior** 属性的值设置为 3。

1. 关闭注册表编辑器。

有关 LoadBehavior 的详细信息，请参阅 [VSTO 增益集的注册表项](https://msdn.microsoft.com/en-us/library/bb386106.aspx#LoadBehavior)一文。

## 管理任务疑难解答 {#admintasks}

此部分讨论安装 AEM Document Security Extension 时的可能问题。

### Microsoft Office 应用程序在安装 Document Security Extension 时不会顺利启动 {#microsoft-office-applications-dont-start-smoothly-on-installing-document-security-extension}

在安装了 Document Security Extension 并为 McAfee VirusScan 启用了 On-Access Scan 的计算机上，为了确保 Office 应用程序顺利启动，请在 McAfee VirusScan 控制台中禁用 Buffer Overflow Protection 选项。
