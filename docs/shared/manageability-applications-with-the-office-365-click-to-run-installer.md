---
title: 将可管理性应用程序与 Microsoft 365 应用程序集成即点即用安装程序
manager: lindalu
ms.date: 09/28/2020
ms.audience: ITPro
localization_priority: Normal
ms.assetid: c0fa8fed-1585-4566-a9be-ef6d6d1b4ce8
description: 了解如何将 Microsoft 365 应用即点即用安装程序与软件管理解决方案集成。
ms.openlocfilehash: eccd634f7906acf25b521ed2deb456ca914f37da
ms.sourcegitcommit: c8c51bd3f51c0a59fe44c014c8e56f1ba7c7aa03
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/28/2020
ms.locfileid: "48297312"
---
# <a name="integrating-manageability-applications-with-microsoft-365-apps-click-to-run-installer"></a><span data-ttu-id="55143-103">将可管理性应用程序与 Microsoft 365 应用程序集成即点即用安装程序</span><span class="sxs-lookup"><span data-stu-id="55143-103">Integrating manageability applications with Microsoft 365 Apps Click-to-Run installer</span></span>

<span data-ttu-id="55143-104">了解如何将 Microsoft 365 应用即点即用安装程序与软件管理解决方案集成。</span><span class="sxs-lookup"><span data-stu-id="55143-104">Learn how to integrate the Microsoft 365 Apps Click-to-Run installer with a software management solution.</span></span>
  
<span data-ttu-id="55143-105">Microsoft 365 应用程序即点即用安装程序提供了一个 COM 接口，使 IT 专业人员和软件管理解决方案可以编程方式控制更新管理。</span><span class="sxs-lookup"><span data-stu-id="55143-105">The Microsoft 365 Apps Click-to-Run installer provides a COM interface that allows IT Professionals and software management solutions programmatic control over update management.</span></span> <span data-ttu-id="55143-106">此接口提供了 Office 部署工具所提供功能之外的其他管理功能。</span><span class="sxs-lookup"><span data-stu-id="55143-106">This interface provides additional management capabilities beyond what is provided by the Office Deployment Tool.</span></span>
  
> [!NOTE]
> <span data-ttu-id="55143-107">本文适用于使用即点即用安装程序的 Office 应用程序。</span><span class="sxs-lookup"><span data-stu-id="55143-107">This article applies to Office apps that use the Click-to-Run installer.</span></span> 
  
## <a name="integrating-with-the-click-to-run"></a><span data-ttu-id="55143-108">与即点即用集成</span><span class="sxs-lookup"><span data-stu-id="55143-108">Integrating with the Click-to-Run</span></span>

<span data-ttu-id="55143-109">若要使用此接口，可管理性应用程序将调用 COM 接口，并调用与即点即用安装服务直接通信的公开 Api。</span><span class="sxs-lookup"><span data-stu-id="55143-109">To use this interface, a manageability application invokes the COM interface and calls exposed APIs that communicate directly with the Click-to-Run installation service.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="55143-110">可以通过命令行运行 Office 即点即用安装程序，这些参数可以控制针对即点即用的 [Office 部署工具](https://docs.microsoft.com/DeployOffice/overview-office-deployment-tool)中所述的行为。</span><span class="sxs-lookup"><span data-stu-id="55143-110">The Office Click-to-Run installer can be run from the command-line with parameters that can control the behavior, as documented in [Office Deployment Tool for Click-to-Run](https://docs.microsoft.com/DeployOffice/overview-office-deployment-tool).</span></span> 
  
<span data-ttu-id="55143-111">**以下是 COM 接口的概念图**</span><span class="sxs-lookup"><span data-stu-id="55143-111">**Following is a conceptual diagram of the COM interface**</span></span>

<span data-ttu-id="55143-112">![在 Office 单击即运行安装程序上使用 COM 接口的图。](media/e7ac2523-e67b-4a44-ae67-c048709f872a.png "在 Office 即点即用安装程序上使用 COM 接口的关系图")</span><span class="sxs-lookup"><span data-stu-id="55143-112">![A diagram of using the COM interface on  the Office Click-To-Run installer.](media/e7ac2523-e67b-4a44-ae67-c048709f872a.png "A diagram of using the COM interface on  the Office Click-To-Run installer")</span></span>
  
<span data-ttu-id="55143-113">Microsoft 365 应用程序即点即用安装程序实现基于 COM 的接口， **IUpdateNotify** 注册到 CLSID **CLSID_UpdateNotifyObject**。</span><span class="sxs-lookup"><span data-stu-id="55143-113">The Microsoft 365 Apps Click-to-Run installer implements a COM-based interface, **IUpdateNotify** registered to CLSID **CLSID_UpdateNotifyObject**.</span></span>
  
<span data-ttu-id="55143-114">可以按如下方式调用此接口：</span><span class="sxs-lookup"><span data-stu-id="55143-114">This interface can be invoked as follows:</span></span>
  
```cpp
hr = CoCreateInstance(CLSID_UpdateNotifyObject, NULL, CLSCTX_ALL,
       IID_IUpdateNotify, 
      (void **)&p); 
```

<span data-ttu-id="55143-115">仅当呼叫者在提升的权限下运行时，调用才会成功，因为必须使用提升的权限运行即点即用安装程序。</span><span class="sxs-lookup"><span data-stu-id="55143-115">The call will only succeed if the caller is running under elevated privileges, as the Click-to-Run installation program must be run with elevated privileges.</span></span>
  
<span data-ttu-id="55143-116">**IUpdateNotify** COM 接口公开三个异步功能，负责验证命令和参数，并使用即点即用安装服务执行计划的运行。</span><span class="sxs-lookup"><span data-stu-id="55143-116">The **IUpdateNotify** COM interface exposes three asynchronous functions responsible for validating the commands and parameters and scheduling execution with the Click-to-Run installation service.</span></span> 
  
```cpp
HRESULT Download([in] LPWSTR pcwszParameters) // Download update content.
HRESULT Apply([in] LPWSTR pcwszParameters) // Apply update content.
HRESULT Cancel() // Cancel the download action.

```

<span data-ttu-id="55143-117">" **状态**" 方法可用于获取有关上次执行的命令状态的信息，或当前正在执行的命令的状态 (即 "成功"、"失败"、"详细" 错误代码) 。</span><span class="sxs-lookup"><span data-stu-id="55143-117">A forth method, **Status**, can be used to get information about the status of the last executed command or the status of the currently executing command (i.e. success, failure, detailed error codes).</span></span>
  
```cpp
HRESULT status([out] _UPDATE_STATUS_REPORT* pUpdateStatusReport) // Get status of current action. 
typedef struct _UPDATE_STATUS_REPORT  
{  
UPDATE_STATUS status;  
UINT error; 
BSTR contentid;  
} UPDATE_STATUS_REPORT;

```

<span data-ttu-id="55143-118">在其生命周期中，即点即用安装服务可能处于运行状态的四种状态，在此期间可以调用 **IUpdateNotify** 方法;重新启动、空闲、下载和应用。</span><span class="sxs-lookup"><span data-stu-id="55143-118">There are four states that the Click-to-Run installation service may be in during its lifecycle, during which **IUpdateNotify** methods may be called; Rebooting, Idle, Downloading and Applying.</span></span> 
  
<span data-ttu-id="55143-119">**以下是 COM 接口状态机关系图**</span><span class="sxs-lookup"><span data-stu-id="55143-119">**Following is the COM Interface State Machine diagram**</span></span>

<span data-ttu-id="55143-120">![COM 接口的状态图。](media/a409003e-6876-4ab3-bb4c-cd0c0fed5cbb.png "COM 接口的状态图")</span><span class="sxs-lookup"><span data-stu-id="55143-120">![A state diagram for the COM interface.](media/a409003e-6876-4ab3-bb4c-cd0c0fed5cbb.png "A state diagram for the COM interface")</span></span>
  
> [!NOTE]
> <span data-ttu-id="55143-121">**重新启动**：当计算机启动时，即点即用安装程序服务不可用时的一段时间。</span><span class="sxs-lookup"><span data-stu-id="55143-121">**Rebooting**: When the machine is booting there is a period of time when the Click-to-Run installer service is not available.</span></span> <span data-ttu-id="55143-122">重新启动后，对 Status 方法的成功调用将返回 eUPDATE_UNKNOWN。</span><span class="sxs-lookup"><span data-stu-id="55143-122">A successful call to the Status method after a reboot will return eUPDATE_UNKNOWN.</span></span> 
  
<span data-ttu-id="55143-123">**空闲：** 当即点即用安装程序处于空闲状态时，您可以调用：</span><span class="sxs-lookup"><span data-stu-id="55143-123">**Idle:** When the Click-to-Run installer is in the idle state, you can call:</span></span> 
  
- <span data-ttu-id="55143-124">**应用**：安装以前下载的内容。</span><span class="sxs-lookup"><span data-stu-id="55143-124">**Apply**: Install previously downloaded content.</span></span>
    
- <span data-ttu-id="55143-125">**取消**：返回  `0x800000e` "在意外的时间调用方法"。</span><span class="sxs-lookup"><span data-stu-id="55143-125">**Cancel**: Returns  `0x800000e`, "A method was called at an unexpected time."</span></span>
    
- <span data-ttu-id="55143-126">**下载**：将新内容下载到客户端，以供以后安装。</span><span class="sxs-lookup"><span data-stu-id="55143-126">**Download**: Downloads new content to the client for later installation.</span></span>
    
- <span data-ttu-id="55143-127">**Status**：返回上次完成的操作的结果，如果操作在失败时结束，则返回错误消息。</span><span class="sxs-lookup"><span data-stu-id="55143-127">**Status**: Returns the result of the last completed action, or an error message if the action ended in failure.</span></span> <span data-ttu-id="55143-128">如果没有上一个操作， **状态** 将返回  `eUPDATE_UNKNOWN` 。</span><span class="sxs-lookup"><span data-stu-id="55143-128">If there is no previous action, **Status** returns  `eUPDATE_UNKNOWN`.</span></span>
    
<span data-ttu-id="55143-129">**下载：** 当即点即用安装程序处于下载状态时，您可以调用：</span><span class="sxs-lookup"><span data-stu-id="55143-129">**Downloading:** When the Click-to-Run installer is in the downloading state, you can call:</span></span> 
  
- <span data-ttu-id="55143-130">**应用**：返回值**HRESULT**为 `0x800000e` "在意外的时间调用了某个方法的 HRESULT"。</span><span class="sxs-lookup"><span data-stu-id="55143-130">**Apply**: Returns an **HRESULT** with the value  `0x800000e`, "A method was called at an unexpected time."</span></span>
    
- <span data-ttu-id="55143-131">**取消**：停止下载并删除部分下载的内容。</span><span class="sxs-lookup"><span data-stu-id="55143-131">**Cancel**: Stops the download and removes the partially downloaded content.</span></span>
    
- <span data-ttu-id="55143-132">**下载**：返回值**HRESULT**为 `0x800000e` "在意外时间调用方法" 的 HRESULT。</span><span class="sxs-lookup"><span data-stu-id="55143-132">**Download**: Returns an **HRESULT** with the value  `0x800000e`, "A method was called at an unexpected time."</span></span> 
    
- <span data-ttu-id="55143-133">**Status**：返回 **DOWNLOAD_WIP** 以指示正在进行下载工作。</span><span class="sxs-lookup"><span data-stu-id="55143-133">**Status**: Returns **DOWNLOAD_WIP** to indicate that download work is in progress.</span></span> 
    
<span data-ttu-id="55143-134">**应用：** 当即点即用安装程序安装之前的下载内容的过程中：</span><span class="sxs-lookup"><span data-stu-id="55143-134">**Applying:** When the Click-to-Run installer is in the process of installing previously download content:</span></span> 
  
- <span data-ttu-id="55143-135">**应用**：返回值**HRESULT**为 `0x800000e` "在意外的时间调用了某个方法的 HRESULT"。</span><span class="sxs-lookup"><span data-stu-id="55143-135">**Apply**: Returns an **HRESULT** with the value  `0x800000e`, "A method was called at an unexpected time."</span></span>
    
- <span data-ttu-id="55143-136">**取消**：返回  `0x800000e` ，无法取消应用操作。</span><span class="sxs-lookup"><span data-stu-id="55143-136">**Cancel**: Returns  `0x800000e`, the Apply action cannot be canceled.</span></span>
    
- <span data-ttu-id="55143-137">**下载**：返回值**HRESULT**为 `0x800000e` "在意外时间调用方法" 的 HRESULT。</span><span class="sxs-lookup"><span data-stu-id="55143-137">**Download**: Returns an **HRESULT** with the value  `0x800000e`, "A method was called at an unexpected time."</span></span> 
    
- <span data-ttu-id="55143-138">**Status**：返回 **APPLY_WIP** 以指示应用工作正在进行中。</span><span class="sxs-lookup"><span data-stu-id="55143-138">**Status**: Returns **APPLY_WIP** to indicate that apply work is in progress.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="55143-139">由于 OfficeC2RCOM 是 COM + 服务并且已动态加载，因此您需要在每次调用此类上的方法时调用 **CoCreateInstance** ，以确保获得预期的结果。</span><span class="sxs-lookup"><span data-stu-id="55143-139">Since OfficeC2RCOM is a COM+ service and is dynamically loaded, you need to call **CoCreateInstance** every time you call a method on this class to ensure that you get the expected result.</span></span> <span data-ttu-id="55143-140">如果需要，COM + 服务将处理创建新实例的情况。</span><span class="sxs-lookup"><span data-stu-id="55143-140">The COM+ service will handle creating a new instance if necessary.</span></span> <span data-ttu-id="55143-141">当首次调用其中一种方法时，COM + 将加载 **IUpdateNotify** 对象并在其中一个 dllhost.exe 实例中运行它。</span><span class="sxs-lookup"><span data-stu-id="55143-141">When one of the methods is called for the first time, COM+ will load the **IUpdateNotify** object and run it within one of the dllhost.exe instances.</span></span> <span data-ttu-id="55143-142">新对象将保持活动状态大约3分钟，并处于空闲状态。</span><span class="sxs-lookup"><span data-stu-id="55143-142">The new object will stay active for about 3 minutes in idle.</span></span> <span data-ttu-id="55143-143">如果在最后一次呼叫的三分钟内进行后续调用，则 **IUpdateNotify** 对象将保持加载，并且不会创建新的实例。</span><span class="sxs-lookup"><span data-stu-id="55143-143">If a subsequent call is made within three minutes of the last call, the **IUpdateNotify** object will remain loaded and a new instance is not created.</span></span> <span data-ttu-id="55143-144">如果在三分钟内未进行任何调用，则将卸载 IUpdateNotify 对象，并在下一次调用时创建一个新的 **IUpdateNotify** 对象。</span><span class="sxs-lookup"><span data-stu-id="55143-144">If no call is made within three minutes, the IUpdateNotify object will be unloaded and a new **IUpdateNotify** object will be created when the next call is made.</span></span> 
  
## <a name="click-to-run-installer-com-api-reference-guide"></a><span data-ttu-id="55143-145">即点即用安装程序 COM API 参考指南</span><span class="sxs-lookup"><span data-stu-id="55143-145">Click-to-Run installer COM API reference guide</span></span>

<span data-ttu-id="55143-146">在下面的 API 参考文档中：</span><span class="sxs-lookup"><span data-stu-id="55143-146">In the following API reference documentation:</span></span>
  
- <span data-ttu-id="55143-147">参数的键/值对格式由空格分隔。</span><span class="sxs-lookup"><span data-stu-id="55143-147">Parameters are in a key/value pair format separated by a space.</span></span>
    
- <span data-ttu-id="55143-148">参数不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="55143-148">The parameters are not case-sensitive.</span></span>
    
- <span data-ttu-id="55143-149">有可用的带有文档 [的参数的列表](https://blogs.technet.microsoft.com/odsupport/2014/03/03/the-new-update-now-feature-for-office-2013-click-to-run-for-office365-and-its-associated-command-line-and-switches/) 。</span><span class="sxs-lookup"><span data-stu-id="55143-149">There is a [list of parameters](https://blogs.technet.microsoft.com/odsupport/2014/03/03/the-new-update-now-feature-for-office-2013-click-to-run-for-office365-and-its-associated-command-line-and-switches/) with documentation available.</span></span> 
    
- <span data-ttu-id="55143-150">IUpdateNotify2 接口摘要现已包括在内。</span><span class="sxs-lookup"><span data-stu-id="55143-150">Summary of IUpdateNotify2 interface is now included.</span></span>
    
### <a name="apply"></a><span data-ttu-id="55143-151">应用</span><span class="sxs-lookup"><span data-stu-id="55143-151">Apply</span></span>

```cpp
HRESULT Apply([in] LPWSTR pcwszParameters) // Apply update content.
```

#### <a name="parameters"></a><span data-ttu-id="55143-152">参数</span><span class="sxs-lookup"><span data-stu-id="55143-152">Parameters</span></span>

-  <span data-ttu-id="55143-153">_displaylevel_： **true** 以在更新过程中显示安装状态（包括错误）; **如果为 false** ，则在更新过程中隐藏安装状态，包括错误。</span><span class="sxs-lookup"><span data-stu-id="55143-153">_displaylevel_: **true** to show the installation status, including errors, during the update process; **false** to hide the installation status, including errors, during the update process.</span></span> <span data-ttu-id="55143-154">默认值为 **false**。</span><span class="sxs-lookup"><span data-stu-id="55143-154">The default is **false**.</span></span>
    
-  <span data-ttu-id="55143-155">_forceappshutdown_： **True** 以强制 Office 应用程序在触发 **应用** 程序操作时立即关闭; **假** 如果有任何 Office 应用程序在运行时失败。</span><span class="sxs-lookup"><span data-stu-id="55143-155">_forceappshutdown_: **true** to force Office applications to shut down immediately when the **Apply** action is triggered; **false** to fail if any Office applications are running.</span></span> <span data-ttu-id="55143-156">默认值为 **false**。</span><span class="sxs-lookup"><span data-stu-id="55143-156">The default is **false**.</span></span> <span data-ttu-id="55143-157">有关详细信息，请参阅 " [备注](#bk_ApplyRemark) "。</span><span class="sxs-lookup"><span data-stu-id="55143-157">See [Remarks](#bk_ApplyRemark) for more information.</span></span> 
    
  <span data-ttu-id="55143-158">如果在触发 **应用** 操作时任何 Office 应用程序正在运行，则 **apply** 操作通常会失败。</span><span class="sxs-lookup"><span data-stu-id="55143-158">If any Office application is running when the **Apply** action is triggered, the **Apply** action will usually fail.</span></span> <span data-ttu-id="55143-159">传递  `forceappshutdown=true` 给 **Apply** 方法将导致 **OfficeClickToRun** 服务立即关闭应用程序并应用更新。</span><span class="sxs-lookup"><span data-stu-id="55143-159">Passing  `forceappshutdown=true` to the **Apply** method will cause the **OfficeClickToRun** service to immediately shut down the applications and apply the update.</span></span> <span data-ttu-id="55143-160">在这种情况下，用户可能会遇到数据丢失。</span><span class="sxs-lookup"><span data-stu-id="55143-160">The user may experience data loss in this case.</span></span> 
    
#### <a name="return-results"></a><span data-ttu-id="55143-161">返回结果</span><span class="sxs-lookup"><span data-stu-id="55143-161">Return results</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="55143-162">**S_OK**</span><span class="sxs-lookup"><span data-stu-id="55143-162">**S_OK**</span></span> <br/> |<span data-ttu-id="55143-163">操作已成功提交到即点即用服务以执行。</span><span class="sxs-lookup"><span data-stu-id="55143-163">Action was successfully submitted to the Click-To-Run service for execution.</span></span>  <br/> |
|<span data-ttu-id="55143-164">**E_ACCESSDENIED**</span><span class="sxs-lookup"><span data-stu-id="55143-164">**E_ACCESSDENIED**</span></span> <br/> |<span data-ttu-id="55143-165">呼叫者未使用提升的权限运行。</span><span class="sxs-lookup"><span data-stu-id="55143-165">The caller is not running with elevated privileges.</span></span>  <br/> |
|<span data-ttu-id="55143-166">**E_INVALIDARG**</span><span class="sxs-lookup"><span data-stu-id="55143-166">**E_INVALIDARG**</span></span> <br/> |<span data-ttu-id="55143-167">传递的参数无效。</span><span class="sxs-lookup"><span data-stu-id="55143-167">Invalid parameters were passed.</span></span>  <br/> |
|<span data-ttu-id="55143-168">**E_ILLEGAL_METHOD_CALL**</span><span class="sxs-lookup"><span data-stu-id="55143-168">**E_ILLEGAL_METHOD_CALL**</span></span> <br/> |<span data-ttu-id="55143-169">此时不允许执行操作。</span><span class="sxs-lookup"><span data-stu-id="55143-169">Action is not allowed at this time.</span></span> <span data-ttu-id="55143-170">有关详细信息，请参阅 " [备注](#bk_ApplyRemark) "。</span><span class="sxs-lookup"><span data-stu-id="55143-170">See [Remarks](#bk_ApplyRemark) for more information.</span></span>  <br/> |

<a name="bk_ApplyRemark"></a>

#### <a name="remarks"></a><span data-ttu-id="55143-171">说明</span><span class="sxs-lookup"><span data-stu-id="55143-171">Remarks</span></span>

- <span data-ttu-id="55143-172">如果在触发 **应用** 操作时任何 Office 应用程序正在运行，则 **应用** 操作将失败。</span><span class="sxs-lookup"><span data-stu-id="55143-172">If any Office application is running when the **Apply** action is triggered, the **Apply** action will fail.</span></span> <span data-ttu-id="55143-173">传递  `forceappshutdown=true` 给 **Apply** 方法将导致 **OfficeClickToRun** 服务立即关闭任何正在运行的 Office 应用程序并应用更新。</span><span class="sxs-lookup"><span data-stu-id="55143-173">Passing  `forceappshutdown=true` to the **Apply** method will cause the **OfficeClickToRun** service to immediately shut down any Office applications that are running and apply the update.</span></span> <span data-ttu-id="55143-174">用户可能会遇到数据，因为不提示他们保存对打开文档所做的更改。。</span><span class="sxs-lookup"><span data-stu-id="55143-174">The user may experience data as they are not prompted to save changes to open documents..</span></span> 
    
- <span data-ttu-id="55143-175">仅当 COM 状态为以下情况之一时，才能触发此操作：</span><span class="sxs-lookup"><span data-stu-id="55143-175">This action can only be triggered when the COM status is one of the following:</span></span> 
    
  - <span data-ttu-id="55143-176">**eUPDATE_UNKNOWN**</span><span class="sxs-lookup"><span data-stu-id="55143-176">**eUPDATE_UNKNOWN**</span></span>
    
  - <span data-ttu-id="55143-177">**eDOWNLOAD_CANCELLED**</span><span class="sxs-lookup"><span data-stu-id="55143-177">**eDOWNLOAD_CANCELLED**</span></span>
    
  - <span data-ttu-id="55143-178">**eDOWNLOAD_FAILED**</span><span class="sxs-lookup"><span data-stu-id="55143-178">**eDOWNLOAD_FAILED**</span></span>
    
  - <span data-ttu-id="55143-179">**eDOWNLOAD_SUCCEEDED**</span><span class="sxs-lookup"><span data-stu-id="55143-179">**eDOWNLOAD_SUCCEEDED**</span></span>
    
  - <span data-ttu-id="55143-180">**eAPPLY_SUCCEEDED**</span><span class="sxs-lookup"><span data-stu-id="55143-180">**eAPPLY_SUCCEEDED**</span></span>
    
  - <span data-ttu-id="55143-181">**eAPPLY_FAILED**</span><span class="sxs-lookup"><span data-stu-id="55143-181">**eAPPLY_FAILED**</span></span>
    
- <span data-ttu-id="55143-182">如果在不下载内容的情况下调用 **Apply** 方法，则 **Apply** 方法将报告 **成功** ，因为它检测到什么内容未成功应用并已完成 **应用** 过程。</span><span class="sxs-lookup"><span data-stu-id="55143-182">If you call the **Apply** method without previously downloading content, the **Apply** method will report **Succeeded** as it detected nothing to apply and completed the **Apply** process successfully.</span></span> 
    
### <a name="cancel"></a><span data-ttu-id="55143-183">取消</span><span class="sxs-lookup"><span data-stu-id="55143-183">Cancel</span></span>

```cpp
HRESULT Cancel() // Cancel the download action.
```

#### <a name="return-results"></a><span data-ttu-id="55143-184">返回结果</span><span class="sxs-lookup"><span data-stu-id="55143-184">Return results</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="55143-185">S_OK</span><span class="sxs-lookup"><span data-stu-id="55143-185">S_OK</span></span>  <br/> |<span data-ttu-id="55143-186">操作已成功提交到即点即用服务以执行。</span><span class="sxs-lookup"><span data-stu-id="55143-186">Action was successfully submitted to the Click-to-Run service for execution.</span></span>  <br/> |
|<span data-ttu-id="55143-187">E_ILLEGAL_METHOD_CALL</span><span class="sxs-lookup"><span data-stu-id="55143-187">E_ILLEGAL_METHOD_CALL</span></span>  <br/> |<span data-ttu-id="55143-188">此时不允许执行操作。</span><span class="sxs-lookup"><span data-stu-id="55143-188">Action is not allowed at this time.</span></span> <span data-ttu-id="55143-189">有关详细信息，请参阅 " [备注](#bk_CancelRemarks) " 部分</span><span class="sxs-lookup"><span data-stu-id="55143-189">See the [Remarks](#bk_CancelRemarks) section for more information</span></span>  <br/> |

<a name="bk_CancelRemarks"></a>

#### <a name="remarks"></a><span data-ttu-id="55143-190">说明</span><span class="sxs-lookup"><span data-stu-id="55143-190">Remarks</span></span>

- <span data-ttu-id="55143-191">仅当 COM 状态 id **eDOWNLOAD_WIP**时，才能触发此方法。</span><span class="sxs-lookup"><span data-stu-id="55143-191">This method can only be triggered when the COM status id **eDOWNLOAD_WIP**.</span></span> <span data-ttu-id="55143-192">它将尝试取消当前的下载操作。</span><span class="sxs-lookup"><span data-stu-id="55143-192">It will attempt to cancel the current download action.</span></span> <span data-ttu-id="55143-193">COM 状态将更改为 " **eDOWNLOAD_CANCELLING** "，并最终更改为 " **eDOWNLOAD_CANCELED**"。</span><span class="sxs-lookup"><span data-stu-id="55143-193">The COM status will change to **eDOWNLOAD_CANCELLING** and eventually change to **eDOWNLOAD_CANCELED**.</span></span> <span data-ttu-id="55143-194">如果在任何其他时间触发，COM 状态将返回 **E_ILLEGAL_METHOD_CALL** 。</span><span class="sxs-lookup"><span data-stu-id="55143-194">The COM status will return **E_ILLEGAL_METHOD_CALL** if triggered at any other time.</span></span> 
    
### <a name="download"></a><span data-ttu-id="55143-195">下载</span><span class="sxs-lookup"><span data-stu-id="55143-195">Download</span></span>

```cpp
HRESULT Download([in] LPWSTR pcwszParameters) // Download update content.
```

#### <a name="parameters"></a><span data-ttu-id="55143-196">参数</span><span class="sxs-lookup"><span data-stu-id="55143-196">Parameters</span></span>

-  <span data-ttu-id="55143-197">_displaylevel_： **true** 以在更新过程中显示安装状态（包括错误）; **如果为 false** ，则在更新过程中隐藏安装状态，包括错误。</span><span class="sxs-lookup"><span data-stu-id="55143-197">_displaylevel_: **true** to show the installation status, including errors, during the update process; **false** to hide the installation status, including errors, during the update process.</span></span> <span data-ttu-id="55143-198">默认值为 **false**。</span><span class="sxs-lookup"><span data-stu-id="55143-198">The default is **false**.</span></span>
    
-  <span data-ttu-id="55143-199">_updatebaseurl_：指向备用下载源的 URL。</span><span class="sxs-lookup"><span data-stu-id="55143-199">_updatebaseurl_: URL to the alternate download source.</span></span>
    
-  <span data-ttu-id="55143-200">_updatetoversion_：将 Office 更新到的版本。</span><span class="sxs-lookup"><span data-stu-id="55143-200">_updatetoversion_: The version to update Office to.</span></span> <span data-ttu-id="55143-201">如果要更新到比当前安装的版本更旧的版本，请定义此参数。</span><span class="sxs-lookup"><span data-stu-id="55143-201">Define this parameter if you want to update to an older version than the version that is currently installed.</span></span>
    
-  <span data-ttu-id="55143-202">_downloadsource_：自定义 **IBACKGROUNDCOPYMANAGER** 实现 (BITS 管理器的 CLSID) 。</span><span class="sxs-lookup"><span data-stu-id="55143-202">_downloadsource_: CLSID of the customized **IBackgroundCopyManager** implementation (BITS manager).</span></span> 
    
-  <span data-ttu-id="55143-203">_contentid_：标识要通过自定义的 BITS 管理器从内容服务器下载的内容。</span><span class="sxs-lookup"><span data-stu-id="55143-203">_contentid_: Identifies the content to download from the content server through the customized BITS manager.</span></span> <span data-ttu-id="55143-204">此值通过 BITS 接口传递以用于解释。</span><span class="sxs-lookup"><span data-stu-id="55143-204">This value is passed through the BITS interface for interpretation.</span></span>
    
#### <a name="return-results"></a><span data-ttu-id="55143-205">返回结果</span><span class="sxs-lookup"><span data-stu-id="55143-205">Return results</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="55143-206">**S_OK**</span><span class="sxs-lookup"><span data-stu-id="55143-206">**S_OK**</span></span> <br/> |<span data-ttu-id="55143-207">操作已成功提交到即点即用服务以执行。</span><span class="sxs-lookup"><span data-stu-id="55143-207">Action was successfully submitted to the Click-To-Run service for execution.</span></span>  <br/> |
|<span data-ttu-id="55143-208">**E_ACCESSDENIED**</span><span class="sxs-lookup"><span data-stu-id="55143-208">**E_ACCESSDENIED**</span></span> <br/> |<span data-ttu-id="55143-209">呼叫者未使用提升的权限运行。</span><span class="sxs-lookup"><span data-stu-id="55143-209">The caller is not running with elevated privileges.</span></span>  <br/> |
|<span data-ttu-id="55143-210">**E_INVALIDARG**</span><span class="sxs-lookup"><span data-stu-id="55143-210">**E_INVALIDARG**</span></span> <br/> |<span data-ttu-id="55143-211">传递的参数无效。</span><span class="sxs-lookup"><span data-stu-id="55143-211">Invalid parameters were passed.</span></span>  <br/> |
|<span data-ttu-id="55143-212">**E_ILLEGAL_METHOD_CALL**</span><span class="sxs-lookup"><span data-stu-id="55143-212">**E_ILLEGAL_METHOD_CALL**</span></span> <br/> |<span data-ttu-id="55143-213">此时不允许执行操作。</span><span class="sxs-lookup"><span data-stu-id="55143-213">Action is not allowed at this time.</span></span> <span data-ttu-id="55143-214">有关详细信息，请参阅 " [备注](#bk_DownloadRemark) "。</span><span class="sxs-lookup"><span data-stu-id="55143-214">See [Remarks](#bk_DownloadRemark) for more information.</span></span>  <br/> |

<a name="bk_DownloadRemark"></a>

#### <a name="remarks"></a><span data-ttu-id="55143-215">说明</span><span class="sxs-lookup"><span data-stu-id="55143-215">Remarks</span></span>

- <span data-ttu-id="55143-216">必须将  _downloadsource_ 和  _contentid_ 指定为一对。</span><span class="sxs-lookup"><span data-stu-id="55143-216">You must specify  _downloadsource_ and  _contentid_ as a pair.</span></span> <span data-ttu-id="55143-217">如果不是，则 **下载** 方法将返回一个 **E_INVALIDARG** 错误。</span><span class="sxs-lookup"><span data-stu-id="55143-217">If not, the **Download** method will return an **E_INVALIDARG** error.</span></span> 
    
- <span data-ttu-id="55143-218">如果提供了  _downloadsource_、  _contentid_和  _updatebaseurl_ ，则将忽略  _updatebaseurl_ 。</span><span class="sxs-lookup"><span data-stu-id="55143-218">If  _downloadsource_,  _contentid_, and  _updatebaseurl_ are provided,  _updatebaseurl_ will be ignored.</span></span> 
    
- <span data-ttu-id="55143-219">仅当 COM 状态为以下情况之一时，才能触发此操作：</span><span class="sxs-lookup"><span data-stu-id="55143-219">This action can only be triggered when the COM status is one of the following:</span></span> 
    
  - <span data-ttu-id="55143-220">**eUPDATE_UNKNOWN**</span><span class="sxs-lookup"><span data-stu-id="55143-220">**eUPDATE_UNKNOWN**</span></span>
    
  - <span data-ttu-id="55143-221">**eDOWNLOAD_CANCELLED**</span><span class="sxs-lookup"><span data-stu-id="55143-221">**eDOWNLOAD_CANCELLED**</span></span>
    
  - <span data-ttu-id="55143-222">**eDOWNLOAD_FAILED**</span><span class="sxs-lookup"><span data-stu-id="55143-222">**eDOWNLOAD_FAILED**</span></span>
    
  - <span data-ttu-id="55143-223">**eDOWNLOAD_SUCCEEDED**</span><span class="sxs-lookup"><span data-stu-id="55143-223">**eDOWNLOAD_SUCCEEDED**</span></span>
    
  - <span data-ttu-id="55143-224">**eAPPLY_SUCCEEDED**</span><span class="sxs-lookup"><span data-stu-id="55143-224">**eAPPLY_SUCCEEDED**</span></span>
    
  - <span data-ttu-id="55143-225">**eAPPLY_FAILED**</span><span class="sxs-lookup"><span data-stu-id="55143-225">**eAPPLY_FAILED**</span></span>
    
- <span data-ttu-id="55143-226">如果在未下载内容的情况下调用 **apply** 方法，则 **Apply** 方法将报告 **成功** ，因为它检测到什么内容未成功应用并已完成 **应用** 过程。</span><span class="sxs-lookup"><span data-stu-id="55143-226">If you call the **Apply** method without previously downloaded content, the **Apply** method will report **Succeeded** as it detected nothing to apply and completed the **Apply** process successfully.</span></span> 
    
#### <a name="examples"></a><span data-ttu-id="55143-227">示例</span><span class="sxs-lookup"><span data-stu-id="55143-227">Examples</span></span>

- <span data-ttu-id="55143-228">若要从自定义的 BITS 管理器下载内容：调用 \*\*下载 ( # B1 \*\* 函数传递以下参数：</span><span class="sxs-lookup"><span data-stu-id="55143-228">To download the content from the customized BITS manager: Call the **download()** function passing the following parameters:</span></span> 
    
  ```cpp
  "downloadsource=CLSIDofBITSInterface contentid=BITSServerContentIdentifier"
  ```

- <span data-ttu-id="55143-229">若要从 Office 内容传递网络 (CDN) 下载内容，请在未指定_downloadsource_、 _contentid_或_Updatebaseurl_参数的情况下调用**下载 ( # B3**函数。</span><span class="sxs-lookup"><span data-stu-id="55143-229">To download the content from the Office Content Delivery Network (CDN): Call the **download()** function without specifying the  _downloadsource_,  _contentid_, or  _updatebaseurl_ parameters.</span></span> 
    
- <span data-ttu-id="55143-230">若要从自定义位置下载内容：调用 \*\*下载 ( # B1 \*\* 函数传递以下参数：</span><span class="sxs-lookup"><span data-stu-id="55143-230">To download the content from a customized location: Call the **download()** function passing the following parameter:</span></span> 
    
  ```cpp
  "updatebaseurl=yourcontentserverurl"
  ```

### <a name="status"></a><span data-ttu-id="55143-231">状态</span><span class="sxs-lookup"><span data-stu-id="55143-231">Status</span></span>

```cpp
typdef struct _UPDATE_STATUS_REPORT
{
    UPDATE_STATUS status;
    UINT error;
    LPCWSTR contentid;
}UPDATE_STATUS_REPORT;
HRESULT status([out] _UPDATE_STATUS_REPORT& pUpdateStatusReport) // Get status of current action
```

#### <a name="parameters"></a><span data-ttu-id="55143-232">参数</span><span class="sxs-lookup"><span data-stu-id="55143-232">Parameters</span></span>

|||
|:-----|:-----|
| <span data-ttu-id="55143-233">_pUpdateStatusReport_</span><span class="sxs-lookup"><span data-stu-id="55143-233">_pUpdateStatusReport_</span></span> <br/> |<span data-ttu-id="55143-234">指向 UPDATE_STATUS_REPORT 结构的指针。</span><span class="sxs-lookup"><span data-stu-id="55143-234">Pointer to an UPDATE_STATUS_REPORT structure.</span></span>  <br/> |
   
#### <a name="return-results"></a><span data-ttu-id="55143-235">返回结果</span><span class="sxs-lookup"><span data-stu-id="55143-235">Return results</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="55143-236">**S_OK**</span><span class="sxs-lookup"><span data-stu-id="55143-236">**S_OK**</span></span> <br/> |<span data-ttu-id="55143-237">**Status**方法始终返回此结果。</span><span class="sxs-lookup"><span data-stu-id="55143-237">The **Status** method always returns this result.</span></span> <span data-ttu-id="55143-238">检查  `UPDATE_STATUS_RESULT` 当前操作的状态的结构。</span><span class="sxs-lookup"><span data-stu-id="55143-238">Inspect the  `UPDATE_STATUS_RESULT` structure for the status of the current action.</span></span>  <br/> |
   
#### <a name="remarks"></a><span data-ttu-id="55143-239">说明</span><span class="sxs-lookup"><span data-stu-id="55143-239">Remarks</span></span>

- <span data-ttu-id="55143-240">的 "状态" 字段  `UPDATE_STATUS_REPORT` 包含当前操作的状态。</span><span class="sxs-lookup"><span data-stu-id="55143-240">The status field of the  `UPDATE_STATUS_REPORT` contains the status of the current action.</span></span> <span data-ttu-id="55143-241">将返回以下状态值之一：</span><span class="sxs-lookup"><span data-stu-id="55143-241">One of the following status values is returned:</span></span> 
    
  ```cpp
  typedef enum _UPDATE_STATUS
  {
  eUPDATE_UNKNOWN = 0,
  eDOWNLOAD_PENDING,
  eDOWNLOAD_WIP,
  eDOWNLOAD_CANCELLING,
  eDOWNLOAD_CANCELLED,
  eDOWNLOAD_FAILED,
  eDOWNLOAD_SUCCEEDED,
  eAPPLY_PENDING,
  eAPPLY_WIP,
  eAPPLY_SUCCEEDED,
  eAPPLY_FAILED,
  } UPDATE_STATUS;
  
  ```

- <span data-ttu-id="55143-242">如果最后一个命令导致错误，则中的 "错误" 字段  `UPDATE_STATUS_REPORT` 包含有关错误的详细信息。</span><span class="sxs-lookup"><span data-stu-id="55143-242">If the last command resulted in an error, the error field of the  `UPDATE_STATUS_REPORT` contains detailed information about the error.</span></span> <span data-ttu-id="55143-243">**状态**方法返回两种类型的错误代码。</span><span class="sxs-lookup"><span data-stu-id="55143-243">Two types of error codes are returned from the **Status** method.</span></span> 
    
- <span data-ttu-id="55143-244">如果错误小于，则此  `UPDATE_ERROR_CODE::eUNKNOWN` 错误为下列预定义的错误代码之一：</span><span class="sxs-lookup"><span data-stu-id="55143-244">If the error less than  `UPDATE_ERROR_CODE::eUNKNOWN`, the error is one of the following pre-defined error codes:</span></span>
    
  ```cpp
  typedef enum _UPDATE_ERROR_CODE
  {
  eOK = 0,
  eFAILED_UNEXPECTED,
  eTRIGGER_DISABLED,
  ePIPELINE_IN_USE,
  eFAILED_STOP_C2RSERVICE,
  eFAILED_GET_CLIENTUPDATEFOLDER,
  eFAILED_LOCK_PACKAGE_TO_UPDATE,
  eFAILED_CREATE_STREAM_SESSION,
  eFAILED_PUBLISH_WORKING_CONFIGURATION,
  eFAILED_DOWNLOAD_UPGRADE_PACKAGE,
  eFAILED_APPLY_UPGRADE_PACKAGE,
  eFAILED_INITIALIZE_RSOD,
  eFAILED_PUBLISH_RSOD,
  // Keep this one as the last
  eUNKNOWN
  } UPDATE_ERROR_CODE;
  
  ```

  <span data-ttu-id="55143-245">如果返回错误代码大于  `UPDATE_ERROR_CODE::eUNKNOWN` 为失败的函数调用的 **HRESULT** 。</span><span class="sxs-lookup"><span data-stu-id="55143-245">If the return error code is larger than  `UPDATE_ERROR_CODE::eUNKNOWN` it is the **HRESULT** of a failed function call.</span></span> <span data-ttu-id="55143-246">`UPDATE_ERROR_CODE::eUNKNOWN`从的 "错误" 字段中返回的值中提取 HRESULT 减去 `UPDATE_STATUS_REPORT` 。</span><span class="sxs-lookup"><span data-stu-id="55143-246">To extract the HRESULT subtract  `UPDATE_ERROR_CODE::eUNKNOWN` from the value returned in the error field of the  `UPDATE_STATUS_REPORT`.</span></span>
    
  <span data-ttu-id="55143-247">可以通过检查嵌入在 OfficeC2RCom.dll 中的 **IUpdateNotify** 类型库来查看状态和错误值的完整列表。</span><span class="sxs-lookup"><span data-stu-id="55143-247">The complete list of status and error values can be viewed by inspecting the **IUpdateNotify** type library embedded in OfficeC2RCom.dll.</span></span> 
    
- <span data-ttu-id="55143-248">Contentid 字段用于在开始**下载**后对**状态**的调用，并返回传入到**下载**调用的 contentid。</span><span class="sxs-lookup"><span data-stu-id="55143-248">The contentid field is used for calls to **Status** after **Download** has initiated and returns the contentid that was passed in to the **Download** call.</span></span> <span data-ttu-id="55143-249">最佳做法是，在调用**status**方法之前将此字段初始化为**null** ，然后在返回**状态**后检查值。</span><span class="sxs-lookup"><span data-stu-id="55143-249">It is a best practice to initialize this field to **null** before you call the **Status** method and then check the value after **Status** has been returned.</span></span> <span data-ttu-id="55143-250">如果该值仍为 **null**，则表示没有要返回的 contentid。</span><span class="sxs-lookup"><span data-stu-id="55143-250">If the value is still **null**, that means there is no contentid to return.</span></span> <span data-ttu-id="55143-251">如果值不为 **null**，则需要通过调用 \*\*SysFreeString ( # B1 \*\*将其释放。</span><span class="sxs-lookup"><span data-stu-id="55143-251">If the value is not **null**, you need to free it with a call to **SysFreeString()**.</span></span> <span data-ttu-id="55143-252">下面是一个代码段，介绍了如何在**下载**后调用**状态**。</span><span class="sxs-lookup"><span data-stu-id="55143-252">Here is a code snippet of how to call **Status** after **Download**.</span></span>
    
  ```cpp
  std::wstring contentID;
  UPDATE_STATUS_REPORT statusReport;
  statusReport.status = eUPDATE_UNKNOWN;
  statusReport.error = eOK;
  statusReport.contentid = NULL;
  hr = p->Status(&statusReport);
  if (statusReport.contentid != NULL)
  {
  contentID = statusReport.contentid;
  SysFreeString(statusReport.contentid);
  }
  wprintf(L"ContentID: %s, Status: %d, LastError: %d", contentID.c_str(), statusReport.status, statusReport.error);
  
  ```

### <a name="summary-of-iupdatenotify2-interface"></a><span data-ttu-id="55143-253">IUpdateNotify2 接口摘要</span><span class="sxs-lookup"><span data-stu-id="55143-253">Summary of IUpdateNotify2 interface</span></span>

<span data-ttu-id="55143-254">自版本 [16.0.8208.6352] 我们添加了新的 **IUpdateNotify2** 接口。</span><span class="sxs-lookup"><span data-stu-id="55143-254">From version [16.0.8208.6352] we have added a new **IUpdateNotify2** interface.</span></span> 
  
- <span data-ttu-id="55143-255">CLSID_UpdateNotifyObject2，{52C2F9C2-F1AC-4021-BF50-756A5FA8DDFE}</span><span class="sxs-lookup"><span data-stu-id="55143-255">CLSID_UpdateNotifyObject2, {52C2F9C2-F1AC-4021-BF50-756A5FA8DDFE}</span></span>
    
- <span data-ttu-id="55143-256">此接口也托管原始 IUpdateNotify 接口，以提供向后兼容性。</span><span class="sxs-lookup"><span data-stu-id="55143-256">This interface also hosted the original IUpdateNotify interface to provide backward compatibility.</span></span> <span data-ttu-id="55143-257">这意味着，如果您使用此接口，则可以访问 **UpdateNotifyObject** 接口中提供的所有方法。</span><span class="sxs-lookup"><span data-stu-id="55143-257">Which means if you use this interface, you have access to all the methods provided in **UpdateNotifyObject** interface.</span></span> 
    
- <span data-ttu-id="55143-258">添加到 IUpdateNotify2 的新方法：</span><span class="sxs-lookup"><span data-stu-id="55143-258">New methods added to IUpdateNotify2:</span></span>
    
  - <span data-ttu-id="55143-259">**HRESULT** GetBlockingApps ( [out] BSTR \* AppsList) 。</span><span class="sxs-lookup"><span data-stu-id="55143-259">**HRESULT** GetBlockingApps([out] BSTR \* AppsList).</span></span> <span data-ttu-id="55143-260">获取更新阻止应用程序列表。</span><span class="sxs-lookup"><span data-stu-id="55143-260">Get updates blocking apps list.</span></span> <span data-ttu-id="55143-261">此调用将返回运行的 Office 应用程序，这将阻止更新过程继续进行。</span><span class="sxs-lookup"><span data-stu-id="55143-261">This call will return running Office apps which will block the update process from proceeding.</span></span> 
    
  - <span data-ttu-id="55143-262">**HRESULT** GetOfficeDeploymentData ( [in] int dataType，[in] **一个 lpcwstr** pcwszName，[OUT] BSTR \* OfficeData) 。</span><span class="sxs-lookup"><span data-stu-id="55143-262">**HRESULT** GetOfficeDeploymentData([in] int dataType, [in] **LPCWSTR** pcwszName, [out] BSTR \* OfficeData).</span></span> <span data-ttu-id="55143-263">获取 Office 部署数据。</span><span class="sxs-lookup"><span data-stu-id="55143-263">Get Office deployment Data.</span></span> 
    
- <span data-ttu-id="55143-264">如果要使用新的方法，您需要确保：</span><span class="sxs-lookup"><span data-stu-id="55143-264">If you want to use the new methods, you need to make sure:</span></span>
    
  - <span data-ttu-id="55143-265">您的 C2R 版本比上面的版本 (\> = 六月的分叉构建) 高。</span><span class="sxs-lookup"><span data-stu-id="55143-265">Your C2R version is newer than the above build (\>= June fork build).</span></span>
    
  - <span data-ttu-id="55143-266">使用 UpdateNotifyObject2 而不是 **UpdateNotifyObject** 调用 **CoCreateInstance**。</span><span class="sxs-lookup"><span data-stu-id="55143-266">Use UpdateNotifyObject2, instead of **UpdateNotifyObject** to call **CoCreateInstance**.</span></span>
    
<span data-ttu-id="55143-267">如果不使用任何新方法，则无需更改任何内容。</span><span class="sxs-lookup"><span data-stu-id="55143-267">If you don't use any of the new methods, you don't need to change anything.</span></span> <span data-ttu-id="55143-268">所有现有方法的工作方式都与之前完全相同。</span><span class="sxs-lookup"><span data-stu-id="55143-268">All the existing methods will work as exact the same way as before.</span></span>
  
## <a name="implementing-the-bits-interface"></a><span data-ttu-id="55143-269">实现 BITS 接口</span><span class="sxs-lookup"><span data-stu-id="55143-269">Implementing the BITS interface</span></span>

<span data-ttu-id="55143-270">[后台智能传输服务](https://docs.microsoft.com/windows/win32/bits/background-intelligent-transfer-service-portal) (BITS) 是 Microsoft 提供的一种服务，用于在客户端和服务器之间传输文件。</span><span class="sxs-lookup"><span data-stu-id="55143-270">The [Background Intelligent Transfer Service](https://docs.microsoft.com/windows/win32/bits/background-intelligent-transfer-service-portal) (BITS) is a service provided by Microsoft to transfer files between a client and server.</span></span> <span data-ttu-id="55143-271">BITS 是 Office 即点即用安装程序可用于下载内容的频道之一。</span><span class="sxs-lookup"><span data-stu-id="55143-271">BITS is one of the channels that Office Click-To-Run installer can use to download content.</span></span> <span data-ttu-id="55143-272">默认情况下，Microsoft 365 应用程序即点即用安装程序使用 Windows 内置的 BITS 实现从 CDN 下载内容。</span><span class="sxs-lookup"><span data-stu-id="55143-272">By default, the Microsoft 365 Apps Click-To-Run installer uses the Windows' built in implementation of BITS to download the content from the CDN.</span></span> 
  
<span data-ttu-id="55143-273">通过将自定义的 BITS 实现提供给**IUpdateNotify**接口的**下载 ( # B1**方法，您的可管理性软件可以控制客户端的下载内容的位置和方式。</span><span class="sxs-lookup"><span data-stu-id="55143-273">By providing a customized BITS implementation to the **download()** method of the **IUpdateNotify** interface, your manageability software can control where and how the client downloads the content.</span></span> <span data-ttu-id="55143-274">当提供自定义内容分发通道（而不是即点即用的内置通道，如 CDN、IIS 服务器或文件共享）时，自定义的 BITS 接口非常有用。</span><span class="sxs-lookup"><span data-stu-id="55143-274">A customized BITS interface is useful when providing a custom content distribution channel other than the Click-to-Run built-in channels, such as the CDN, IIS servers, or file shares.</span></span> 
  
<span data-ttu-id="55143-275">与 Office C2R service 配合使用的自定义位接口的最低要求是：</span><span class="sxs-lookup"><span data-stu-id="55143-275">The minimum requirement for a customized BITS interface to work with Office C2R service is:</span></span>
  
- <span data-ttu-id="55143-276">对于 **IBackgroundCopyManager**：</span><span class="sxs-lookup"><span data-stu-id="55143-276">For **IBackgroundCopyManager**:</span></span>
    
  ```cpp
  HRESULT _stdcall CreateJob(
                      [in] LPWSTR DisplayName, 
                      [in] BG_JOB_TYPE Type, 
                      [out] GUID* pJobId, 
                      [out] IBackgroundCopyJob** ppJob)
  HRESULT _stdcall GetJob(
                      [in] GUID* jobID, 
                      [out] IBackgroundCopyJob** ppJob)
  HRESULT _stdcall EnumJobs(
                      [in] unsigned long dwFlags, 
                      [out] IEnumBackgroundCopyJobs** ppenum)
  
  ```

- <span data-ttu-id="55143-277">对于 **IBackgroundCopyJob**：</span><span class="sxs-lookup"><span data-stu-id="55143-277">For **IBackgroundCopyJob**:</span></span>
    
  ```cpp
  HRESULT _stdcall AddFile(
                      [in] LPWSTR RemoteUrl, 
                      [in] LPWSTR LocalName)
  HRESULT _stdcall Resume()
  HRESULT _stdcall Complete()
  HRESULT _stdcall Cancel();
  HRESULT _stdcall GetState([out] BG_JOB_STATE* pVal);
  HRESULT GetProgress( [out] BG_JOB_PROGRESS *pProgress);
  
  ```

- <span data-ttu-id="55143-278">对于 **IBackgroundCopyJob3**：</span><span class="sxs-lookup"><span data-stu-id="55143-278">For **IBackgroundCopyJob3**:</span></span>
    
  ```cpp
  HRESULT _stdcall AddFileWithRanges(
                      [in] LPWSTR RemoteUrl, 
                      [in] LPWSTR LocalName,
                      [in] DWORD RangeCount,
                      [in] BG_FILE_RANGE Ranges[])
  
  ```

- <span data-ttu-id="55143-279">对于  `Addfile` 和  `AddFileWithRanges` 函数，远程 URL 采用以下格式：</span><span class="sxs-lookup"><span data-stu-id="55143-279">For the  `Addfile` and  `AddFileWithRanges` functions, the remote URL is in the following format:</span></span> 
    
  ```cpp
  cmbits://<contentid>/<relative path to target file>
  ```

  - <span data-ttu-id="55143-280">cmbits 是硬编码的，并代表自定义位。</span><span class="sxs-lookup"><span data-stu-id="55143-280">cmbits is hard coded, and stands for customized BITS.</span></span>
    
  -  <span data-ttu-id="55143-281">_\<contentid\>_ 是\*\* ( # B1\*\*方法的下载的_contentid_参数。</span><span class="sxs-lookup"><span data-stu-id="55143-281">_\<contentid\>_ is the  _contentid_ parameter for the **Download()** method.</span></span> 
    
  -  <span data-ttu-id="55143-282">_\<relative path to target file\>_ 提供要下载的文件的位置和文件名。</span><span class="sxs-lookup"><span data-stu-id="55143-282">_\<relative path to target file\>_ provides the location and file name of the file to download.</span></span> 
    
    <span data-ttu-id="55143-283">例如，如果您已提供_contentid_ `f732af58-5d86-4299-abe9-7595c35136ef` \*\* ( # B1**方法的下载项的 contentid，而 Office C2R 想要下载版本 cab 文件（如 `v32.cab` File），它将调用**AddFile ( # B3\*\* ，并提供以下 `RemoteUrl` 内容：</span><span class="sxs-lookup"><span data-stu-id="55143-283">For example, if you have provided a  _contentid_ of  `f732af58-5d86-4299-abe9-7595c35136ef` to the **Download()** method, and Office C2R wants to download the version cab file, such as  `v32.cab` file, it will call **AddFile()** with the following  `RemoteUrl`:</span></span>
    
  ```cpp
  cmbits://f732af58-5d86-4299-abe9-7595c35136ef/Office/Data/V32.cab
  ```

- <span data-ttu-id="55143-284">对于 **IBackgroundCopyError**：</span><span class="sxs-lookup"><span data-stu-id="55143-284">For **IBackgroundCopyError**:</span></span>
    
  ```cpp
  HRESULT _stdcall GetErrorDescription(
        [in]  DWORD  LanguageId,
        [out] LPWSTR *ppErrorDescription);
  
  ```

- <span data-ttu-id="55143-285">对于 **IBackgroundCopyFile**：</span><span class="sxs-lookup"><span data-stu-id="55143-285">For **IBackgroundCopyFile**:</span></span>
    
  ```cpp
  HRESULT _stdcall GetLocalName([out] LPWSTR *ppName); 
  HRESULT _stdcall GetRemoteName([out] LPWSTR *ppName);
  
  ```
## <a name="automating-content-staging"></a><span data-ttu-id="55143-286">自动化内容暂存</span><span class="sxs-lookup"><span data-stu-id="55143-286">Automating content staging</span></span>

<span data-ttu-id="55143-287">IT 管理员可以选择让桌面客户端在可直接从 CDN 获取更新时自动接收更新，也可以选择使用 Office 部署工具或 Microsoft 终结点配置管理器来控制更新通道中可用的更新的部署。</span><span class="sxs-lookup"><span data-stu-id="55143-287">IT administrators can choose to have desktop clients enabled to automatically receive updates when they are available directly from the CDN or they can choose to control the deployment of updates available from the update channels using the Office Deployment Tool or Microsoft Endpoint Configuration Manager.</span></span>
  
<span data-ttu-id="55143-288">服务支持管理工具在更新可用时识别和自动下载内容的功能。</span><span class="sxs-lookup"><span data-stu-id="55143-288">The service supports the ability for management tools to recognize and automate the download of the content when updates are made available.</span></span>
  
<span data-ttu-id="55143-289">**下图概述了下载自定义图像**</span><span class="sxs-lookup"><span data-stu-id="55143-289">**The following image is an overview of downloading a custom image**</span></span>

<span data-ttu-id="55143-290">![在 Office 单击即运行安装程序上使用 COM 接口的图。](media/e7ac2523-e67b-4a44-ae67-c048709f872a.png "在 Office 即点即用安装程序上使用 COM 接口的关系图")</span><span class="sxs-lookup"><span data-stu-id="55143-290">![A diagram of using the COM interface on  the Office Click-To-Run installer.](media/e7ac2523-e67b-4a44-ae67-c048709f872a.png "A diagram of using the COM interface on the Office Click-To-Run installer")</span></span>
  
### <a name="overview-of-downloading-a-custom-image"></a><span data-ttu-id="55143-291">下载自定义图像概述</span><span class="sxs-lookup"><span data-stu-id="55143-291">Overview of downloading a custom image</span></span>
  
<span data-ttu-id="55143-292">在上图中，您会看到新的 Microsoft 365 应用程序映像在 CDN 上可用。</span><span class="sxs-lookup"><span data-stu-id="55143-292">In the previous diagram, you see that a new Microsoft 365 Apps image is available on the CDN.</span></span> <span data-ttu-id="55143-293">除了 Microsoft 365 应用程序映像外，还提供了一个 API，其中包含启用可管理性软件以直接创建自定义图像以替换使用 Office 部署工具的需求所需的信息。</span><span class="sxs-lookup"><span data-stu-id="55143-293">Along with the Microsoft 365 Apps image, an API is available which has the information needed to enable manageability software to directly create customized images replacing the need for using the Office Deployment Tool.</span></span>

<span data-ttu-id="55143-294">企业将其 WSUS 配置为同步 Microsoft 365 应用更新。</span><span class="sxs-lookup"><span data-stu-id="55143-294">An enterprise configures their WSUS to sync the Microsoft 365 Apps updates.</span></span> <span data-ttu-id="55143-295">这些更新不包含实际图像负载，但允许可管理性软件识别新内容何时可用。</span><span class="sxs-lookup"><span data-stu-id="55143-295">These updates do not contain the actual image payload but does allow the manageability software to recognize when new content is available.</span></span> <span data-ttu-id="55143-296">然后，可管理性软件可阅读 Microsoft 365 应用更新元数据，了解更新适用于什么 Office 版本。</span><span class="sxs-lookup"><span data-stu-id="55143-296">The manageability software can then read the Microsoft 365 Apps Update metadata to understand what version of Office the update applies to.</span></span>

<span data-ttu-id="55143-297">如果更新适用，可管理性软件可以使用 CDN 内容和文件列表来创建自定义图像，并将其存储在配置为使用的文件共享位置上。</span><span class="sxs-lookup"><span data-stu-id="55143-297">If the update is applicable, the manageability software can use the CDN content and the file list to create the custom image and store it onto the file share location that it is configured to use.</span></span>
  
### <a name="using-the-microsoft-365-apps-file-list-api"></a><span data-ttu-id="55143-298">使用 Microsoft 365 应用程序文件列表 API</span><span class="sxs-lookup"><span data-stu-id="55143-298">Using the Microsoft 365 Apps file list API</span></span>

<span data-ttu-id="55143-299">Microsoft 365 应用程序文件列表 API 用于检索特定 Microsoft 365 应用程序更新所需的文件的名称。</span><span class="sxs-lookup"><span data-stu-id="55143-299">The Microsoft 365 Apps file list API is used to retrieve the names of the files needed for a particular Microsoft 365 Apps update.</span></span>

<span data-ttu-id="55143-300">HTTP 请求</span><span class="sxs-lookup"><span data-stu-id="55143-300">HTTP Request</span></span>

<span data-ttu-id="55143-301">获取 https://config.office.com/api/filelist</span><span class="sxs-lookup"><span data-stu-id="55143-301">GET https://config.office.com/api/filelist</span></span>

<span data-ttu-id="55143-302">请勿提供此方法的请求正文。</span><span class="sxs-lookup"><span data-stu-id="55143-302">Do not supply a request body for this method.</span></span>

<span data-ttu-id="55143-303">调用此 API 不需要任何权限。</span><span class="sxs-lookup"><span data-stu-id="55143-303">No permissions are required to call this API.</span></span>

<span data-ttu-id="55143-304">可选的查询参数</span><span class="sxs-lookup"><span data-stu-id="55143-304">Optional query parameters</span></span>

|<span data-ttu-id="55143-305">**名称**</span><span class="sxs-lookup"><span data-stu-id="55143-305">**Name**</span></span>|<span data-ttu-id="55143-306">**说明**</span><span class="sxs-lookup"><span data-stu-id="55143-306">**Description**</span></span>|
|:-----|:-----|
| <span data-ttu-id="55143-307">频道</span><span class="sxs-lookup"><span data-stu-id="55143-307">channel</span></span> <br/>| <span data-ttu-id="55143-308">指定通道名称</span><span class="sxs-lookup"><span data-stu-id="55143-308">Specifies the channel name</span></span>  <br/> <span data-ttu-id="55143-309">可选–默认为 "半年"</span><span class="sxs-lookup"><span data-stu-id="55143-309">Optional – default to ‘SemiAnnual’</span></span> <br/> <span data-ttu-id="55143-310">支持的值 https://docs.microsoft.com/DeployOffice/office-deployment-tool-configuration-options#channel-attribute-part-of-add-element</span><span class="sxs-lookup"><span data-stu-id="55143-310">Supported values https://docs.microsoft.com/DeployOffice/office-deployment-tool-configuration-options#channel-attribute-part-of-add-element</span></span> |
| <span data-ttu-id="55143-311">version</span><span class="sxs-lookup"><span data-stu-id="55143-311">version</span></span> <br/>| <span data-ttu-id="55143-312">指定更新版本</span><span class="sxs-lookup"><span data-stu-id="55143-312">Specifies the update version</span></span> <br/> <span data-ttu-id="55143-313">可选–默认为可用于指定通道的最新版本</span><span class="sxs-lookup"><span data-stu-id="55143-313">Optional – defaults to the latest version available for the specified channel</span></span> |
| <span data-ttu-id="55143-314">弧</span><span class="sxs-lookup"><span data-stu-id="55143-314">arch</span></span> <br/>| <span data-ttu-id="55143-315">指定客户端体系结构</span><span class="sxs-lookup"><span data-stu-id="55143-315">Specifies client architecture</span></span> <br/> <span data-ttu-id="55143-316">可选–默认为 "x64"</span><span class="sxs-lookup"><span data-stu-id="55143-316">Optional – defaults to ‘x64’</span></span> <br/> <span data-ttu-id="55143-317">支持的值： x64、x86</span><span class="sxs-lookup"><span data-stu-id="55143-317">Supported values: x64, x86</span></span> |
| <span data-ttu-id="55143-318">盖子</span><span class="sxs-lookup"><span data-stu-id="55143-318">lid</span></span> <br/>| <span data-ttu-id="55143-319">指定要包含的语言文件</span><span class="sxs-lookup"><span data-stu-id="55143-319">Specifies the language files to include</span></span> <br/> <span data-ttu-id="55143-320">可选–默认值为无</span><span class="sxs-lookup"><span data-stu-id="55143-320">Optional – defaults to none</span></span> <br/> <span data-ttu-id="55143-321">若要指定多种语言，请为每种语言包含一个盖子查询参数</span><span class="sxs-lookup"><span data-stu-id="55143-321">To specify multiple languages, include an lid query parameter for each language</span></span> <br/> <span data-ttu-id="55143-322">使用语言标识符格式（ex）。</span><span class="sxs-lookup"><span data-stu-id="55143-322">Use the language identifier format, ex.</span></span> <span data-ttu-id="55143-323">' en-us '，' fr-fr '</span><span class="sxs-lookup"><span data-stu-id="55143-323">‘en-us’, ‘fr-fr’</span></span> |
| <span data-ttu-id="55143-324">alllanguages</span><span class="sxs-lookup"><span data-stu-id="55143-324">alllanguages</span></span> <br/>| <span data-ttu-id="55143-325">指定包含所有语言文件</span><span class="sxs-lookup"><span data-stu-id="55143-325">Specifies to include all language files</span></span> <br/> <span data-ttu-id="55143-326">可选–默认值为 false</span><span class="sxs-lookup"><span data-stu-id="55143-326">Optional – defaults to false</span></span> |

<span data-ttu-id="55143-327">HTTP 响应</span><span class="sxs-lookup"><span data-stu-id="55143-327">HTTP Response</span></span>

<span data-ttu-id="55143-328">如果成功，此方法在响应正文中返回 200 OK 响应代码和 file 对象集合。</span><span class="sxs-lookup"><span data-stu-id="55143-328">If successful, this method returns a 200 OK response code and collection of file objects in the response body.</span></span>

<span data-ttu-id="55143-329">若要创建图像，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="55143-329">To create an image, follow these steps:</span></span>
1.  <span data-ttu-id="55143-330">调用 API，为您感兴趣的更新的通道、版本和体系结构提供相应的查询参数。</span><span class="sxs-lookup"><span data-stu-id="55143-330">Call the API, providing the appropriate query parameters for the channel, version and architecture of the update you are interested in.</span></span>
<span data-ttu-id="55143-331">注意：属性为 "lcid" 的 File 对象为 "lcid"： "0" 为中性语言文件，必须包含在映像中。</span><span class="sxs-lookup"><span data-stu-id="55143-331">Note: File objects with the attribute "lcid": "0" are language neutral files and must be included in the image.</span></span>
2.  <span data-ttu-id="55143-332">通过循环访问文件对象和复制 CDN 文件来构造 CDN 的本地映像，同时创建由为每个 file 对象定义的 "relativePath" 属性指定的文件夹结构。</span><span class="sxs-lookup"><span data-stu-id="55143-332">Construct a local image of the CDN by iterating through the file objects and copying the CDN files, while creating the folder structure as specified by the “relativePath” attribute defined for each of the file objects.</span></span>

<span data-ttu-id="55143-333">下面的示例检索当前频道的文件列表和64位版本的16.0.4229.1004，并包含法语和英语语言文件：</span><span class="sxs-lookup"><span data-stu-id="55143-333">The following example retrieves the file list for the Current Channel and version 16.0.4229.1004 for 64bit and includes the French and English language files:</span></span>

```http
Get https://config.office.com/api/filelist?Channel=Current&Version=16.0.4229.1004&Arch=x64&Lid=fr-fr&Lid=en-US
```

### <a name="hash-verification-of-dat-files"></a><span data-ttu-id="55143-334">.Dat 文件的哈希验证</span><span class="sxs-lookup"><span data-stu-id="55143-334">Hash verification of .dat files</span></span>

<span data-ttu-id="55143-335">通过将计算的哈希值与与每个 .dat 文件相关联的提供的哈希值相比较，图像创建工具可以验证下载的 .dat 文件的完整性。</span><span class="sxs-lookup"><span data-stu-id="55143-335">Image creation tools may verify the integrity of the downloaded .dat files by comparing a computed hash value with the supplied hash value associated with each of the .dat files.</span></span> <span data-ttu-id="55143-336">以下是一个 file 对象的示例，该对象指定 hashLocation 和 hashAlgorithm 值：</span><span class="sxs-lookup"><span data-stu-id="55143-336">Following is an example of a file object that specifies hashLocation and hashAlgorithm values:</span></span>
  
```xml
{
  "url": "https://officecdn.microsoft.com/pr/7ffbc6bf-bc32-4f92-8982-f9dd17fd3114/office/data/16.0.1234.1001/stream.x64.x-none.dat",
  "name": "stream.x64.x-none.dat",
  "relativePath": "/office/data/16.0.1234.1001/",
  "hashLocation": "s640.cab/stream.x64.x-none.hash",
  "hashAlgorithm": "Sha256",
  "lcid": "0"
},
```

- <span data-ttu-id="55143-337">**HashLocation**属性指定包含哈希值的 .cab 文件的相对路径位置。</span><span class="sxs-lookup"><span data-stu-id="55143-337">The **hashLocation** attribute specifies the relative path location of .cab file that contains the hash value.</span></span> <span data-ttu-id="55143-338">通过串联 URL + relativePath + hashLocation 构造哈希文件位置。</span><span class="sxs-lookup"><span data-stu-id="55143-338">Construct the hash file location by concatenating URL + relativePath + hashLocation.</span></span> <span data-ttu-id="55143-339">在下面的示例中，stream.x64.bg 的哈希位置将为：</span><span class="sxs-lookup"><span data-stu-id="55143-339">In the following example, the stream.x64.bg-bg.hash location would be:</span></span> 
    
  ```http
  https://officecdn.microsoft.com/pr/492350f6-3a01-4f97-b9c0-c7c6ddf67d60/office/data/16.0.4229.1004/s641026.cab/stream.x64.bg-bg.hash 
  ```

- <span data-ttu-id="55143-340">**HashAlgorithm**属性指定使用哪种哈希算法。</span><span class="sxs-lookup"><span data-stu-id="55143-340">The **hashAlgorithm** attribute specifies what hashing algorithm was used.</span></span> 
    
  <span data-ttu-id="55143-341">若要验证 stream.x64.bg-bg 文件的完整性，请打开 stream.x64.bg-bg. 哈希，并读取哈希值，该值是哈希文件中的第一行文本。</span><span class="sxs-lookup"><span data-stu-id="55143-341">To validate the integrity of the stream.x64.bg-bg.dat file, open the stream.x64.bg-bg.hash and read the HASH value which is the first line of text in the hash file.</span></span> <span data-ttu-id="55143-342">将此值与计算的哈希值进行比较， (使用指定的哈希算法) 验证下载的 .dat 文件的完整性。</span><span class="sxs-lookup"><span data-stu-id="55143-342">Compare this to the computed hash value (using the specified hashing algorithm) to verify the integrity of the downloaded .dat file.</span></span>
    
  <span data-ttu-id="55143-343">下面的示例演示用于读取哈希的 c # 代码。</span><span class="sxs-lookup"><span data-stu-id="55143-343">The following example shows the C# code to read the hash.</span></span>
    
  ```cs
    string[] readHashes = System.IO.File.ReadAllLines(tmpFile, Encoding.Unicode);
    string readHash = readHashes.First();
  ```

### <a name="microsoft-365-apps-updates"></a><span data-ttu-id="55143-344">Microsoft 365 应用更新</span><span class="sxs-lookup"><span data-stu-id="55143-344">Microsoft 365 Apps Updates</span></span>

<span data-ttu-id="55143-345">所有 Microsoft 365 应用更新都将发布到 [Microsoft Update 目录](https://www.catalog.update.microsoft.com/Search.aspx?q=office+365+client)。</span><span class="sxs-lookup"><span data-stu-id="55143-345">All Microsoft 365 Apps Updates are published to the [Microsoft Update Catalog](https://www.catalog.update.microsoft.com/Search.aspx?q=office+365+client).</span></span>
  
<span data-ttu-id="55143-346">Microsoft 365 Apps Updates 使可管理性软件能够以与任何其他 WU 更新（只是一个例外）相似的方式来处理 Microsoft 365 应用更新。客户端更新不包含实际有效负载。</span><span class="sxs-lookup"><span data-stu-id="55143-346">Microsoft 365 Apps Updates enable manageability software to treat Microsoft 365 Apps Updates in a manner very similar to any other WU update with one exception; the client updates do not contain an actual payload.</span></span> <span data-ttu-id="55143-347">Microsoft 365 应用程序更新不应安装在任何客户端上，而是使用可管理性软件将安装命令替换为上面所示的基于 COM 的安装机制，从而触发工作流。</span><span class="sxs-lookup"><span data-stu-id="55143-347">The Microsoft 365 Apps Updates should not be installed on any clients but rather used to trigger the workflows with the manageability software replacing the installation command with the COM based installation mechanism shown above.</span></span>

<span data-ttu-id="55143-348">**下图显示了 Office 365 客户端更新工作流的关系图。**</span><span class="sxs-lookup"><span data-stu-id="55143-348">**The following figure shows a diagram of the Office 365 Client Update workflow.**</span></span>

<span data-ttu-id="55143-349">![O365PP 客户端更新的工作流图。](media/bc8092b0-62b8-402c-a5c0-04d55cca01d4.png "O365PP 客户端更新的工作流图表")</span><span class="sxs-lookup"><span data-stu-id="55143-349">![Workflow diagram for O365PP client updates.](media/bc8092b0-62b8-402c-a5c0-04d55cca01d4.png "Workflow diagram for O365PP client updates")</span></span>
  
<span data-ttu-id="55143-350">发布的每个 Microsoft 365 应用更新都包含有关更新的元数据。</span><span class="sxs-lookup"><span data-stu-id="55143-350">Each Microsoft 365 Apps Update that is published includes metadata about the update.</span></span> <span data-ttu-id="55143-351">此元数据包含一个名为 MoreInfoUrl 的参数，可用于为该特定更新派生对文件列表 API 的 API 调用。</span><span class="sxs-lookup"><span data-stu-id="55143-351">This metadata includes a parameter called MoreInfoUrl which can be used to derive the API call to the file list API for that specific update.</span></span>

<span data-ttu-id="55143-352">在下面的示例中，文件列表 API 嵌入在 MoreInfoURL 中，并以 "ServicePath =" 开头。</span><span class="sxs-lookup"><span data-stu-id="55143-352">In the following example, the file list API is embedded in the MoreInfoURL and starts with “ServicePath=”</span></span>

<span data-ttu-id="55143-353">http://go.microsoft.com/fwlink/?LinkId=626090&Ver=16.0.12527.21104&Branch=Insiders&Arch=64&XMLVer=1.6&xmlPath=http://officecdn.microsoft.com/pr/wsus/ofl.cab&xmlFile=O365Client_64bit.xml& ServicePath =https://config.office.com/api/filelist?Channel=Insiders&Version=16.0.12527.21104&Arch=64&AllLanguages=True</span><span class="sxs-lookup"><span data-stu-id="55143-353">http://go.microsoft.com/fwlink/?LinkId=626090&Ver=16.0.12527.21104&Branch=Insiders&Arch=64&XMLVer=1.6&xmlPath=http://officecdn.microsoft.com/pr/wsus/ofl.cab&xmlFile=O365Client_64bit.xml& ServicePath=https://config.office.com/api/filelist?Channel=Insiders&Version=16.0.12527.21104&Arch=64&AllLanguages=True</span></span>
  
### <a name="additional-metadata-for-automating-content-staging"></a><span data-ttu-id="55143-354">用于自动执行内容暂存的其他元数据</span><span class="sxs-lookup"><span data-stu-id="55143-354">Additional metadata for automating content staging</span></span>

<span data-ttu-id="55143-355">**发布历史记录 API**</span><span class="sxs-lookup"><span data-stu-id="55143-355">**Release History API**</span></span>
  
<span data-ttu-id="55143-356">Microsoft 365 应用版本历史记录 API 用于检索与频道名称和其他通道属性一起发布到 CDN 的每个更新的详细信息。</span><span class="sxs-lookup"><span data-stu-id="55143-356">The Microsoft 365 Apps release history API is used to retrieve details for each of the updates published to the CDN along with the channel names and other channel attributes.</span></span>

<span data-ttu-id="55143-357">HTTP 请求</span><span class="sxs-lookup"><span data-stu-id="55143-357">HTTP Request</span></span>

```http
GET https://config.office.com/api/filelist/channels 
```

<span data-ttu-id="55143-358">请勿提供此方法的请求正文。</span><span class="sxs-lookup"><span data-stu-id="55143-358">Do not supply a request body for this method.</span></span>

<span data-ttu-id="55143-359">调用此 API 不需要任何权限。</span><span class="sxs-lookup"><span data-stu-id="55143-359">No permissions are required to call this API.</span></span>

<span data-ttu-id="55143-360">HTTP 响应</span><span class="sxs-lookup"><span data-stu-id="55143-360">HTTP Response</span></span>

<span data-ttu-id="55143-361">如果成功，此方法在响应正文中返回 200 OK 响应代码和 file 对象集合。</span><span class="sxs-lookup"><span data-stu-id="55143-361">If successful, this method returns a 200 OK response code and collection of file objects in the response body.</span></span>

<span data-ttu-id="55143-362">**Sku API**</span><span class="sxs-lookup"><span data-stu-id="55143-362">**SKUs API**</span></span>
  
<span data-ttu-id="55143-363">Sku API 返回的信息可用于确定哪些产品可用于从 Office CDN 中进行部署和服务，以及每个产品的各种选项。</span><span class="sxs-lookup"><span data-stu-id="55143-363">The SKUs API returns information that is useful for determining which products are available for deployment and servicing from the Office CDN along with various options for each.</span></span>

<span data-ttu-id="55143-364">HTTP 请求</span><span class="sxs-lookup"><span data-stu-id="55143-364">HTTP Request</span></span>

```http
GET https://config.office.com/api/filelist/skus 
```

<span data-ttu-id="55143-365">请勿提供此方法的请求正文。</span><span class="sxs-lookup"><span data-stu-id="55143-365">Do not supply a request body for this method.</span></span>

<span data-ttu-id="55143-366">调用此 API 不需要任何权限。</span><span class="sxs-lookup"><span data-stu-id="55143-366">No permissions are required to call this API.</span></span>

<span data-ttu-id="55143-367">HTTP 响应</span><span class="sxs-lookup"><span data-stu-id="55143-367">HTTP Response</span></span>

<span data-ttu-id="55143-368">如果成功，此方法在响应正文中返回 200 OK 响应代码和 file 对象集合。</span><span class="sxs-lookup"><span data-stu-id="55143-368">If successful, this method returns a 200 OK response code and collection of file objects in the response body.</span></span>
