---
title: 帐户
TOCTitle: Accounts
ms:assetid: 28df6dbd-4d24-42f3-91c1-fd8b3a4ea722
ms:mtpsurl: https://msdn.microsoft.com/library/office/ff184597(v=office.15)
ms:contentKeyID: 55119790
ms.date: 07/24/2014
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: d539f38419a8eaac60cd3054da6283a49bf4cc00
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32331183"
---
# <a name="accounts"></a>帐户 

本节收录了与电子邮件帐户相关的示例任务。 例如，电子邮件帐户包括 Microsoft Exchange Server、邮局协议 3 (POP3)、Internet 消息访问协议 (IMAP) 和超文本传输协议 (HTTP) 帐户。 当前配置文件的帐户由 [Account](https://docs.microsoft.com/dotnet/api/microsoft.office.interop.outlook.account?view=outlook-pia) 对象表示。


|主题|说明|
|:----|:----------|
|[获取帐户信息](how-to-get-account-information.md) | 将输入参数视为受信任的 Microsoft Outlook [Application](https://docs.microsoft.com/dotnet/api/microsoft.office.interop.outlook.application?view=outlook-pia) 对象，并使用 **Account** 对象来显示可用于当前 Outlook 配置文件的每个帐户的详细信息。|
|[为基于当前文件夹的特定帐户创建可发送项](how-to-create-a-sendable-item-for-a-specific-account-based-on-the-current-folder.md) | 包含两个代码示例，展示了如何创建可发送的电子邮件项和会议请求，并使用基于当前文件夹的特定帐户发送它们。|
|[获取与文件夹关联的帐户](how-to-get-the-account-for-a-folder.md) | 介绍了如何获取当前会话中与文件夹关联的帐户。|
|[获取多个帐户的信息](how-to-get-information-about-multiple-accounts.md) | 介绍了如何获取并显示当前配置文件中每个帐户的杂项信息。|
|[使用 Hotmail 帐户发送邮件项](how-to-send-a-mail-item-by-using-a-hotmail-account.md) | 介绍了如何使用 [SendUsingAccount](https://docs.microsoft.com/dotnet/api/microsoft.office.interop.outlook._mailitem.sendusingaccount?view=outlook-pia) 属性通过 Windows Live Hotmail 帐户发送邮件项。|

## <a name="see-also"></a>另请参阅

- [Exchange 用户](exchange-users.md)
- [邮件](mail.md)
- [收件人](recipients.md)
- [我如何...（Outlook 2013 PIA 参考）](how-do-i-outlook-2013-pia-reference.md)

