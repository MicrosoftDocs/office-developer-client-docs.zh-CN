---
title: 邮件存储提供程序的结构
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 064b2fc1-e690-43e6-95d3-a61438115de5
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: eda62a4cd31e0de695d52391a6717e7a0f5ea581
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33426420"
---
# <a name="structure-of-message-store-providers"></a>邮件存储提供程序的结构
  
**适用于**：Outlook 2013 | Outlook 2016 
  
消息存储提供程序在内存中运行时，是 [IMSProvider ： IUnknown](imsprovideriunknown.md) 接口。 **IMSProvider** 接口允许客户端应用程序和 MAPI 后台处理程序登录到和注销消息存储。 客户端应用程序和 MAPI 后台处理程序用于访问邮件存储中的文件夹和消息的接口是 [IMSLogon](imslogoniunknown.md) 和 [IMsgStore](imsgstoreimapiprop.md) 接口。 虽然邮件存储 DLL 的 [MSProviderInit](msproviderinit.md) 入口点也可以创建它们，但是这些接口通常是在邮件存储首次登录时创建的。 
  
由于 **IMSLogon** 和 **IMsgStore** 接口共享一些方法，因此创建一个继承自这两个接口的类对象可能会更容易。 您还可以在单独的对象中实现这些接口，在 DLL 内部编写帮助程序函数，这些函数实现共享方法，然后可以从 **IMSLogon** 和 **IMsgStore** 接口中的方法调用这些方法。 
  
下图显示了正在运行的邮件存储中对象层次结构的简要概述。
  
**消息存储对象层次结构**
  
![邮件存储对象层次结构](media/storeobj.gif "邮件存储对象层次结构")
  
## <a name="see-also"></a>另请参阅

- [开发 MAPI 邮件存储提供程序](developing-a-mapi-message-store-provider.md)

