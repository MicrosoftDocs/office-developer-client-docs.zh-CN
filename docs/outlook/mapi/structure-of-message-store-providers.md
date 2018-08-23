---
title: 消息存储提供程序的结构
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 064b2fc1-e690-43e6-95d3-a61438115de5
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 58b6771c6bdae91ad0e496189258e4745de5bc84
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22584287"
---
# <a name="structure-of-message-store-providers"></a>消息存储提供程序的结构
  
**适用于**： Outlook 2013 |Outlook 2016 
  
消息存储提供程序，在内存中，运行时是[IMSProvider: IUnknown](imsprovideriunknown.md)接口。 **IMSProvider**界面允许客户端应用程序和 MAPI 后台处理程序登录到和移开的邮件存储区。 客户端应用程序和 MAPI 后台处理程序用来访问文件夹和邮件存储区中的邮件的接口是[IMSLogon](imslogoniunknown.md)和[IMsgStore](imsgstoreimapiprop.md)接口。 消息存储首次登录到时，通常创建这些接口，尽管[MSProviderInit](msproviderinit.md)入口点的邮件存储 DLL 无法创建它们。 
  
因为**IMSLogon**和**IMsgStore**接口共享一些方法，所以可能更轻松地创建继承自这两种接口的一个类对象。 此外可以在独立的对象，实现这些接口和写入 helper 函数内部为您的 DLL 的实现共享然后可从**IMSLogon**和**IMsgStore**接口中的方法调用的方法。 
  
下图显示内运行的消息存储对象层次结构的高级大纲。
  
**消息存储对象层次结构**
  
![消息存储对象层次结构](media/storeobj.gif "消息存储对象层次结构")
  
## <a name="see-also"></a>另请参阅

- [开发 MAPI 邮件存储区提供程序](developing-a-mapi-message-store-provider.md)

