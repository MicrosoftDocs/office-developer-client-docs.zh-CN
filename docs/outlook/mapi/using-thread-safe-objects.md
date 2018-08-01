---
title: 使用线程安全对象
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: e688db5e-d1a1-4afc-998f-b3d31eb6239b
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 4a66f892043b9a90893a60f3fa6ba69ea6457f5a
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779092"
---
# <a name="using-thread-safe-objects"></a><span data-ttu-id="0c1f0-103">使用线程安全对象</span><span class="sxs-lookup"><span data-stu-id="0c1f0-103">Using Thread-Safe Objects</span></span>

  
  
<span data-ttu-id="0c1f0-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="0c1f0-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="0c1f0-105">客户端应用程序可以假设对象直接使用或作为回调将始终线程安全除在出现以下情况：</span><span class="sxs-lookup"><span data-stu-id="0c1f0-105">Client applications can assume that objects used directly or as callbacks are always thread-safe except in the following cases:</span></span>
  
- <span data-ttu-id="0c1f0-106">传输提供程序的状态对象获取通过客户端调用[IMAPISession::OpenEntry](imapisession-openentry.md)条目标识符从提供程序的状态表格行。</span><span class="sxs-lookup"><span data-stu-id="0c1f0-106">A transport provider's status object obtained through a client call to [IMAPISession::OpenEntry](imapisession-openentry.md) with an entry identifier from the provider's status table row.</span></span> 
    
- <span data-ttu-id="0c1f0-107">通过客户端调用[MAPIOpenFormMgr](mapiopenformmgr.md)获取所有 MAPI 表单对象。</span><span class="sxs-lookup"><span data-stu-id="0c1f0-107">All MAPI form objects obtained through a client call to [MAPIOpenFormMgr](mapiopenformmgr.md).</span></span> <span data-ttu-id="0c1f0-108">表单对象遵循单元模型规则和客户端必须使用它们和仅在用于创建它们的线程上通过它们包含的所有对象。</span><span class="sxs-lookup"><span data-stu-id="0c1f0-108">Form objects obey apartment model rules and clients must use them and all objects contained by them only on the thread that created them.</span></span>
    
<span data-ttu-id="0c1f0-109">当客户端访问包含关联的状态对象的项标识符状态表中的传输提供程序的行时，客户端可以使用该条目标识符打开状态对象调用**OpenEntry** 。</span><span class="sxs-lookup"><span data-stu-id="0c1f0-109">When a client accesses a transport provider's row in the status table that includes the entry identifier of the associated status object, the client can call **OpenEntry** with that entry identifier to open the status object.</span></span> <span data-ttu-id="0c1f0-110">此状态对象不是线程安全，因为传输提供程序的 MAPI 后台处理程序上下文中运行，并且不维护其状态对象的单独的上下文。</span><span class="sxs-lookup"><span data-stu-id="0c1f0-110">This status object is not thread-safe because transport providers run in the context of the MAPI spooler and do not maintain a separate context for their status object.</span></span> <span data-ttu-id="0c1f0-111">状态对象服从单元模型规则和客户端必须仅在创建它的线程上使用它。</span><span class="sxs-lookup"><span data-stu-id="0c1f0-111">The status object obeys apartment model rules and clients must use it only on the thread that created it.</span></span> 
  
<span data-ttu-id="0c1f0-112">客户端必须还调用[MAPIInitialize](mapiinitialize.md)每个线程上使用完成时使用的任何 MAPI 对象和[MAPIUninitialize](mapiuninitialize.md)之前。</span><span class="sxs-lookup"><span data-stu-id="0c1f0-112">A client must also invoke [MAPIInitialize](mapiinitialize.md) on every thread before using any MAPI objects and [MAPIUninitialize](mapiuninitialize.md) when that use is complete.</span></span> <span data-ttu-id="0c1f0-113">即使要使用对象传递到线程从外部源应将这些呼叫。</span><span class="sxs-lookup"><span data-stu-id="0c1f0-113">These calls should be made even if the objects to be used are passed to the thread from an external source.</span></span> <span data-ttu-id="0c1f0-114">**MAPIInitialize**和**MAPIUninitialize**可以从任何地方除从中调用 Win32 **DllMain**函数，由系统时进程和线程初始化并终止，或者调用**时调用的函数LoadLibrary**和**句**函数。</span><span class="sxs-lookup"><span data-stu-id="0c1f0-114">**MAPIInitialize** and **MAPIUninitialize** can be called from anywhere except from within a Win32 **DllMain** function, a function that is invoked by the system when processes and threads are initialized and terminated, or upon calls to the **LoadLibrary** and **FreeLibrary** functions.</span></span> 
  
<span data-ttu-id="0c1f0-115">从不应假定间接使用对象可线程安全。</span><span class="sxs-lookup"><span data-stu-id="0c1f0-115">Indirect use objects should never be assumed to be thread-safe.</span></span> <span data-ttu-id="0c1f0-116">需要作为输入参数的目标接口指针方法返回间接使用对象。</span><span class="sxs-lookup"><span data-stu-id="0c1f0-116">Indirect use objects are returned by methods that require destination interface pointers as input parameters.</span></span> <span data-ttu-id="0c1f0-117">这种方法的示例是**IMAPIProp::CopyTo**和**CopyProps**、 **IMAPIFolder::CopyFolder**和**CopyMessage**和**IMsgServiceAdmin::CopyMsgService**。</span><span class="sxs-lookup"><span data-stu-id="0c1f0-117">Examples of such methods are **IMAPIProp::CopyTo** and **CopyProps**, **IMAPIFolder::CopyFolder** and **CopyMessage**, and **IMsgServiceAdmin::CopyMsgService**.</span></span> <span data-ttu-id="0c1f0-118">如果服务提供商想要在其上以外传递给它的线程从呼叫这样的对象，提供程序负责明确封送处理对象。</span><span class="sxs-lookup"><span data-stu-id="0c1f0-118">If a service provider wants to call such an object from a thread other than the one on which it was passed, the provider is responsible for explicitly marshaling the object.</span></span>
  

