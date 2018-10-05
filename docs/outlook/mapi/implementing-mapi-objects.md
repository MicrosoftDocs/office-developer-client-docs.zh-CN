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
# <a name="implementing-mapi-objects"></a><span data-ttu-id="7cd4d-103">实现 MAPI 对象</span><span class="sxs-lookup"><span data-stu-id="7cd4d-103">Implementing MAPI Objects</span></span>

  
  
<span data-ttu-id="7cd4d-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="7cd4d-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="7cd4d-105">可以通过使用 c + + 类或 C 数据结构，具体取决于语言实现 MAPI 对象和 API 设置客户端或使用服务提供商。</span><span class="sxs-lookup"><span data-stu-id="7cd4d-105">MAPI objects can be implemented by using C++ classes or C data structures, depending on the language and the API set a client or service provider is using.</span></span> <span data-ttu-id="7cd4d-106">服务提供商 C 或 c + + 中使用 MAPI 服务提供程序接口; 可编写C 或 c + + 中，还可以使用客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="7cd4d-106">Service providers can be written in C or C++ with the MAPI service provider interface; client applications can also use C or C++.</span></span> <span data-ttu-id="7cd4d-107">如果可能，客户端和使用的面向对象的编程接口的服务提供商应使用 c + +。</span><span class="sxs-lookup"><span data-stu-id="7cd4d-107">If possible, clients and service providers that use the object-oriented programming interface should use C++.</span></span> 
  
<span data-ttu-id="7cd4d-108">C + + 是首选，因为 MAPI 是面向对象的技术和 c + + 人士更容易面向对象的开发。</span><span class="sxs-lookup"><span data-stu-id="7cd4d-108">C++ is the preferred choice because MAPI is an object-oriented technology, and C++ lends itself more readily to object-oriented development.</span></span> <span data-ttu-id="7cd4d-109">生成的代码是更简单、 更简单，使其更易于维护。</span><span class="sxs-lookup"><span data-stu-id="7cd4d-109">The resulting code is simpler and more straightforward, making it easier to maintain.</span></span> <span data-ttu-id="7cd4d-110">MAPI 文档主要面向 c + + 开发人员;本参考中的 MAPI 接口方法的语法说明都在 c + +。</span><span class="sxs-lookup"><span data-stu-id="7cd4d-110">The MAPI documentation is written primarily for C++ developers; all of the syntax descriptions for the MAPI interface methods in this Reference are in C++.</span></span>
  
<span data-ttu-id="7cd4d-111">开发人员可以使用 Microsoft Visual Studio 和第三方开发工具开发解决方案的呼叫 MAPI。</span><span class="sxs-lookup"><span data-stu-id="7cd4d-111">Developers can use Microsoft Visual Studio and third-party development tools to develop solutions that call MAPI.</span></span> <span data-ttu-id="7cd4d-112">请注意，开发人员应使用 C 或非托管 c + + 中，但不是托管 c + + 编写 MAPI 解决方案。</span><span class="sxs-lookup"><span data-stu-id="7cd4d-112">Note that developers should use C or unmanaged C++, but not managed C++ to write MAPI solutions.</span></span>
  
<span data-ttu-id="7cd4d-113">当实现 MAPI 对象时，客户端或服务提供程序创建接口方法、 特定于实现，任何私有方法的代码和代码以支持维护状态信息的私有数据成员的所有代码。</span><span class="sxs-lookup"><span data-stu-id="7cd4d-113">When a MAPI object is implemented, a client or service provider creates code for all of the interface methods, code for any private methods that are specific to the implementation, and code to support private data members for maintaining state information.</span></span> <span data-ttu-id="7cd4d-114">接口方法的代码必须遵循的规范 MAPI 发布文档的正常的行为。</span><span class="sxs-lookup"><span data-stu-id="7cd4d-114">The code for the interface methods must follow the specifications published by MAPI that document expected behavior.</span></span> 
  
<span data-ttu-id="7cd4d-115">有很多宏 Mapidefs.h 头文件和客户端和在其中任一种语言中的服务提供商可用于帮助他们与 MAPI 对象及其定义的 OLE 头文件中。</span><span class="sxs-lookup"><span data-stu-id="7cd4d-115">There are many macros in the Mapidefs.h header file and OLE header files that clients and service providers in either language can use to help them with their definitions of MAPI objects.</span></span> <span data-ttu-id="7cd4d-116">例如，是用于定义的每个 MAPI 的接口方法的宏。</span><span class="sxs-lookup"><span data-stu-id="7cd4d-116">For example, there is a macro to define the methods of each of the MAPI interfaces.</span></span> <span data-ttu-id="7cd4d-117">要定义的[IUnknown](https://msdn.microsoft.com/library/ms680509%28v=VS.85%29.aspx)接口方法的宏在 Mapidefs.h 中显示，如下所示：</span><span class="sxs-lookup"><span data-stu-id="7cd4d-117">The macro to define the methods of the [IUnknown](https://msdn.microsoft.com/library/ms680509%28v=VS.85%29.aspx) interface appears in Mapidefs.h as follows:</span></span> 
  
```cpp
#define MAPI_IUNKNOWN_METHODS(IPURE)          \
    MAPIMETHOD(QueryInterface)                \
        (THIS_ REFIID riid, LPVOID FAR * ppvObj) IPURE;    \
    MAPIMETHOD_(ULONG,AddRef)  (THIS) IPURE;               \
    MAPIMETHOD_(ULONG,Release) (THIS) IPURE;   \
 
```

## <a name="see-also"></a><span data-ttu-id="7cd4d-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7cd4d-118">See also</span></span>



[<span data-ttu-id="7cd4d-119">MAPI 对象和接口概述</span><span class="sxs-lookup"><span data-stu-id="7cd4d-119">MAPI Object and Interface Overview</span></span>](mapi-object-and-interface-overview.md)

