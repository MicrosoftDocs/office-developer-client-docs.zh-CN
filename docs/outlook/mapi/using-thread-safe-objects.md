---
title: 使用线程安全对象
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: e688db5e-d1a1-4afc-998f-b3d31eb6239b
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 611e0a49f0fd8df8fe40205a33ed5501055c3d45
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33425167"
---
# <a name="using-thread-safe-objects"></a><span data-ttu-id="de3a4-103">使用线程安全对象</span><span class="sxs-lookup"><span data-stu-id="de3a4-103">Using Thread-Safe Objects</span></span>

  
  
<span data-ttu-id="de3a4-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="de3a4-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="de3a4-105">客户端应用程序可以假定直接使用或以回调方式使用的对象总是线程安全的, 但在以下情况除外:</span><span class="sxs-lookup"><span data-stu-id="de3a4-105">Client applications can assume that objects used directly or as callbacks are always thread-safe except in the following cases:</span></span>
  
- <span data-ttu-id="de3a4-106">通过客户端调用[IMAPISession:: OpenEntry](imapisession-openentry.md)获取的传输提供程序的 status 对象是提供程序状态表行中的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="de3a4-106">A transport provider's status object obtained through a client call to [IMAPISession::OpenEntry](imapisession-openentry.md) with an entry identifier from the provider's status table row.</span></span> 
    
- <span data-ttu-id="de3a4-107">通过客户端调用获取的所有 MAPI 表单对象[MAPIOpenFormMgr](mapiopenformmgr.md)。</span><span class="sxs-lookup"><span data-stu-id="de3a4-107">All MAPI form objects obtained through a client call to [MAPIOpenFormMgr](mapiopenformmgr.md).</span></span> <span data-ttu-id="de3a4-108">表单对象遵循单元模型规则, 并且客户端必须仅在创建它们的线程上使用它们及其包含的所有对象。</span><span class="sxs-lookup"><span data-stu-id="de3a4-108">Form objects obey apartment model rules and clients must use them and all objects contained by them only on the thread that created them.</span></span>
    
<span data-ttu-id="de3a4-109">当客户端访问状态表中的传输提供程序的行, 其中包括关联状态对象的条目标识符时, 客户端可以使用该条目标识符调用**OpenEntry** , 以打开 status 对象。</span><span class="sxs-lookup"><span data-stu-id="de3a4-109">When a client accesses a transport provider's row in the status table that includes the entry identifier of the associated status object, the client can call **OpenEntry** with that entry identifier to open the status object.</span></span> <span data-ttu-id="de3a4-110">此状态对象不是线程安全的, 因为传输提供程序在 MAPI 后台处理程序的上下文中运行, 并且没有为其状态对象维护单独的上下文。</span><span class="sxs-lookup"><span data-stu-id="de3a4-110">This status object is not thread-safe because transport providers run in the context of the MAPI spooler and do not maintain a separate context for their status object.</span></span> <span data-ttu-id="de3a4-111">status 对象 obeys 单元模型规则和客户端必须仅在创建它的线程上使用。</span><span class="sxs-lookup"><span data-stu-id="de3a4-111">The status object obeys apartment model rules and clients must use it only on the thread that created it.</span></span> 
  
<span data-ttu-id="de3a4-112">在使用任何 MAPI 对象和[MAPIUninitialize](mapiuninitialize.md)时, 客户端还必须对每个线程调用[MAPIInitialize](mapiinitialize.md) , 然后再使用该对象。</span><span class="sxs-lookup"><span data-stu-id="de3a4-112">A client must also invoke [MAPIInitialize](mapiinitialize.md) on every thread before using any MAPI objects and [MAPIUninitialize](mapiuninitialize.md) when that use is complete.</span></span> <span data-ttu-id="de3a4-113">即使要使用的对象被传递给外部源中的线程, 也应进行这些调用。</span><span class="sxs-lookup"><span data-stu-id="de3a4-113">These calls should be made even if the objects to be used are passed to the thread from an external source.</span></span> <span data-ttu-id="de3a4-114">**MAPIInitialize**和**MAPIUninitialize**可以从任何位置调用, 除了 Win32 **DllMain**函数之外, 在进程和线程初始化和终止时, 或者在调用**时由系统调用的函数LoadLibrary**和**FreeLibrary**函数。</span><span class="sxs-lookup"><span data-stu-id="de3a4-114">**MAPIInitialize** and **MAPIUninitialize** can be called from anywhere except from within a Win32 **DllMain** function, a function that is invoked by the system when processes and threads are initialized and terminated, or upon calls to the **LoadLibrary** and **FreeLibrary** functions.</span></span> 
  
<span data-ttu-id="de3a4-115">间接使用对象决不应假定为线程安全对象。</span><span class="sxs-lookup"><span data-stu-id="de3a4-115">Indirect use objects should never be assumed to be thread-safe.</span></span> <span data-ttu-id="de3a4-116">间接使用对象由需要将目标接口指针作为输入参数的方法返回。</span><span class="sxs-lookup"><span data-stu-id="de3a4-116">Indirect use objects are returned by methods that require destination interface pointers as input parameters.</span></span> <span data-ttu-id="de3a4-117">此类方法的示例包括**IMAPIProp:: CopyTo**和**CopyProps**、 **IMAPIFolder:: CopyFolder**和**CopyMessage**和**IMsgServiceAdmin:: CopyMsgService**。</span><span class="sxs-lookup"><span data-stu-id="de3a4-117">Examples of such methods are **IMAPIProp::CopyTo** and **CopyProps**, **IMAPIFolder::CopyFolder** and **CopyMessage**, and **IMsgServiceAdmin::CopyMsgService**.</span></span> <span data-ttu-id="de3a4-118">如果服务提供程序要从传递此对象的线程以外的线程调用此类对象, 则提供程序将负责显式封送该对象。</span><span class="sxs-lookup"><span data-stu-id="de3a4-118">If a service provider wants to call such an object from a thread other than the one on which it was passed, the provider is responsible for explicitly marshaling the object.</span></span>
  

