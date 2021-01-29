---
title: 对AEM文档 Security Extension for Microsoft Office进行疑难解答
description: 如果您在安装、配置或使用AEM文档 Security Extension for Microsoft Office时遇到问题，请按照本文档中列出的说明操作。
uuid: 61001ca8-a25a-4879-98ac-563a6eb126e7
contentOwner: khsingh
content-type: reference
topic-tags: using
discoiquuid: bdc3f174-e417-4d3e-b3af-972cdcc10133
translation-type: tm+mt
source-git-commit: ac26ec61f62d7a3db2429c8a9d3f68b82ba8f77a
workflow-type: tm+mt
source-wordcount: '294'
ht-degree: 0%

---


# 排除AEM文档 Security Extension for Microsoft Office{#troubleshooting-aem-document-security-extension-for-microsoft-office}故障

## 安装和配置问题疑难解答{#troubleshootinginstallationandconfiguration}

如果安装和配置AEM文档 Security Extension for Microsoft Office时遇到问题，请确保仔细遵循[安装](installing-configuring-aemdsext.md)文章的“安装前-”部分中列出的说明。

如果您根据文档安装并配置了所有内容，请查看以下部分以了解与您遇到的问题类似的问题。

### 文档安全扩展无法加载Microsoft Office应用程序{#document-security-extension-fails-to-load-for-microsoft-office-applications}

Windows注册表中的LoadBehavior属性指定文档安全插件的运行时行为。 如果LoadBehavior属性设置为3，则自动加载所有插件。 在安装文档Security Extension for Microsoft office之前，请确保将值LoadBehavior属性设置为3。

1. 在对Windows注册表进行更改之前备份它。 有关详细说明，请参阅[如何修改Windows注册表](https://support.microsoft.com/en-us/kb/136393)。
1. 在注册表编辑器中，导航toHKEY_CURRENT_USER\Software\Microsoft\Office\Word\Addins\Adobe.DRMIntegration.WordAddin或HKEY_LOCAL_MACHINE\Software\Microsoft\Office\Word\Addins\Adobe.DRM。
1. 将&#x200B;**LoadBehavior**&#x200B;属性的值设置为3。

1. 关闭注册表编辑器。

有关LoadBehavior的详细信息，请参阅[VSTO Add-ins的注册表条目](https://msdn.microsoft.com/en-us/library/bb386106.aspx#LoadBehavior)文章。

## 管理任务{#admintasks}疑难解答

本节讨论安装的AEM文档安全扩展的可能问题。

### 安装文档安全扩展{#microsoft-office-applications-dont-start-smoothly-on-installing-document-security-extension}时，Microsoft Office应用程序开始不顺畅

要确保在装有文档安全扩展和已启用“按访问扫描程序”的McAfee VirusScan的计算机上顺利开始Office应用程序，请禁用McAfee VirusScan控制台中的“缓冲区溢出保护”选项。
