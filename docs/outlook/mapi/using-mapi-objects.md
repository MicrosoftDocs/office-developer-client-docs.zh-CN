---
title: 使用 MAPI 对象
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: e342c1bd-8bee-4b02-a93f-e3941f4716c1
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: a355faf85a44f6257b77b7171aa965faabf57fe9
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779079"
---
# <a name="using-mapi-objects"></a>使用 MAPI 对象

**适用于**： Outlook 
  
客户端和服务提供商使用 MAPI 对象通过在其接口实现中调用的方法。 这是唯一的方法，可以使用 MAPI 对象;实现由外部 MAPI 界面对象的方法不公开访问。 通过继承相关的所有对象的接口，因为对象的用户可以调用基接口或继承的接口之一中的方法，就好像它们属于同一接口。 
  
时对象的用户想要对方法的调用，该对象通过继承相关的几个接口实现，用户不需要知道所属的方法的接口。 用户可以调用任何方法对任何具有指向对象的单个接口。 例如下, 图显示了客户端应用程序如何使用 folder 对象。 文件夹对象实现[IMAPIFolder: IMAPIContainer](imapifolderimapicontainer.md)接口，从[IUnknown](http://msdn.microsoft.com/library/33f1d79a-33fc-4ce5-a372-e08bda378332%28Office.15%29.aspx)间接到继承[IMAPIProp: IUnknown](imapipropiunknown.md)和[IMAPIContainer: IMAPIProp](imapicontainerimapiprop.md)。 客户端可以调用**IMAPIProp**方法，如[IMAPIProp::GetProps](imapiprop-getprops.md)，之一和之一[IMAPIFolder: IMAPIContainer](imapifolderimapicontainer.md)方法，例如[IMAPIFolder::CreateMessage](imapifolder-createmessage.md)，具有相同的对象指针相同的方式。 客户端不识别或受影响的这一事实这些呼叫属于不同的接口。
  
**客户端对文件夹对象的使用**
  
![客户端使用的一个 folder 对象](media/amapi_40.gif "客户端使用的一个 folder 对象")
  
这些呼叫将转换不同根据是否发出呼叫的客户端写入 C 或 c + + 中的代码。 在进行任何方法调用前，必须检索对该接口实现的指针。 接口指针可以获得以下方式：
  
- 在不同对象上调用方法。
    
- 调用 API 函数。
    
- 在目标对象上调用[IUnknown::QueryInterface](http://msdn.microsoft.com/library/54d5ff80-18db-43f2-b636-f93ac053146d%28Office.15%29.aspx)方法。 
    
MAPI 提供了一些方法和 API 函数将指针返回到接口实现。 例如，客户端可以调用[IMAPISession::GetMsgStoresTable](imapisession-getmsgstorestable.md)方法来检索向 table 对象的指针提供消息存储提供程序通过对信息的访问权[IMAPITable: IUnknown](imapitableiunknown.md)接口。 服务提供商可以调用 API 函数[CreateTable](createtable.md)检索指向表数据对象的指针。 当没有任何函数或方法可用和客户端或服务提供程序已经具有指向对象的指针时，它们可以调用该对象的**QueryInterface**方法，以便检索指向另一个对象的接口实现。 
  
## <a name="see-also"></a>另请参阅

- [MAPI 对象和接口概述](mapi-object-and-interface-overview.md)

