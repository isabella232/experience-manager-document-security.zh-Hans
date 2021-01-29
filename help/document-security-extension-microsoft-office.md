---
title: AEM文档 Security Extension for Microsoft Office简介
description: 使用文档Security Extension for Microsoft Office，您可以对Microsoft Office文件应用预定义的机密性设置。
uuid: a5428c50-fae3-4823-9e6f-0f5306e7248f
content-type: reference
topic-tags: using
discoiquuid: cf93f9f5-1fb6-4909-815e-0ffb8c6ea6d1
translation-type: tm+mt
source-git-commit: 19de0b62ac493c7507581abb607b008c64f77597
workflow-type: tm+mt
source-wordcount: '1304'
ht-degree: 0%

---


# 介绍AEM文档 Security Extension for Microsoft Office{#introduction-to-aem-document-security-extension-for-microsoft-office}

Adobe®Experience Manager文档安全扩展，Microsoft® Office确保只有经您授权的人员才能使用包含您的知识产权的Word、Excel和PowerPoint文件。 通过使用Microsoft Office的文档安全扩展，可以对文件应用预定义的机密性设置。

文档安全扩展(Microsoft Office)扩展了Adobe Experience Manager Forms的LiveCycleRights Management和文档安全插件，以保护Word、Excel和PowerPoint文件，并允许安装该软件的授权用户根据策略中建立的机密性设置使用受策略保护的文件。

## 文档安全如何保护知识产权{#how-document-security-protects-intellectual-property}

文档安全确保只有经您授权的人员才能使用包含您的知识产权的文件。 使用文档安全性，您可以使用机密性策略保护文件。 *策略*&#x200B;是包含机密性设置和授权用户列表的信息集合。 在策略中指定的设置决定了收件人如何使用您应用策略的文件。 例如，您可以指定收件人可以打印、复制文本还是保存更改。

文档安全管理员和用户创建策略。 管理员创建可供所有授权用户使用的组织策略。 管理员或策略集协调员还可以创建称为&#x200B;*策略集*&#x200B;的策略组，这些策略组对用户子集可用。 用户可以创建自己的策略，只有他们才能使用。 管理员、策略集协调员和用户可使用文档安全网页创建策略。

虽然策略存储在文档安全上，但您可以通过Word、Excel或PowerPoint将其应用到文件。 对文件应用策略时，文件包含的信息受策略中指定的机密性设置保护。 分发受策略保护的文件时，只有经过策略授权的收件人才能访问文件的内容。

使用策略保护文件即使在分发文件后，也可以继续控制该文件。 您可以审核事件以跟踪收件人使用文件的时间和方式，对策略进行更改，阻止用户继续访问文件，以及更改附加到文件的策略。

## 策略的工作方式{#how-policies-work}

策略包含有关授权用户的信息以及适用于知识产权的机密性设置。 用户可以是文档安全通过包含在链接的LDAP或Active Directory列表中而被识别的任何用户。 用户也可以是受邀向文档安全部门注册的人员，或者是管理员为其创建帐户的人员。

策略中的机密性设置决定了收件人如何使用受策略保护的文件。 例如，策略指定收件人是可以打印文件、将内容复制到其他文件，还是可以保存对受保护文件所做的更改。 策略还可以为不同用户指定不同的机密性设置。

对文件应用策略时，文件包含的信息受策略中指定的机密性设置保护。 在您分发文件时，文档安全会验证尝试打开文件的收件人，并根据策略中指定的权限授予访问权。

对文件应用策略后，策略的机密性设置可随时更改，允许您添加或删除授权用户，或在用户收到文件后更改其权限。 可以更改应用于文件的策略，并可撤销对文件的访问权，以便拥有文件副本的任何人都不能再打开它。

如果策略允许脱机访问，收件人还可以在策略中指定的时间段内脱机使用受策略保护的文件（没有活动的因特网或网络连接）。

## 受策略保护的文件的工作方式{#how-policy-protected-files-work}

如果用户要打开和使用受策略保护的Word、Excel和PowerPoint文件，策略必须将该用户作为收件人或允许匿名访问，并且该用户必须安装文档安全扩展for Microsoft Office。 要将受策略保护的文件提供给没有Microsoft Office文档安全扩展的用户，请为他们提供软件副本，或告知他们如何从您的网站下载它。 如果您没有安装程序，可以从[下载页面](https://www.adobe.com/products/livecycle/rightsmanagement/extension/downloads.html)下载它。

当用户尝试打开受策略保护的文件时，Microsoft Office的文档安全扩展将连接到文档安全以验证用户。 如果文档安全配置为审核文件使用情况，则用户将看到通知，指示正在审核文件使用情况。 文档安全性决定授予用户哪些文件权限，然后用户可以根据策略设置在以下条件下使用文件：

* 在策略中指定的有效期。
* 在管理员或应用策略的人员撤销对文件的访问权或更改策略之前。

   如果应用策略的人员更改了策略或撤销了对文件的访问权限，则即使用户已经拥有该文件，用户对该文件的权限也会更改或删除。 如果文件本身被撤销，则可能会向用户提供URL以获取更新的副本。

   如果策略允许脱机访问，则可在策略中指定的脱机租用期内脱机（无需Internet或网络连接）打开受策略保护的文件。 脱机租用期结束时，用户必须联机并与文档安全同步，这将开始新的租用期。

   如果策略允许保存文件，并且用户保存受策略保护的文件的副本，则会自动对保存的文件应用并强制实施该策略。 事件（如尝试打开新文件）也会与原始文件一样进行审核和记录。

## 使用文档安全保护文件{#using-document-security-to-protect-your-files}

您可以在各种情况下使用策略保护您的文件。

例如，制造商正在接受将为新产品提供部件的供应商的投标。 制造商必须向投标人提供其完成提交所需的专有信息。 该制造商使用文档安全保护文件，策略允许投标人打开文件并视图信息。 但是，不允许投标人更改、打印或复制文件，并且不允许任何没有权限的人打开文件。

在接受其中一个投标后，制造商更新策略以授予中标人在本地打印、复制和保存更改的权限，并删除中标人，以便他们不再具有打开文件的权限。

与中标人合作时，制造商的工程师将更改文件中的一些设计规范。 要发布新规范，制造商撤销对某些文件的访问权并发布新版本。 当中标人的工程师尝试打开文件时，他们会看到一条消息，指示已撤销对文件的访问权。 邮件中包含一个URL，用户可从中下载文件的新版本。

## 附加信息 {#additional-information}

此表中的资源可以帮助您了解有关AEM文档安全性的更多信息：

<table >
 <tbody>
  <tr>
   <th><p>有关</p> </th>
   <th><p>请参阅</p> </th>
  </tr>
  <tr>
   <td><p>AEM forms Administrator帮助</p> </td>
   <td><p><a href="http://www.adobe.com/go/learn_aemforms_admin_65">管</a> 理员帮助，在“文档安全”管理页面上，单击页面右上角的“帮助”链接。</p> </td>
  </tr>
  <tr>
   <td><p>有关此产品版本的修补程序更新、技术说明和其他信息</p> </td>
   <td><p><a href="https://helpx.adobe.com/cn/marketing-cloud/contact-support.html">Marketing Cloud技术支持</a></p> </td>
  </tr>
 </tbody>
</table>

