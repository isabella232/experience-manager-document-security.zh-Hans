---
title: AEM Document Security Extension for Microsoft Office 简介
description: 使用 Document Security Extension for Microsoft Office，您可以将预定义的机密性设置应用于 Microsoft Office 文件。
uuid: a5428c50-fae3-4823-9e6f-0f5306e7248f
content-type: reference
topic-tags: using
discoiquuid: cf93f9f5-1fb6-4909-815e-0ffb8c6ea6d1
exl-id: 3e07c031-3f88-4bde-bdb3-b136ef5f9527
source-git-commit: a15d49cdd21ccb8e6ec6c770a92bf16cb24ffaa1
workflow-type: tm+mt
source-wordcount: '1304'
ht-degree: 100%

---

# AEM Document Security Extension for Microsoft Office 简介{#introduction-to-aem-document-security-extension-for-microsoft-office}

Adobe® Experience Manager Document Security Extension for Microsoft® Office 确保只有您授权的人可以使用包含您知识产权的 Word、Excel 和 PowerPoint 文件。使用 Document Security Extension for Microsoft Office，您可以将预定义的机密性设置应用于您的文件。

Document Security Extension for Microsoft Office 扩展了 Adobe Experience Manager Forms 的 LiveCycle Rights Management 和 Document Security 插件，可以保护 Word、Excel 和 PowerPoint 文件并允许安装了本软件的授权用户根据在策略中建立的机密性设置使用受策略保护的文件。

## Document Security 如何保护知识产权 {#how-document-security-protects-intellectual-property}

Document Security 确保只有您授权的人可以使用包含您知识产权的文件。使用 Document Security，您可以使用机密性策略保护文件。*策略*&#x200B;是包含机密性设置和授权用户列表的信息的集合。您在策略中指定的设置确定收件人可以如何使用您应用了策略的文件。例如，您可以指定收件人是否可以打印或复制文本或者保存更改。

Document Security 管理员和用户创建策略。管理员创建对所有授权用户可用的组织策略。管理员或策略集协调员也可以创建称为&#x200B;*策略集*&#x200B;的策略组，策略组可供一部分用户使用。用户可以创建自己的策略，这些策略只有自己能使用。管理员、策略集协调员和用户使用 Document Security 网页以创建策略。

虽然策略存储在 Document Security 中，您可通过 Word、Excel 或 PowerPoint 将它们应用到文件。将策略应用到文件时，该文件中包含的信息受在策略中指定的机密性设置保护。当您分发受策略保护的文件时，只有策略授权的收件人才能访问文件的内容。

使用受策略保护文件让您可以持续控制文件，即使在您分发文件之后。您可以审核事件以跟踪收件人在什么时候如何使用文件，对策略进行更改，防止用户继续访问文件，以及更改附加到文件的策略。

## 策略的工作方式 {#how-policies-work}

策略包含有关授权用户的信息以及应用到知识产权的机密性设置。用户可以是 Document Security 通过包含在链接的 LDAP 或 Active Directory 列表中所识别的任意用户。用户也可以是受邀注册 Document Security 的人或者管理员为其创建了帐户的人。

策略中的机密性设置确定收件人可以如何使用受策略保护的文件。例如，策略指定收件人是否可以打印文件、将内容复制到其他文件或者将更改保存到受保护文件。策略还可以为不同用户指定不同的机密性设置。

将策略应用到文件时，该文件中包含的信息受在策略中指定的机密性设置保护。当您分发文件时，Document Security 对尝试打开文件的收件人进行身份验证，并根据在策略中指定的权限授权访问权限。

将策略应用到文件之后，策略的机密性设置可以随时更改，允许您添加或删除授权用户，或者在用户收到文件之后更改权限。应用到文件的策略可以更改，对文件的访问权限可以撤销，这样拥有该文件副本的任何人都无法再打开它。

如果策略允许离线访问，收件人还可以在策略指定的时段内离线使用受策略保护的文件（无需活动的 Internet 或网络连接）。

## 受策略保护文件的工作方式 {#how-policy-protected-files-work}

对于打开和使用受策略保护的 Word、Excel 和 PowerPoint 文件的用户，策略必须包括用户作为收件人或者允许匿名访问，并且用户必须安装了 Document Security Extension for Microsoft Office。要向没有 Document Security Extension for Microsoft Office 的用户提供受策略保护的文件，请向其提供软件的副本或者告诉他们如何从您的网站下载。如果您没有安装程序，则可以从[下载页面](https://www.adobe.com/products/livecycle/rightsmanagement/extension/downloads.html)下载。

用户尝试打开受策略保护的文件时，Document Security Extension for Microsoft Office 连接到 Document Security 以对用户进行身份验证。如果配置 Document Security 审核文件使用情况，则用户可以看到通知，指示要审核文件使用情况。Document Security 确定将哪些文件权限授予用户，然后用户可以按照以下条件，根据策略设置使用文件：

* 在策略指定的有效期内。
* 在管理员或者应用策略的人撤销对文件的访问权限或者更改策略之前。

   如果应用策略的人更改策略或者撤销对文件的访问权限，则用户对该文件的权限将更改或删除，即使用户已拥有该文件。如果文件本身被撤销，则会向用户提供 URL 以获取更新副本。

   如果策略允许离线访问，受策略保护的文件可以在策略指定的离线租赁期的持续时间内离线打开（没有 Internet 或网络连接）。离线租赁期结束时，用户必须上线并与 Document Security 同步，它会启动新的租赁期。

   如果策略允许保存文件并且用户保存了受策略保护文件的副本，则将自动为保存的文件应用和实施策略。与原始文件一样，尝试打开新文件之类的事件也将被审核并记录。

## 使用 Document Security 保护文件 {#using-document-security-to-protect-your-files}

您可以使用策略在各种情况下保护文件。

例如，制造商在接受供应商为新产品提供零件的投标。制造商必须向投标人提供完成意见书所需的专有信息。制造商使用 Document Security 保护文件，其策略允许投标人打开文件和查看信息。但是，阻止投标人更改、打印或复制文件，并阻止任何没有权限的人打开文件。

在接受一个投标后，制造商更新策略，向中标人提供权限以在本地打印、复制和保存更改，并删除未中标的人，这样他们再也无权打开文件。

在与中标人合作时，制造商的工程师可以在文件中更改一些设计规格。为了发布新的规格，制造商撤销对一些文件的访问权限并发布新的版本。当中标人的工程师尝试打开文件时，他们会看到消息，说明对文件的访问权限已撤销。该消息包含可用于下载文件新版本的 URL。

## 附加信息 {#additional-information}

此表中的资源可帮助您详细了解 AEM Document Security：

<table >
 <tbody>
  <tr>
   <th><p>有关信息</p> </th>
   <th><p>请参阅</p> </th>
  </tr>
  <tr>
   <td><p>AEM forms 管理员帮助</p> </td>
   <td><p><a href="http://www.adobe.com/go/learn_aemforms_admin_65_cn">管理员帮助</a> 或者，在 Document Security 管理页面上，单击页面右上角的“帮助”链接。</p> </td>
  </tr>
  <tr>
   <td><p>有关此产品版本的修补程序更新、技术说明和附加信息</p> </td>
   <td><p><a href="https://helpx.adobe.com/cn/marketing-cloud/contact-support.html">Marketing Cloud 技术支持</a></p> </td>
  </tr>
 </tbody>
</table>
