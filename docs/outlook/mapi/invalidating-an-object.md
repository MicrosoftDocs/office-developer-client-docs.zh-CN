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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33407674"
---
# <a name="invalidating-an-object"></a>使对象无效

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
作为提供程序关闭过程的一部分，你可能希望使对象失效。 使对象无效涉及将其 vtable 替换为包含三个 **IUnknown** 方法的实现 **（AddRef、Release** 和 **QueryInterface）的 vtable。** 通过调用 [IMAPISupport：：MakeInvalid](imapisupport-makeinvalid.md)使对象失效，该方法包含在三种常见提供程序类型的每个支持对象中。 提供程序通常在实现其登录对象的 **Logoff** 方法时进行此调用。 
  
如果对象无效，MAPI 将承担释放与对象关联的内存的最终责任。 可以释放与某个对象连接的所有资源，然后调用 **MakeInvalid** 使其继承的接口中所有方法失效。 调用这些方法之一将返回MAPI_E_INVALID_OBJECT。 使用 **MakeInvalid** 是许多服务提供商选择忽略的选项。 
  
## <a name="see-also"></a>另请参阅



[关闭服务提供商](shutting-down-a-service-provider.md)

