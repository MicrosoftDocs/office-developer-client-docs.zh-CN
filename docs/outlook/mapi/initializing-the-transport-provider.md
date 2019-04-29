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
# <a name="initializing-the-transport-provider"></a><span data-ttu-id="5552b-103">初始化传输提供程序</span><span class="sxs-lookup"><span data-stu-id="5552b-103">Initializing the Transport Provider</span></span>

  
  
<span data-ttu-id="5552b-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="5552b-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="5552b-105">传输后台处理程序接口定义 MAPI 后台处理程序对传输提供程序的调用。</span><span class="sxs-lookup"><span data-stu-id="5552b-105">The transport-spooler interface defines calls the MAPI spooler makes to a transport provider.</span></span> <span data-ttu-id="5552b-106">传输提供程序在动态链接库 (DLL) 中实现这些例程。</span><span class="sxs-lookup"><span data-stu-id="5552b-106">Transport providers implement these routines in a dynamic-link library (DLL).</span></span> <span data-ttu-id="5552b-107">MAPI 后台处理程序使用的 DLL 的第一个直接入口点必须是传输提供程序初始化函数[XPProviderInit](xpproviderinit.md)。</span><span class="sxs-lookup"><span data-stu-id="5552b-107">The first direct entry point into the DLL used by the MAPI spooler must be the transport provider initialization function [XPProviderInit](xpproviderinit.md).</span></span>
  
<span data-ttu-id="5552b-108">MAPI 使用例程**GetProcAddress**获取服务提供程序的初始化例程的地址, 然后调用该例程。</span><span class="sxs-lookup"><span data-stu-id="5552b-108">MAPI uses the routine **GetProcAddress** to get the address of the service provider's initialization routine and then calls that routine.</span></span> <span data-ttu-id="5552b-109">初始化例程的名称是传输提供程序的**XPProviderInit** 。</span><span class="sxs-lookup"><span data-stu-id="5552b-109">The name of the initialization routine is **XPProviderInit** for transport providers.</span></span> <span data-ttu-id="5552b-110">其他类型的 MAPI 服务提供程序是不同的, 因此一个 DLL 可以包含服务提供程序类型的任意组合, 但只有一个特定类型的服务提供程序。</span><span class="sxs-lookup"><span data-stu-id="5552b-110">It is different for other types of MAPI service providers so that one DLL can contain any combination of service provider types, but only one service provider of a particular type.</span></span> <span data-ttu-id="5552b-111">但是, 给定类型的一个服务提供程序可以实现其类型的多个服务。</span><span class="sxs-lookup"><span data-stu-id="5552b-111">However, one service provider of a given type can implement multiple services of its type.</span></span> <span data-ttu-id="5552b-112">例如, 一个传输提供程序可以实现邮件传输到多个邮件服务的功能。</span><span class="sxs-lookup"><span data-stu-id="5552b-112">For example, one transport provider can implement message transport functionality to multiple message services.</span></span> 
  
<span data-ttu-id="5552b-113">mapispi 头文件具有传输提供程序初始化函数的 function 原型的类型定义以及它的预定义过程名称。</span><span class="sxs-lookup"><span data-stu-id="5552b-113">The mapispi.h header file has a type definition for the function prototype of the transport provider initialization function, and a predefined procedure name for it.</span></span> <span data-ttu-id="5552b-114">通过在您的 C 和 c + + 文件中使用与**GetProcAddress**相同的名称命名的初始化例程以及在 DLL 中使用简单的导出声明来命名这些例程。DEF 文件中, 您将自动获取对初始化例程上参数的类型检查。</span><span class="sxs-lookup"><span data-stu-id="5552b-114">By naming the initialization routines in your C and C++ files with the same names used by **GetProcAddress** and by using a straightforward export declaration in your DLL.DEF file, you automatically get type checking of the parameters on your initialization routine.</span></span> <span data-ttu-id="5552b-115">有关示例, 请参阅传输提供程序的示例源代码。</span><span class="sxs-lookup"><span data-stu-id="5552b-115">See the sample transport provider source code for examples.</span></span> <span data-ttu-id="5552b-116">有关详细信息, 请参阅[传输提供程序示例](transport-provider-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="5552b-116">For more information, see [Transport Provider Sample](transport-provider-sample.md).</span></span>
  
<span data-ttu-id="5552b-117">如果服务提供程序的初始化调用成功, 但返回的服务提供程序接口版本号太小, mapi 无法处理, mapi 将立即调用服务提供程序对象的**Release**方法, 如同初始化调用一样失败, MAPI_E_VERSION。</span><span class="sxs-lookup"><span data-stu-id="5552b-117">If a service provider's initialization call succeeds but returns a service provider interface version number too small for MAPI to handle, MAPI immediately calls the **Release** method of the service provider object and proceeds as if the initialization call had failed with MAPI_E_VERSION.</span></span> <span data-ttu-id="5552b-118">通过这种方式, MAPI 和服务提供商可以共同定义他们可以处理的服务提供程序接口版本号的范围, 如果没有匹配项, 则服务提供程序加载将失败, 并返回 MAPI_E_VERSION 返回值。</span><span class="sxs-lookup"><span data-stu-id="5552b-118">This way MAPI and the service provider jointly define the range of service provider interface version numbers they can handle, and if nothing matches then service provider loading fails with a MAPI_E_VERSION return value.</span></span> 
  
<span data-ttu-id="5552b-119">MAPI 后台处理程序获取服务提供程序资源访问权限的最后一步是登录到传输提供程序。</span><span class="sxs-lookup"><span data-stu-id="5552b-119">The last step for the MAPI spooler in getting access to service provider resources is to log on to the transport provider.</span></span> <span data-ttu-id="5552b-120">MAPI 后台处理程序调用从**XPProviderInit**返回的[IXPProvider: IUnknown](ixpprovideriunknown.md)对象的[IXPProvider:: TransportLogon](ixpprovider-transportlogon.md)方法。</span><span class="sxs-lookup"><span data-stu-id="5552b-120">The MAPI spooler calls the [IXPProvider::TransportLogon](ixpprovider-transportlogon.md) method of the [IXPProvider : IUnknown](ixpprovideriunknown.md) object returned from **XPProviderInit**.</span></span> <span data-ttu-id="5552b-121">此呼叫将选中凭据 (如果已使用), 并且可以允许使用对话框。</span><span class="sxs-lookup"><span data-stu-id="5552b-121">This is the call where credentials, if used, are checked and dialog boxes can be allowed.</span></span>
  
<span data-ttu-id="5552b-122">如果某个进程在同一传输提供程序和 MAPI 会话中打开了第二个传输会话, 则传输提供程序 DLL 不应创建第二个 provider 对象。</span><span class="sxs-lookup"><span data-stu-id="5552b-122">If a process opens a second transport session on the same transport provider and MAPI session, the transport provider DLL should not create a second provider object.</span></span> <span data-ttu-id="5552b-123">应使用第一个 provider 对象登录到第二个传输会话。</span><span class="sxs-lookup"><span data-stu-id="5552b-123">The first provider object should be used to log on to the second transport session.</span></span> <span data-ttu-id="5552b-124">应将传输提供程序设计为支持单个提供程序对象中的多个传输会话。</span><span class="sxs-lookup"><span data-stu-id="5552b-124">A transport provider should be programmed to support multiple transport sessions in a single provider object.</span></span> <span data-ttu-id="5552b-125">仅当在同一进程中使用不同的 MAPI 会话时, 才应创建第二个提供程序对象。</span><span class="sxs-lookup"><span data-stu-id="5552b-125">A second provider object should only be created if different MAPI sessions are used in the same process.</span></span>
  

