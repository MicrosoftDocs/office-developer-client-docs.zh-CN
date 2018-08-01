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
ms.openlocfilehash: d22c24088960debcd18ccd818dad23656f6a01f2
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776382"
---
# <a name="mapiinitialize"></a><span data-ttu-id="d0ad6-103">MAPIInitialize</span><span class="sxs-lookup"><span data-stu-id="d0ad6-103">MAPIInitialize</span></span>

  
  
<span data-ttu-id="d0ad6-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="d0ad6-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="d0ad6-105">增加 MAPI 子系统引用计数和 MAPI dll 初始化全局数据。</span><span class="sxs-lookup"><span data-stu-id="d0ad6-105">Increments the MAPI subsystem reference count and initializes global data for the MAPI DLL.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="d0ad6-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="d0ad6-106">Header file:</span></span>  <br/> |<span data-ttu-id="d0ad6-107">Mapix.h</span><span class="sxs-lookup"><span data-stu-id="d0ad6-107">Mapix.h</span></span>  <br/> |
|<span data-ttu-id="d0ad6-108">通过实现：</span><span class="sxs-lookup"><span data-stu-id="d0ad6-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="d0ad6-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="d0ad6-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="d0ad6-110">调用：</span><span class="sxs-lookup"><span data-stu-id="d0ad6-110">Called by:</span></span>  <br/> |<span data-ttu-id="d0ad6-111">客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="d0ad6-111">Client applications</span></span>  <br/> |
   
```cpp
HRESULT MAPIInitialize(
  LPVOID lpMapiInit
);
```

## <a name="parameters"></a><span data-ttu-id="d0ad6-112">参数</span><span class="sxs-lookup"><span data-stu-id="d0ad6-112">Parameters</span></span>

 <span data-ttu-id="d0ad6-113">_lpMapiInit_</span><span class="sxs-lookup"><span data-stu-id="d0ad6-113">_lpMapiInit_</span></span>
  
> <span data-ttu-id="d0ad6-114">[in]指向[MAPIINIT_0](mapiinit_0.md)结构。</span><span class="sxs-lookup"><span data-stu-id="d0ad6-114">[in] Pointer to a [MAPIINIT_0](mapiinit_0.md) structure.</span></span> <span data-ttu-id="d0ad6-115">_LpMapiInit_参数可以设置为 NULL。</span><span class="sxs-lookup"><span data-stu-id="d0ad6-115">The  _lpMapiInit_ parameter can be set to NULL.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="d0ad6-116">返回值</span><span class="sxs-lookup"><span data-stu-id="d0ad6-116">Return value</span></span>

<span data-ttu-id="d0ad6-117">S_OK</span><span class="sxs-lookup"><span data-stu-id="d0ad6-117">S_OK</span></span> 
  
> <span data-ttu-id="d0ad6-118">MAPI 子系统初始化成功。</span><span class="sxs-lookup"><span data-stu-id="d0ad6-118">The MAPI subsystem was initialized successfully.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="d0ad6-119">说明</span><span class="sxs-lookup"><span data-stu-id="d0ad6-119">Remarks</span></span>

<span data-ttu-id="d0ad6-120">MAPI 引用计数 MAPI 子系统和[MAPIUninitialize](mapiuninitialize.md)函数递减**MAPIInitialize**函数增量内部引用计数。</span><span class="sxs-lookup"><span data-stu-id="d0ad6-120">The **MAPIInitialize** function increments the MAPI reference count for the MAPI subsystem, and the [MAPIUninitialize](mapiuninitialize.md) function decrements the internal reference count.</span></span> <span data-ttu-id="d0ad6-121">因此，一个函数调用次数必须等于到其他呼叫的数目。</span><span class="sxs-lookup"><span data-stu-id="d0ad6-121">Thus, the number of calls to one function must equal the number of calls to the other.</span></span> <span data-ttu-id="d0ad6-122">如果未以前初始化 MAPI， **MAPIInitialize**返回 S_OK。</span><span class="sxs-lookup"><span data-stu-id="d0ad6-122">**MAPIInitialize** returns S_OK if MAPI has not been previously initialized.</span></span> 
  
<span data-ttu-id="d0ad6-123">客户端或服务提供程序必须在进行任何其他 MAPI 调用之前调用**MAPIInitialize** 。</span><span class="sxs-lookup"><span data-stu-id="d0ad6-123">A client or service provider must call **MAPIInitialize** before making any other MAPI call.</span></span> <span data-ttu-id="d0ad6-124">否则，使客户端或服务提供程序调用 MAPI_E_NOT_INITIALIZED 值返回。</span><span class="sxs-lookup"><span data-stu-id="d0ad6-124">Failure to do so causes client or service provider calls to return the MAPI_E_NOT_INITIALIZED value.</span></span> 
  
<span data-ttu-id="d0ad6-125">从多线程应用程序中调用**MAPIInitialize**时, 将_lpMapiInit_参数设置为[MAPIINIT_0](mapiinit_0.md)结构的声明，如下所示：</span><span class="sxs-lookup"><span data-stu-id="d0ad6-125">When calling **MAPIInitialize** from a multithreaded application, set the  _lpMapiInit_ parameter to a [MAPIINIT_0](mapiinit_0.md) structure that is declared as follows:</span></span> 
  
 <span data-ttu-id="d0ad6-126">**MAPIINIT_0**MAPIINIT = {0，MAPI_MULTITHREAD_NOTIFICATIONS}</span><span class="sxs-lookup"><span data-stu-id="d0ad6-126">**MAPIINIT_0** MAPIINIT= { 0, MAPI_MULTITHREAD_NOTIFICATIONS}</span></span> 
  
<span data-ttu-id="d0ad6-127">和呼叫：</span><span class="sxs-lookup"><span data-stu-id="d0ad6-127">and call:</span></span> 
  
 <span data-ttu-id="d0ad6-128">**MAPIInitialize**(&amp;MAPIINIT);</span><span class="sxs-lookup"><span data-stu-id="d0ad6-128">**MAPIInitialize** (&amp;MAPIINIT);</span></span> 
  
<span data-ttu-id="d0ad6-129">在声明此结构，MAPI 将创建一个单独的线程，来处理通知窗口中，将一直为零属于 initialize 引用计数。</span><span class="sxs-lookup"><span data-stu-id="d0ad6-129">When this structure is declared, MAPI creates a separate thread to handle the notification window, which continues until the initialize reference count falls to zero.</span></span> <span data-ttu-id="d0ad6-130">Windows 服务，必须设置所指的_lpMapiInit_到 MAPI_NT_SERVICE **MAPIINIT_0**结构的**ulflags**成员。</span><span class="sxs-lookup"><span data-stu-id="d0ad6-130">A Windows service must set the **ulflags** member of the **MAPIINIT_0** structure pointed to by  _lpMapiInit_ to MAPI_NT_SERVICE.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="d0ad6-131">不能调用**MAPIInitialize**或从**MAPIUninitialize** Win32 **DllMain**函数或创建或终止线程的任何其他函数中。</span><span class="sxs-lookup"><span data-stu-id="d0ad6-131">You cannot call **MAPIInitialize** or **MAPIUninitialize** from within a Win32 **DllMain** function or any other function that creates or terminates threads.</span></span> <span data-ttu-id="d0ad6-132">有关详细信息，请参阅[使用线程安全对象](using-thread-safe-objects.md)。</span><span class="sxs-lookup"><span data-stu-id="d0ad6-132">For more information, see [Using Thread-Safe Objects](using-thread-safe-objects.md).</span></span> 
  
 <span data-ttu-id="d0ad6-133">**MAPIInitialize**不返回任何扩展的错误的信息。</span><span class="sxs-lookup"><span data-stu-id="d0ad6-133">**MAPIInitialize** does not return any extended error information.</span></span> <span data-ttu-id="d0ad6-134">与大多数其他 MAPI 调用，其返回值的含义严格定义对应于初始化失败的特定步骤：</span><span class="sxs-lookup"><span data-stu-id="d0ad6-134">Unlike most other MAPI calls, the meanings of its return values are strictly defined to correspond to the particular step of the initialization that failed:</span></span> 
  
1. <span data-ttu-id="d0ad6-135">检查参数和标志。</span><span class="sxs-lookup"><span data-stu-id="d0ad6-135">Checks parameters and flags.</span></span>
    
    <span data-ttu-id="d0ad6-136">MAPI_E_INVALID_PARAMETER 或 MAPI_E_UNKNOWN_FLAGS。</span><span class="sxs-lookup"><span data-stu-id="d0ad6-136">MAPI_E_INVALID_PARAMETER or MAPI_E_UNKNOWN_FLAGS.</span></span> <span data-ttu-id="d0ad6-137">呼叫者传递参数无效或标志。</span><span class="sxs-lookup"><span data-stu-id="d0ad6-137">Caller passed invalid parameter or flag.</span></span>
    
2. <span data-ttu-id="d0ad6-138">初始化 MAPI 所需的注册表项，并确认操作系统的类型。</span><span class="sxs-lookup"><span data-stu-id="d0ad6-138">Initializes registry keys required by MAPI and confirms the type of operating system.</span></span> <span data-ttu-id="d0ad6-139">此步骤只发生如果客户端进程作为下 Windows 服务运行，并将 MAPI_NT 服务标志设置**MAPIINIT_0**结构中。</span><span class="sxs-lookup"><span data-stu-id="d0ad6-139">This step only happens if the client process is running as a service under Windows and sets the MAPI_NT SERVICE flag in the **MAPIINIT_0** structure.</span></span> 
    
    <span data-ttu-id="d0ad6-140">MAPI_E_TOO_COMPLEX。</span><span class="sxs-lookup"><span data-stu-id="d0ad6-140">MAPI_E_TOO_COMPLEX.</span></span> <span data-ttu-id="d0ad6-141">调用过程是一个 Windows 服务，并且无法初始化 MAPI 所需的注册表项。</span><span class="sxs-lookup"><span data-stu-id="d0ad6-141">The calling process is a Windows service and registry keys required by MAPI could not be initialized.</span></span> 
    
    <span data-ttu-id="d0ad6-142">其他信息可能会在应用程序事件日志中可用。</span><span class="sxs-lookup"><span data-stu-id="d0ad6-142">Additional information may be available in the application event log.</span></span>
    
3. <span data-ttu-id="d0ad6-143">检查 OLE，使用 MAPI 的兼容性，然后初始化 OLE。</span><span class="sxs-lookup"><span data-stu-id="d0ad6-143">Check for the compatibility of MAPI with OLE, then initialize OLE.</span></span>
    
1. <span data-ttu-id="d0ad6-144">MAPI 和 OLE 当前版本之间的兼容性检查。</span><span class="sxs-lookup"><span data-stu-id="d0ad6-144">Checks for compatibility between the current versions of OLE and MAPI.</span></span> 
    
    <span data-ttu-id="d0ad6-145">MAPI_E_VERSION。</span><span class="sxs-lookup"><span data-stu-id="d0ad6-145">MAPI_E_VERSION.</span></span> <span data-ttu-id="d0ad6-146">OLE 工作站上安装的版本不是与此版本的 MAPI 兼容的。</span><span class="sxs-lookup"><span data-stu-id="d0ad6-146">The version of OLE installed on the workstation is not compatible with this version of MAPI.</span></span>
    
2. <span data-ttu-id="d0ad6-147">初始化 OLE。</span><span class="sxs-lookup"><span data-stu-id="d0ad6-147">Initializes OLE.</span></span> 
    
    <span data-ttu-id="d0ad6-148">在此步骤仅，此函数可以返回未在此处列出的错误代码。</span><span class="sxs-lookup"><span data-stu-id="d0ad6-148">During this step only, this function can return an error code not listed here.</span></span> <span data-ttu-id="d0ad6-149">任何错误_未_列出此处应假定来自 OLE 函数**CoInitialize**。</span><span class="sxs-lookup"><span data-stu-id="d0ad6-149">Any error  _not_ listed here should be assumed to come from the OLE function **CoInitialize**.</span></span>
    
4. <span data-ttu-id="d0ad6-150">初始化每个过程的全局变量。</span><span class="sxs-lookup"><span data-stu-id="d0ad6-150">Initializes per-process global variables.</span></span>
    
    <span data-ttu-id="d0ad6-151">MAPI_E_SESSION_LIMIT。</span><span class="sxs-lookup"><span data-stu-id="d0ad6-151">MAPI_E_SESSION_LIMIT.</span></span> <span data-ttu-id="d0ad6-152">MAPI 将上下文设置特定于当前过程。</span><span class="sxs-lookup"><span data-stu-id="d0ad6-152">MAPI sets up context specific to the current process.</span></span> <span data-ttu-id="d0ad6-153">可能会失败或任何系统上 Win16 如果进程数超过特定数量，如果耗尽可用内存。</span><span class="sxs-lookup"><span data-stu-id="d0ad6-153">Failures may occur on Win16 if the number of processes exceeds a certain number, or on any system if available memory is exhausted.</span></span>
    
5. <span data-ttu-id="d0ad6-154">初始化共享所有进程的全局的变量。</span><span class="sxs-lookup"><span data-stu-id="d0ad6-154">Initializes shared global variables of all processes.</span></span>
    
    <span data-ttu-id="d0ad6-155">MAPI_E_NOT_ENOUGH_RESOURCES。</span><span class="sxs-lookup"><span data-stu-id="d0ad6-155">MAPI_E_NOT_ENOUGH_RESOURCES.</span></span> <span data-ttu-id="d0ad6-156">没有足够的系统资源已无法完成操作。</span><span class="sxs-lookup"><span data-stu-id="d0ad6-156">Not enough system resources were available to complete the operation.</span></span>
    
6. <span data-ttu-id="d0ad6-157">初始化通知引擎，创建其窗口和其线程，如果请求 MAPI_MULTITHREAD_NOTIFICATIONS 标志。</span><span class="sxs-lookup"><span data-stu-id="d0ad6-157">Initializes the notification engine, creates its window and its thread if requested by the MAPI_MULTITHREAD_NOTIFICATIONS flag.</span></span> 
    
    <span data-ttu-id="d0ad6-158">MAPI_E_INVALID_OBJECT。</span><span class="sxs-lookup"><span data-stu-id="d0ad6-158">MAPI_E_INVALID_OBJECT.</span></span> <span data-ttu-id="d0ad6-159">如果用完系统资源可能失败。</span><span class="sxs-lookup"><span data-stu-id="d0ad6-159">May fail if system resources are exhausted.</span></span> 
    
7. <span data-ttu-id="d0ad6-160">加载并初始化配置文件提供程序。</span><span class="sxs-lookup"><span data-stu-id="d0ad6-160">Loads and initializes the profile provider.</span></span> <span data-ttu-id="d0ad6-161">验证**MAPIInitialize**可以访问存储配置文件数据的注册表项。</span><span class="sxs-lookup"><span data-stu-id="d0ad6-161">Verifies that **MAPIInitialize** can access the registry key where profile data are stored.</span></span> 
    
    <span data-ttu-id="d0ad6-162">MAPI_E_NOT_INITIALIZED。</span><span class="sxs-lookup"><span data-stu-id="d0ad6-162">MAPI_E_NOT_INITIALIZED.</span></span> <span data-ttu-id="d0ad6-163">配置文件提供程序出错。</span><span class="sxs-lookup"><span data-stu-id="d0ad6-163">The profile provider has encountered an error.</span></span> 
    
## <a name="mfcmapi-reference"></a><span data-ttu-id="d0ad6-164">MFCMAPI 参考 （英文）</span><span class="sxs-lookup"><span data-stu-id="d0ad6-164">MFCMAPI reference</span></span>

<span data-ttu-id="d0ad6-165">MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="d0ad6-165">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="d0ad6-166">**文件**</span><span class="sxs-lookup"><span data-stu-id="d0ad6-166">**File**</span></span>|<span data-ttu-id="d0ad6-167">**函数**</span><span class="sxs-lookup"><span data-stu-id="d0ad6-167">**Function**</span></span>|<span data-ttu-id="d0ad6-168">**Comment**</span><span class="sxs-lookup"><span data-stu-id="d0ad6-168">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d0ad6-169">ContentsTableListCtrl.cpp</span><span class="sxs-lookup"><span data-stu-id="d0ad6-169">ContentsTableListCtrl.cpp</span></span>  <br/> ||<span data-ttu-id="d0ad6-170">MFCMAPI 使用**MAPIInitialize**方法在后台线程执行一些表处理初始化 MAPI。</span><span class="sxs-lookup"><span data-stu-id="d0ad6-170">MFCMAPI uses the **MAPIInitialize** method to initialize MAPI on a background thread to do some table processing.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="d0ad6-171">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d0ad6-171">See also</span></span>



[<span data-ttu-id="d0ad6-172">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="d0ad6-172">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

