---
title: 实现 MAPI 对象
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: b1ee2533-8077-4976-846b-d42d148bf8c6
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: c0d67d10d54591de926724cbf594a44f17e9ea14
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32310169"
---
# <a name="implementing-mapi-objects"></a>实现 MAPI 对象

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
MAPI 对象可以使用 C++ 类或 C 数据结构实现，具体取决于语言和客户端或服务提供商使用的 API 集。 可以使用 MAPI 服务提供程序接口用 C 或 C++ 编写服务提供程序;客户端应用程序还可使用 C 或 C++。 如果可能，使用面向对象的编程接口的客户端和服务提供商应该使用 C++。 
  
C++ 是首选选项，因为 MAPI 是一种面向对象的技术，而 C++ 更便于进行面向对象的开发。 生成的代码更简单、更简单，更易于维护。 MAPI 文档主要面向 C++ 开发人员编写;本参考中 MAPI 接口方法的所有语法说明都使用 C++。
  
开发人员可以使用Microsoft Visual Studio第三方开发工具来开发调用 MAPI 的解决方案。 请注意，开发人员应该使用 C 或非托管 C++，但不能使用托管 C++ 编写 MAPI 解决方案。
  
实现 MAPI 对象时，客户端或服务提供商会创建所有接口方法的代码、特定于实现的任何私有方法的代码，以及支持私有数据成员维护状态信息的代码。 接口方法的代码必须遵循 MAPI 发布的文档预期行为的规范。 
  
Mapidefs.h 头文件和 OLE 头文件中有许多宏，客户端和服务提供商可以使用这两种语言来帮助他们定义 MAPI 对象。 例如，有一个宏可定义每个 MAPI 接口的方法。 用于定义 [IUnknown](https://msdn.microsoft.com/library/ms680509%28v=VS.85%29.aspx) 接口方法的宏显示在 Mapidefs.h 中，如下所示： 
  
```cpp
#define MAPI_IUNKNOWN_METHODS(IPURE)          \
    MAPIMETHOD(QueryInterface)                \
        (THIS_ REFIID riid, LPVOID FAR * ppvObj) IPURE;    \
    MAPIMETHOD_(ULONG,AddRef)  (THIS) IPURE;               \
    MAPIMETHOD_(ULONG,Release) (THIS) IPURE;   \
 
```

## <a name="see-also"></a>另请参阅



[MAPI 对象和接口概述](mapi-object-and-interface-overview.md)

