---
title: 初始化传输提供程序
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 977c18ce-ece5-4ad1-ac97-5a680846ab83
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 474a8085ca8b82d11efd68c9fd4d8719fe239207
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33416599"
---
# <a name="initializing-the-transport-provider"></a><span data-ttu-id="cc2ba-103">初始化传输提供程序</span><span class="sxs-lookup"><span data-stu-id="cc2ba-103">Initializing the Transport Provider</span></span>

  
  
<span data-ttu-id="cc2ba-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="cc2ba-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="cc2ba-105">transport-spooler 接口定义 MAPI 后台处理程序对传输提供程序的调用。</span><span class="sxs-lookup"><span data-stu-id="cc2ba-105">The transport-spooler interface defines calls the MAPI spooler makes to a transport provider.</span></span> <span data-ttu-id="cc2ba-106">传输提供程序在动态链接库中实现这些例程 (DLL) 。</span><span class="sxs-lookup"><span data-stu-id="cc2ba-106">Transport providers implement these routines in a dynamic-link library (DLL).</span></span> <span data-ttu-id="cc2ba-107">MAPI 后台处理程序使用的 DLL 的第一个直接入口点必须是传输提供程序初始化函数 [XPProviderInit](xpproviderinit.md)。</span><span class="sxs-lookup"><span data-stu-id="cc2ba-107">The first direct entry point into the DLL used by the MAPI spooler must be the transport provider initialization function [XPProviderInit](xpproviderinit.md).</span></span>
  
<span data-ttu-id="cc2ba-108">MAPI 使用 **例程 GetProcAddress** 获取服务提供商的初始化例程的地址，然后调用该例程。</span><span class="sxs-lookup"><span data-stu-id="cc2ba-108">MAPI uses the routine **GetProcAddress** to get the address of the service provider's initialization routine and then calls that routine.</span></span> <span data-ttu-id="cc2ba-109">对于传输提供程序，初始化例程的名称为 **XPProviderInit。**</span><span class="sxs-lookup"><span data-stu-id="cc2ba-109">The name of the initialization routine is **XPProviderInit** for transport providers.</span></span> <span data-ttu-id="cc2ba-110">对于其他类型的 MAPI 服务提供程序，这有所不同，因此一个 DLL 可以包含任何服务提供程序类型组合，但只能包含一个特定类型的服务提供程序。</span><span class="sxs-lookup"><span data-stu-id="cc2ba-110">It is different for other types of MAPI service providers so that one DLL can contain any combination of service provider types, but only one service provider of a particular type.</span></span> <span data-ttu-id="cc2ba-111">但是，给定类型的一个服务提供商可以实现其类型的多个服务。</span><span class="sxs-lookup"><span data-stu-id="cc2ba-111">However, one service provider of a given type can implement multiple services of its type.</span></span> <span data-ttu-id="cc2ba-112">例如，一个传输提供程序可以将邮件传输功能实现到多个邮件服务。</span><span class="sxs-lookup"><span data-stu-id="cc2ba-112">For example, one transport provider can implement message transport functionality to multiple message services.</span></span> 
  
<span data-ttu-id="cc2ba-113">mapispi.h 头文件具有传输提供程序初始化函数的函数原型的类型定义，以及它的预定义过程名称。</span><span class="sxs-lookup"><span data-stu-id="cc2ba-113">The mapispi.h header file has a type definition for the function prototype of the transport provider initialization function, and a predefined procedure name for it.</span></span> <span data-ttu-id="cc2ba-114">通过使用 **GetProcAddress** 使用的相同名称在 C 和 C++ 文件中命名初始化例程，在 DLL.DEF 文件中使用简单的导出声明，可自动获取初始化例程上参数的类型检查。</span><span class="sxs-lookup"><span data-stu-id="cc2ba-114">By naming the initialization routines in your C and C++ files with the same names used by **GetProcAddress** and by using a straightforward export declaration in your DLL.DEF file, you automatically get type checking of the parameters on your initialization routine.</span></span> <span data-ttu-id="cc2ba-115">有关示例，请参阅示例传输提供程序源代码。</span><span class="sxs-lookup"><span data-stu-id="cc2ba-115">See the sample transport provider source code for examples.</span></span> <span data-ttu-id="cc2ba-116">有关详细信息，请参阅传输 [提供程序示例](transport-provider-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="cc2ba-116">For more information, see [Transport Provider Sample](transport-provider-sample.md).</span></span>
  
<span data-ttu-id="cc2ba-117">如果服务提供商的初始化调用成功，但返回的服务提供商接口版本号太小，MAPI 无法处理，MAPI 将立即调用服务提供商对象的 **Release** 方法，然后继续，就像初始化调用在 MAPI_E_VERSION 中失败一样。</span><span class="sxs-lookup"><span data-stu-id="cc2ba-117">If a service provider's initialization call succeeds but returns a service provider interface version number too small for MAPI to handle, MAPI immediately calls the **Release** method of the service provider object and proceeds as if the initialization call had failed with MAPI_E_VERSION.</span></span> <span data-ttu-id="cc2ba-118">这样，MAPI 和服务提供商可以一起定义他们可以处理的服务提供商接口版本号的范围，如果没有任何匹配项，则服务提供程序加载将失败，MAPI_E_VERSION值。</span><span class="sxs-lookup"><span data-stu-id="cc2ba-118">This way MAPI and the service provider jointly define the range of service provider interface version numbers they can handle, and if nothing matches then service provider loading fails with a MAPI_E_VERSION return value.</span></span> 
  
<span data-ttu-id="cc2ba-119">MAPI 后台处理程序获取对服务提供商资源的访问权限的最后一步是登录到传输提供程序。</span><span class="sxs-lookup"><span data-stu-id="cc2ba-119">The last step for the MAPI spooler in getting access to service provider resources is to log on to the transport provider.</span></span> <span data-ttu-id="cc2ba-120">MAPI 后台处理程序调用从 **XPProviderInit** 返回的 [IXPProvider ： IUnknown](ixpprovideriunknown.md)对象的 IXPProvider：：TransportLogon 方法。 [](ixpprovider-transportlogon.md)</span><span class="sxs-lookup"><span data-stu-id="cc2ba-120">The MAPI spooler calls the [IXPProvider::TransportLogon](ixpprovider-transportlogon.md) method of the [IXPProvider : IUnknown](ixpprovideriunknown.md) object returned from **XPProviderInit**.</span></span> <span data-ttu-id="cc2ba-121">这是检查凭据（如果使用）并允许对话框的调用。</span><span class="sxs-lookup"><span data-stu-id="cc2ba-121">This is the call where credentials, if used, are checked and dialog boxes can be allowed.</span></span>
  
<span data-ttu-id="cc2ba-122">如果进程在同一传输提供程序和 MAPI 会话上打开第二个传输会话，则传输提供程序 DLL 不应创建第二个提供程序对象。</span><span class="sxs-lookup"><span data-stu-id="cc2ba-122">If a process opens a second transport session on the same transport provider and MAPI session, the transport provider DLL should not create a second provider object.</span></span> <span data-ttu-id="cc2ba-123">第一个提供程序对象应该用于登录到第二个传输会话。</span><span class="sxs-lookup"><span data-stu-id="cc2ba-123">The first provider object should be used to log on to the second transport session.</span></span> <span data-ttu-id="cc2ba-124">传输提供程序应进行编程以支持单个提供程序对象中的多个传输会话。</span><span class="sxs-lookup"><span data-stu-id="cc2ba-124">A transport provider should be programmed to support multiple transport sessions in a single provider object.</span></span> <span data-ttu-id="cc2ba-125">只有当同一进程中使用不同的 MAPI 会话时，才应创建第二个提供程序对象。</span><span class="sxs-lookup"><span data-stu-id="cc2ba-125">A second provider object should only be created if different MAPI sessions are used in the same process.</span></span>
  

