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
# <a name="implementing-mapi-objects"></a><span data-ttu-id="df5a1-103">实现 MAPI 对象</span><span class="sxs-lookup"><span data-stu-id="df5a1-103">Implementing MAPI Objects</span></span>

  
  
<span data-ttu-id="df5a1-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="df5a1-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="df5a1-105">MAPI 对象可以通过使用 c + + 类或 C 数据结构来实现, 具体取决于客户端或服务提供商所使用的语言和 API 集。</span><span class="sxs-lookup"><span data-stu-id="df5a1-105">MAPI objects can be implemented by using C++ classes or C data structures, depending on the language and the API set a client or service provider is using.</span></span> <span data-ttu-id="df5a1-106">可以使用 MAPI 服务提供程序接口在 c 或 c + + 中编写服务提供程序;客户端应用程序还可以使用 c 或 c + +。</span><span class="sxs-lookup"><span data-stu-id="df5a1-106">Service providers can be written in C or C++ with the MAPI service provider interface; client applications can also use C or C++.</span></span> <span data-ttu-id="df5a1-107">如果可能, 使用面向对象的编程接口的客户端和服务提供程序应使用 c + +。</span><span class="sxs-lookup"><span data-stu-id="df5a1-107">If possible, clients and service providers that use the object-oriented programming interface should use C++.</span></span> 
  
<span data-ttu-id="df5a1-108">c + + 是首选的选择, 因为 MAPI 是面向对象的技术, 而 c + + 可以更轻松地在面向对象的开发中进行自我定位。</span><span class="sxs-lookup"><span data-stu-id="df5a1-108">C++ is the preferred choice because MAPI is an object-oriented technology, and C++ lends itself more readily to object-oriented development.</span></span> <span data-ttu-id="df5a1-109">生成的代码更简单且更简单, 使其更易于维护。</span><span class="sxs-lookup"><span data-stu-id="df5a1-109">The resulting code is simpler and more straightforward, making it easier to maintain.</span></span> <span data-ttu-id="df5a1-110">MAPI 文档主要针对 c + + 开发人员编写;此参考中的 MAPI 接口方法的所有语法说明都在 c + + 中。</span><span class="sxs-lookup"><span data-stu-id="df5a1-110">The MAPI documentation is written primarily for C++ developers; all of the syntax descriptions for the MAPI interface methods in this Reference are in C++.</span></span>
  
<span data-ttu-id="df5a1-111">开发人员可以使用 Microsoft Visual Studio 和第三方开发工具来开发调用 MAPI 的解决方案。</span><span class="sxs-lookup"><span data-stu-id="df5a1-111">Developers can use Microsoft Visual Studio and third-party development tools to develop solutions that call MAPI.</span></span> <span data-ttu-id="df5a1-112">请注意, 开发人员应使用 c 或非托管 c + +, 而不是托管的 c + + 来编写 MAPI 解决方案。</span><span class="sxs-lookup"><span data-stu-id="df5a1-112">Note that developers should use C or unmanaged C++, but not managed C++ to write MAPI solutions.</span></span>
  
<span data-ttu-id="df5a1-113">在实现 MAPI 对象时, 客户端或服务提供程序将为所有接口方法创建代码、针对特定实现的任何专用方法的代码以及支持用于维护状态信息的私有数据成员的代码。</span><span class="sxs-lookup"><span data-stu-id="df5a1-113">When a MAPI object is implemented, a client or service provider creates code for all of the interface methods, code for any private methods that are specific to the implementation, and code to support private data members for maintaining state information.</span></span> <span data-ttu-id="df5a1-114">接口方法的代码必须遵循 MAPI 所发布的规范, 以记录预期行为。</span><span class="sxs-lookup"><span data-stu-id="df5a1-114">The code for the interface methods must follow the specifications published by MAPI that document expected behavior.</span></span> 
  
<span data-ttu-id="df5a1-115">mapidefs.h 头文件和 OLE 头文件中有许多宏可以使用任意一种语言的客户端和服务提供商来帮助他们定义自己的 MAPI 对象。</span><span class="sxs-lookup"><span data-stu-id="df5a1-115">There are many macros in the Mapidefs.h header file and OLE header files that clients and service providers in either language can use to help them with their definitions of MAPI objects.</span></span> <span data-ttu-id="df5a1-116">例如, 有一个用于定义每个 MAPI 接口的方法的宏。</span><span class="sxs-lookup"><span data-stu-id="df5a1-116">For example, there is a macro to define the methods of each of the MAPI interfaces.</span></span> <span data-ttu-id="df5a1-117">用于定义[IUnknown](https://msdn.microsoft.com/library/ms680509%28v=VS.85%29.aspx)接口方法的宏显示在 mapidefs.h 中, 如下所示:</span><span class="sxs-lookup"><span data-stu-id="df5a1-117">The macro to define the methods of the [IUnknown](https://msdn.microsoft.com/library/ms680509%28v=VS.85%29.aspx) interface appears in Mapidefs.h as follows:</span></span> 
  
```cpp
#define MAPI_IUNKNOWN_METHODS(IPURE)          \
    MAPIMETHOD(QueryInterface)                \
        (THIS_ REFIID riid, LPVOID FAR * ppvObj) IPURE;    \
    MAPIMETHOD_(ULONG,AddRef)  (THIS) IPURE;               \
    MAPIMETHOD_(ULONG,Release) (THIS) IPURE;   \
 
```

## <a name="see-also"></a><span data-ttu-id="df5a1-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="df5a1-118">See also</span></span>



[<span data-ttu-id="df5a1-119">MAPI 对象和接口概述</span><span class="sxs-lookup"><span data-stu-id="df5a1-119">MAPI Object and Interface Overview</span></span>](mapi-object-and-interface-overview.md)

