---
title: 初始化传输提供程序
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 977c18ce-ece5-4ad1-ac97-5a680846ab83
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 423b03d674028a2f81b4c042d6e65e9acfb57274
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775944"
---
# <a name="initializing-the-transport-provider"></a><span data-ttu-id="000e2-103">初始化传输提供程序</span><span class="sxs-lookup"><span data-stu-id="000e2-103">Initializing the Transport Provider</span></span>

  
  
<span data-ttu-id="000e2-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="000e2-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="000e2-105">传输-后台处理程序接口定义 MAPI 后台处理程序向传输提供程序的呼叫。</span><span class="sxs-lookup"><span data-stu-id="000e2-105">The transport-spooler interface defines calls the MAPI spooler makes to a transport provider.</span></span> <span data-ttu-id="000e2-106">传输提供程序动态链接库 (DLL) 中实现这些例程。</span><span class="sxs-lookup"><span data-stu-id="000e2-106">Transport providers implement these routines in a dynamic-link library (DLL).</span></span> <span data-ttu-id="000e2-107">使用 MAPI 后台处理程序的 DLL 的第一个直接入口点必须传输提供程序初始化函数[XPProviderInit](xpproviderinit.md)。</span><span class="sxs-lookup"><span data-stu-id="000e2-107">The first direct entry point into the DLL used by the MAPI spooler must be the transport provider initialization function [XPProviderInit](xpproviderinit.md).</span></span>
  
<span data-ttu-id="000e2-108">MAPI 使用例程**GetProcAddress**来获取服务提供商的初始化例程的地址，然后调用该例程。</span><span class="sxs-lookup"><span data-stu-id="000e2-108">MAPI uses the routine **GetProcAddress** to get the address of the service provider's initialization routine and then calls that routine.</span></span> <span data-ttu-id="000e2-109">初始化例程的名称是**XPProviderInit**传输提供程序。</span><span class="sxs-lookup"><span data-stu-id="000e2-109">The name of the initialization routine is **XPProviderInit** for transport providers.</span></span> <span data-ttu-id="000e2-110">使一个 DLL 可以包含服务提供程序类型，但只有一个服务提供程序特定类型的任意组合，它是不同的其他类型的 MAPI 服务提供商。</span><span class="sxs-lookup"><span data-stu-id="000e2-110">It is different for other types of MAPI service providers so that one DLL can contain any combination of service provider types, but only one service provider of a particular type.</span></span> <span data-ttu-id="000e2-111">但是，给定类型的一个服务提供商可以实现与其类型的多项服务。</span><span class="sxs-lookup"><span data-stu-id="000e2-111">However, one service provider of a given type can implement multiple services of its type.</span></span> <span data-ttu-id="000e2-112">例如，一个传输提供程序可以实现多个消息服务的邮件传输功能。</span><span class="sxs-lookup"><span data-stu-id="000e2-112">For example, one transport provider can implement message transport functionality to multiple message services.</span></span> 
  
<span data-ttu-id="000e2-113">Mapispi.h 头文件具有的传输提供程序初始化函数，该函数原型的类型定义和它的预定义的过程名称。</span><span class="sxs-lookup"><span data-stu-id="000e2-113">The mapispi.h header file has a type definition for the function prototype of the transport provider initialization function, and a predefined procedure name for it.</span></span> <span data-ttu-id="000e2-114">通过使用由**GetProcAddress**并通过使用简单的相同名称命名您的 C 和 c + + 文件中的初始化例程导出 DLL 中的声明。DEF 文件，您将自动获取类型检查的初始化例程的参数。</span><span class="sxs-lookup"><span data-stu-id="000e2-114">By naming the initialization routines in your C and C++ files with the same names used by **GetProcAddress** and by using a straightforward export declaration in your DLL.DEF file, you automatically get type checking of the parameters on your initialization routine.</span></span> <span data-ttu-id="000e2-115">请参阅示例的示例传输提供程序源代码。</span><span class="sxs-lookup"><span data-stu-id="000e2-115">See the sample transport provider source code for examples.</span></span> <span data-ttu-id="000e2-116">有关详细信息，请参阅[传输提供程序示例](transport-provider-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="000e2-116">For more information, see [Transport Provider Sample](transport-provider-sample.md).</span></span>
  
<span data-ttu-id="000e2-117">如果服务提供商的初始化调用成功，但返回的服务提供商接口版本号 MAPI 处理的太小，MAPI 立即调用服务提供商对象的**发布**方法和直接如同初始化呼叫具有 MAPI_E_VERSION 失败。</span><span class="sxs-lookup"><span data-stu-id="000e2-117">If a service provider's initialization call succeeds but returns a service provider interface version number too small for MAPI to handle, MAPI immediately calls the **Release** method of the service provider object and proceeds as if the initialization call had failed with MAPI_E_VERSION.</span></span> <span data-ttu-id="000e2-118">这种方式 MAPI 服务提供商共同定义和号码范围的服务提供程序界面版本能够处理，并使用 MAPI_E_VERSION 失败如果 nothing 匹配，则服务提供商加载返回值。</span><span class="sxs-lookup"><span data-stu-id="000e2-118">This way MAPI and the service provider jointly define the range of service provider interface version numbers they can handle, and if nothing matches then service provider loading fails with a MAPI_E_VERSION return value.</span></span> 
  
<span data-ttu-id="000e2-119">获取服务提供程序资源的访问权限 MAPI 后台处理程序的最后一步是登录到传输提供程序。</span><span class="sxs-lookup"><span data-stu-id="000e2-119">The last step for the MAPI spooler in getting access to service provider resources is to log on to the transport provider.</span></span> <span data-ttu-id="000e2-120">MAPI 后台处理程序调用的[IXPProvider::TransportLogon](ixpprovider-transportlogon.md)方法[IXPProvider: IUnknown](ixpprovideriunknown.md) **XPProviderInit**从返回的对象。</span><span class="sxs-lookup"><span data-stu-id="000e2-120">The MAPI spooler calls the [IXPProvider::TransportLogon](ixpprovider-transportlogon.md) method of the [IXPProvider : IUnknown](ixpprovideriunknown.md) object returned from **XPProviderInit**.</span></span> <span data-ttu-id="000e2-121">这是的调用其中检查凭据，如果使用，并且可以允许对话框。</span><span class="sxs-lookup"><span data-stu-id="000e2-121">This is the call where credentials, if used, are checked and dialog boxes can be allowed.</span></span>
  
<span data-ttu-id="000e2-122">如果一个进程打开的上同一传输提供程序的第二个传输会话和 MAPI 会话，请传输提供程序 DLL 不应创建第二个提供程序对象。</span><span class="sxs-lookup"><span data-stu-id="000e2-122">If a process opens a second transport session on the same transport provider and MAPI session, the transport provider DLL should not create a second provider object.</span></span> <span data-ttu-id="000e2-123">第一个提供商对象用于登录到第二个传输会话。</span><span class="sxs-lookup"><span data-stu-id="000e2-123">The first provider object should be used to log on to the second transport session.</span></span> <span data-ttu-id="000e2-124">应该对传输提供程序进行编程，以支持多个传输会话在单个提供程序对象。</span><span class="sxs-lookup"><span data-stu-id="000e2-124">A transport provider should be programmed to support multiple transport sessions in a single provider object.</span></span> <span data-ttu-id="000e2-125">如果在同一个进程使用不同的 MAPI 会话，则只应创建第二个提供程序对象。</span><span class="sxs-lookup"><span data-stu-id="000e2-125">A second provider object should only be created if different MAPI sessions are used in the same process.</span></span>
  

