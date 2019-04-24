---
title: 使对象无效
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 7d601cee-ffc4-4c7c-8006-40b717dee247
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: bf7ef15ccfd9cd015771785bda9d6ad79415736b
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32317197"
---
# <a name="invalidating-an-object"></a>使对象无效

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
作为提供程序关闭过程的一部分, 您可能需要使对象无效。 使对象失效的操作涉及将其 vtable 替换为包含三个**IUnknown**方法的实现的 vtable: **AddRef**、 **Release**和**QueryInterface**。 通过调用[IMAPISupport:: MakeInvalid](imapisupport-makeinvalid.md), 可通过以下三种常见提供程序类型的每个支持对象中包含的方法使对象无效。 提供程序通常会在其登录对象的**注销**方法的实现中进行此调用。 
  
使对象无效的方式使 MAPI 成为释放与对象关联的内存的最终责任。 您可以释放与某个对象连接的所有资源, 然后调用**MakeInvalid**以使其继承的接口中的所有方法无效。 对上述任一方法的调用将返回 MAPI_E_INVALID_OBJECT。 使用**MakeInvalid**是许多服务提供商选择忽略的一个选项。 
  
## <a name="see-also"></a>另请参阅



[关闭服务提供程序](shutting-down-a-service-provider.md)

