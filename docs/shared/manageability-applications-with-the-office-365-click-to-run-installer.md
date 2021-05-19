---
title: 将可管理性Microsoft 365 应用版与一键式安装程序集成
manager: lindalu
ms.date: 09/28/2020
ms.audience: ITPro
localization_priority: Normal
ms.assetid: c0fa8fed-1585-4566-a9be-ef6d6d1b4ce8
description: 了解如何将Microsoft 365 应用版即点即用安装程序与软件管理解决方案集成。
ms.openlocfilehash: eccd634f7906acf25b521ed2deb456ca914f37da
ms.sourcegitcommit: c8c51bd3f51c0a59fe44c014c8e56f1ba7c7aa03
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/28/2020
ms.locfileid: "48297312"
---
# <a name="integrating-manageability-applications-with-microsoft-365-apps-click-to-run-installer"></a><span data-ttu-id="24ce4-103">将可管理性Microsoft 365 应用版与一键式安装程序集成</span><span class="sxs-lookup"><span data-stu-id="24ce4-103">Integrating manageability applications with Microsoft 365 Apps Click-to-Run installer</span></span>

<span data-ttu-id="24ce4-104">了解如何将Microsoft 365 应用版即点即用安装程序与软件管理解决方案集成。</span><span class="sxs-lookup"><span data-stu-id="24ce4-104">Learn how to integrate the Microsoft 365 Apps Click-to-Run installer with a software management solution.</span></span>
  
<span data-ttu-id="24ce4-105">该Microsoft 365 应用版即点即用安装程序提供了 COM 接口，使 IT 专业人员和软件管理解决方案可以编程方式控制更新管理。</span><span class="sxs-lookup"><span data-stu-id="24ce4-105">The Microsoft 365 Apps Click-to-Run installer provides a COM interface that allows IT Professionals and software management solutions programmatic control over update management.</span></span> <span data-ttu-id="24ce4-106">此接口提供除 Office 工具提供的其他管理功能。</span><span class="sxs-lookup"><span data-stu-id="24ce4-106">This interface provides additional management capabilities beyond what is provided by the Office Deployment Tool.</span></span>
  
> [!NOTE]
> <span data-ttu-id="24ce4-107">本文适用于Office即点即用安装程序的应用。</span><span class="sxs-lookup"><span data-stu-id="24ce4-107">This article applies to Office apps that use the Click-to-Run installer.</span></span> 
  
## <a name="integrating-with-the-click-to-run"></a><span data-ttu-id="24ce4-108">与"单击运行"集成</span><span class="sxs-lookup"><span data-stu-id="24ce4-108">Integrating with the Click-to-Run</span></span>

<span data-ttu-id="24ce4-109">为了使用此接口，可管理性应用程序调用 COM 接口并调用直接与即点即用安装服务通信的公开的 API。</span><span class="sxs-lookup"><span data-stu-id="24ce4-109">To use this interface, a manageability application invokes the COM interface and calls exposed APIs that communicate directly with the Click-to-Run installation service.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="24ce4-110">The Office Click-to-Run installer can be run from the command-line with parameters that can control the behavior， as documented in [Office Deployment Tool for Click-to-Run](https://docs.microsoft.com/DeployOffice/overview-office-deployment-tool).</span><span class="sxs-lookup"><span data-stu-id="24ce4-110">The Office Click-to-Run installer can be run from the command-line with parameters that can control the behavior, as documented in [Office Deployment Tool for Click-to-Run](https://docs.microsoft.com/DeployOffice/overview-office-deployment-tool).</span></span> 
  
<span data-ttu-id="24ce4-111">**下面是 COM 接口的概念图**</span><span class="sxs-lookup"><span data-stu-id="24ce4-111">**Following is a conceptual diagram of the COM interface**</span></span>

<span data-ttu-id="24ce4-112">![在 Office 单击即运行安装程序上使用 COM 接口的图。](media/e7ac2523-e67b-4a44-ae67-c048709f872a.png "在&quot;单击到运行&quot;安装程序Office COM 接口的关系图")</span><span class="sxs-lookup"><span data-stu-id="24ce4-112">![A diagram of using the COM interface on  the Office Click-To-Run installer.](media/e7ac2523-e67b-4a44-ae67-c048709f872a.png "A diagram of using the COM interface on  the Office Click-To-Run installer")</span></span>
  
<span data-ttu-id="24ce4-113">即Microsoft 365 应用版即点即用安装程序实现基于 COM 的接口，**即** 注册到 CLSID CLSID_UpdateNotifyObject。</span><span class="sxs-lookup"><span data-stu-id="24ce4-113">The Microsoft 365 Apps Click-to-Run installer implements a COM-based interface, **IUpdateNotify** registered to CLSID **CLSID_UpdateNotifyObject**.</span></span>
  
<span data-ttu-id="24ce4-114">可以按如下方式调用此接口：</span><span class="sxs-lookup"><span data-stu-id="24ce4-114">This interface can be invoked as follows:</span></span>
  
```cpp
hr = CoCreateInstance(CLSID_UpdateNotifyObject, NULL, CLSCTX_ALL,
       IID_IUpdateNotify, 
      (void **)&p); 
```

<span data-ttu-id="24ce4-115">只有在呼叫者以提升的权限运行时，调用才能成功，因为即点即用安装程序必须使用提升的权限运行。</span><span class="sxs-lookup"><span data-stu-id="24ce4-115">The call will only succeed if the caller is running under elevated privileges, as the Click-to-Run installation program must be run with elevated privileges.</span></span>
  
<span data-ttu-id="24ce4-116">**IUpdateNotify** COM 接口公开了三个异步函数，这些函数负责验证命令和参数以及使用即点即用安装服务计划执行。</span><span class="sxs-lookup"><span data-stu-id="24ce4-116">The **IUpdateNotify** COM interface exposes three asynchronous functions responsible for validating the commands and parameters and scheduling execution with the Click-to-Run installation service.</span></span> 
  
```cpp
HRESULT Download([in] LPWSTR pcwszParameters) // Download update content.
HRESULT Apply([in] LPWSTR pcwszParameters) // Apply update content.
HRESULT Cancel() // Cancel the download action.

```

<span data-ttu-id="24ce4-117">前一个方法 **Status** 可用于获取有关上次执行的命令的状态或当前执行的命令的状态的信息 (例如成功、失败、详细的错误代码) 。</span><span class="sxs-lookup"><span data-stu-id="24ce4-117">A forth method, **Status**, can be used to get information about the status of the last executed command or the status of the currently executing command (i.e. success, failure, detailed error codes).</span></span>
  
```cpp
HRESULT status([out] _UPDATE_STATUS_REPORT* pUpdateStatusReport) // Get status of current action. 
typedef struct _UPDATE_STATUS_REPORT  
{  
UPDATE_STATUS status;  
UINT error; 
BSTR contentid;  
} UPDATE_STATUS_REPORT;

```

<span data-ttu-id="24ce4-118">即点即用安装服务在其生命周期内可能存在四种状态，在此期间可能会调用 **IUpdateNotify** 方法;正在重启、空闲、正在下载和应用。</span><span class="sxs-lookup"><span data-stu-id="24ce4-118">There are four states that the Click-to-Run installation service may be in during its lifecycle, during which **IUpdateNotify** methods may be called; Rebooting, Idle, Downloading and Applying.</span></span> 
  
<span data-ttu-id="24ce4-119">**下面是 COM 接口状态机图**</span><span class="sxs-lookup"><span data-stu-id="24ce4-119">**Following is the COM Interface State Machine diagram**</span></span>

<span data-ttu-id="24ce4-120">![COM 接口的状态图。](media/a409003e-6876-4ab3-bb4c-cd0c0fed5cbb.png "COM 接口的状态图")</span><span class="sxs-lookup"><span data-stu-id="24ce4-120">![A state diagram for the COM interface.](media/a409003e-6876-4ab3-bb4c-cd0c0fed5cbb.png "A state diagram for the COM interface")</span></span>
  
> [!NOTE]
> <span data-ttu-id="24ce4-121">**正在** 重新启动：当计算机启动时，有一段时间即点即用安装程序服务不可用。</span><span class="sxs-lookup"><span data-stu-id="24ce4-121">**Rebooting**: When the machine is booting there is a period of time when the Click-to-Run installer service is not available.</span></span> <span data-ttu-id="24ce4-122">重新启动后成功调用 Status 方法将返回eUPDATE_UNKNOWN。</span><span class="sxs-lookup"><span data-stu-id="24ce4-122">A successful call to the Status method after a reboot will return eUPDATE_UNKNOWN.</span></span> 
  
<span data-ttu-id="24ce4-123">**空闲：** 当 Click-to-Run 安装程序处于空闲状态时，你可以调用：</span><span class="sxs-lookup"><span data-stu-id="24ce4-123">**Idle:** When the Click-to-Run installer is in the idle state, you can call:</span></span> 
  
- <span data-ttu-id="24ce4-124">**应用**：安装之前下载的内容。</span><span class="sxs-lookup"><span data-stu-id="24ce4-124">**Apply**: Install previously downloaded content.</span></span>
    
- <span data-ttu-id="24ce4-125">**Cancel**： Returns  `0x800000e` ， "A method was called at an unexpected time."</span><span class="sxs-lookup"><span data-stu-id="24ce4-125">**Cancel**: Returns  `0x800000e`, "A method was called at an unexpected time."</span></span>
    
- <span data-ttu-id="24ce4-126">**下载**：将新内容下载到客户端以稍后安装。</span><span class="sxs-lookup"><span data-stu-id="24ce4-126">**Download**: Downloads new content to the client for later installation.</span></span>
    
- <span data-ttu-id="24ce4-127">**状态**：返回上一个已完成操作的结果，或返回一条错误消息（如果操作以失败结束）。</span><span class="sxs-lookup"><span data-stu-id="24ce4-127">**Status**: Returns the result of the last completed action, or an error message if the action ended in failure.</span></span> <span data-ttu-id="24ce4-128">如果之前没有操作 **，Status** 将返回  `eUPDATE_UNKNOWN` 。</span><span class="sxs-lookup"><span data-stu-id="24ce4-128">If there is no previous action, **Status** returns  `eUPDATE_UNKNOWN`.</span></span>
    
<span data-ttu-id="24ce4-129">**正在下载：** 当 Click-to-Run 安装程序位于下载状态时，你可以调用：</span><span class="sxs-lookup"><span data-stu-id="24ce4-129">**Downloading:** When the Click-to-Run installer is in the downloading state, you can call:</span></span> 
  
- <span data-ttu-id="24ce4-130">**Apply**：返回一 **个 HRESULT，** 值为  `0x800000e` "A method was called at an unexpected time."</span><span class="sxs-lookup"><span data-stu-id="24ce4-130">**Apply**: Returns an **HRESULT** with the value  `0x800000e`, "A method was called at an unexpected time."</span></span>
    
- <span data-ttu-id="24ce4-131">**取消**：停止下载并删除部分下载的内容。</span><span class="sxs-lookup"><span data-stu-id="24ce4-131">**Cancel**: Stops the download and removes the partially downloaded content.</span></span>
    
- <span data-ttu-id="24ce4-132">**下载**：返回一 **个 HRESULT，** 值为  `0x800000e` "A method was called at an unexpected time."</span><span class="sxs-lookup"><span data-stu-id="24ce4-132">**Download**: Returns an **HRESULT** with the value  `0x800000e`, "A method was called at an unexpected time."</span></span> 
    
- <span data-ttu-id="24ce4-133">**状态\*\*\*\*：DOWNLOAD_WIP，** 以指示下载工作正在进行。</span><span class="sxs-lookup"><span data-stu-id="24ce4-133">**Status**: Returns **DOWNLOAD_WIP** to indicate that download work is in progress.</span></span> 
    
<span data-ttu-id="24ce4-134">**应用：** 当"单击运行"安装程序正在安装之前下载的内容时：</span><span class="sxs-lookup"><span data-stu-id="24ce4-134">**Applying:** When the Click-to-Run installer is in the process of installing previously download content:</span></span> 
  
- <span data-ttu-id="24ce4-135">**Apply**：返回一 **个 HRESULT，** 值为  `0x800000e` "A method was called at an unexpected time."</span><span class="sxs-lookup"><span data-stu-id="24ce4-135">**Apply**: Returns an **HRESULT** with the value  `0x800000e`, "A method was called at an unexpected time."</span></span>
    
- <span data-ttu-id="24ce4-136">**Cancel**：返回  `0x800000e` ，无法取消 Apply 操作。</span><span class="sxs-lookup"><span data-stu-id="24ce4-136">**Cancel**: Returns  `0x800000e`, the Apply action cannot be canceled.</span></span>
    
- <span data-ttu-id="24ce4-137">**下载**：返回一 **个 HRESULT，** 值为  `0x800000e` "A method was called at an unexpected time."</span><span class="sxs-lookup"><span data-stu-id="24ce4-137">**Download**: Returns an **HRESULT** with the value  `0x800000e`, "A method was called at an unexpected time."</span></span> 
    
- <span data-ttu-id="24ce4-138">**Status**： returns **APPLY_WIP** to indicate that apply work is in progress.</span><span class="sxs-lookup"><span data-stu-id="24ce4-138">**Status**: Returns **APPLY_WIP** to indicate that apply work is in progress.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="24ce4-139">由于 OfficeC2RCOM 是一个 COM+ 服务且是动态加载的，因此每次在此类上调用方法时都需要调用 **CoCreateInstance，** 以确保获得预期的结果。</span><span class="sxs-lookup"><span data-stu-id="24ce4-139">Since OfficeC2RCOM is a COM+ service and is dynamically loaded, you need to call **CoCreateInstance** every time you call a method on this class to ensure that you get the expected result.</span></span> <span data-ttu-id="24ce4-140">COM+ 服务将在必要时处理创建新实例。</span><span class="sxs-lookup"><span data-stu-id="24ce4-140">The COM+ service will handle creating a new instance if necessary.</span></span> <span data-ttu-id="24ce4-141">当首次调用其中一个方法时，COM+ 将加载 **IUpdateNotify** 对象，并在其实例之一dllhost.exe它。</span><span class="sxs-lookup"><span data-stu-id="24ce4-141">When one of the methods is called for the first time, COM+ will load the **IUpdateNotify** object and run it within one of the dllhost.exe instances.</span></span> <span data-ttu-id="24ce4-142">新对象在空闲时将保持活动状态大约 3 分钟。</span><span class="sxs-lookup"><span data-stu-id="24ce4-142">The new object will stay active for about 3 minutes in idle.</span></span> <span data-ttu-id="24ce4-143">如果最后一次调用的三分钟内进行了后续调用， **则 IUpdateNotify** 对象将保持加载状态，并且不会创建一个新实例。</span><span class="sxs-lookup"><span data-stu-id="24ce4-143">If a subsequent call is made within three minutes of the last call, the **IUpdateNotify** object will remain loaded and a new instance is not created.</span></span> <span data-ttu-id="24ce4-144">如果在三分钟内未进行调用，将卸载 IUpdateNotify 对象，并且将在下一次调用时创建一个新的 **IUpdateNotify** 对象。</span><span class="sxs-lookup"><span data-stu-id="24ce4-144">If no call is made within three minutes, the IUpdateNotify object will be unloaded and a new **IUpdateNotify** object will be created when the next call is made.</span></span> 
  
## <a name="click-to-run-installer-com-api-reference-guide"></a><span data-ttu-id="24ce4-145">Click-to-Run installer COM API 参考指南</span><span class="sxs-lookup"><span data-stu-id="24ce4-145">Click-to-Run installer COM API reference guide</span></span>

<span data-ttu-id="24ce4-146">在下面的 API 参考文档中：</span><span class="sxs-lookup"><span data-stu-id="24ce4-146">In the following API reference documentation:</span></span>
  
- <span data-ttu-id="24ce4-147">参数采用键/值对格式，用空格分隔。</span><span class="sxs-lookup"><span data-stu-id="24ce4-147">Parameters are in a key/value pair format separated by a space.</span></span>
    
- <span data-ttu-id="24ce4-148">参数不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="24ce4-148">The parameters are not case-sensitive.</span></span>
    
- <span data-ttu-id="24ce4-149">有一 [个包含可用文档](https://blogs.technet.microsoft.com/odsupport/2014/03/03/the-new-update-now-feature-for-office-2013-click-to-run-for-office365-and-its-associated-command-line-and-switches/) 的参数列表。</span><span class="sxs-lookup"><span data-stu-id="24ce4-149">There is a [list of parameters](https://blogs.technet.microsoft.com/odsupport/2014/03/03/the-new-update-now-feature-for-office-2013-click-to-run-for-office365-and-its-associated-command-line-and-switches/) with documentation available.</span></span> 
    
- <span data-ttu-id="24ce4-150">现在包含 IUpdateNotify2 接口的摘要。</span><span class="sxs-lookup"><span data-stu-id="24ce4-150">Summary of IUpdateNotify2 interface is now included.</span></span>
    
### <a name="apply"></a><span data-ttu-id="24ce4-151">应用</span><span class="sxs-lookup"><span data-stu-id="24ce4-151">Apply</span></span>

```cpp
HRESULT Apply([in] LPWSTR pcwszParameters) // Apply update content.
```

#### <a name="parameters"></a><span data-ttu-id="24ce4-152">参数</span><span class="sxs-lookup"><span data-stu-id="24ce4-152">Parameters</span></span>

-  <span data-ttu-id="24ce4-153">_displaylevel_ **：true** 表示更新过程中安装状态（包括错误）; **false** 以在更新过程中隐藏安装状态（包括错误）。</span><span class="sxs-lookup"><span data-stu-id="24ce4-153">_displaylevel_: **true** to show the installation status, including errors, during the update process; **false** to hide the installation status, including errors, during the update process.</span></span> <span data-ttu-id="24ce4-154">默认值为 **false**。</span><span class="sxs-lookup"><span data-stu-id="24ce4-154">The default is **false**.</span></span>
    
-  <span data-ttu-id="24ce4-155">_forceappshutdown_：如果为 **true，Office** 应用在触发 **Apply** 操作时立即关闭;**如果** 任何应用程序正在运行，Office false。</span><span class="sxs-lookup"><span data-stu-id="24ce4-155">_forceappshutdown_: **true** to force Office applications to shut down immediately when the **Apply** action is triggered; **false** to fail if any Office applications are running.</span></span> <span data-ttu-id="24ce4-156">默认值为 **false**。</span><span class="sxs-lookup"><span data-stu-id="24ce4-156">The default is **false**.</span></span> <span data-ttu-id="24ce4-157">有关详细信息 [，](#bk_ApplyRemark) 请参阅"说明"。</span><span class="sxs-lookup"><span data-stu-id="24ce4-157">See [Remarks](#bk_ApplyRemark) for more information.</span></span> 
    
  <span data-ttu-id="24ce4-158">如果在Office **应用** 操作时应用程序正在运行，**则 Apply** 操作通常会失败。</span><span class="sxs-lookup"><span data-stu-id="24ce4-158">If any Office application is running when the **Apply** action is triggered, the **Apply** action will usually fail.</span></span> <span data-ttu-id="24ce4-159">传递到  `forceappshutdown=true` **Apply** 方法将导致 **OfficeClickToRun** 服务立即关闭应用程序并应用更新。</span><span class="sxs-lookup"><span data-stu-id="24ce4-159">Passing  `forceappshutdown=true` to the **Apply** method will cause the **OfficeClickToRun** service to immediately shut down the applications and apply the update.</span></span> <span data-ttu-id="24ce4-160">在这种情况下，用户可能会遇到数据丢失问题。</span><span class="sxs-lookup"><span data-stu-id="24ce4-160">The user may experience data loss in this case.</span></span> 
    
#### <a name="return-results"></a><span data-ttu-id="24ce4-161">返回结果</span><span class="sxs-lookup"><span data-stu-id="24ce4-161">Return results</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="24ce4-162">**S_OK**</span><span class="sxs-lookup"><span data-stu-id="24ce4-162">**S_OK**</span></span> <br/> |<span data-ttu-id="24ce4-163">操作已成功提交到即点即用服务以执行。</span><span class="sxs-lookup"><span data-stu-id="24ce4-163">Action was successfully submitted to the Click-To-Run service for execution.</span></span>  <br/> |
|<span data-ttu-id="24ce4-164">**E_ACCESSDENIED**</span><span class="sxs-lookup"><span data-stu-id="24ce4-164">**E_ACCESSDENIED**</span></span> <br/> |<span data-ttu-id="24ce4-165">调用方没有使用提升的权限运行。</span><span class="sxs-lookup"><span data-stu-id="24ce4-165">The caller is not running with elevated privileges.</span></span>  <br/> |
|<span data-ttu-id="24ce4-166">**E_INVALIDARG**</span><span class="sxs-lookup"><span data-stu-id="24ce4-166">**E_INVALIDARG**</span></span> <br/> |<span data-ttu-id="24ce4-167">传递的参数无效。</span><span class="sxs-lookup"><span data-stu-id="24ce4-167">Invalid parameters were passed.</span></span>  <br/> |
|<span data-ttu-id="24ce4-168">**E_ILLEGAL_METHOD_CALL**</span><span class="sxs-lookup"><span data-stu-id="24ce4-168">**E_ILLEGAL_METHOD_CALL**</span></span> <br/> |<span data-ttu-id="24ce4-169">目前不允许操作。</span><span class="sxs-lookup"><span data-stu-id="24ce4-169">Action is not allowed at this time.</span></span> <span data-ttu-id="24ce4-170">有关详细信息 [，](#bk_ApplyRemark) 请参阅"说明"。</span><span class="sxs-lookup"><span data-stu-id="24ce4-170">See [Remarks](#bk_ApplyRemark) for more information.</span></span>  <br/> |

<a name="bk_ApplyRemark"></a>

#### <a name="remarks"></a><span data-ttu-id="24ce4-171">备注</span><span class="sxs-lookup"><span data-stu-id="24ce4-171">Remarks</span></span>

- <span data-ttu-id="24ce4-172">如果在Office **应用** 操作时应用程序正在运行，**则 Apply** 操作将失败。</span><span class="sxs-lookup"><span data-stu-id="24ce4-172">If any Office application is running when the **Apply** action is triggered, the **Apply** action will fail.</span></span> <span data-ttu-id="24ce4-173">传递到 `forceappshutdown=true` **Apply** 方法将导致 **OfficeClickToRun** 服务立即关闭Office应用程序并应用更新的任何应用程序。</span><span class="sxs-lookup"><span data-stu-id="24ce4-173">Passing  `forceappshutdown=true` to the **Apply** method will cause the **OfficeClickToRun** service to immediately shut down any Office applications that are running and apply the update.</span></span> <span data-ttu-id="24ce4-174">用户可能会遇到数据，因为系统不会提示他们保存对打开的文档所做的更改。</span><span class="sxs-lookup"><span data-stu-id="24ce4-174">The user may experience data as they are not prompted to save changes to open documents..</span></span> 
    
- <span data-ttu-id="24ce4-175">只有当 COM 状态为以下状态之一时，才能触发此操作：</span><span class="sxs-lookup"><span data-stu-id="24ce4-175">This action can only be triggered when the COM status is one of the following:</span></span> 
    
  - <span data-ttu-id="24ce4-176">**eUPDATE_UNKNOWN**</span><span class="sxs-lookup"><span data-stu-id="24ce4-176">**eUPDATE_UNKNOWN**</span></span>
    
  - <span data-ttu-id="24ce4-177">**eDOWNLOAD_CANCELLED**</span><span class="sxs-lookup"><span data-stu-id="24ce4-177">**eDOWNLOAD_CANCELLED**</span></span>
    
  - <span data-ttu-id="24ce4-178">**eDOWNLOAD_FAILED**</span><span class="sxs-lookup"><span data-stu-id="24ce4-178">**eDOWNLOAD_FAILED**</span></span>
    
  - <span data-ttu-id="24ce4-179">**eDOWNLOAD_SUCCEEDED**</span><span class="sxs-lookup"><span data-stu-id="24ce4-179">**eDOWNLOAD_SUCCEEDED**</span></span>
    
  - <span data-ttu-id="24ce4-180">**eAPPLY_SUCCEEDED**</span><span class="sxs-lookup"><span data-stu-id="24ce4-180">**eAPPLY_SUCCEEDED**</span></span>
    
  - <span data-ttu-id="24ce4-181">**eAPPLY_FAILED**</span><span class="sxs-lookup"><span data-stu-id="24ce4-181">**eAPPLY_FAILED**</span></span>
    
- <span data-ttu-id="24ce4-182">如果在之前未下载内容的情况下调用 **Apply** 方法， **则 Apply** 方法将报告 **Succeeded，** 因为它未检测到任何要应用并且成功完成 **了应用** 过程。</span><span class="sxs-lookup"><span data-stu-id="24ce4-182">If you call the **Apply** method without previously downloading content, the **Apply** method will report **Succeeded** as it detected nothing to apply and completed the **Apply** process successfully.</span></span> 
    
### <a name="cancel"></a><span data-ttu-id="24ce4-183">取消</span><span class="sxs-lookup"><span data-stu-id="24ce4-183">Cancel</span></span>

```cpp
HRESULT Cancel() // Cancel the download action.
```

#### <a name="return-results"></a><span data-ttu-id="24ce4-184">返回结果</span><span class="sxs-lookup"><span data-stu-id="24ce4-184">Return results</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="24ce4-185">S_OK</span><span class="sxs-lookup"><span data-stu-id="24ce4-185">S_OK</span></span>  <br/> |<span data-ttu-id="24ce4-186">操作已成功提交到即点即用服务以执行。</span><span class="sxs-lookup"><span data-stu-id="24ce4-186">Action was successfully submitted to the Click-to-Run service for execution.</span></span>  <br/> |
|<span data-ttu-id="24ce4-187">E_ILLEGAL_METHOD_CALL</span><span class="sxs-lookup"><span data-stu-id="24ce4-187">E_ILLEGAL_METHOD_CALL</span></span>  <br/> |<span data-ttu-id="24ce4-188">目前不允许操作。</span><span class="sxs-lookup"><span data-stu-id="24ce4-188">Action is not allowed at this time.</span></span> <span data-ttu-id="24ce4-189">有关详细信息 [，请参阅](#bk_CancelRemarks) "备注"部分</span><span class="sxs-lookup"><span data-stu-id="24ce4-189">See the [Remarks](#bk_CancelRemarks) section for more information</span></span>  <br/> |

<a name="bk_CancelRemarks"></a>

#### <a name="remarks"></a><span data-ttu-id="24ce4-190">备注</span><span class="sxs-lookup"><span data-stu-id="24ce4-190">Remarks</span></span>

- <span data-ttu-id="24ce4-191">此方法只能在 COM 状态 ID 为 eDOWNLOAD_WIP 时 **触发**。</span><span class="sxs-lookup"><span data-stu-id="24ce4-191">This method can only be triggered when the COM status id **eDOWNLOAD_WIP**.</span></span> <span data-ttu-id="24ce4-192">它将尝试取消当前下载操作。</span><span class="sxs-lookup"><span data-stu-id="24ce4-192">It will attempt to cancel the current download action.</span></span> <span data-ttu-id="24ce4-193">COM 状态将更改为 eDOWNLOAD_CANCELLING **并最终更改为\*\*\*\*eDOWNLOAD_CANCELED**。</span><span class="sxs-lookup"><span data-stu-id="24ce4-193">The COM status will change to **eDOWNLOAD_CANCELLING** and eventually change to **eDOWNLOAD_CANCELED**.</span></span> <span data-ttu-id="24ce4-194">COM 状态将在任何其他 **E_ILLEGAL_METHOD_CALL** 触发时返回该状态。</span><span class="sxs-lookup"><span data-stu-id="24ce4-194">The COM status will return **E_ILLEGAL_METHOD_CALL** if triggered at any other time.</span></span> 
    
### <a name="download"></a><span data-ttu-id="24ce4-195">下载</span><span class="sxs-lookup"><span data-stu-id="24ce4-195">Download</span></span>

```cpp
HRESULT Download([in] LPWSTR pcwszParameters) // Download update content.
```

#### <a name="parameters"></a><span data-ttu-id="24ce4-196">参数</span><span class="sxs-lookup"><span data-stu-id="24ce4-196">Parameters</span></span>

-  <span data-ttu-id="24ce4-197">_displaylevel_ **：true** 表示更新过程中安装状态（包括错误）; **false** 以在更新过程中隐藏安装状态（包括错误）。</span><span class="sxs-lookup"><span data-stu-id="24ce4-197">_displaylevel_: **true** to show the installation status, including errors, during the update process; **false** to hide the installation status, including errors, during the update process.</span></span> <span data-ttu-id="24ce4-198">默认值为 **false**。</span><span class="sxs-lookup"><span data-stu-id="24ce4-198">The default is **false**.</span></span>
    
-  <span data-ttu-id="24ce4-199">_updatebaseurl_：备用下载源的 URL。</span><span class="sxs-lookup"><span data-stu-id="24ce4-199">_updatebaseurl_: URL to the alternate download source.</span></span>
    
-  <span data-ttu-id="24ce4-200">_updatetoversion_：要更新Office的版本。</span><span class="sxs-lookup"><span data-stu-id="24ce4-200">_updatetoversion_: The version to update Office to.</span></span> <span data-ttu-id="24ce4-201">如果要更新到比当前安装的版本更旧的版本，请定义此参数。</span><span class="sxs-lookup"><span data-stu-id="24ce4-201">Define this parameter if you want to update to an older version than the version that is currently installed.</span></span>
    
-  <span data-ttu-id="24ce4-202">_downloadsource_：BITS 管理器中自定义 **的 IBackgroundCopyManager** (CLSID) 。</span><span class="sxs-lookup"><span data-stu-id="24ce4-202">_downloadsource_: CLSID of the customized **IBackgroundCopyManager** implementation (BITS manager).</span></span> 
    
-  <span data-ttu-id="24ce4-203">_contentid：_ 标识要通过自定义 BITS 管理器从内容服务器下载的内容。</span><span class="sxs-lookup"><span data-stu-id="24ce4-203">_contentid_: Identifies the content to download from the content server through the customized BITS manager.</span></span> <span data-ttu-id="24ce4-204">此值通过 BITS 接口传递进行解释。</span><span class="sxs-lookup"><span data-stu-id="24ce4-204">This value is passed through the BITS interface for interpretation.</span></span>
    
#### <a name="return-results"></a><span data-ttu-id="24ce4-205">返回结果</span><span class="sxs-lookup"><span data-stu-id="24ce4-205">Return results</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="24ce4-206">**S_OK**</span><span class="sxs-lookup"><span data-stu-id="24ce4-206">**S_OK**</span></span> <br/> |<span data-ttu-id="24ce4-207">操作已成功提交到即点即用服务以执行。</span><span class="sxs-lookup"><span data-stu-id="24ce4-207">Action was successfully submitted to the Click-To-Run service for execution.</span></span>  <br/> |
|<span data-ttu-id="24ce4-208">**E_ACCESSDENIED**</span><span class="sxs-lookup"><span data-stu-id="24ce4-208">**E_ACCESSDENIED**</span></span> <br/> |<span data-ttu-id="24ce4-209">调用方没有使用提升的权限运行。</span><span class="sxs-lookup"><span data-stu-id="24ce4-209">The caller is not running with elevated privileges.</span></span>  <br/> |
|<span data-ttu-id="24ce4-210">**E_INVALIDARG**</span><span class="sxs-lookup"><span data-stu-id="24ce4-210">**E_INVALIDARG**</span></span> <br/> |<span data-ttu-id="24ce4-211">传递的参数无效。</span><span class="sxs-lookup"><span data-stu-id="24ce4-211">Invalid parameters were passed.</span></span>  <br/> |
|<span data-ttu-id="24ce4-212">**E_ILLEGAL_METHOD_CALL**</span><span class="sxs-lookup"><span data-stu-id="24ce4-212">**E_ILLEGAL_METHOD_CALL**</span></span> <br/> |<span data-ttu-id="24ce4-213">目前不允许操作。</span><span class="sxs-lookup"><span data-stu-id="24ce4-213">Action is not allowed at this time.</span></span> <span data-ttu-id="24ce4-214">有关详细信息 [，](#bk_DownloadRemark) 请参阅"说明"。</span><span class="sxs-lookup"><span data-stu-id="24ce4-214">See [Remarks](#bk_DownloadRemark) for more information.</span></span>  <br/> |

<a name="bk_DownloadRemark"></a>

#### <a name="remarks"></a><span data-ttu-id="24ce4-215">备注</span><span class="sxs-lookup"><span data-stu-id="24ce4-215">Remarks</span></span>

- <span data-ttu-id="24ce4-216">必须将  _downloadsource 和_  _contentid 指定为_ 对。</span><span class="sxs-lookup"><span data-stu-id="24ce4-216">You must specify  _downloadsource_ and  _contentid_ as a pair.</span></span> <span data-ttu-id="24ce4-217">如果没有，则 **Download** 方法 **将返回E_INVALIDARG** 错误。</span><span class="sxs-lookup"><span data-stu-id="24ce4-217">If not, the **Download** method will return an **E_INVALIDARG** error.</span></span> 
    
- <span data-ttu-id="24ce4-218">如果 _提供了 downloadsource、contentid_ 和 _updatebaseurl，__则 updatebaseurl_ 将被忽略。 </span><span class="sxs-lookup"><span data-stu-id="24ce4-218">If  _downloadsource_,  _contentid_, and  _updatebaseurl_ are provided,  _updatebaseurl_ will be ignored.</span></span> 
    
- <span data-ttu-id="24ce4-219">只有当 COM 状态为以下状态之一时，才能触发此操作：</span><span class="sxs-lookup"><span data-stu-id="24ce4-219">This action can only be triggered when the COM status is one of the following:</span></span> 
    
  - <span data-ttu-id="24ce4-220">**eUPDATE_UNKNOWN**</span><span class="sxs-lookup"><span data-stu-id="24ce4-220">**eUPDATE_UNKNOWN**</span></span>
    
  - <span data-ttu-id="24ce4-221">**eDOWNLOAD_CANCELLED**</span><span class="sxs-lookup"><span data-stu-id="24ce4-221">**eDOWNLOAD_CANCELLED**</span></span>
    
  - <span data-ttu-id="24ce4-222">**eDOWNLOAD_FAILED**</span><span class="sxs-lookup"><span data-stu-id="24ce4-222">**eDOWNLOAD_FAILED**</span></span>
    
  - <span data-ttu-id="24ce4-223">**eDOWNLOAD_SUCCEEDED**</span><span class="sxs-lookup"><span data-stu-id="24ce4-223">**eDOWNLOAD_SUCCEEDED**</span></span>
    
  - <span data-ttu-id="24ce4-224">**eAPPLY_SUCCEEDED**</span><span class="sxs-lookup"><span data-stu-id="24ce4-224">**eAPPLY_SUCCEEDED**</span></span>
    
  - <span data-ttu-id="24ce4-225">**eAPPLY_FAILED**</span><span class="sxs-lookup"><span data-stu-id="24ce4-225">**eAPPLY_FAILED**</span></span>
    
- <span data-ttu-id="24ce4-226">如果调用 **Apply** 方法时未下载之前的内容， **则 Apply** 方法将报告 **Succeeded，** 因为它未检测到应用任何内容，并且成功完成 **了应用** 过程。</span><span class="sxs-lookup"><span data-stu-id="24ce4-226">If you call the **Apply** method without previously downloaded content, the **Apply** method will report **Succeeded** as it detected nothing to apply and completed the **Apply** process successfully.</span></span> 
    
#### <a name="examples"></a><span data-ttu-id="24ce4-227">示例</span><span class="sxs-lookup"><span data-stu-id="24ce4-227">Examples</span></span>

- <span data-ttu-id="24ce4-228">若要从自定义 BITS 管理器下载内容：调用 **download ()** 函数，以传递以下参数：</span><span class="sxs-lookup"><span data-stu-id="24ce4-228">To download the content from the customized BITS manager: Call the **download()** function passing the following parameters:</span></span> 
    
  ```cpp
  "downloadsource=CLSIDofBITSInterface contentid=BITSServerContentIdentifier"
  ```

- <span data-ttu-id="24ce4-229">若要从网站下载Office 内容分发网络 (CDN) ：调用 **download ()** 函数，而不指定 _downloadsource、contentid_ 或 _updatebaseurl_ 参数。</span><span class="sxs-lookup"><span data-stu-id="24ce4-229">To download the content from the Office Content Delivery Network (CDN): Call the **download()** function without specifying the  _downloadsource_,  _contentid_, or  _updatebaseurl_ parameters.</span></span> 
    
- <span data-ttu-id="24ce4-230">若要从自定义位置下载内容：调用 **传递 ()** 参数的 download () 函数：</span><span class="sxs-lookup"><span data-stu-id="24ce4-230">To download the content from a customized location: Call the **download()** function passing the following parameter:</span></span> 
    
  ```cpp
  "updatebaseurl=yourcontentserverurl"
  ```

### <a name="status"></a><span data-ttu-id="24ce4-231">状态</span><span class="sxs-lookup"><span data-stu-id="24ce4-231">Status</span></span>

```cpp
typdef struct _UPDATE_STATUS_REPORT
{
    UPDATE_STATUS status;
    UINT error;
    LPCWSTR contentid;
}UPDATE_STATUS_REPORT;
HRESULT status([out] _UPDATE_STATUS_REPORT& pUpdateStatusReport) // Get status of current action
```

#### <a name="parameters"></a><span data-ttu-id="24ce4-232">参数</span><span class="sxs-lookup"><span data-stu-id="24ce4-232">Parameters</span></span>

|||
|:-----|:-----|
| <span data-ttu-id="24ce4-233">_pUpdateStatusReport_</span><span class="sxs-lookup"><span data-stu-id="24ce4-233">_pUpdateStatusReport_</span></span> <br/> |<span data-ttu-id="24ce4-234">指向结构UPDATE_STATUS_REPORT指针。</span><span class="sxs-lookup"><span data-stu-id="24ce4-234">Pointer to an UPDATE_STATUS_REPORT structure.</span></span>  <br/> |
   
#### <a name="return-results"></a><span data-ttu-id="24ce4-235">返回结果</span><span class="sxs-lookup"><span data-stu-id="24ce4-235">Return results</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="24ce4-236">**S_OK**</span><span class="sxs-lookup"><span data-stu-id="24ce4-236">**S_OK**</span></span> <br/> |<span data-ttu-id="24ce4-237">**Status** 方法始终返回此结果。</span><span class="sxs-lookup"><span data-stu-id="24ce4-237">The **Status** method always returns this result.</span></span> <span data-ttu-id="24ce4-238">检查  `UPDATE_STATUS_RESULT` 结构以检查当前操作的状态。</span><span class="sxs-lookup"><span data-stu-id="24ce4-238">Inspect the  `UPDATE_STATUS_RESULT` structure for the status of the current action.</span></span>  <br/> |
   
#### <a name="remarks"></a><span data-ttu-id="24ce4-239">备注</span><span class="sxs-lookup"><span data-stu-id="24ce4-239">Remarks</span></span>

- <span data-ttu-id="24ce4-240">的状态字段  `UPDATE_STATUS_REPORT` 包含当前操作的状态。</span><span class="sxs-lookup"><span data-stu-id="24ce4-240">The status field of the  `UPDATE_STATUS_REPORT` contains the status of the current action.</span></span> <span data-ttu-id="24ce4-241">返回以下状态值之一：</span><span class="sxs-lookup"><span data-stu-id="24ce4-241">One of the following status values is returned:</span></span> 
    
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

- <span data-ttu-id="24ce4-242">如果最后一个命令导致错误，则 的错误字段  `UPDATE_STATUS_REPORT` 包含有关错误的详细信息。</span><span class="sxs-lookup"><span data-stu-id="24ce4-242">If the last command resulted in an error, the error field of the  `UPDATE_STATUS_REPORT` contains detailed information about the error.</span></span> <span data-ttu-id="24ce4-243">Status 方法返回两种类型的 **错误** 代码。</span><span class="sxs-lookup"><span data-stu-id="24ce4-243">Two types of error codes are returned from the **Status** method.</span></span> 
    
- <span data-ttu-id="24ce4-244">如果错误小于  `UPDATE_ERROR_CODE::eUNKNOWN` ，则错误是以下预定义的错误代码之一：</span><span class="sxs-lookup"><span data-stu-id="24ce4-244">If the error less than  `UPDATE_ERROR_CODE::eUNKNOWN`, the error is one of the following pre-defined error codes:</span></span>
    
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

  <span data-ttu-id="24ce4-245">如果返回错误代码大于失败函数调用的 `UPDATE_ERROR_CODE::eUNKNOWN` **HRESULT。**</span><span class="sxs-lookup"><span data-stu-id="24ce4-245">If the return error code is larger than  `UPDATE_ERROR_CODE::eUNKNOWN` it is the **HRESULT** of a failed function call.</span></span> <span data-ttu-id="24ce4-246">从 的错误字段中返回的值中提取 HRESULT  `UPDATE_ERROR_CODE::eUNKNOWN`  `UPDATE_STATUS_REPORT` 减去 。</span><span class="sxs-lookup"><span data-stu-id="24ce4-246">To extract the HRESULT subtract  `UPDATE_ERROR_CODE::eUNKNOWN` from the value returned in the error field of the  `UPDATE_STATUS_REPORT`.</span></span>
    
  <span data-ttu-id="24ce4-247">通过检查 **IUpdateNotify 类型库中嵌入的 IUpdateNotify** 类型库，可以查看状态和错误值的完整OfficeC2RCom.dll。</span><span class="sxs-lookup"><span data-stu-id="24ce4-247">The complete list of status and error values can be viewed by inspecting the **IUpdateNotify** type library embedded in OfficeC2RCom.dll.</span></span> 
    
- <span data-ttu-id="24ce4-248">contentid 字段用于在 **启动 Download** 后调用 **Status，** 并返回传递到 Download 调用的 **contentid。**</span><span class="sxs-lookup"><span data-stu-id="24ce4-248">The contentid field is used for calls to **Status** after **Download** has initiated and returns the contentid that was passed in to the **Download** call.</span></span> <span data-ttu-id="24ce4-249">最佳做法是在调用 **Status** 方法之前将此字段初始化为 **null，** 然后在 **返回 Status** 后检查该值。</span><span class="sxs-lookup"><span data-stu-id="24ce4-249">It is a best practice to initialize this field to **null** before you call the **Status** method and then check the value after **Status** has been returned.</span></span> <span data-ttu-id="24ce4-250">如果值仍为 **null，** 则意味着没有要返回的 contentid。</span><span class="sxs-lookup"><span data-stu-id="24ce4-250">If the value is still **null**, that means there is no contentid to return.</span></span> <span data-ttu-id="24ce4-251">如果值不为 **null，** 则需要通过调用 **SysFreeString** () 释放它。</span><span class="sxs-lookup"><span data-stu-id="24ce4-251">If the value is not **null**, you need to free it with a call to **SysFreeString()**.</span></span> <span data-ttu-id="24ce4-252">下面是在下载后如何调用 **Status** 的代码 **段**。</span><span class="sxs-lookup"><span data-stu-id="24ce4-252">Here is a code snippet of how to call **Status** after **Download**.</span></span>
    
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

### <a name="summary-of-iupdatenotify2-interface"></a><span data-ttu-id="24ce4-253">IUpdateNotify2 接口摘要</span><span class="sxs-lookup"><span data-stu-id="24ce4-253">Summary of IUpdateNotify2 interface</span></span>

<span data-ttu-id="24ce4-254">从版本 [16.0.8208.6352] 我们添加了一个新的 **IUpdateNotify2** 接口。</span><span class="sxs-lookup"><span data-stu-id="24ce4-254">From version [16.0.8208.6352] we have added a new **IUpdateNotify2** interface.</span></span> 
  
- <span data-ttu-id="24ce4-255">CLSID_UpdateNotifyObject2，{52C2F9C2-F1AC-4021-BF50-756A5FA8DDFE}</span><span class="sxs-lookup"><span data-stu-id="24ce4-255">CLSID_UpdateNotifyObject2, {52C2F9C2-F1AC-4021-BF50-756A5FA8DDFE}</span></span>
    
- <span data-ttu-id="24ce4-256">此接口还托管了原始 IUpdateNotify 接口以提供向后兼容性。</span><span class="sxs-lookup"><span data-stu-id="24ce4-256">This interface also hosted the original IUpdateNotify interface to provide backward compatibility.</span></span> <span data-ttu-id="24ce4-257">这意味着如果使用此接口，则有权访问 **UpdateNotifyObject** 接口中提供的所有方法。</span><span class="sxs-lookup"><span data-stu-id="24ce4-257">Which means if you use this interface, you have access to all the methods provided in **UpdateNotifyObject** interface.</span></span> 
    
- <span data-ttu-id="24ce4-258">添加到 IUpdateNotify2 的新方法：</span><span class="sxs-lookup"><span data-stu-id="24ce4-258">New methods added to IUpdateNotify2:</span></span>
    
  - <span data-ttu-id="24ce4-259">**HRESULT** GetBlockingApps ([out] BSTR \* AppsList) 。</span><span class="sxs-lookup"><span data-stu-id="24ce4-259">**HRESULT** GetBlockingApps([out] BSTR \* AppsList).</span></span> <span data-ttu-id="24ce4-260">获取阻止应用的更新列表。</span><span class="sxs-lookup"><span data-stu-id="24ce4-260">Get updates blocking apps list.</span></span> <span data-ttu-id="24ce4-261">此调用将返回正在运行的Office应用，这些应用将阻止更新过程继续。</span><span class="sxs-lookup"><span data-stu-id="24ce4-261">This call will return running Office apps which will block the update process from proceeding.</span></span> 
    
  - <span data-ttu-id="24ce4-262">**HRESULT** GetOfficeDeploymentData ([in] int dataType， [in] **LPCWSTR** pcwszName， [out] BSTR \* OfficeData) 。</span><span class="sxs-lookup"><span data-stu-id="24ce4-262">**HRESULT** GetOfficeDeploymentData([in] int dataType, [in] **LPCWSTR** pcwszName, [out] BSTR \* OfficeData).</span></span> <span data-ttu-id="24ce4-263">获取Office数据。</span><span class="sxs-lookup"><span data-stu-id="24ce4-263">Get Office deployment Data.</span></span> 
    
- <span data-ttu-id="24ce4-264">如果要使用新方法，需要确保：</span><span class="sxs-lookup"><span data-stu-id="24ce4-264">If you want to use the new methods, you need to make sure:</span></span>
    
  - <span data-ttu-id="24ce4-265">你的 C2R 版本比上述内部版本更新 (六月 \> 分叉版本) 。</span><span class="sxs-lookup"><span data-stu-id="24ce4-265">Your C2R version is newer than the above build (\>= June fork build).</span></span>
    
  - <span data-ttu-id="24ce4-266">使用 UpdateNotifyObject2，而不是 **UpdateNotifyObject** 调用 **CoCreateInstance**。</span><span class="sxs-lookup"><span data-stu-id="24ce4-266">Use UpdateNotifyObject2, instead of **UpdateNotifyObject** to call **CoCreateInstance**.</span></span>
    
<span data-ttu-id="24ce4-267">如果不使用任何新方法，则无需更改任何内容。</span><span class="sxs-lookup"><span data-stu-id="24ce4-267">If you don't use any of the new methods, you don't need to change anything.</span></span> <span data-ttu-id="24ce4-268">所有现有方法将采用与以前完全相同的方式工作。</span><span class="sxs-lookup"><span data-stu-id="24ce4-268">All the existing methods will work as exact the same way as before.</span></span>
  
## <a name="implementing-the-bits-interface"></a><span data-ttu-id="24ce4-269">实现 BITS 接口</span><span class="sxs-lookup"><span data-stu-id="24ce4-269">Implementing the BITS interface</span></span>

<span data-ttu-id="24ce4-270">BACKGROUND [Intelligent Transfer Service](https://docs.microsoft.com/windows/win32/bits/background-intelligent-transfer-service-portal) (BITS) 是 Microsoft 提供的一项在客户端和服务器之间传输文件的服务。</span><span class="sxs-lookup"><span data-stu-id="24ce4-270">The [Background Intelligent Transfer Service](https://docs.microsoft.com/windows/win32/bits/background-intelligent-transfer-service-portal) (BITS) is a service provided by Microsoft to transfer files between a client and server.</span></span> <span data-ttu-id="24ce4-271">BITS 是即点即Office安装程序可用于下载内容的通道之一。</span><span class="sxs-lookup"><span data-stu-id="24ce4-271">BITS is one of the channels that Office Click-To-Run installer can use to download content.</span></span> <span data-ttu-id="24ce4-272">默认情况下，Microsoft 365 应用版即点即用安装程序使用 BITS Windows的内置实现来下载来自 CDN 的内容。</span><span class="sxs-lookup"><span data-stu-id="24ce4-272">By default, the Microsoft 365 Apps Click-To-Run installer uses the Windows' built in implementation of BITS to download the content from the CDN.</span></span> 
  
<span data-ttu-id="24ce4-273">通过向 **IUpdateNotify** 接口的 **()** 方法提供自定义 BITS 实现，您的可管理性软件可以控制客户端下载内容的地方和方式。</span><span class="sxs-lookup"><span data-stu-id="24ce4-273">By providing a customized BITS implementation to the **download()** method of the **IUpdateNotify** interface, your manageability software can control where and how the client downloads the content.</span></span> <span data-ttu-id="24ce4-274">自定义 BITS 接口在提供自定义内容分发通道（而非即点即用内置通道，如 CDN、IIS 服务器或文件共享）时很有用。</span><span class="sxs-lookup"><span data-stu-id="24ce4-274">A customized BITS interface is useful when providing a custom content distribution channel other than the Click-to-Run built-in channels, such as the CDN, IIS servers, or file shares.</span></span> 
  
<span data-ttu-id="24ce4-275">自定义 BITS 接口与 C2R 服务Office的最低要求是：</span><span class="sxs-lookup"><span data-stu-id="24ce4-275">The minimum requirement for a customized BITS interface to work with Office C2R service is:</span></span>
  
- <span data-ttu-id="24ce4-276">对于 **IBackgroundCopyManager**：</span><span class="sxs-lookup"><span data-stu-id="24ce4-276">For **IBackgroundCopyManager**:</span></span>
    
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

- <span data-ttu-id="24ce4-277">对于 **IBackgroundCopyJob**：</span><span class="sxs-lookup"><span data-stu-id="24ce4-277">For **IBackgroundCopyJob**:</span></span>
    
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

- <span data-ttu-id="24ce4-278">对于 **IBackgroundCopyJob3**：</span><span class="sxs-lookup"><span data-stu-id="24ce4-278">For **IBackgroundCopyJob3**:</span></span>
    
  ```cpp
  HRESULT _stdcall AddFileWithRanges(
                      [in] LPWSTR RemoteUrl, 
                      [in] LPWSTR LocalName,
                      [in] DWORD RangeCount,
                      [in] BG_FILE_RANGE Ranges[])
  
  ```

- <span data-ttu-id="24ce4-279">对于  `Addfile` 和  `AddFileWithRanges` 函数，远程 URL 的格式如下：</span><span class="sxs-lookup"><span data-stu-id="24ce4-279">For the  `Addfile` and  `AddFileWithRanges` functions, the remote URL is in the following format:</span></span> 
    
  ```cpp
  cmbits://<contentid>/<relative path to target file>
  ```

  - <span data-ttu-id="24ce4-280">cmbits 是硬编码的，代表自定义 BITS。</span><span class="sxs-lookup"><span data-stu-id="24ce4-280">cmbits is hard coded, and stands for customized BITS.</span></span>
    
  -  <span data-ttu-id="24ce4-281">_\<contentid\>_ 是 Download () **的**_contentid_ 参数。</span><span class="sxs-lookup"><span data-stu-id="24ce4-281">_\<contentid\>_ is the  _contentid_ parameter for the **Download()** method.</span></span> 
    
  -  <span data-ttu-id="24ce4-282">_\<relative path to target file\>_ 提供要下载的文件的位置和文件名。</span><span class="sxs-lookup"><span data-stu-id="24ce4-282">_\<relative path to target file\>_ provides the location and file name of the file to download.</span></span> 
    
    <span data-ttu-id="24ce4-283">例如，如果你向 Download () 方法提供了 的 _contentid，_ 并且 Office C2R 想要下载版本的 cab 文件（如文件），它将使用以下内容调用 `f732af58-5d86-4299-abe9-7595c35136ef`  `v32.cab` **AddFile** `RemoteUrl` () ：</span><span class="sxs-lookup"><span data-stu-id="24ce4-283">For example, if you have provided a  _contentid_ of  `f732af58-5d86-4299-abe9-7595c35136ef` to the **Download()** method, and Office C2R wants to download the version cab file, such as  `v32.cab` file, it will call **AddFile()** with the following  `RemoteUrl`:</span></span>
    
  ```cpp
  cmbits://f732af58-5d86-4299-abe9-7595c35136ef/Office/Data/V32.cab
  ```

- <span data-ttu-id="24ce4-284">对于 **IBackgroundCopyError**：</span><span class="sxs-lookup"><span data-stu-id="24ce4-284">For **IBackgroundCopyError**:</span></span>
    
  ```cpp
  HRESULT _stdcall GetErrorDescription(
        [in]  DWORD  LanguageId,
        [out] LPWSTR *ppErrorDescription);
  
  ```

- <span data-ttu-id="24ce4-285">对于 **IBackgroundCopyFile**：</span><span class="sxs-lookup"><span data-stu-id="24ce4-285">For **IBackgroundCopyFile**:</span></span>
    
  ```cpp
  HRESULT _stdcall GetLocalName([out] LPWSTR *ppName); 
  HRESULT _stdcall GetRemoteName([out] LPWSTR *ppName);
  
  ```
## <a name="automating-content-staging"></a><span data-ttu-id="24ce4-286">自动执行内容暂存</span><span class="sxs-lookup"><span data-stu-id="24ce4-286">Automating content staging</span></span>

<span data-ttu-id="24ce4-287">IT 管理员可以选择启用桌面客户端，以在直接从 CDN时自动接收更新，也可以选择使用 Office 部署工具或 Microsoft Endpoint Configuration Manager 控制更新频道提供的更新的部署。</span><span class="sxs-lookup"><span data-stu-id="24ce4-287">IT administrators can choose to have desktop clients enabled to automatically receive updates when they are available directly from the CDN or they can choose to control the deployment of updates available from the update channels using the Office Deployment Tool or Microsoft Endpoint Configuration Manager.</span></span>
  
<span data-ttu-id="24ce4-288">该服务支持管理工具在更新可用时识别并自动下载内容。</span><span class="sxs-lookup"><span data-stu-id="24ce4-288">The service supports the ability for management tools to recognize and automate the download of the content when updates are made available.</span></span>
  
<span data-ttu-id="24ce4-289">**下图概述了如何下载自定义映像**</span><span class="sxs-lookup"><span data-stu-id="24ce4-289">**The following image is an overview of downloading a custom image**</span></span>

<span data-ttu-id="24ce4-290">![在 Office 单击即运行安装程序上使用 COM 接口的图。](media/e7ac2523-e67b-4a44-ae67-c048709f872a.png "在&quot;单击到运行&quot;安装程序Office COM 接口的关系图")</span><span class="sxs-lookup"><span data-stu-id="24ce4-290">![A diagram of using the COM interface on  the Office Click-To-Run installer.](media/e7ac2523-e67b-4a44-ae67-c048709f872a.png "A diagram of using the COM interface on the Office Click-To-Run installer")</span></span>
  
### <a name="overview-of-downloading-a-custom-image"></a><span data-ttu-id="24ce4-291">下载自定义映像概述</span><span class="sxs-lookup"><span data-stu-id="24ce4-291">Overview of downloading a custom image</span></span>
  
<span data-ttu-id="24ce4-292">在上图中，可以看到新Microsoft 365 应用版图像可用于CDN。</span><span class="sxs-lookup"><span data-stu-id="24ce4-292">In the previous diagram, you see that a new Microsoft 365 Apps image is available on the CDN.</span></span> <span data-ttu-id="24ce4-293">除了Microsoft 365 应用版映像外，API 也可用，该 API 具有启用可管理性软件以直接创建自定义映像所需的信息，无需使用 Office 部署工具。</span><span class="sxs-lookup"><span data-stu-id="24ce4-293">Along with the Microsoft 365 Apps image, an API is available which has the information needed to enable manageability software to directly create customized images replacing the need for using the Office Deployment Tool.</span></span>

<span data-ttu-id="24ce4-294">企业将其 WSUS 配置为同步Microsoft 365 应用版更新。</span><span class="sxs-lookup"><span data-stu-id="24ce4-294">An enterprise configures their WSUS to sync the Microsoft 365 Apps updates.</span></span> <span data-ttu-id="24ce4-295">这些更新不包含实际的图像有效负载，但允许可管理性软件识别新内容何时可用。</span><span class="sxs-lookup"><span data-stu-id="24ce4-295">These updates do not contain the actual image payload but does allow the manageability software to recognize when new content is available.</span></span> <span data-ttu-id="24ce4-296">然后，可管理性软件可以读取 Microsoft 365 应用版 Update 元数据，以了解此更新Office版本。</span><span class="sxs-lookup"><span data-stu-id="24ce4-296">The manageability software can then read the Microsoft 365 Apps Update metadata to understand what version of Office the update applies to.</span></span>

<span data-ttu-id="24ce4-297">如果更新适用，可管理性软件可以使用 CDN 内容和文件列表创建自定义映像，并存储到配置为使用的文件共享位置。</span><span class="sxs-lookup"><span data-stu-id="24ce4-297">If the update is applicable, the manageability software can use the CDN content and the file list to create the custom image and store it onto the file share location that it is configured to use.</span></span>
  
### <a name="using-the-microsoft-365-apps-file-list-api"></a><span data-ttu-id="24ce4-298">使用Microsoft 365 应用版列表 API</span><span class="sxs-lookup"><span data-stu-id="24ce4-298">Using the Microsoft 365 Apps file list API</span></span>

<span data-ttu-id="24ce4-299">文件Microsoft 365 应用版 API 用于检索特定文件更新所需的Microsoft 365 应用版名称。</span><span class="sxs-lookup"><span data-stu-id="24ce4-299">The Microsoft 365 Apps file list API is used to retrieve the names of the files needed for a particular Microsoft 365 Apps update.</span></span>

<span data-ttu-id="24ce4-300">HTTP 请求</span><span class="sxs-lookup"><span data-stu-id="24ce4-300">HTTP Request</span></span>

<span data-ttu-id="24ce4-301">获取 https://config.office.com/api/filelist</span><span class="sxs-lookup"><span data-stu-id="24ce4-301">GET https://config.office.com/api/filelist</span></span>

<span data-ttu-id="24ce4-302">请勿提供此方法的请求正文。</span><span class="sxs-lookup"><span data-stu-id="24ce4-302">Do not supply a request body for this method.</span></span>

<span data-ttu-id="24ce4-303">调用此 API 不需要任何权限。</span><span class="sxs-lookup"><span data-stu-id="24ce4-303">No permissions are required to call this API.</span></span>

<span data-ttu-id="24ce4-304">可选的查询参数</span><span class="sxs-lookup"><span data-stu-id="24ce4-304">Optional query parameters</span></span>

|<span data-ttu-id="24ce4-305">**名称**</span><span class="sxs-lookup"><span data-stu-id="24ce4-305">**Name**</span></span>|<span data-ttu-id="24ce4-306">**说明**</span><span class="sxs-lookup"><span data-stu-id="24ce4-306">**Description**</span></span>|
|:-----|:-----|
| <span data-ttu-id="24ce4-307">channel</span><span class="sxs-lookup"><span data-stu-id="24ce4-307">channel</span></span> <br/>| <span data-ttu-id="24ce4-308">指定频道名称</span><span class="sxs-lookup"><span data-stu-id="24ce4-308">Specifies the channel name</span></span>  <br/> <span data-ttu-id="24ce4-309">可选 – 默认为"SemiAnnual"</span><span class="sxs-lookup"><span data-stu-id="24ce4-309">Optional – default to ‘SemiAnnual’</span></span> <br/> <span data-ttu-id="24ce4-310">支持的值 https://docs.microsoft.com/DeployOffice/office-deployment-tool-configuration-options#channel-attribute-part-of-add-element</span><span class="sxs-lookup"><span data-stu-id="24ce4-310">Supported values https://docs.microsoft.com/DeployOffice/office-deployment-tool-configuration-options#channel-attribute-part-of-add-element</span></span> |
| <span data-ttu-id="24ce4-311">version</span><span class="sxs-lookup"><span data-stu-id="24ce4-311">version</span></span> <br/>| <span data-ttu-id="24ce4-312">指定更新版本</span><span class="sxs-lookup"><span data-stu-id="24ce4-312">Specifies the update version</span></span> <br/> <span data-ttu-id="24ce4-313">可选 – 默认为可用于指定频道的最新版本</span><span class="sxs-lookup"><span data-stu-id="24ce4-313">Optional – defaults to the latest version available for the specified channel</span></span> |
| <span data-ttu-id="24ce4-314">arch</span><span class="sxs-lookup"><span data-stu-id="24ce4-314">arch</span></span> <br/>| <span data-ttu-id="24ce4-315">指定客户端体系结构</span><span class="sxs-lookup"><span data-stu-id="24ce4-315">Specifies client architecture</span></span> <br/> <span data-ttu-id="24ce4-316">可选 – 默认为"x64"</span><span class="sxs-lookup"><span data-stu-id="24ce4-316">Optional – defaults to ‘x64’</span></span> <br/> <span data-ttu-id="24ce4-317">支持的值：x64、x86</span><span class="sxs-lookup"><span data-stu-id="24ce4-317">Supported values: x64, x86</span></span> |
| <span data-ttu-id="24ce4-318">一个</span><span class="sxs-lookup"><span data-stu-id="24ce4-318">lid</span></span> <br/>| <span data-ttu-id="24ce4-319">指定要包含的语言文件</span><span class="sxs-lookup"><span data-stu-id="24ce4-319">Specifies the language files to include</span></span> <br/> <span data-ttu-id="24ce4-320">可选 – 默认为无</span><span class="sxs-lookup"><span data-stu-id="24ce4-320">Optional – defaults to none</span></span> <br/> <span data-ttu-id="24ce4-321">若要指定多种语言，请包含每种语言的一个盖查询参数</span><span class="sxs-lookup"><span data-stu-id="24ce4-321">To specify multiple languages, include an lid query parameter for each language</span></span> <br/> <span data-ttu-id="24ce4-322">使用语言标识符格式，例如</span><span class="sxs-lookup"><span data-stu-id="24ce4-322">Use the language identifier format, ex.</span></span> <span data-ttu-id="24ce4-323">"en-us"、"fr-fr"</span><span class="sxs-lookup"><span data-stu-id="24ce4-323">‘en-us’, ‘fr-fr’</span></span> |
| <span data-ttu-id="24ce4-324">alllanguages</span><span class="sxs-lookup"><span data-stu-id="24ce4-324">alllanguages</span></span> <br/>| <span data-ttu-id="24ce4-325">指定包括所有语言文件</span><span class="sxs-lookup"><span data-stu-id="24ce4-325">Specifies to include all language files</span></span> <br/> <span data-ttu-id="24ce4-326">可选 – 默认为 false</span><span class="sxs-lookup"><span data-stu-id="24ce4-326">Optional – defaults to false</span></span> |

<span data-ttu-id="24ce4-327">HTTP 响应</span><span class="sxs-lookup"><span data-stu-id="24ce4-327">HTTP Response</span></span>

<span data-ttu-id="24ce4-328">如果成功，此方法在响应正文中返回 200 OK 响应代码和 file 对象集合。</span><span class="sxs-lookup"><span data-stu-id="24ce4-328">If successful, this method returns a 200 OK response code and collection of file objects in the response body.</span></span>

<span data-ttu-id="24ce4-329">若要创建映像，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="24ce4-329">To create an image, follow these steps:</span></span>
1.  <span data-ttu-id="24ce4-330">调用 API，为感兴趣的更新的通道、版本和体系结构提供适当的查询参数。</span><span class="sxs-lookup"><span data-stu-id="24ce4-330">Call the API, providing the appropriate query parameters for the channel, version and architecture of the update you are interested in.</span></span>
<span data-ttu-id="24ce4-331">注意：属性为"lcid"："0"的 File 对象是中性语言文件，必须包含在映像中。</span><span class="sxs-lookup"><span data-stu-id="24ce4-331">Note: File objects with the attribute "lcid": "0" are language neutral files and must be included in the image.</span></span>
2.  <span data-ttu-id="24ce4-332">通过访问文件对象并复制 CDN 文件来构造 CDN 的本地映像，同时创建由为每个文件对象定义的"relativePath"属性指定的文件夹结构。</span><span class="sxs-lookup"><span data-stu-id="24ce4-332">Construct a local image of the CDN by iterating through the file objects and copying the CDN files, while creating the folder structure as specified by the “relativePath” attribute defined for each of the file objects.</span></span>

<span data-ttu-id="24ce4-333">以下示例检索 64bit 的当前频道和版本 16.0.4229.1004 的文件列表，并包括法语和英语语言文件：</span><span class="sxs-lookup"><span data-stu-id="24ce4-333">The following example retrieves the file list for the Current Channel and version 16.0.4229.1004 for 64bit and includes the French and English language files:</span></span>

```http
Get https://config.office.com/api/filelist?Channel=Current&Version=16.0.4229.1004&Arch=x64&Lid=fr-fr&Lid=en-US
```

### <a name="hash-verification-of-dat-files"></a><span data-ttu-id="24ce4-334">.dat 文件的哈希验证</span><span class="sxs-lookup"><span data-stu-id="24ce4-334">Hash verification of .dat files</span></span>

<span data-ttu-id="24ce4-335">映像创建工具可能会通过将计算哈希值与提供的与每个 .dat 文件关联的哈希值进行比较来验证下载的 .dat 文件的完整性。</span><span class="sxs-lookup"><span data-stu-id="24ce4-335">Image creation tools may verify the integrity of the downloaded .dat files by comparing a computed hash value with the supplied hash value associated with each of the .dat files.</span></span> <span data-ttu-id="24ce4-336">下面是指定 hashLocation 和 hashAlgorithm 值的文件对象的示例：</span><span class="sxs-lookup"><span data-stu-id="24ce4-336">Following is an example of a file object that specifies hashLocation and hashAlgorithm values:</span></span>
  
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

- <span data-ttu-id="24ce4-337">**hashLocation** 属性指定包含哈希值的.cab文件的相对路径位置。</span><span class="sxs-lookup"><span data-stu-id="24ce4-337">The **hashLocation** attribute specifies the relative path location of .cab file that contains the hash value.</span></span> <span data-ttu-id="24ce4-338">通过连接 URL + relativePath + hashLocation 构造哈希文件位置。</span><span class="sxs-lookup"><span data-stu-id="24ce4-338">Construct the hash file location by concatenating URL + relativePath + hashLocation.</span></span> <span data-ttu-id="24ce4-339">在下面的示例中，stream.x64.bg-bg.hash 位置为：</span><span class="sxs-lookup"><span data-stu-id="24ce4-339">In the following example, the stream.x64.bg-bg.hash location would be:</span></span> 
    
  ```http
  https://officecdn.microsoft.com/pr/492350f6-3a01-4f97-b9c0-c7c6ddf67d60/office/data/16.0.4229.1004/s641026.cab/stream.x64.bg-bg.hash 
  ```

- <span data-ttu-id="24ce4-340">**hashAlgorithm** 属性指定使用的哈希算法。</span><span class="sxs-lookup"><span data-stu-id="24ce4-340">The **hashAlgorithm** attribute specifies what hashing algorithm was used.</span></span> 
    
  <span data-ttu-id="24ce4-341">若要验证 stream.x64.bg-bg.dat 文件的完整性，请打开 stream.x64.bg-bg.hash 并读取 HASH 值，它是哈希文件的第一行文本。</span><span class="sxs-lookup"><span data-stu-id="24ce4-341">To validate the integrity of the stream.x64.bg-bg.dat file, open the stream.x64.bg-bg.hash and read the HASH value which is the first line of text in the hash file.</span></span> <span data-ttu-id="24ce4-342">将此与使用指定的哈希算法 (哈希值值进行比较) 验证下载的 .dat 文件的完整性。</span><span class="sxs-lookup"><span data-stu-id="24ce4-342">Compare this to the computed hash value (using the specified hashing algorithm) to verify the integrity of the downloaded .dat file.</span></span>
    
  <span data-ttu-id="24ce4-343">以下示例显示用于C#哈希的代码。</span><span class="sxs-lookup"><span data-stu-id="24ce4-343">The following example shows the C# code to read the hash.</span></span>
    
  ```cs
    string[] readHashes = System.IO.File.ReadAllLines(tmpFile, Encoding.Unicode);
    string readHash = readHashes.First();
  ```

### <a name="microsoft-365-apps-updates"></a><span data-ttu-id="24ce4-344">Microsoft 365 应用版更新</span><span class="sxs-lookup"><span data-stu-id="24ce4-344">Microsoft 365 Apps Updates</span></span>

<span data-ttu-id="24ce4-345">所有Microsoft 365 应用版更新都发布到[Microsoft 更新目录](https://www.catalog.update.microsoft.com/Search.aspx?q=office+365+client)。</span><span class="sxs-lookup"><span data-stu-id="24ce4-345">All Microsoft 365 Apps Updates are published to the [Microsoft Update Catalog](https://www.catalog.update.microsoft.com/Search.aspx?q=office+365+client).</span></span>
  
<span data-ttu-id="24ce4-346">Microsoft 365 应用版更新使可管理性软件Microsoft 365 应用版处理更新的方式与任何其他 WU 更新非常类似，只有一个例外;客户端更新不包含实际有效负载。</span><span class="sxs-lookup"><span data-stu-id="24ce4-346">Microsoft 365 Apps Updates enable manageability software to treat Microsoft 365 Apps Updates in a manner very similar to any other WU update with one exception; the client updates do not contain an actual payload.</span></span> <span data-ttu-id="24ce4-347">该Microsoft 365 应用版更新不应安装在任何客户端上，而应该用于使用可管理性软件触发工作流，将安装命令替换为上述基于 COM 的安装机制。</span><span class="sxs-lookup"><span data-stu-id="24ce4-347">The Microsoft 365 Apps Updates should not be installed on any clients but rather used to trigger the workflows with the manageability software replacing the installation command with the COM based installation mechanism shown above.</span></span>

<span data-ttu-id="24ce4-348">**下图显示了客户端更新Office 365的图表。**</span><span class="sxs-lookup"><span data-stu-id="24ce4-348">**The following figure shows a diagram of the Office 365 Client Update workflow.**</span></span>

<span data-ttu-id="24ce4-349">![O365PP 客户端更新的工作流图。](media/bc8092b0-62b8-402c-a5c0-04d55cca01d4.png "O365PP 客户端更新的工作流关系图")</span><span class="sxs-lookup"><span data-stu-id="24ce4-349">![Workflow diagram for O365PP client updates.](media/bc8092b0-62b8-402c-a5c0-04d55cca01d4.png "Workflow diagram for O365PP client updates")</span></span>
  
<span data-ttu-id="24ce4-350">发布的Microsoft 365 应用版更新包括有关更新的元数据。</span><span class="sxs-lookup"><span data-stu-id="24ce4-350">Each Microsoft 365 Apps Update that is published includes metadata about the update.</span></span> <span data-ttu-id="24ce4-351">此元数据包括一个称为 MoreInfoUrl 的参数，该参数可用于将 API 调用派生到特定更新的文件列表 API。</span><span class="sxs-lookup"><span data-stu-id="24ce4-351">This metadata includes a parameter called MoreInfoUrl which can be used to derive the API call to the file list API for that specific update.</span></span>

<span data-ttu-id="24ce4-352">在下面的示例中，文件列表 API 嵌入到 MoreInfoURL 中，以"ServicePath="开头。</span><span class="sxs-lookup"><span data-stu-id="24ce4-352">In the following example, the file list API is embedded in the MoreInfoURL and starts with “ServicePath=”</span></span>

<span data-ttu-id="24ce4-353"> http://go.microsoft.com/fwlink/?LinkId=626090&Ver=16.0.12527.21104&Branch=Insiders&Arch=64&XMLVer=1.6&xmlPath=http://officecdn.microsoft.com/pr/wsus/ofl.cab&xmlFile=O365Client_64bit.xml& ServicePath=https://config.office.com/api/filelist?Channel=Insiders&Version=16.0.12527.21104&Arch=64&AllLanguages=True</span><span class="sxs-lookup"><span data-stu-id="24ce4-353">http://go.microsoft.com/fwlink/?LinkId=626090&Ver=16.0.12527.21104&Branch=Insiders&Arch=64&XMLVer=1.6&xmlPath=http://officecdn.microsoft.com/pr/wsus/ofl.cab&xmlFile=O365Client_64bit.xml& ServicePath=https://config.office.com/api/filelist?Channel=Insiders&Version=16.0.12527.21104&Arch=64&AllLanguages=True</span></span>
  
### <a name="additional-metadata-for-automating-content-staging"></a><span data-ttu-id="24ce4-354">用于自动执行内容暂存的其他元数据</span><span class="sxs-lookup"><span data-stu-id="24ce4-354">Additional metadata for automating content staging</span></span>

<span data-ttu-id="24ce4-355">**版本历史记录 API**</span><span class="sxs-lookup"><span data-stu-id="24ce4-355">**Release History API**</span></span>
  
<span data-ttu-id="24ce4-356">发布Microsoft 365 应用版 API 用于检索发布到该版本的每个更新的详细信息CDN通道名称和其他通道属性。</span><span class="sxs-lookup"><span data-stu-id="24ce4-356">The Microsoft 365 Apps release history API is used to retrieve details for each of the updates published to the CDN along with the channel names and other channel attributes.</span></span>

<span data-ttu-id="24ce4-357">HTTP 请求</span><span class="sxs-lookup"><span data-stu-id="24ce4-357">HTTP Request</span></span>

```http
GET https://config.office.com/api/filelist/channels 
```

<span data-ttu-id="24ce4-358">请勿提供此方法的请求正文。</span><span class="sxs-lookup"><span data-stu-id="24ce4-358">Do not supply a request body for this method.</span></span>

<span data-ttu-id="24ce4-359">调用此 API 不需要任何权限。</span><span class="sxs-lookup"><span data-stu-id="24ce4-359">No permissions are required to call this API.</span></span>

<span data-ttu-id="24ce4-360">HTTP 响应</span><span class="sxs-lookup"><span data-stu-id="24ce4-360">HTTP Response</span></span>

<span data-ttu-id="24ce4-361">如果成功，此方法在响应正文中返回 200 OK 响应代码和 file 对象集合。</span><span class="sxs-lookup"><span data-stu-id="24ce4-361">If successful, this method returns a 200 OK response code and collection of file objects in the response body.</span></span>

<span data-ttu-id="24ce4-362">**SKUs API**</span><span class="sxs-lookup"><span data-stu-id="24ce4-362">**SKUs API**</span></span>
  
<span data-ttu-id="24ce4-363">SKUs API 返回的信息可用于确定哪些产品可用于从 Office CDN部署和维护，以及每种产品的各种选项。</span><span class="sxs-lookup"><span data-stu-id="24ce4-363">The SKUs API returns information that is useful for determining which products are available for deployment and servicing from the Office CDN along with various options for each.</span></span>

<span data-ttu-id="24ce4-364">HTTP 请求</span><span class="sxs-lookup"><span data-stu-id="24ce4-364">HTTP Request</span></span>

```http
GET https://config.office.com/api/filelist/skus 
```

<span data-ttu-id="24ce4-365">请勿提供此方法的请求正文。</span><span class="sxs-lookup"><span data-stu-id="24ce4-365">Do not supply a request body for this method.</span></span>

<span data-ttu-id="24ce4-366">调用此 API 不需要任何权限。</span><span class="sxs-lookup"><span data-stu-id="24ce4-366">No permissions are required to call this API.</span></span>

<span data-ttu-id="24ce4-367">HTTP 响应</span><span class="sxs-lookup"><span data-stu-id="24ce4-367">HTTP Response</span></span>

<span data-ttu-id="24ce4-368">如果成功，此方法在响应正文中返回 200 OK 响应代码和 file 对象集合。</span><span class="sxs-lookup"><span data-stu-id="24ce4-368">If successful, this method returns a 200 OK response code and collection of file objects in the response body.</span></span>
