---
title: 实现 MAPI 对象
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: b1ee2533-8077-4976-846b-d42d148bf8c6
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: c0d67d10d54591de926724cbf594a44f17e9ea14
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25397098"
---
# <a name="implementing-mapi-objects"></a>实现 MAPI 对象

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
可以通过使用 c + + 类或 C 数据结构，具体取决于语言实现 MAPI 对象和 API 设置客户端或使用服务提供商。 服务提供商 C 或 c + + 中使用 MAPI 服务提供程序接口; 可编写C 或 c + + 中，还可以使用客户端应用程序。 如果可能，客户端和使用的面向对象的编程接口的服务提供商应使用 c + +。 
  
C + + 是首选，因为 MAPI 是面向对象的技术和 c + + 人士更容易面向对象的开发。 生成的代码是更简单、 更简单，使其更易于维护。 MAPI 文档主要面向 c + + 开发人员;本参考中的 MAPI 接口方法的语法说明都在 c + +。
  
开发人员可以使用 Microsoft Visual Studio 和第三方开发工具开发解决方案的呼叫 MAPI。 请注意，开发人员应使用 C 或非托管 c + + 中，但不是托管 c + + 编写 MAPI 解决方案。
  
当实现 MAPI 对象时，客户端或服务提供程序创建接口方法、 特定于实现，任何私有方法的代码和代码以支持维护状态信息的私有数据成员的所有代码。 接口方法的代码必须遵循的规范 MAPI 发布文档的正常的行为。 
  
有很多宏 Mapidefs.h 头文件和客户端和在其中任一种语言中的服务提供商可用于帮助他们与 MAPI 对象及其定义的 OLE 头文件中。 例如，是用于定义的每个 MAPI 的接口方法的宏。 要定义的[IUnknown](https://msdn.microsoft.com/library/ms680509%28v=VS.85%29.aspx)接口方法的宏在 Mapidefs.h 中显示，如下所示： 
  
```cpp
#define MAPI_IUNKNOWN_METHODS(IPURE)          \
    MAPIMETHOD(QueryInterface)                \
        (THIS_ REFIID riid, LPVOID FAR * ppvObj) IPURE;    \
    MAPIMETHOD_(ULONG,AddRef)  (THIS) IPURE;               \
    MAPIMETHOD_(ULONG,Release) (THIS) IPURE;   \
 
```

## <a name="see-also"></a>另请参阅



[MAPI 对象和接口概述](mapi-object-and-interface-overview.md)

