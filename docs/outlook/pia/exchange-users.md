---
title: Exchange 用户
TOCTitle: Exchange users
ms:assetid: 01802032-fd60-400b-ad83-1f4eefe596bd
ms:mtpsurl: https://msdn.microsoft.com/library/Ff184585(v=office.15)
ms:contentKeyID: 55119835
ms.date: 07/24/2014
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 667f8a07477c527d251c4e50f35baa2da2e417ed
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32357832"
---
# <a name="exchange-users"></a>Exchange 用户

本节提供涉及 Microsoft Exchange 邮箱用户的示例任务。Exchange 用户连接到 Exchange 服务器，并由派生自 [AddressEntry](https://msdn.microsoft.com/library/bb609574\(v=office.15\)) 对象的 [ExchangeUser](https://msdn.microsoft.com/library/bb609728\(v=office.15\)) 对象表示。

## <a name="in-this-section"></a>本节内容

|主题|说明|
|:----|:----------|
|[获取当前用户的相关信息](how-to-get-information-about-the-current-user.md)  |介绍了如何获取当前用户的相关信息（如姓名、职务和电话号码）。|
|[获取当前用户所属全部通讯组列表的相关信息](how-to-get-information-about-all-distribution-lists-of-which-the-current-user-is-a-member.md)  |介绍了如何使用 [GetMemberOfList()](https://msdn.microsoft.com/library/bb623397\(v=office.15\)) 方法，获取当前用户所属全部通讯组列表的相关信息。|
|[创建通讯组列表](how-to-create-a-distribution-list.md)  |介绍了如何创建通讯组列表，并将它显示给用户。|
[获取 Exchange 通讯组列表的成员](how-to-get-members-of-an-exchange-distribution-list.md)  |提示用户从“选择姓名”对话框中选择一个 Exchange 通讯组列表，然后展开该通讯组列表以显示其成员。|
[获取当前用户的经理信息](how-to-get-information-about-the-current-user-s-manager.md)  |介绍了如何获取当前用户的经理信息（如姓名、职务和电话号码）。|
[获取 Exchange 用户的经理闲/忙状态信息](how-to-get-availability-information-for-an-exchange-user-s-manager.md) |  介绍了如何在日历中显示用户经理的下一个空闲 60 分钟时间段。|
|[检查经理对会议请求的响应](how-to-check-a-manager-s-response-to-a-meeting-request.md) | 介绍了如何通过使用 [GetExchangeUser()](https://msdn.microsoft.com/library/bb611808\(v=office.15\)) 和 [GetExchangeUserManager()](https://msdn.microsoft.com/library/bb646656\(v=office.15\)) 方法，检查当前用户的经理对会议请求的响应状态。|
|[获取当前用户的经理的直接下属的相关信息](how-to-get-information-about-direct-reports-of-the-current-user-s-manager.md) | 介绍了如何获取当前用户的经理的直接下属（若有），然后显示经理的每个直接下属的相关信息。|

## <a name="see-also"></a>另请参阅

- [帐户](accounts.md)
- [通讯簿](address-book.md)
- [存储](stores.md)
- [我如何...（Outlook 2013 PIA 参考）](how-do-i-outlook-2013-pia-reference.md)

