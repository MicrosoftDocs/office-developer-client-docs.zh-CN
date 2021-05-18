---
title: 使用 MAPI 对象
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: e342c1bd-8bee-4b02-a93f-e3941f4716c1
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: d732efe5276f4756f43b4aca46e1c33d6f103844
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32329673"
---
# <a name="using-mapi-objects"></a>使用 MAPI 对象

**适用于**：Outlook 2013 | Outlook 2016 
  
客户端和服务提供商通过调用其接口实现中的方法来使用 MAPI 对象。 这是可以使用 MAPI 对象的唯一方式;由 MAPI 接口外部的对象实现的方法不可公开访问。 由于对象的所有接口都是通过继承相关的，因此对象的用户可以在基本接口或继承的接口之一中调用方法，就像它们属于同一接口一样。 
  
当对象的用户想要调用某个方法，并且该对象实现几个通过继承相关的接口时，用户无需知道该方法属于哪个接口。 用户可以使用指向对象的单个指针在任何接口上调用任何方法。 例如，下图显示了客户端应用程序如何使用文件夹对象。 Folder 对象实现 [IMAPIFolder ： IMAPIContainer](imapifolderimapicontainer.md) 接口，该接口通过 IMAPIProp 间接继承自 [IUnknown](https://msdn.microsoft.com/library/33f1d79a-33fc-4ce5-a372-e08bda378332%28Office.15%29.aspx) [： IUnknown](imapipropiunknown.md) and [IMAPIContainer ： IMAPIProp](imapicontainerimapiprop.md)。 客户端可以使用相同的对象指针以相同方式调用 **IMAPIProp** 方法之一（如 [IMAPIProp：：GetProps）](imapiprop-getprops.md)和 [IMAPIFolder ： IMAPIContainer](imapifolderimapicontainer.md)方法之一（如 [IMAPIFolder：：CreateMessage）。](imapifolder-createmessage.md) 客户端不会注意到或受这些调用属于不同接口这一事实的影响。
  
**客户端对文件夹对象的使用**
  
![文件夹对象的客户端使用](media/amapi_40.gif "客户端使用文件夹对象")
  
这些调用转换为代码的方式不同，具体取决于执行调用的客户端是使用 C 还是 C++ 编写。 在可以调用方法之前，必须检索指向接口实现的指针。 可通过以下方式获取接口指针：
  
- 对另一个对象调用方法。
    
- 调用 API 函数。
    
- 对目标 [对象调用 IUnknown：：QueryInterface](https://msdn.microsoft.com/library/54d5ff80-18db-43f2-b636-f93ac053146d%28Office.15%29.aspx) 方法。 
    
MAPI 提供了多个方法和 API 函数，用于返回指向接口实现的指针。 例如，客户端可以调用 [IMAPISession：：GetMsgStoresTable](imapisession-getmsgstorestable.md) 方法来检索指向表对象的指针，该对象通过 [IMAPITable ： IUnknown](imapitableiunknown.md) 接口提供对邮件存储提供程序信息的访问。 服务提供程序可以调用 API 函数 [CreateTable](createtable.md) 来检索指向表数据对象的指针。 如果没有可用的函数或方法，并且客户端或服务提供商已具有指向对象的指针，则它们可以调用对象的 **QueryInterface** 方法以检索指向该对象的另一个接口实现的指针。 
  
## <a name="see-also"></a>另请参阅

- [MAPI 对象和接口概述](mapi-object-and-interface-overview.md)

