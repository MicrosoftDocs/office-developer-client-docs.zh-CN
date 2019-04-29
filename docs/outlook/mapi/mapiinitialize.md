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
# <a name="mapiinitialize"></a><span data-ttu-id="b31ac-103">MAPIInitialize</span><span class="sxs-lookup"><span data-stu-id="b31ac-103">MAPIInitialize</span></span>

  
  
<span data-ttu-id="b31ac-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="b31ac-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="b31ac-105">递增 mapi 子系统引用计数并为 mapi DLL 初始化全局数据。</span><span class="sxs-lookup"><span data-stu-id="b31ac-105">Increments the MAPI subsystem reference count and initializes global data for the MAPI DLL.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="b31ac-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="b31ac-106">Header file:</span></span>  <br/> |<span data-ttu-id="b31ac-107">Mapix</span><span class="sxs-lookup"><span data-stu-id="b31ac-107">Mapix.h</span></span>  <br/> |
|<span data-ttu-id="b31ac-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="b31ac-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="b31ac-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="b31ac-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="b31ac-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="b31ac-110">Called by:</span></span>  <br/> |<span data-ttu-id="b31ac-111">客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="b31ac-111">Client applications</span></span>  <br/> |
   
```cpp
HRESULT MAPIInitialize(
  LPVOID lpMapiInit
);
```

## <a name="parameters"></a><span data-ttu-id="b31ac-112">参数</span><span class="sxs-lookup"><span data-stu-id="b31ac-112">Parameters</span></span>

 <span data-ttu-id="b31ac-113">_lpMapiInit_</span><span class="sxs-lookup"><span data-stu-id="b31ac-113">_lpMapiInit_</span></span>
  
> <span data-ttu-id="b31ac-114">实时指向[MAPIINIT_0](mapiinit_0.md)结构的指针。</span><span class="sxs-lookup"><span data-stu-id="b31ac-114">[in] Pointer to a [MAPIINIT_0](mapiinit_0.md) structure.</span></span> <span data-ttu-id="b31ac-115">可以将_lpMapiInit_参数设置为 NULL。</span><span class="sxs-lookup"><span data-stu-id="b31ac-115">The  _lpMapiInit_ parameter can be set to NULL.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="b31ac-116">返回值</span><span class="sxs-lookup"><span data-stu-id="b31ac-116">Return value</span></span>

<span data-ttu-id="b31ac-117">S_OK</span><span class="sxs-lookup"><span data-stu-id="b31ac-117">S_OK</span></span> 
  
> <span data-ttu-id="b31ac-118">MAPI 子系统已成功初始化。</span><span class="sxs-lookup"><span data-stu-id="b31ac-118">The MAPI subsystem was initialized successfully.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="b31ac-119">说明</span><span class="sxs-lookup"><span data-stu-id="b31ac-119">Remarks</span></span>

<span data-ttu-id="b31ac-120">**MAPIInitialize**函数递增 mapi 子系统的 mapi 引用计数, [MAPIUninitialize](mapiuninitialize.md)函数递减内部引用计数。</span><span class="sxs-lookup"><span data-stu-id="b31ac-120">The **MAPIInitialize** function increments the MAPI reference count for the MAPI subsystem, and the [MAPIUninitialize](mapiuninitialize.md) function decrements the internal reference count.</span></span> <span data-ttu-id="b31ac-121">因此, 对一个函数的调用次数必须等于对另一个函数的调用次数。</span><span class="sxs-lookup"><span data-stu-id="b31ac-121">Thus, the number of calls to one function must equal the number of calls to the other.</span></span> <span data-ttu-id="b31ac-122">如果 MAPI 以前尚未初始化, 则**MAPIInitialize**将返回 S_OK。</span><span class="sxs-lookup"><span data-stu-id="b31ac-122">**MAPIInitialize** returns S_OK if MAPI has not been previously initialized.</span></span> 
  
<span data-ttu-id="b31ac-123">在进行任何其他 MAPI 呼叫之前, 客户端或服务提供程序必须调用**MAPIInitialize** 。</span><span class="sxs-lookup"><span data-stu-id="b31ac-123">A client or service provider must call **MAPIInitialize** before making any other MAPI call.</span></span> <span data-ttu-id="b31ac-124">如果不这样做, 则会导致客户端或服务提供程序调用返回 MAPI_E_NOT_INITIALIZED 值。</span><span class="sxs-lookup"><span data-stu-id="b31ac-124">Failure to do so causes client or service provider calls to return the MAPI_E_NOT_INITIALIZED value.</span></span> 
  
<span data-ttu-id="b31ac-125">从多线程应用程序调用**MAPIInitialize**时, 请将_lpMapiInit_参数设置为以下声明的[MAPIINIT_0](mapiinit_0.md)结构:</span><span class="sxs-lookup"><span data-stu-id="b31ac-125">When calling **MAPIInitialize** from a multithreaded application, set the  _lpMapiInit_ parameter to a [MAPIINIT_0](mapiinit_0.md) structure that is declared as follows:</span></span> 
  
 <span data-ttu-id="b31ac-126">**MAPIINIT_0**MAPIINIT = {0, MAPI_MULTITHREAD_NOTIFICATIONS}</span><span class="sxs-lookup"><span data-stu-id="b31ac-126">**MAPIINIT_0** MAPIINIT= { 0, MAPI_MULTITHREAD_NOTIFICATIONS}</span></span> 
  
<span data-ttu-id="b31ac-127">和呼叫:</span><span class="sxs-lookup"><span data-stu-id="b31ac-127">and call:</span></span> 
  
 <span data-ttu-id="b31ac-128">**MAPIInitialize**(&amp;MAPIINIT);</span><span class="sxs-lookup"><span data-stu-id="b31ac-128">**MAPIInitialize** (&amp;MAPIINIT);</span></span> 
  
<span data-ttu-id="b31ac-129">声明此结构时, MAPI 将创建单独的线程来处理通知窗口, 这将一直持续到初始化引用计数降为零。</span><span class="sxs-lookup"><span data-stu-id="b31ac-129">When this structure is declared, MAPI creates a separate thread to handle the notification window, which continues until the initialize reference count falls to zero.</span></span> <span data-ttu-id="b31ac-130">Windows 服务必须将_lpMapiInit_指向的**MAPIINIT_0**结构的**ulflags**成员设置为 MAPI_NT_SERVICE。</span><span class="sxs-lookup"><span data-stu-id="b31ac-130">A Windows service must set the **ulflags** member of the **MAPIINIT_0** structure pointed to by  _lpMapiInit_ to MAPI_NT_SERVICE.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="b31ac-131">无法从 Win32 **DllMain**函数或任何其他创建或终止线程的函数中调用**MAPIInitialize**或**MAPIUninitialize** 。</span><span class="sxs-lookup"><span data-stu-id="b31ac-131">You cannot call **MAPIInitialize** or **MAPIUninitialize** from within a Win32 **DllMain** function or any other function that creates or terminates threads.</span></span> <span data-ttu-id="b31ac-132">有关详细信息, 请参阅[使用线程安全对象](using-thread-safe-objects.md)。</span><span class="sxs-lookup"><span data-stu-id="b31ac-132">For more information, see [Using Thread-Safe Objects](using-thread-safe-objects.md).</span></span> 
  
 <span data-ttu-id="b31ac-133">**MAPIInitialize**不会返回任何扩展的错误消息。</span><span class="sxs-lookup"><span data-stu-id="b31ac-133">**MAPIInitialize** does not return any extended error information.</span></span> <span data-ttu-id="b31ac-134">与大多数其他 MAPI 调用不同的是, 其返回值的含义严格定义为与失败的初始化的特定步骤相对应:</span><span class="sxs-lookup"><span data-stu-id="b31ac-134">Unlike most other MAPI calls, the meanings of its return values are strictly defined to correspond to the particular step of the initialization that failed:</span></span> 
  
1. <span data-ttu-id="b31ac-135">检查参数和标志。</span><span class="sxs-lookup"><span data-stu-id="b31ac-135">Checks parameters and flags.</span></span>
    
    <span data-ttu-id="b31ac-136">MAPI_E_INVALID_PARAMETER 或 MAPI_E_UNKNOWN_FLAGS。</span><span class="sxs-lookup"><span data-stu-id="b31ac-136">MAPI_E_INVALID_PARAMETER or MAPI_E_UNKNOWN_FLAGS.</span></span> <span data-ttu-id="b31ac-137">呼叫者传递了无效参数或标志。</span><span class="sxs-lookup"><span data-stu-id="b31ac-137">Caller passed invalid parameter or flag.</span></span>
    
2. <span data-ttu-id="b31ac-138">初始化 MAPI 所需的注册表项, 并确认操作系统的类型。</span><span class="sxs-lookup"><span data-stu-id="b31ac-138">Initializes registry keys required by MAPI and confirms the type of operating system.</span></span> <span data-ttu-id="b31ac-139">仅当客户端进程在 Windows 下作为服务运行, 并在**MAPIINIT_0**结构中设置 MAPI_NT 服务标记时, 才会发生此步骤。</span><span class="sxs-lookup"><span data-stu-id="b31ac-139">This step only happens if the client process is running as a service under Windows and sets the MAPI_NT SERVICE flag in the **MAPIINIT_0** structure.</span></span> 
    
    <span data-ttu-id="b31ac-140">MAPI_E_TOO_COMPLEX。</span><span class="sxs-lookup"><span data-stu-id="b31ac-140">MAPI_E_TOO_COMPLEX.</span></span> <span data-ttu-id="b31ac-141">调用进程是一种 Windows 服务, 无法初始化 MAPI 所需的注册表项。</span><span class="sxs-lookup"><span data-stu-id="b31ac-141">The calling process is a Windows service and registry keys required by MAPI could not be initialized.</span></span> 
    
    <span data-ttu-id="b31ac-142">应用程序事件日志中可能提供了其他信息。</span><span class="sxs-lookup"><span data-stu-id="b31ac-142">Additional information may be available in the application event log.</span></span>
    
3. <span data-ttu-id="b31ac-143">请检查 MAPI 与 ole 的兼容性, 然后初始化 ole。</span><span class="sxs-lookup"><span data-stu-id="b31ac-143">Check for the compatibility of MAPI with OLE, then initialize OLE.</span></span>
    
1. <span data-ttu-id="b31ac-144">检查当前版本的 OLE 和 MAPI 之间的兼容性。</span><span class="sxs-lookup"><span data-stu-id="b31ac-144">Checks for compatibility between the current versions of OLE and MAPI.</span></span> 
    
    <span data-ttu-id="b31ac-145">MAPI_E_VERSION。</span><span class="sxs-lookup"><span data-stu-id="b31ac-145">MAPI_E_VERSION.</span></span> <span data-ttu-id="b31ac-146">在工作站上安装的 OLE 版本与此版本的 MAPI 不兼容。</span><span class="sxs-lookup"><span data-stu-id="b31ac-146">The version of OLE installed on the workstation is not compatible with this version of MAPI.</span></span>
    
2. <span data-ttu-id="b31ac-147">初始化 OLE。</span><span class="sxs-lookup"><span data-stu-id="b31ac-147">Initializes OLE.</span></span> 
    
    <span data-ttu-id="b31ac-148">在此步骤中, 此函数可能返回未在此处列出的错误代码。</span><span class="sxs-lookup"><span data-stu-id="b31ac-148">During this step only, this function can return an error code not listed here.</span></span> <span data-ttu-id="b31ac-149">此处_未_列出的任何错误都应假定为来自 OLE 函数**CoInitialize**。</span><span class="sxs-lookup"><span data-stu-id="b31ac-149">Any error  _not_ listed here should be assumed to come from the OLE function **CoInitialize**.</span></span>
    
4. <span data-ttu-id="b31ac-150">初始化每个进程的全局变量。</span><span class="sxs-lookup"><span data-stu-id="b31ac-150">Initializes per-process global variables.</span></span>
    
    <span data-ttu-id="b31ac-151">MAPI_E_SESSION_LIMIT。</span><span class="sxs-lookup"><span data-stu-id="b31ac-151">MAPI_E_SESSION_LIMIT.</span></span> <span data-ttu-id="b31ac-152">MAPI 设置特定于当前进程的上下文。</span><span class="sxs-lookup"><span data-stu-id="b31ac-152">MAPI sets up context specific to the current process.</span></span> <span data-ttu-id="b31ac-153">如果进程数超过一定数量, 或者如果可用内存耗尽, 则在 Win16 上可能会发生失败。</span><span class="sxs-lookup"><span data-stu-id="b31ac-153">Failures may occur on Win16 if the number of processes exceeds a certain number, or on any system if available memory is exhausted.</span></span>
    
5. <span data-ttu-id="b31ac-154">初始化所有进程的共享全局变量。</span><span class="sxs-lookup"><span data-stu-id="b31ac-154">Initializes shared global variables of all processes.</span></span>
    
    <span data-ttu-id="b31ac-155">MAPI_E_NOT_ENOUGH_RESOURCES。</span><span class="sxs-lookup"><span data-stu-id="b31ac-155">MAPI_E_NOT_ENOUGH_RESOURCES.</span></span> <span data-ttu-id="b31ac-156">可用的系统资源不足, 无法完成此操作。</span><span class="sxs-lookup"><span data-stu-id="b31ac-156">Not enough system resources were available to complete the operation.</span></span>
    
6. <span data-ttu-id="b31ac-157">初始化通知引擎, 如果 MAPI_MULTITHREAD_NOTIFICATIONS 标志请求, 则会创建其窗口及其线程。</span><span class="sxs-lookup"><span data-stu-id="b31ac-157">Initializes the notification engine, creates its window and its thread if requested by the MAPI_MULTITHREAD_NOTIFICATIONS flag.</span></span> 
    
    <span data-ttu-id="b31ac-158">MAPI_E_INVALID_OBJECT。</span><span class="sxs-lookup"><span data-stu-id="b31ac-158">MAPI_E_INVALID_OBJECT.</span></span> <span data-ttu-id="b31ac-159">如果系统资源耗尽, 可能会失败。</span><span class="sxs-lookup"><span data-stu-id="b31ac-159">May fail if system resources are exhausted.</span></span> 
    
7. <span data-ttu-id="b31ac-160">加载并初始化配置文件提供程序。</span><span class="sxs-lookup"><span data-stu-id="b31ac-160">Loads and initializes the profile provider.</span></span> <span data-ttu-id="b31ac-161">验证**MAPIInitialize**是否可以访问存储配置文件数据的注册表项。</span><span class="sxs-lookup"><span data-stu-id="b31ac-161">Verifies that **MAPIInitialize** can access the registry key where profile data are stored.</span></span> 
    
    <span data-ttu-id="b31ac-162">MAPI_E_NOT_INITIALIZED。</span><span class="sxs-lookup"><span data-stu-id="b31ac-162">MAPI_E_NOT_INITIALIZED.</span></span> <span data-ttu-id="b31ac-163">配置文件提供程序遇到错误。</span><span class="sxs-lookup"><span data-stu-id="b31ac-163">The profile provider has encountered an error.</span></span> 
    
## <a name="mfcmapi-reference"></a><span data-ttu-id="b31ac-164">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="b31ac-164">MFCMAPI reference</span></span>

<span data-ttu-id="b31ac-165">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="b31ac-165">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="b31ac-166">**文件**</span><span class="sxs-lookup"><span data-stu-id="b31ac-166">**File**</span></span>|<span data-ttu-id="b31ac-167">**函数**</span><span class="sxs-lookup"><span data-stu-id="b31ac-167">**Function**</span></span>|<span data-ttu-id="b31ac-168">**备注**</span><span class="sxs-lookup"><span data-stu-id="b31ac-168">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="b31ac-169">ContentsTableListCtrl</span><span class="sxs-lookup"><span data-stu-id="b31ac-169">ContentsTableListCtrl.cpp</span></span>  <br/> ||<span data-ttu-id="b31ac-170">MFCMAPI 使用**MAPIInitialize**方法在后台线程上初始化 MAPI, 以执行某些表处理。</span><span class="sxs-lookup"><span data-stu-id="b31ac-170">MFCMAPI uses the **MAPIInitialize** method to initialize MAPI on a background thread to do some table processing.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="b31ac-171">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b31ac-171">See also</span></span>



[<span data-ttu-id="b31ac-172">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="b31ac-172">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

