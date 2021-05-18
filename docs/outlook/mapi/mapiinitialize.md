---
title: MAPIInitialize
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPIInitialize
api_type:
- HeaderDef
ms.assetid: b9584226-79d2-4d83-8f31-dbfbc50f16c5
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 6464f16d9ad73b332ff20dc007ef162b9525c6d5
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33411174"
---
# <a name="mapiinitialize"></a><span data-ttu-id="478c4-103">MAPIInitialize</span><span class="sxs-lookup"><span data-stu-id="478c4-103">MAPIInitialize</span></span>

  
  
<span data-ttu-id="478c4-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="478c4-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="478c4-105">增加 MAPI 子系统引用计数并初始化 MAPI DLL 的全局数据。</span><span class="sxs-lookup"><span data-stu-id="478c4-105">Increments the MAPI subsystem reference count and initializes global data for the MAPI DLL.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="478c4-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="478c4-106">Header file:</span></span>  <br/> |<span data-ttu-id="478c4-107">Mapix.h</span><span class="sxs-lookup"><span data-stu-id="478c4-107">Mapix.h</span></span>  <br/> |
|<span data-ttu-id="478c4-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="478c4-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="478c4-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="478c4-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="478c4-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="478c4-110">Called by:</span></span>  <br/> |<span data-ttu-id="478c4-111">客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="478c4-111">Client applications</span></span>  <br/> |
   
```cpp
HRESULT MAPIInitialize(
  LPVOID lpMapiInit
);
```

## <a name="parameters"></a><span data-ttu-id="478c4-112">参数</span><span class="sxs-lookup"><span data-stu-id="478c4-112">Parameters</span></span>

 <span data-ttu-id="478c4-113">_lpMapiInit_</span><span class="sxs-lookup"><span data-stu-id="478c4-113">_lpMapiInit_</span></span>
  
> <span data-ttu-id="478c4-114">[in]指向结构 [MAPIINIT_0](mapiinit_0.md) 指针。</span><span class="sxs-lookup"><span data-stu-id="478c4-114">[in] Pointer to a [MAPIINIT_0](mapiinit_0.md) structure.</span></span> <span data-ttu-id="478c4-115">可以将  _lpMapiInit_ 参数设置为 NULL。</span><span class="sxs-lookup"><span data-stu-id="478c4-115">The  _lpMapiInit_ parameter can be set to NULL.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="478c4-116">返回值</span><span class="sxs-lookup"><span data-stu-id="478c4-116">Return value</span></span>

<span data-ttu-id="478c4-117">S_OK</span><span class="sxs-lookup"><span data-stu-id="478c4-117">S_OK</span></span> 
  
> <span data-ttu-id="478c4-118">MAPI 子系统已成功初始化。</span><span class="sxs-lookup"><span data-stu-id="478c4-118">The MAPI subsystem was initialized successfully.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="478c4-119">备注</span><span class="sxs-lookup"><span data-stu-id="478c4-119">Remarks</span></span>

<span data-ttu-id="478c4-120">**MAPIInitialize** 函数增加 MAPI 子系统的 MAPI 引用计数，[而 MAPIUninitialize](mapiuninitialize.md)函数会缩小内部引用计数。</span><span class="sxs-lookup"><span data-stu-id="478c4-120">The **MAPIInitialize** function increments the MAPI reference count for the MAPI subsystem, and the [MAPIUninitialize](mapiuninitialize.md) function decrements the internal reference count.</span></span> <span data-ttu-id="478c4-121">因此，对一个函数的调用数必须等于对另一个函数的调用数。</span><span class="sxs-lookup"><span data-stu-id="478c4-121">Thus, the number of calls to one function must equal the number of calls to the other.</span></span> <span data-ttu-id="478c4-122">**如果 MAPI 尚未S_OK，MAPIInitialize** 将返回值。</span><span class="sxs-lookup"><span data-stu-id="478c4-122">**MAPIInitialize** returns S_OK if MAPI has not been previously initialized.</span></span> 
  
<span data-ttu-id="478c4-123">客户端或服务提供商必须先调用 **MAPIInitialize，** 然后才能进行任何其他 MAPI 调用。</span><span class="sxs-lookup"><span data-stu-id="478c4-123">A client or service provider must call **MAPIInitialize** before making any other MAPI call.</span></span> <span data-ttu-id="478c4-124">如果不这样做，客户端或服务提供商调用将返回MAPI_E_NOT_INITIALIZED值。</span><span class="sxs-lookup"><span data-stu-id="478c4-124">Failure to do so causes client or service provider calls to return the MAPI_E_NOT_INITIALIZED value.</span></span> 
  
<span data-ttu-id="478c4-125">从多 **线程应用程序调用 MAPIInitialize** 时，将 _lpMapiInit_ 参数设置为 [](mapiinit_0.md)MAPIINIT_0 结构，声明如下：</span><span class="sxs-lookup"><span data-stu-id="478c4-125">When calling **MAPIInitialize** from a multithreaded application, set the  _lpMapiInit_ parameter to a [MAPIINIT_0](mapiinit_0.md) structure that is declared as follows:</span></span> 
  
 <span data-ttu-id="478c4-126">**MAPIINIT_0** MAPIINIT= { 0，MAPI_MULTITHREAD_NOTIFICATIONS}</span><span class="sxs-lookup"><span data-stu-id="478c4-126">**MAPIINIT_0** MAPIINIT= { 0, MAPI_MULTITHREAD_NOTIFICATIONS}</span></span> 
  
<span data-ttu-id="478c4-127">和 调用：</span><span class="sxs-lookup"><span data-stu-id="478c4-127">and call:</span></span> 
  
 <span data-ttu-id="478c4-128">**MAPIInitialize** (&amp; MAPIINIT) ;</span><span class="sxs-lookup"><span data-stu-id="478c4-128">**MAPIInitialize** (&amp;MAPIINIT);</span></span> 
  
<span data-ttu-id="478c4-129">声明此结构时，MAPI 将创建一个单独的线程来处理通知窗口，该窗口将一直持续到初始化引用计数为零。</span><span class="sxs-lookup"><span data-stu-id="478c4-129">When this structure is declared, MAPI creates a separate thread to handle the notification window, which continues until the initialize reference count falls to zero.</span></span> <span data-ttu-id="478c4-130">Windows 服务必须将 _lpMapiInit_ 指向的 MAPIINIT_0 **ulflags** 成员设置为 MAPI_NT_SERVICE。</span><span class="sxs-lookup"><span data-stu-id="478c4-130">A Windows service must set the **ulflags** member of the **MAPIINIT_0** structure pointed to by  _lpMapiInit_ to MAPI_NT_SERVICE.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="478c4-131">不能从 Win32 **DllMain** 函数或其他创建或终止线程的函数中调用 **MAPIInitialize** 或 **MAPIUninitialize。**</span><span class="sxs-lookup"><span data-stu-id="478c4-131">You cannot call **MAPIInitialize** or **MAPIUninitialize** from within a Win32 **DllMain** function or any other function that creates or terminates threads.</span></span> <span data-ttu-id="478c4-132">有关详细信息，请参阅使用对象 [Thread-Safe对象](using-thread-safe-objects.md)。</span><span class="sxs-lookup"><span data-stu-id="478c4-132">For more information, see [Using Thread-Safe Objects](using-thread-safe-objects.md).</span></span> 
  
 <span data-ttu-id="478c4-133">**MAPIInitialize** 不会返回任何扩展的错误信息。</span><span class="sxs-lookup"><span data-stu-id="478c4-133">**MAPIInitialize** does not return any extended error information.</span></span> <span data-ttu-id="478c4-134">与大多数其他 MAPI 调用不同，其返回值的含义严格定义为对应于失败的初始化的特定步骤：</span><span class="sxs-lookup"><span data-stu-id="478c4-134">Unlike most other MAPI calls, the meanings of its return values are strictly defined to correspond to the particular step of the initialization that failed:</span></span> 
  
1. <span data-ttu-id="478c4-135">检查参数和标志。</span><span class="sxs-lookup"><span data-stu-id="478c4-135">Checks parameters and flags.</span></span>
    
    <span data-ttu-id="478c4-136">MAPI_E_INVALID_PARAMETER 或 MAPI_E_UNKNOWN_FLAGS。</span><span class="sxs-lookup"><span data-stu-id="478c4-136">MAPI_E_INVALID_PARAMETER or MAPI_E_UNKNOWN_FLAGS.</span></span> <span data-ttu-id="478c4-137">调用方传递的参数或标志无效。</span><span class="sxs-lookup"><span data-stu-id="478c4-137">Caller passed invalid parameter or flag.</span></span>
    
2. <span data-ttu-id="478c4-138">初始化 MAPI 所需的注册表项并确认操作系统的类型。</span><span class="sxs-lookup"><span data-stu-id="478c4-138">Initializes registry keys required by MAPI and confirms the type of operating system.</span></span> <span data-ttu-id="478c4-139">只有当客户端进程作为 Windows 下的服务运行，并设置 MAPI_NT 结构中的服务标记时，MAPIINIT_0 **执行此步骤** 。</span><span class="sxs-lookup"><span data-stu-id="478c4-139">This step only happens if the client process is running as a service under Windows and sets the MAPI_NT SERVICE flag in the **MAPIINIT_0** structure.</span></span> 
    
    <span data-ttu-id="478c4-140">MAPI_E_TOO_COMPLEX。</span><span class="sxs-lookup"><span data-stu-id="478c4-140">MAPI_E_TOO_COMPLEX.</span></span> <span data-ttu-id="478c4-141">调用过程是 Windows 服务，无法初始化 MAPI 所需的注册表项。</span><span class="sxs-lookup"><span data-stu-id="478c4-141">The calling process is a Windows service and registry keys required by MAPI could not be initialized.</span></span> 
    
    <span data-ttu-id="478c4-142">应用程序事件日志中可能提供了其他信息。</span><span class="sxs-lookup"><span data-stu-id="478c4-142">Additional information may be available in the application event log.</span></span>
    
3. <span data-ttu-id="478c4-143">检查 MAPI 与 OLE 的兼容性，然后初始化 OLE。</span><span class="sxs-lookup"><span data-stu-id="478c4-143">Check for the compatibility of MAPI with OLE, then initialize OLE.</span></span>
    
1. <span data-ttu-id="478c4-144">检查当前版本的 OLE 和 MAPI 之间的兼容性。</span><span class="sxs-lookup"><span data-stu-id="478c4-144">Checks for compatibility between the current versions of OLE and MAPI.</span></span> 
    
    <span data-ttu-id="478c4-145">MAPI_E_VERSION。</span><span class="sxs-lookup"><span data-stu-id="478c4-145">MAPI_E_VERSION.</span></span> <span data-ttu-id="478c4-146">工作站上安装的 OLE 版本与此版本的 MAPI 不兼容。</span><span class="sxs-lookup"><span data-stu-id="478c4-146">The version of OLE installed on the workstation is not compatible with this version of MAPI.</span></span>
    
2. <span data-ttu-id="478c4-147">初始化 OLE。</span><span class="sxs-lookup"><span data-stu-id="478c4-147">Initializes OLE.</span></span> 
    
    <span data-ttu-id="478c4-148">仅在此步骤中，此函数可能会返回此处未列出的错误代码。</span><span class="sxs-lookup"><span data-stu-id="478c4-148">During this step only, this function can return an error code not listed here.</span></span> <span data-ttu-id="478c4-149">应  _假定_ 此处未列出的任何错误来自 OLE 函数 **CoInitialize**。</span><span class="sxs-lookup"><span data-stu-id="478c4-149">Any error  _not_ listed here should be assumed to come from the OLE function **CoInitialize**.</span></span>
    
4. <span data-ttu-id="478c4-150">初始化每个进程全局变量。</span><span class="sxs-lookup"><span data-stu-id="478c4-150">Initializes per-process global variables.</span></span>
    
    <span data-ttu-id="478c4-151">MAPI_E_SESSION_LIMIT。</span><span class="sxs-lookup"><span data-stu-id="478c4-151">MAPI_E_SESSION_LIMIT.</span></span> <span data-ttu-id="478c4-152">MAPI 设置特定于当前进程的上下文。</span><span class="sxs-lookup"><span data-stu-id="478c4-152">MAPI sets up context specific to the current process.</span></span> <span data-ttu-id="478c4-153">如果进程数超过特定数量，则 Win16 上可能发生故障;如果可用内存已耗尽，则在任何系统上可能发生故障。</span><span class="sxs-lookup"><span data-stu-id="478c4-153">Failures may occur on Win16 if the number of processes exceeds a certain number, or on any system if available memory is exhausted.</span></span>
    
5. <span data-ttu-id="478c4-154">初始化所有进程共享的全局变量。</span><span class="sxs-lookup"><span data-stu-id="478c4-154">Initializes shared global variables of all processes.</span></span>
    
    <span data-ttu-id="478c4-155">MAPI_E_NOT_ENOUGH_RESOURCES。</span><span class="sxs-lookup"><span data-stu-id="478c4-155">MAPI_E_NOT_ENOUGH_RESOURCES.</span></span> <span data-ttu-id="478c4-156">没有足够的系统资源来完成该操作。</span><span class="sxs-lookup"><span data-stu-id="478c4-156">Not enough system resources were available to complete the operation.</span></span>
    
6. <span data-ttu-id="478c4-157">初始化通知引擎，创建其窗口及其线程（如果由 MAPI_MULTITHREAD_NOTIFICATIONS 请求）。</span><span class="sxs-lookup"><span data-stu-id="478c4-157">Initializes the notification engine, creates its window and its thread if requested by the MAPI_MULTITHREAD_NOTIFICATIONS flag.</span></span> 
    
    <span data-ttu-id="478c4-158">MAPI_E_INVALID_OBJECT。</span><span class="sxs-lookup"><span data-stu-id="478c4-158">MAPI_E_INVALID_OBJECT.</span></span> <span data-ttu-id="478c4-159">如果系统资源用尽，可能会失败。</span><span class="sxs-lookup"><span data-stu-id="478c4-159">May fail if system resources are exhausted.</span></span> 
    
7. <span data-ttu-id="478c4-160">加载并初始化配置文件提供程序。</span><span class="sxs-lookup"><span data-stu-id="478c4-160">Loads and initializes the profile provider.</span></span> <span data-ttu-id="478c4-161">验证 **MAPIInitialize** 能否访问存储配置文件数据的注册表项。</span><span class="sxs-lookup"><span data-stu-id="478c4-161">Verifies that **MAPIInitialize** can access the registry key where profile data are stored.</span></span> 
    
    <span data-ttu-id="478c4-162">MAPI_E_NOT_INITIALIZED。</span><span class="sxs-lookup"><span data-stu-id="478c4-162">MAPI_E_NOT_INITIALIZED.</span></span> <span data-ttu-id="478c4-163">配置文件提供程序遇到错误。</span><span class="sxs-lookup"><span data-stu-id="478c4-163">The profile provider has encountered an error.</span></span> 
    
## <a name="mfcmapi-reference"></a><span data-ttu-id="478c4-164">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="478c4-164">MFCMAPI reference</span></span>

<span data-ttu-id="478c4-165">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="478c4-165">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="478c4-166">**文件**</span><span class="sxs-lookup"><span data-stu-id="478c4-166">**File**</span></span>|<span data-ttu-id="478c4-167">**函数**</span><span class="sxs-lookup"><span data-stu-id="478c4-167">**Function**</span></span>|<span data-ttu-id="478c4-168">**备注**</span><span class="sxs-lookup"><span data-stu-id="478c4-168">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="478c4-169">ContentsTableListCtrl.cpp</span><span class="sxs-lookup"><span data-stu-id="478c4-169">ContentsTableListCtrl.cpp</span></span>  <br/> ||<span data-ttu-id="478c4-170">MFCMAPI 使用 **MAPIInitialize** 方法初始化后台线程上的 MAPI 以执行一些表处理。</span><span class="sxs-lookup"><span data-stu-id="478c4-170">MFCMAPI uses the **MAPIInitialize** method to initialize MAPI on a background thread to do some table processing.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="478c4-171">另请参阅</span><span class="sxs-lookup"><span data-stu-id="478c4-171">See also</span></span>



[<span data-ttu-id="478c4-172">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="478c4-172">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

