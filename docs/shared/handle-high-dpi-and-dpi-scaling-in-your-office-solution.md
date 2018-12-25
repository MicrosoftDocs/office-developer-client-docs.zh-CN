---
title: 在 Office 解决方案中处理高 DPI 和 DPI 缩放
description: 更新 Office 解决方案（如自定义任务窗格或 ActiveX 控件）以支持高 DPI 监视器。
ms.date: 12/18/2018
localization_priority: Normal
ms.openlocfilehash: 95b7e8b64570421dddf66e2f64cbff7a87152499
ms.sourcegitcommit: fe79d898c27908fc80020b210bdf69c337191d51
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2018
ms.locfileid: "27426880"
---
# <a name="handle-high-dpi-and-dpi-scaling-in-your-office-solution"></a><span data-ttu-id="4d82f-103">在 Office 解决方案中处理高 DPI 和 DPI 缩放</span><span class="sxs-lookup"><span data-stu-id="4d82f-103">Handle high DPI and DPI scaling in your Office solution</span></span>

<span data-ttu-id="4d82f-104">许多计算机和显示器配置现在都支持高 DPI（每英寸点数）分辨率，并且可以连接具有不同大小和像素密度的多个监视器。</span><span class="sxs-lookup"><span data-stu-id="4d82f-104">Many computer and display configurations now support high DPI (dots-per-inch) resolutions, and can connect multiple monitors with different sizes and pixel densities.</span></span> <span data-ttu-id="4d82f-105">这要求用户将应用移动到具有不同 DPI 的监视器时调整应用程序，或者更改缩放级别。</span><span class="sxs-lookup"><span data-stu-id="4d82f-105">This requires applications to adjust when the user moves the app to a monitor with a different DPI, or changes the zoom level.</span></span> <span data-ttu-id="4d82f-106">不支持 DPI 缩放的应用程序在低 DPI 监视器上可能看起来很好，但在高 DPI 监视器上将显得模糊不清。</span><span class="sxs-lookup"><span data-stu-id="4d82f-106">Applications that don’t support DPI scaling might look fine on low DPI monitors, but will look stretched and blurry when shown on a high DPI monitor.</span></span> 

<span data-ttu-id="4d82f-107">Office 2016 应用程序（如 Word 和 Excel）已更新，以响应缩放比例的更改。</span><span class="sxs-lookup"><span data-stu-id="4d82f-107">Office 2016 applications, such as Word and Excel, have been updated to respond to changes in scale factor.</span></span> <span data-ttu-id="4d82f-108">然而，你的 Office 解决方案还必须响应更改，以便在 DPI 更改时正确进行绘制。</span><span class="sxs-lookup"><span data-stu-id="4d82f-108">However, your Office solution must also respond to changes to draw correctly when the DPI changes.</span></span> <span data-ttu-id="4d82f-109">本文介绍 Office 如何支持动态 DPI，以及你可以采取哪些步骤来确保 Office 可扩展性解决方案在处理 DPI 缩放时带来最佳查看体验。</span><span class="sxs-lookup"><span data-stu-id="4d82f-109">This article describes how Office supports dynamic DPI, and what steps you can take to ensure the best viewing experience for your Office extensibility solution to handle DPI scaling.</span></span> 

## <a name="dpi-scaling-symptoms-in-your-solution"></a><span data-ttu-id="4d82f-110">解决方案中的 DPI 缩放症状</span><span class="sxs-lookup"><span data-stu-id="4d82f-110">DPI scaling symptoms in your solution</span></span>

<span data-ttu-id="4d82f-111">当应用程序从一个显示器移动到另一个具有不同 DPI 的显示器时，Windows 会应用 DPI 缩放。</span><span class="sxs-lookup"><span data-stu-id="4d82f-111">Windows applies DPI scaling when an application is moved from one display to another display with a different DPI.</span></span> <span data-ttu-id="4d82f-112">例如，将应用程序拖动到其他显示器或插接笔记本电脑时会发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="4d82f-112">This happens in scenarios such as dragging an application to a different monitor or docking your laptop.</span></span> <span data-ttu-id="4d82f-113">如果 DPI 缩放对你的 Office 解决方案造成不良影响，你将看到以下一个或多个症状：</span><span class="sxs-lookup"><span data-stu-id="4d82f-113">If your Office solution is adversely affected by DPI scaling, you will see one or more of the following symptoms:</span></span>

- <span data-ttu-id="4d82f-114">Windows 在错误位置绘制或者大小调整不正确。</span><span class="sxs-lookup"><span data-stu-id="4d82f-114">The windows draw in the wrong location or have incorrect sizing.</span></span>
- <span data-ttu-id="4d82f-115">按钮和标签等元素显示在解决方案窗口的错误位置。</span><span class="sxs-lookup"><span data-stu-id="4d82f-115">Elements such as buttons and labels appear in the wrong location in your solution’s window.</span></span>
- <span data-ttu-id="4d82f-116">字体和图像显得太小、太大或位于错误位置。</span><span class="sxs-lookup"><span data-stu-id="4d82f-116">Fonts and images appear too small, too large or in the wrong location.</span></span>

<span data-ttu-id="4d82f-117">DPI 缩放可能会影响以下类型的 Office 解决方案：</span><span class="sxs-lookup"><span data-stu-id="4d82f-117">The following types of Office solutions can be affected by DPI scaling:</span></span>

- <span data-ttu-id="4d82f-118">VSTO 加载项</span><span class="sxs-lookup"><span data-stu-id="4d82f-118">VSTO Add-ins</span></span>
- <span data-ttu-id="4d82f-119">自定义任务窗格</span><span class="sxs-lookup"><span data-stu-id="4d82f-119">Custom Task Panes</span></span>
- <span data-ttu-id="4d82f-120">COM 加载项</span><span class="sxs-lookup"><span data-stu-id="4d82f-120">COM Add-ins</span></span>
- <span data-ttu-id="4d82f-121">ActiveX 控件</span><span class="sxs-lookup"><span data-stu-id="4d82f-121">ActiveX controls</span></span>
- <span data-ttu-id="4d82f-122">功能区扩展</span><span class="sxs-lookup"><span data-stu-id="4d82f-122">Ribbon extensions</span></span>
- <span data-ttu-id="4d82f-123">Ole 服务器</span><span class="sxs-lookup"><span data-stu-id="4d82f-123">Ole servers</span></span>
- <span data-ttu-id="4d82f-124">Office Web 加载项</span><span class="sxs-lookup"><span data-stu-id="4d82f-124">Office Web Add-ins</span></span>

## <a name="windows-dpi-awareness-modes"></a><span data-ttu-id="4d82f-125">Windows DPI 感知模式</span><span class="sxs-lookup"><span data-stu-id="4d82f-125">Windows DPI awareness modes</span></span>

<span data-ttu-id="4d82f-126">在整篇文章中，我们将引用 Windows 支持的 DPI 感知模式。</span><span class="sxs-lookup"><span data-stu-id="4d82f-126">Throughout this article we’ll refer to the DPI awareness modes that Windows supports.</span></span> <span data-ttu-id="4d82f-127">每种 DPI 感知模式都支持不同的功能，如下表所述。</span><span class="sxs-lookup"><span data-stu-id="4d82f-127">Each DPI awareness mode supports different capabilities, as described in the following table.</span></span> <span data-ttu-id="4d82f-128">这是有关这些模式的简化描述，用于介绍 Office 如何为其提供支持。</span><span class="sxs-lookup"><span data-stu-id="4d82f-128">This is a simplified description of the modes to explain how Office solutions support them.</span></span> <span data-ttu-id="4d82f-129">有关 DPI 感知模式的详细信息，请参阅 [Windows 上的高 DPI 桌面应用程序开发](https://docs.microsoft.com/zh-CN/windows/desktop/hidpi/high-dpi-desktop-application-development-on-windows)。</span><span class="sxs-lookup"><span data-stu-id="4d82f-129">For more information about the DPI awareness modes, see [High DPI Desktop Application Development on Windows](https://docs.microsoft.com/zh-CN/windows/desktop/hidpi/high-dpi-desktop-application-development-on-windows).</span></span>

|<span data-ttu-id="4d82f-130">模式</span><span class="sxs-lookup"><span data-stu-id="4d82f-130">Mode</span></span>  |<span data-ttu-id="4d82f-131">描述</span><span class="sxs-lookup"><span data-stu-id="4d82f-131">Description</span></span>  |<span data-ttu-id="4d82f-132">DPI 发生更改时</span><span class="sxs-lookup"><span data-stu-id="4d82f-132">When DPI changes</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="4d82f-133">非 DPI 感知</span><span class="sxs-lookup"><span data-stu-id="4d82f-133">DPI unaware</span></span>     |    <span data-ttu-id="4d82f-134">应用程序始终呈现为如同在 DPI 值为 96 的显示器上显示。</span><span class="sxs-lookup"><span data-stu-id="4d82f-134">Application always renders as if it is on a display with a DPI value of 96.</span></span>     |    <span data-ttu-id="4d82f-135">应用程序在主显示器和辅助显示器上将位图拉伸到预期大小。</span><span class="sxs-lookup"><span data-stu-id="4d82f-135">Application is bitmap stretched to expected size on primary and secondary displays.</span></span>    |
|<span data-ttu-id="4d82f-136">系统 DPI 感知</span><span class="sxs-lookup"><span data-stu-id="4d82f-136">System DPI aware</span></span>     |   <span data-ttu-id="4d82f-137">应用程序将在 Windows 登录时检测主连接监视器的 DPI，但无法响应 DPI 更改。</span><span class="sxs-lookup"><span data-stu-id="4d82f-137">Application detects the DPI of the primary connected monitor at Windows login but cannot respond to DPI changes.</span></span> <span data-ttu-id="4d82f-138">有关详细信息，请参阅本文中的[配置 Windows 以修复模糊应用](#Configure-Windows-to-fix-blurry-apps)部分。</span><span class="sxs-lookup"><span data-stu-id="4d82f-138">For more information, see [Configure Windows to fix blurry apps](#Configure-Windows-to-fix-blurry-apps) section in this article.</span></span>      |     <span data-ttu-id="4d82f-139">当移动到具有不同 DPI 的新显示器时，应用程序将拉伸位图。</span><span class="sxs-lookup"><span data-stu-id="4d82f-139">Application is bitmap stretched when moved to a new display with a different DPI.</span></span>    |
|<span data-ttu-id="4d82f-140">按监视器 DPI 感知</span><span class="sxs-lookup"><span data-stu-id="4d82f-140">Per Monitor DPI aware</span></span>     |    <span data-ttu-id="4d82f-141">应用程序能够在 DPI 发生更改时正确地进行重绘。</span><span class="sxs-lookup"><span data-stu-id="4d82f-141">Application is capable of redrawing itself correctly when the DPI changes.</span></span>     |    <span data-ttu-id="4d82f-142">Windows 会将 DPI 通知发送到应用程序中的顶级窗口，以便在 DPI 发生更改时进行重绘。</span><span class="sxs-lookup"><span data-stu-id="4d82f-142">Windows will send DPI notifications to top-level windows in the application so that it can redraw when the DPI changes.</span></span>     |
|<span data-ttu-id="4d82f-143">按监视器 v2</span><span class="sxs-lookup"><span data-stu-id="4d82f-143">Per Monitor v2</span></span>     |   <span data-ttu-id="4d82f-144">应用程序能够在 DPI 发生更改时正确地进行重绘。</span><span class="sxs-lookup"><span data-stu-id="4d82f-144">Application is capable of redrawing itself correctly when the DPI changes.</span></span>      |        <span data-ttu-id="4d82f-145">Windows 将同时向顶级窗口和子窗口发送 DPI 通知，以便应用程序能够在 DPI 发生更改时进行重绘。</span><span class="sxs-lookup"><span data-stu-id="4d82f-145">Windows will send DPI notifications to both top-level and child windows so that the application can redraw when the DPI changes.</span></span> |

## <a name="how-office-supports-dpi-scaling"></a><span data-ttu-id="4d82f-146">Office 如何支持 DPI 缩放</span><span class="sxs-lookup"><span data-stu-id="4d82f-146">How Office supports DPI scaling</span></span>

<span data-ttu-id="4d82f-147">决定 Office 解决方案如何处理 DPI 缩放的最重要因素是你的解决方案是顶级窗口还是子窗口。</span><span class="sxs-lookup"><span data-stu-id="4d82f-147">The most significant factor in determining how your Office solution can handle DPI scaling is whether your solution is a top-level window, or a child window.</span></span> <span data-ttu-id="4d82f-148">下图显示了作为顶级窗口或子窗口运行的 Office 解决方案的一些示例，以及它们将在 Windows 2018 年 4 月更新 (1803) 及更高版本中使用的 DPI 感知模式。</span><span class="sxs-lookup"><span data-stu-id="4d82f-148">The following picture shows a few examples of Office solutions running as top-level or child windows, and which DPI awareness mode they will use on Windows April 2018 Update (1803) and later.</span></span>

![Excel 将 ActiveX 控件和自定义任务窗格托管为子窗口。](./media/office-dpi-awareness-for-solution-types.png)

<span data-ttu-id="4d82f-152">在此图中：</span><span class="sxs-lookup"><span data-stu-id="4d82f-152">In this image:</span></span>
- <span data-ttu-id="4d82f-153">COM/VSTO 顶级窗口是“按监视器 DPI 感知”。</span><span class="sxs-lookup"><span data-stu-id="4d82f-153">The COM/VSTO top-level window is Per Monitor DPI aware.</span></span>
- <span data-ttu-id="4d82f-154">ActiveX 控件子窗口是“系统 DPI 感知”。</span><span class="sxs-lookup"><span data-stu-id="4d82f-154">The ActiveX control child window is System DPI aware.</span></span>
- <span data-ttu-id="4d82f-155">Office 顶级窗口是“按监视器 DPI 感知”。</span><span class="sxs-lookup"><span data-stu-id="4d82f-155">The Office top-level window is Per Monitor DPI aware.</span></span>
- <span data-ttu-id="4d82f-156">自定义任务窗格子窗口是“系统 DPI 感知”。</span><span class="sxs-lookup"><span data-stu-id="4d82f-156">The custom task pane child window is System DPI aware.</span></span>

## <a name="managing-thread-dpi-context"></a><span data-ttu-id="4d82f-157">管理线程 DPI 上下文</span><span class="sxs-lookup"><span data-stu-id="4d82f-157">Managing thread DPI context</span></span>

<span data-ttu-id="4d82f-158">当主机 Office 应用启动时，其主线程将在“按监视器 DPI 感知”上下文中运行。</span><span class="sxs-lookup"><span data-stu-id="4d82f-158">When the host Office app starts, its main thread runs in Per Monitor DPI aware context.</span></span> <span data-ttu-id="4d82f-159">当你的解决方案代码创建线程或从 Office 接收调用时，你需要管理线程 DPI 上下文。</span><span class="sxs-lookup"><span data-stu-id="4d82f-159">When your solution code creates threads, or receives calls from Office, you need to manage the thread DPI context.</span></span>

### <a name="creating-new-threads-with-the-correct-dpi-context"></a><span data-ttu-id="4d82f-160">使用正确的 DPI 上下文创建新线程</span><span class="sxs-lookup"><span data-stu-id="4d82f-160">Creating new threads with the correct DPI context</span></span>

<span data-ttu-id="4d82f-161">如果你的解决方案创建了其他线程，则 Office 将强制该线程进入“按监视器 DPI 感知”上下文。</span><span class="sxs-lookup"><span data-stu-id="4d82f-161">If your solution creates additional threads, Office will force the threads into Per Monitor DPI aware context.</span></span> <span data-ttu-id="4d82f-162">如果你的代码需要不同的上下文，则需要使用 [SetThreadDpiAwarenessContext](https://docs.microsoft.com/zh-CN/windows/desktop/api/winuser/nf-winuser-setthreaddpiawarenesscontext) 函数设置预期的线程 DPI 感知。</span><span class="sxs-lookup"><span data-stu-id="4d82f-162">If your code expects a different context, you need to use the [SetThreadDpiAwarenessContext](https://docs.microsoft.com/zh-CN/windows/desktop/api/winuser/nf-winuser-setthreaddpiawarenesscontext) function to set the expected thread DPI awareness.</span></span> 

### <a name="build-a-context-block-for-incoming-thread-calls"></a><span data-ttu-id="4d82f-163">为传入的线程调用构建上下文块</span><span class="sxs-lookup"><span data-stu-id="4d82f-163">Build a context block for incoming thread calls</span></span>

![该图显示 Office 应用中的上下文块，它在调用顶级窗口时将线程切换到系统感知上下文。](./media/thread-dpi-awareness-context-block.png)

<span data-ttu-id="4d82f-165">你的解决方案将与其主机 Office 应用进行交互，因此你可以对 Office 中的解决方案进行传入调用，例如事件回调。</span><span class="sxs-lookup"><span data-stu-id="4d82f-165">Your solution will interact with its host Office app, so you will have incoming calls to your solution from Office such as event callbacks.</span></span> <span data-ttu-id="4d82f-166">当 Office 调用你的解决方案时，它有一个上下文块，用于强制线程上下文位于“系统 DPI 感知”上下文中。</span><span class="sxs-lookup"><span data-stu-id="4d82f-166">When Office calls your solution, it has a context block that forces the thread context to be in System DPI Aware context.</span></span> <span data-ttu-id="4d82f-167">你必须更改线程上下文，使其匹配窗口的 DPI 感知。</span><span class="sxs-lookup"><span data-stu-id="4d82f-167">You must change the thread context to match the DPI awareness of your window.</span></span> <span data-ttu-id="4d82f-168">你可以实施类似的上下文块以切换传入调用的线程上下文。</span><span class="sxs-lookup"><span data-stu-id="4d82f-168">You can implement a similar context block to switch the thread context on incoming calls.</span></span> <span data-ttu-id="4d82f-169">使用 [SetThreadDpiAwarenessContext](https://docs.microsoft.com/zh-CN/windows/desktop/api/winuser/nf-winuser-setthreaddpiawarenesscontext) 函数更改上下文，使其匹配窗口上下文。</span><span class="sxs-lookup"><span data-stu-id="4d82f-169">Use the [SetThreadDpiAwarenessContext](https://docs.microsoft.com/zh-CN/windows/desktop/api/winuser/nf-winuser-setthreaddpiawarenesscontext) function to change the context to match your window context.</span></span> 

> [!NOTE]
> <span data-ttu-id="4d82f-170">在调用解决方案代码之外的其他组件之前，上下文块应该会还原原始 DPI 线程上下文。</span><span class="sxs-lookup"><span data-stu-id="4d82f-170">Your context block should restore the original DPI thread context before calling other components outside of your solution code.</span></span>

#### <a name="managed-code-context-block"></a><span data-ttu-id="4d82f-171">托管代码上下文块</span><span class="sxs-lookup"><span data-stu-id="4d82f-171">Managed code context block</span></span>

<span data-ttu-id="4d82f-172">以下示例代码显示了如何构建自己的上下文块。</span><span class="sxs-lookup"><span data-stu-id="4d82f-172">The following example code shows how to construct your own context block.</span></span>

```csharp
public struct DPI_AWARENESS_CONTEXT
        {
            private IntPtr value;

            private DPI_AWARENESS_CONTEXT(IntPtr value)
            {
                this.value = value;
            }
            public static implicit operator DPI_AWARENESS_CONTEXT(IntPtr value)
            {
                return new DPI_AWARENESS_CONTEXT(value);
            }

            public static implicit operator IntPtr(DPI_AWARENESS_CONTEXT context)
            {
                return context.value;
            }

            public static DPI_AWARENESS_CONTEXT operator -(DPI_AWARENESS_CONTEXT context, long value)
            {
                return (IntPtr)(context.value.ToInt64() - value);
            }
            public static DPI_AWARENESS_CONTEXT operator -(DPI_AWARENESS_CONTEXT context, int value)
            {
                return (IntPtr)(context.value.ToInt32() - value);
            }

            public static bool operator ==(DPI_AWARENESS_CONTEXT context1, DPI_AWARENESS_CONTEXT context2)
            {
                return context1.value == context2;
            }
            public static bool operator !=(DPI_AWARENESS_CONTEXT context1, DPI_AWARENESS_CONTEXT context2)
            {
                return context1.value != context2;
            }

            public static bool operator ==(IntPtr context1, DPI_AWARENESS_CONTEXT context2)
            {
                return AreDpiAwarenessContextsEqual(context1, context2);
            }
            public static bool operator !=(IntPtr context1, DPI_AWARENESS_CONTEXT context2)
            {
                return !AreDpiAwarenessContextsEqual(context1, context2);
            }

            public override bool Equals(object obj)
            {
                return base.Equals(obj);
            }

            public override int GetHashCode()
            {
                return base.GetHashCode();
            }

            public override string ToString()
            {
                if (this.value == DPI_AWARENESS_CONTEXT_UNAWARE)
                {
                    return "Unaware";
                }
                if (this.value == DPI_AWARENESS_CONTEXT_SYSTEM_AWARE)
                {
                    return "System Aware";
                }
                if (this.value == DPI_AWARENESS_CONTEXT_PER_MONITOR_AWARE)
                {
                    return "Per Monitor Aware";
                }
                if (this.value == DPI_AWARENESS_CONTEXT_PER_MONITOR_AWARE_V2)
                {
                    return "Per Monitor Aware V2";
                }
                return "Unknown";
            }
        }

        private static DPI_AWARENESS_CONTEXT DPI_AWARENESS_CONTEXT_HANDLE = IntPtr.Zero;

        public static readonly DPI_AWARENESS_CONTEXT DPI_AWARENESS_CONTEXT_INVALID = IntPtr.Zero;
        public static readonly DPI_AWARENESS_CONTEXT DPI_AWARENESS_CONTEXT_UNAWARE = DPI_AWARENESS_CONTEXT_HANDLE - 1;
        public static readonly DPI_AWARENESS_CONTEXT DPI_AWARENESS_CONTEXT_SYSTEM_AWARE = DPI_AWARENESS_CONTEXT_HANDLE - 2;
        public static readonly DPI_AWARENESS_CONTEXT DPI_AWARENESS_CONTEXT_PER_MONITOR_AWARE = DPI_AWARENESS_CONTEXT_HANDLE - 3;
        public static readonly DPI_AWARENESS_CONTEXT DPI_AWARENESS_CONTEXT_PER_MONITOR_AWARE_V2 = DPI_AWARENESS_CONTEXT_HANDLE - 4;

        public static DPI_AWARENESS_CONTEXT[] DpiAwarenessContexts =
        {
            DPI_AWARENESS_CONTEXT_UNAWARE,
            DPI_AWARENESS_CONTEXT_SYSTEM_AWARE,
            DPI_AWARENESS_CONTEXT_PER_MONITOR_AWARE,
            DPI_AWARENESS_CONTEXT_PER_MONITOR_AWARE_V2
        };

class DPIContextBlock : IDisposable
    {
        private DPI_AWARENESS_CONTEXT resetContext;
        private bool disposed = false;

        public DPIContextBlock(DPI_AWARENESS_CONTEXT contextSwitchTo)
        {
            resetContext = SetThreadDpiAwarenessContext(contextSwitchTo);
         }

        public void Dispose()
        {
            Dispose(true);
            GC.SuppressFinalize(this);
        }

        protected virtual void Dispose(bool disposing)
        {
            if (!disposed)
            {
                if (disposing)
                {
                    SetThreadDpiAwarenessContext(resetContext);
                }
            }
            disposed = true;
        }
    }
```

#### <a name="native-code-context-block"></a><span data-ttu-id="4d82f-173">本机代码上下文块</span><span class="sxs-lookup"><span data-stu-id="4d82f-173">Native code context block</span></span>

```cpp
#include <winuser.h>
/* DpiAwarenessContextBlock can be used to simplify setting and resetting the DPI_AWARENESS_CONTEXT of
the current thread.  When the object is constructed, the DPI_AWARENESS_CONTEXT is set, and when the object is
destructed, the DPI awareness context is reverted to the previous awareness context at construct time.

This object allows us to write code such as:

// Thread state is currently DPI_AWARENESS_SYSTEM_AWARE
if (condition)
{
DpiAwarenessContextBlock perMonitorAware(DPI_AWARENESS_PER_MONITOR_AWARE);
... // Create a top-level hwnd with the current thread state, DPI_AWARENESS_PER_MONITOR_AWARE
}
// Thread state automatically returns to DPI_AWARENESS_SYSTEM_AWARE

*/
class DpiAwarenessContextBlock
{
public:
      DpiAwarenessContextBlock(DPI_AWARENESS_CONTEXT dpiContext) noexcept;
      ~DpiAwarenessContextBlock();

      // Copy and move are not to be used with these context objects
      DpiAwarenessContextBlock(const DpiAwarenessContextBlock&) = delete;
      DpiAwarenessContextBlock(DpiAwarenessContextBlock&&) = delete;

private:
      DPI_AWARENESS_CONTEXT m_contextReversalType;
      bool m_doContextSwitch;
};

inline DpiAwarenessContextBlock::DpiAwarenessContextBlock(DPI_AWARENESS_CONTEXT dpiContext) noexcept
{
      m_contextReversalType = SetThreadDpiAwarenessContext(dpiContext);
}

inline DpiAwarenessContextBlock::~DpiAwarenessContextBlock()
{
      SetThreadDpiAwarenessContext(m_contextReversalType);
}
```
<h2 id="top-level-window-management"><span data-ttu-id="4d82f-174">顶级窗口管理</span><span class="sxs-lookup"><span data-stu-id="4d82f-174">Top-level window management</span></span></h2>

<span data-ttu-id="4d82f-175">当 Office 应用程序启动时，将以 DPI_AWARENESS_CONTEXT_PER_MONITOR_AWARE 的形式调用 [SetThreadDpiAwarenessContext](https://docs.microsoft.com/zh-CN/windows/desktop/api/winuser/nf-winuser-setthreaddpiawarenesscontext)。</span><span class="sxs-lookup"><span data-stu-id="4d82f-175">When Office applications start, a call is made to [SetThreadDpiAwarenessContext](https://docs.microsoft.com/zh-CN/windows/desktop/api/winuser/nf-winuser-setthreaddpiawarenesscontext) as DPI_AWARENESS_CONTEXT_PER_MONITOR_AWARE.</span></span> <span data-ttu-id="4d82f-176">在此上下文中，DPI 更改将发送到以“按监视器 DPI 感知”形式运行的进程中的任何顶级窗口的 HWND。</span><span class="sxs-lookup"><span data-stu-id="4d82f-176">In this context, DPI changes are sent to the HWND of any top-level windows in the process that are running as Per Monitor DPI aware.</span></span> <span data-ttu-id="4d82f-177">顶级窗口是指 Office 应用程序窗口以及由解决方案创建的任何其他顶级窗口。</span><span class="sxs-lookup"><span data-stu-id="4d82f-177">Top-level windows are the Office application window, and any additional top-level windows created by your solution.</span></span> <span data-ttu-id="4d82f-178">将 Office 应用程序移动到新显示器时，系统会通知它，以便它能够按照新显示器的 DPI 正确地进行动态缩放和绘制。</span><span class="sxs-lookup"><span data-stu-id="4d82f-178">When an Office application is moved to a new display, it gets notified so that it can dynamically scale and draw correctly in the DPI of the new display.</span></span> <span data-ttu-id="4d82f-179">你的 Office 解决方案可以创建处于任何 DPI 感知模式的顶级窗口。</span><span class="sxs-lookup"><span data-stu-id="4d82f-179">Your Office solution can create top-level windows that are in any DPI awareness mode.</span></span> <span data-ttu-id="4d82f-180">顶级窗口还可以通过侦听 Windows 更改消息来响应 DPI 更改。</span><span class="sxs-lookup"><span data-stu-id="4d82f-180">Your top-level windows can also respond to DPI changes by listening to Windows messages for the changes.</span></span>

<span data-ttu-id="4d82f-181">如果已创建作为顶级窗口父级的子窗口，则你也可以将它们设置为任何 DPI 感知模式。</span><span class="sxs-lookup"><span data-stu-id="4d82f-181">If you create child windows that are parented to your top-level window, you can also set them to any DPI awareness mode.</span></span> <span data-ttu-id="4d82f-182">但是，如果使用“按监视器 DPI 感知”模式，则子窗口将不会收到 DPI 更改通知。</span><span class="sxs-lookup"><span data-stu-id="4d82f-182">However, if you use Per Monitor DPI aware mode, your child windows will not receive DPI change notifications.</span></span>  <span data-ttu-id="4d82f-183">有关 Windows DPI 感知模式的详细信息，请参阅 [Windows 上的高 DPI 桌面应用程序开发](https://docs.microsoft.com/zh-CN/windows/desktop/hidpi/high-dpi-desktop-application-development-on-windows)。</span><span class="sxs-lookup"><span data-stu-id="4d82f-183">For more information about Windows DPI awareness modes, see [High DPI Desktop Application Development on Windows](https://docs.microsoft.com/zh-CN/windows/desktop/hidpi/high-dpi-desktop-application-development-on-windows).</span></span>

## <a name="child-window-management"></a><span data-ttu-id="4d82f-184">子窗口管理</span><span class="sxs-lookup"><span data-stu-id="4d82f-184">Child window management</span></span>

<span data-ttu-id="4d82f-185">使用 ActiveX 控件和自定义任务窗格时，Office 会为你的解决方案创建子窗口。</span><span class="sxs-lookup"><span data-stu-id="4d82f-185">When working with ActiveX controls and custom task panes, Office creates the child window for your solution.</span></span> <span data-ttu-id="4d82f-186">你可以创建其他子窗口，但必须知道父窗口 DPI 感知。</span><span class="sxs-lookup"><span data-stu-id="4d82f-186">You can create additional child windows, but you have to be aware of the parent window DPI awareness.</span></span> <span data-ttu-id="4d82f-187">Office 在“按监视器 DPI 感知”模式下运行，这意味着解决方案中的任何子窗口都不会收到 DPI 更改通知。</span><span class="sxs-lookup"><span data-stu-id="4d82f-187">Office runs in Per Monitor DPI awareness mode, which means any child windows in your solution will not get DPI change notifications.</span></span> <span data-ttu-id="4d82f-188">仅“按监视器 v2”模式支持向子窗口发送 DPI 更改（Office 不支持“按监视器 v2”）。</span><span class="sxs-lookup"><span data-stu-id="4d82f-188">Only Per Monitor v2 mode supports sending DPI changes to child windows (Office does not support Per Monitor v2).</span></span> <span data-ttu-id="4d82f-189">但是，对于 ActiveX 控件，有一种解决方法。</span><span class="sxs-lookup"><span data-stu-id="4d82f-189">However, for ActiveX controls, there is a workaround.</span></span> <span data-ttu-id="4d82f-190">有关详细信息，请参阅本文后面的 [ActiveX 控件](#activex-controls)部分。</span><span class="sxs-lookup"><span data-stu-id="4d82f-190">For more information, see the  [Web fonts](#activex-controls) section in this article.</span></span>

> [!NOTE]
> <span data-ttu-id="4d82f-191">如果子窗口创建了顶级窗口，则可以为新的顶级窗口使用任何 DPI 感知模式。</span><span class="sxs-lookup"><span data-stu-id="4d82f-191">If your child window creates a top-level window, you can use any DPI awareness mode for the new top-level window.</span></span> <span data-ttu-id="4d82f-192">有关管理顶级窗口的详细信息，请参阅本文的[顶级窗口管理](#top-level-window-management)部分。</span><span class="sxs-lookup"><span data-stu-id="4d82f-192">For more information about managing top-level windows, see the [Top-level window management](#top-level-window-management) section in this article.</span></span>

<span data-ttu-id="4d82f-193">您将看到应用于子窗口的两种不同的 DPI 模式，具体取决于运行的 Windows 10 Office 版本。</span><span class="sxs-lookup"><span data-stu-id="4d82f-193">You will see two different DPI modes applied to your child window, depending on which version of Windows 10 Office is running on.</span></span>

### <a name="office-dpi-behavior-on-windows-fall-creators-update-1709"></a><span data-ttu-id="4d82f-194">Windows Fall Creators Update (1709) 中的 Office DPI 行为</span><span class="sxs-lookup"><span data-stu-id="4d82f-194">Office DPI behavior on Windows Fall Creators Update (1709)</span></span>

<span data-ttu-id="4d82f-195">由于 Office 应用使用按监视器感知模式，因此还将在“按监视器 DPI 感知”模式下为解决方案创建子窗口。</span><span class="sxs-lookup"><span data-stu-id="4d82f-195">Because Office apps use Per Monitor awareness mode, your solution’s child windows will also be created in Per Monitor DPI awareness mode.</span></span> <span data-ttu-id="4d82f-196">这意味着 Windows 希望在采用新 DPI 进行绘制时更新解决方案。</span><span class="sxs-lookup"><span data-stu-id="4d82f-196">This means Windows expects your solution to update when drawing in a new DPI.</span></span>  <span data-ttu-id="4d82f-197">由于窗口无法收到 DPI 更改通知，因此你的解决方案 UI 可能不正确。</span><span class="sxs-lookup"><span data-stu-id="4d82f-197">Because your window cannot get DPI change notifications, your solution’s UI might be incorrect.</span></span> 

![该图显示在 Windows Fall Creators Update (1709) 的“按监视器 DPI 感知”上下文中运行的子窗口。](./media/office-dpi-behavior-on-windows-fall-creators-update.png)

### <a name="office-dpi-behavior-on-windows-april-2018-update-1803"></a><span data-ttu-id="4d82f-199">Windows 2018 年 4 月更新 (1803) 中的 Office DPI 行为</span><span class="sxs-lookup"><span data-stu-id="4d82f-199">Office DPI behavior on Windows April 2018 Update (1803)</span></span>

<span data-ttu-id="4d82f-200">对于 Windows 2018 年 4 月更新 (1803) 及更高版本，Office DPI 托管行为在某些情况下会使用混合模式 DPI 缩放。</span><span class="sxs-lookup"><span data-stu-id="4d82f-200">With Windows April 2018 (1803) update and later, The Office DPI hosting behavior uses mixed-mode DPI scaling for some scenarios.</span></span> <span data-ttu-id="4d82f-201">这允许系统 DPI 感知窗口成为设置为“按监视器 DPI 感知”的 Office 窗口的父级。</span><span class="sxs-lookup"><span data-stu-id="4d82f-201">This allows System DPI Aware windows to be parented to Office windows set to Per Monitor DPI aware.</span></span> <span data-ttu-id="4d82f-202">这有助于确保在 DPI 发生更改和窗口位图拉伸时提高兼容性。</span><span class="sxs-lookup"><span data-stu-id="4d82f-202">This helps to ensure improved compatibility when the DPI changes when the windows are bitmap stretched.</span></span> <span data-ttu-id="4d82f-203">经过位图拉伸的窗口可能仍模糊不清。</span><span class="sxs-lookup"><span data-stu-id="4d82f-203">The windows might still be blurry from the bitmap stretching.</span></span>

![该图显示在 Windows 2018 年 4 月更新 (1803) 的“系统 DPI 感知”上下文中运行的子窗口。](./media/office-dpi-behavior-on-windows-april-2018-update.png)

<span data-ttu-id="4d82f-205">创建新的子窗口时，请确保它们匹配其父窗口的 DPI 感知。</span><span class="sxs-lookup"><span data-stu-id="4d82f-205">When you create new child windows, be sure they match the DPI awareness of their parent window.</span></span> <span data-ttu-id="4d82f-206">你可以使用 [GetWindowdpiAwarenessContext](https://docs.microsoft.com/zh-CN/windows/desktop/api/winuser/nf-winuser-getwindowdpiawarenesscontext) 函数来获取父窗口的 DPI 感知。</span><span class="sxs-lookup"><span data-stu-id="4d82f-206">You can use the [GetWindowdpiAwarenessContext](https://docs.microsoft.com/zh-CN/windows/desktop/api/winuser/nf-winuser-getwindowdpiawarenesscontext) function to get the DPI awareness of the parent window.</span></span> <span data-ttu-id="4d82f-207">有关 DPI 感知一致性的详细信息，请参阅 [Windows 上的高 DPI 桌面应用程序开发](https://docs.microsoft.com/zh-CN/windows/desktop/hidpi/high-dpi-desktop-application-development-on-windows#related-topics)中的“强制重置整个进程的 DPI 感知”部分。</span><span class="sxs-lookup"><span data-stu-id="4d82f-207">For more information about DPI awareness consistency, see the “Forced reset of process-wide DPI awareness” section in [High DPI Desktop Application Development on Windows](https://docs.microsoft.com/zh-CN/windows/desktop/hidpi/high-dpi-desktop-application-development-on-windows#related-topics).</span></span>

> [!NOTE]
> <span data-ttu-id="4d82f-208">你不能依赖于进程 DPI 感知，因为它可能会返回 [PROCESS_SYSTEM_DPI_AWARE](https://msdn.microsoft.com/en-us/library/windows/desktop/dn280512(v=vs.85).aspx)，即使应用程序主线程 DPI 感知上下文为 [DPI_AWARENESS_CONTEXT_PER_MONITOR_AWARE](https://docs.microsoft.com/zh-CN/windows/desktop/hidpi/dpi-awareness-context) 也是如此。</span><span class="sxs-lookup"><span data-stu-id="4d82f-208">You can’t rely on the Process DPI Awareness as it might return [PROCESS_SYSTEM_DPI_AWARE](https://msdn.microsoft.com/en-us/library/windows/desktop/dn280512(v=vs.85).aspx) even when the application main thread DPI awareness context is [DPI_AWARENESS_CONTEXT_PER_MONITOR_AWARE](https://docs.microsoft.com/zh-CN/windows/desktop/hidpi/dpi-awareness-context).</span></span> <span data-ttu-id="4d82f-209">使用 [GetThreadDpiAwarenessContext](https://docs.microsoft.com/zh-CN/windows/desktop/api/winuser/nf-winuser-getthreaddpiawarenesscontext) 函数获取线程 DPI 感知上下文。</span><span class="sxs-lookup"><span data-stu-id="4d82f-209">Use the [GetThreadDpiAwarenessContext](https://docs.microsoft.com/zh-CN/windows/desktop/api/winuser/nf-winuser-getthreaddpiawarenesscontext) function to get the thread DPI awareness context.</span></span>

## <a name="office-and-windows-dpi-compatibility-settings"></a><span data-ttu-id="4d82f-210">Office 和 Windows DPI 兼容性设置</span><span class="sxs-lookup"><span data-stu-id="4d82f-210">Office and Windows DPI compatibility settings</span></span>

<span data-ttu-id="4d82f-211">当用户遇到无法正确呈现的加载项或解决方案时，某些兼容性设置可帮助解决该问题。</span><span class="sxs-lookup"><span data-stu-id="4d82f-211">When users encounter add-ins or solutions that are not rendering correctly, some compatibility settings can help correct the problem.</span></span>

<h3 id="office-compatibility"><span data-ttu-id="4d82f-212">配置 Office 以优化兼容性</span><span class="sxs-lookup"><span data-stu-id="4d82f-212">Configure Office to optimize for compatibility</span></span></h3>

<span data-ttu-id="4d82f-213">当移动到具有不同 DPI 缩放比例的其他屏幕时，Office 提供了用于优化兼容性的设置。</span><span class="sxs-lookup"><span data-stu-id="4d82f-213">Office has a setting to optimize for compatibility when moving to different DPI scales on different screens.</span></span> <span data-ttu-id="4d82f-214">兼容模式可禁用 DPI 缩放，以便在移动到使用不同 DPI 缩放比例的显示器时，Office 中的所有内容都会进行位图拉伸。</span><span class="sxs-lookup"><span data-stu-id="4d82f-214">The compatibility mode disables DPI scaling so that everything in Office is bitmap stretched when moved to a display using different DPI scaling.</span></span> 

<span data-ttu-id="4d82f-215">兼容性模式强制 Office 在系统 DPI 感知模式下运行。</span><span class="sxs-lookup"><span data-stu-id="4d82f-215">The compatibility mode forces Office to run in System DPI aware mode.</span></span> <span data-ttu-id="4d82f-216">这会导致应用程序窗口进行位图拉伸，并且可能会产生外观模糊的负面影响。</span><span class="sxs-lookup"><span data-stu-id="4d82f-216">This causes application windows to bitmap stretch and can have a side effect of a blurry appearance.</span></span> <span data-ttu-id="4d82f-217">Office 解决方案无法控制此设置，因为这是用户选择的。</span><span class="sxs-lookup"><span data-stu-id="4d82f-217">Your Office solution cannot control this setting because the user chooses it.</span></span> <span data-ttu-id="4d82f-218">使用显示兼容性模式可以解决许多绘图问题。</span><span class="sxs-lookup"><span data-stu-id="4d82f-218">Using the display compatibility mode solves most drawing problems.</span></span> <span data-ttu-id="4d82f-219">有关详细信息，请参阅 [高清晰度显示器的 Office 支持](https://support.office.com/zh-CN/article/office-support-for-high-definition-displays-6720ca0e-be59-41f6-b629-1369f549279d)。</span><span class="sxs-lookup"><span data-stu-id="4d82f-219">For more information, see [Office support for high definition displays](https://support.office.com/zh-CN/article/office-support-for-high-definition-displays-6720ca0e-be59-41f6-b629-1369f549279d).</span></span> 

### <a name="configure-windows-to-fix-blurry-apps"></a><span data-ttu-id="4d82f-220">配置 Windows 以修复模糊应用程序</span><span class="sxs-lookup"><span data-stu-id="4d82f-220">Configure Windows to fix blurry apps</span></span>

<span data-ttu-id="4d82f-221">在 Windows 10（版本 1803）及更高版本中，可以通过设置修复应用程序，使其不再模糊。</span><span class="sxs-lookup"><span data-stu-id="4d82f-221">Windows 10 (Version 1803) and later has a setting to fix apps so they’re not blurry.</span></span> <span data-ttu-id="4d82f-222">如果你的解决方案无法正常呈现，则可以尝试使用这种设置。</span><span class="sxs-lookup"><span data-stu-id="4d82f-222">This is another setting to try if your solution is not rendering correctly.</span></span> <span data-ttu-id="4d82f-223">Office 解决方案无法控制此设置，因为这是用户选择的。</span><span class="sxs-lookup"><span data-stu-id="4d82f-223">Your Office solution cannot control this setting because the user chooses it.</span></span> <span data-ttu-id="4d82f-224">有关详细信息，请参阅[在 Windows 10 中修复显示模糊的应用程序](https://support.microsoft.com/zh-CN/help/4091364/windows-10-fix-blurry-apps)。</span><span class="sxs-lookup"><span data-stu-id="4d82f-224">For more information, see [Fix apps that appear blurry in Windows 10](https://support.microsoft.com/zh-CN/help/4091364/windows-10-fix-blurry-apps).</span></span>

## <a name="how-to-support-dpi-scaling-in-your-solution"></a><span data-ttu-id="4d82f-225">如何支持解决方案中的 DPI 缩放</span><span class="sxs-lookup"><span data-stu-id="4d82f-225">How to support DPI scaling in your solution</span></span>

<span data-ttu-id="4d82f-226">有些解决方案可以接收和响应 DPI 更改。</span><span class="sxs-lookup"><span data-stu-id="4d82f-226">Some solutions can receive and respond to DPI changes.</span></span> <span data-ttu-id="4d82f-227">有些则可以通过解决办法解决无法接收通知的问题。</span><span class="sxs-lookup"><span data-stu-id="4d82f-227">Some have a workaround if they cannot receive notifications.</span></span> <span data-ttu-id="4d82f-228">下表列出了与每种解决方案相关的详细信息。</span><span class="sxs-lookup"><span data-stu-id="4d82f-228">The following table lists the details for each solution type.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="4d82f-229">解决方案类型</span><span class="sxs-lookup"><span data-stu-id="4d82f-229">Solution Type</span></span></th>
            <th><span data-ttu-id="4d82f-230">窗口类型</span><span class="sxs-lookup"><span data-stu-id="4d82f-230">Window type</span></span></th>
            <th><span data-ttu-id="4d82f-231">可响应 DPI 缩放</span><span class="sxs-lookup"><span data-stu-id="4d82f-231">Can respond to DPI scaling</span></span></th>
            <th><span data-ttu-id="4d82f-232">更多详细信息</span><span class="sxs-lookup"><span data-stu-id="4d82f-232">More details</span></span></th>
        </tr>
    </thead>
<tbody>
    <tr>
        <td rowspan="2"><span data-ttu-id="4d82f-233"><a href="#vsto-add-ins">VSTO 加载项</a></span><span class="sxs-lookup"><span data-stu-id="4d82f-233"><a href="#vsto-add-ins">VSTO Add-in</a></span></span></td>
        <td><span data-ttu-id="4d82f-234">顶部及其子代</span><span class="sxs-lookup"><span data-stu-id="4d82f-234">Top and its descendants</span></span></td>
        <td><span data-ttu-id="4d82f-235">是</span><span class="sxs-lookup"><span data-stu-id="4d82f-235">Yes</span></span></td>
        <td><span data-ttu-id="4d82f-236">请参阅 <a href="#vsto-add-ins">VSTO 加载项指南</a>。</span><span class="sxs-lookup"><span data-stu-id="4d82f-236">See <a href="#vsto-add-ins">VSTO add-in guidance</a>.</span></span></td>
    </tr>
<tr>
        <td><span data-ttu-id="4d82f-237">已设置为 Office 窗口父级的子级</span><span class="sxs-lookup"><span data-stu-id="4d82f-237">Child parented to Office window</span></span></td>
        <td><span data-ttu-id="4d82f-238">否</span><span class="sxs-lookup"><span data-stu-id="4d82f-238">No</span></span></td>
        <td><span data-ttu-id="4d82f-239">请参阅<a href="#office-compatibility">配置 Office 以优化兼容性</a>。</span><span class="sxs-lookup"><span data-stu-id="4d82f-239">See <a href="#office-compatibility">Configure Office to optimize for compatibility</a>.</span></span></td>
</tr>
    <tr>
        <td rowspan="2"><span data-ttu-id="4d82f-240"><a href="#custom-task-panes">自定义任务窗格</a></span><span class="sxs-lookup"><span data-stu-id="4d82f-240"><a href="#custom-task-panes">Custom task pane</a></span></span></td>
        <td><span data-ttu-id="4d82f-241">顶部及其子代</span><span class="sxs-lookup"><span data-stu-id="4d82f-241">Top and its descendants</span></span></td>
        <td><span data-ttu-id="4d82f-242">是</span><span class="sxs-lookup"><span data-stu-id="4d82f-242">Yes</span></span></td>
        <td><span data-ttu-id="4d82f-243">请参阅<a href="#top-level-window-management">顶级窗口指南</a>。</span><span class="sxs-lookup"><span data-stu-id="4d82f-243">See <a href="#top-level-window-management">top-level window guidance</a>.</span></span></td>
    </tr>
<tr>
        <td><span data-ttu-id="4d82f-244">已设置为 Office 窗口父级的子级</span><span class="sxs-lookup"><span data-stu-id="4d82f-244">Child parented to Office window</span></span></td>
        <td><span data-ttu-id="4d82f-245">否</span><span class="sxs-lookup"><span data-stu-id="4d82f-245">No</span></span></td>
        <td><span data-ttu-id="4d82f-246">请参阅<a href="#office-compatibility">配置 Office 以优化兼容性</a>。</span><span class="sxs-lookup"><span data-stu-id="4d82f-246">See <a href="#office-compatibility">Configure Office to optimize for compatibility</a>.</span></span></td>
</tr>
    <tr>
        <td rowspan="2"><span data-ttu-id="4d82f-247"><a href="#com-add-ins">COM 加载项</a></span><span class="sxs-lookup"><span data-stu-id="4d82f-247"><a href="#com-add-ins">COM Add-in</a></span></span></td>
        <td><span data-ttu-id="4d82f-248">顶部及其子代</span><span class="sxs-lookup"><span data-stu-id="4d82f-248">Top and its descendants</span></span></td>
        <td><span data-ttu-id="4d82f-249">是</span><span class="sxs-lookup"><span data-stu-id="4d82f-249">Yes</span></span></td>
        <td><span data-ttu-id="4d82f-250">请参阅 <a href="#com-add-ins">COM 加载项指南</a>。</span><span class="sxs-lookup"><span data-stu-id="4d82f-250">See <a href="#com-add-ins">COM Add-in guidance</a>.</span></span></td>
    </tr>
<tr>
        <td><span data-ttu-id="4d82f-251">已设置为 Office 窗口父级的子级</span><span class="sxs-lookup"><span data-stu-id="4d82f-251">Child parented to Office window</span></span></td>
        <td><span data-ttu-id="4d82f-252">否</span><span class="sxs-lookup"><span data-stu-id="4d82f-252">No</span></span></td>
        <td><span data-ttu-id="4d82f-253">请参阅<a href="#office-compatibility">配置 Office 以优化兼容性</a>。</span><span class="sxs-lookup"><span data-stu-id="4d82f-253">See <a href="#office-compatibility">Configure Office to optimize for compatibility</a>.</span></span></td>
</tr>
    <tr>
        <td rowspan="2"><span data-ttu-id="4d82f-254"><a href="#activex-controls">ActiveX 控件</a></span><span class="sxs-lookup"><span data-stu-id="4d82f-254"><a href="#activex-controls">ActiveX control.</a></span></span></td>
        <td><span data-ttu-id="4d82f-255">顶部及其子代</span><span class="sxs-lookup"><span data-stu-id="4d82f-255">Top and its descendants</span></span></td>
        <td><span data-ttu-id="4d82f-256">是</span><span class="sxs-lookup"><span data-stu-id="4d82f-256">Yes</span></span></td>
        <td><span data-ttu-id="4d82f-257">请参阅<a href="#activex-controls">ActiveX 控件指南</a>。</span><span class="sxs-lookup"><span data-stu-id="4d82f-257">See <a href="#activex-controls">ActiveX control guidance</a>.</span></span></td>
    </tr>
    <tr>
        <td><span data-ttu-id="4d82f-258">已设置为 Office 窗口父级的子级</span><span class="sxs-lookup"><span data-stu-id="4d82f-258">Child parented to Office window</span></span></td>
        <td><span data-ttu-id="4d82f-259">是</span><span class="sxs-lookup"><span data-stu-id="4d82f-259">Yes</span></span></td>
    </tr>
    <tr>
        <td><span data-ttu-id="4d82f-260"><a href="#web-add-ins">Web 加载项</a></span><span class="sxs-lookup"><span data-stu-id="4d82f-260"><a href="#web-add-ins">Web Add-in</a></span></span></td>
        <td><span data-ttu-id="4d82f-261">NA</span><span class="sxs-lookup"><span data-stu-id="4d82f-261">NA</span></span></td>
        <td><span data-ttu-id="4d82f-262">是</span><span class="sxs-lookup"><span data-stu-id="4d82f-262">Yes</span></span></td>
        <td><span data-ttu-id="4d82f-263">请参阅<a href="#web-add-ins">Office Web 加载项指南</a>。</span><span class="sxs-lookup"><span data-stu-id="4d82f-263">See <a href="#web-add-ins">Office web add-in guidance</a>.</span></span></td>
    </tr>
    <tr>
        <td><span data-ttu-id="4d82f-264"><a href="#ribbon-extensibility">功能区扩展</a></span><span class="sxs-lookup"><span data-stu-id="4d82f-264"><a href="#ribbon-extensibility">Ribbon extension</a></span></span></td>
        <td><span data-ttu-id="4d82f-265">NA</span><span class="sxs-lookup"><span data-stu-id="4d82f-265">NA</span></span></td>
        <td><span data-ttu-id="4d82f-266">NA</span><span class="sxs-lookup"><span data-stu-id="4d82f-266">NA</span></span></td>
        <td><span data-ttu-id="4d82f-267">请参阅<a href="#ribbon-extensibility">功能区扩展指南</a>。</span><span class="sxs-lookup"><span data-stu-id="4d82f-267">See <a href="#ribbon-extensibility">Ribbon extension guidance</a>.</span></span></td>
    </tr>
    <tr>
        <td><span data-ttu-id="4d82f-268"><a href="#ole">OLE 服务器或客户端</a></span><span class="sxs-lookup"><span data-stu-id="4d82f-268"><a href="#ole">OLE server or client</a></span></span></td>
        <td><span data-ttu-id="4d82f-269">NA</span><span class="sxs-lookup"><span data-stu-id="4d82f-269">NA</span></span></td>
        <td><span data-ttu-id="4d82f-270">NA</span><span class="sxs-lookup"><span data-stu-id="4d82f-270">NA</span></span></td>
        <td><span data-ttu-id="4d82f-271">请参阅<a href="#ole">OLE 服务器/客户端指南</a>。</span><span class="sxs-lookup"><span data-stu-id="4d82f-271">See <a href="#ole">OLE server/client guidance</a>.</span></span></td>
    </tr>
</tbody>
</table>

<h3 id="vsto-add-ins"><span data-ttu-id="4d82f-272">VSTO 加载项</span><span class="sxs-lookup"><span data-stu-id="4d82f-272">VSTO add-in</span></span></h3>

<span data-ttu-id="4d82f-273">如果 VSTO 加载项创建了已设置为任何 Office 窗口的子窗口，请确保它们与其父窗口的 DPI 感知匹配。</span><span class="sxs-lookup"><span data-stu-id="4d82f-273">If your VSTO add-in creates child windows that are parented to any Office windows, be sure they match the DPI awareness of their parent window.</span></span> <span data-ttu-id="4d82f-274">你可以使用 [GetWindowdpiAwarenessContext](https://docs.microsoft.com/zh-CN/windows/desktop/api/winuser/nf-winuser-getwindowdpiawarenesscontext) 函数来获取父窗口的 DPI 感知。</span><span class="sxs-lookup"><span data-stu-id="4d82f-274">You can use the [GetWindowdpiAwarenessContext](https://docs.microsoft.com/zh-CN/windows/desktop/api/winuser/nf-winuser-getwindowdpiawarenesscontext) function to get the DPI awareness of the parent window.</span></span> <span data-ttu-id="4d82f-275">子窗口不会收到任何 DPI 更改通知。</span><span class="sxs-lookup"><span data-stu-id="4d82f-275">Your child windows will not get any DPI change notifications.</span></span> <span data-ttu-id="4d82f-276">如果你的解决方案无法正常呈现，则用户需要将 Office 置于兼容性模式。</span><span class="sxs-lookup"><span data-stu-id="4d82f-276">If your solution is not rendering correctly, users will need to put Office into compatibility mode.</span></span>

<span data-ttu-id="4d82f-277">对于任何 VSTO 加载项创建的顶级窗口，可以将其设置为任意 DPI 感知模式。</span><span class="sxs-lookup"><span data-stu-id="4d82f-277">For any top-level windows your VSTO add-in creates, you can set them to any DPI awareness mode.</span></span> <span data-ttu-id="4d82f-278">以下示例代码显示了如何设置所需的 DPI 感知以及如何响应 DPI 更改。</span><span class="sxs-lookup"><span data-stu-id="4d82f-278">The following sample code shows how to set up the desired DPI awareness, and how to respond to DPI changes.</span></span> <span data-ttu-id="4d82f-279">此外，你需要按照 [High DPI support in Windows Forms](https://docs.microsoft.com/zh-CN/dotnet/framework/winforms/high-dpi-support-in-windows-forms) 文章中所述，调整 app.config。</span><span class="sxs-lookup"><span data-stu-id="4d82f-279">You will also need to adjust your app.config, as described in the [High DPI support in Windows Forms](https://docs.microsoft.com/zh-CN/dotnet/framework/winforms/high-dpi-support-in-windows-forms) article.</span></span> 

```csharp
using System;
using System.Diagnostics;
using System.Drawing;
using System.Runtime.InteropServices;
using System.Windows.Forms;

namespace SharedModule
{
    // DpiAwareWindowsForm
    // For any top level winform you create, derive from the DpiWindowsForm class
    // if you are creating Windows Forms with the Dpi Awareness Context set to 
    // DPI_AWARENESS_CONTEXT_PER_MONITOR_AWARE or DPI_AWARENESS_CONTEXT_PER_MONITOR_AWARE_V2
    //
    // For example, if you Window form class is defined as:
    //    public partial class TopLevelWinForm : Form
    //
    // update to:
    //    public partial class TopLevelWinForm : DpiAwareWindowsForm
    //
    // When showing the form, call SetThreadDpiAwarenessContext() or use a context block to
    // to set the desired Dpi Awareness Context.
    //
    // For example, here is code to show a Windows Form using a context block as Per Monitor Aware v2.
    //
    //    DPIContextBlock context = new DPIContextBlock(DPI_AWARENESS_CONTEXT_PER_MONITOR_AWARE_V2);
    //    TopLevelWinForm frm = new TopLevelWinForm();
    //    frm.Show();
    //
    public partial class DpiAwareWindowsForm : Form
    {
        private SizeF m_newDpi = SizeF.Empty;
        private SizeF m_oldDpi = SizeF.Empty;

        public DpiAwareWindowsForm()
        {
            this.HandleCreated += new EventHandler((sender, args) =>
            {
                m_oldDpi = m_newDpi = DPIHelper.GetDpiForWindowSizeF(this.Handle);
            });
        }

        public void OnDpiChangedEvent(RECT newRect)
        {
            this.SuspendLayout();

            // Resize form
            this.Width = newRect.Width;
            this.Height = newRect.Height;

            // Resize controls and set font sizes
            ScaleAllChildControls(this.Controls, m_oldDpi.Width, m_newDpi.Width);
            this.ResumeLayout(true);
        }

        // Additional changes may be needed for controls that set Anchor or Dock properties 
        private void ScaleAllChildControls(Control.ControlCollection controls, float oldDpi, float newDpi)
        {
            float scaleFactorChange = newDpi / oldDpi;

            foreach (Control control in controls)
            {
                control.Top = (int)(control.Top * scaleFactorChange);
                control.Left = (int)(control.Left * scaleFactorChange);
                control.Width = (int)(control.Width * scaleFactorChange);
                control.Height = (int)(control.Height * scaleFactorChange);
                control.Font = ScaleFont(control.Font, oldDpi, newDpi);
            }
        }

        private Font ScaleFont(Font font, float oldDpi, float newDpi)
        {
            float fontSizePx = 0.0f;
            float fontSizePt = 0.0f;

            fontSizePx = font.SizeInPoints / 72 * oldDpi;
            fontSizePt = fontSizePx * (newDpi / oldDpi) * 72 / oldDpi;

            return new Font(font.Name, fontSizePt, font.Style, GraphicsUnit.Point);
        }

        protected override void WndProc(ref Message m)
        {
            switch ((DPIHelper.WinMessages)m.Msg)
            {
                case DPIHelper.WinMessages.WM_DPICHANGED:
                    // Marshal the value in the lParam into a Rect.
                    RECT newDisplayRect = (RECT)Marshal.PtrToStructure(m.LParam, typeof(RECT));

                    // Remember current DPI and calculate current from WParam.
                    // Both X and Y are the same on Windows for Dpi.
                    m_oldDpi = m_newDpi;

                    m_newDpi.Width = (float)(m.WParam.ToInt32() >> 16);
                    m_newDpi.Height = (float)(m.WParam.ToInt32() & 0x0000FFFF);

                    // DPI should be the same for both width and height on Windows devices.
                    Debug.Assert(m_newDpi.Height == m_newDpi.Width);

                    if (m_oldDpi.Width != m_newDpi.Width)
                    {
                        OnDpiChangedEvent(newDisplayRect);
                    }
                    base.DefWndProc(ref m);
                    break;
                default:
                    base.WndProc(ref m);
                    break;
            }
        }
    }
}
```

<h3 id="custom-task-panes"><span data-ttu-id="4d82f-280">自定义任务窗格</span><span class="sxs-lookup"><span data-stu-id="4d82f-280">Custom Task Panes</span></span></h3>

<span data-ttu-id="4d82f-281">Office 将会创建一个自定义任务窗格，作为子窗口。</span><span class="sxs-lookup"><span data-stu-id="4d82f-281">A custom task pane is created as a child window by Office.</span></span> <span data-ttu-id="4d82f-282">在 Windows Fall Creators Update (1709) 上运行时，自定义任务窗格将使用与 Office 相同的 DPI 感知模式运行。</span><span class="sxs-lookup"><span data-stu-id="4d82f-282">When running on Windows Fall Creators Update (1709), your custom task pane will run using the same DPI awareness mode as Office.</span></span> <span data-ttu-id="4d82f-283">在 Windows April 2018 Update (1803) 及更高版本上运行时，自定义任务窗口将使用系统 DPI 感知模式。</span><span class="sxs-lookup"><span data-stu-id="4d82f-283">When running on Windows April 2018 Update (1803) and later, your custom task pane will run using System DPI awareness mode.</span></span> 

<span data-ttu-id="4d82f-284">自定义任务窗格为子窗口，因此，它们无法接收 DPI 通知。</span><span class="sxs-lookup"><span data-stu-id="4d82f-284">Because custom task panes are child windows, they cannot receive DPI notifications.</span></span> <span data-ttu-id="4d82f-285">如果绘制错误，则用户需要使用 [Office DPI 兼容性模式](https://support.office.com/zh-CN/article/office-support-for-high-definition-displays-6720ca0e-be59-41f6-b629-1369f549279d)。</span><span class="sxs-lookup"><span data-stu-id="4d82f-285">If they are drawing incorrectly, the user will need to use [Office DPI compatibility mode](https://support.office.com/zh-CN/article/office-support-for-high-definition-displays-6720ca0e-be59-41f6-b629-1369f549279d).</span></span>
<span data-ttu-id="4d82f-286">如果自定义任务窗格创建了一个顶级窗口，则这些窗口可以在任何 DPI 感知模式下运行并且可接收 DP 更改通知。</span><span class="sxs-lookup"><span data-stu-id="4d82f-286">If your custom task pane creates top-level windows, those windows can run in any DPI awareness mode and receive DPI change notifications.</span></span> <span data-ttu-id="4d82f-287">有关详细信息，请参阅本文的[顶级窗口管理](#Top-level-window-management)部分。</span><span class="sxs-lookup"><span data-stu-id="4d82f-287">For more information, see the  [Web fonts](#Top-level-window-management) section in this article.</span></span>

<h3 id="com-add-ins"><span data-ttu-id="4d82f-288">COM 加载项</span><span class="sxs-lookup"><span data-stu-id="4d82f-288">COM add-ins</span></span></h3>

<span data-ttu-id="4d82f-289">用于创建顶级窗口的 COM 加载项可以接收 DPI 通知。</span><span class="sxs-lookup"><span data-stu-id="4d82f-289">COM add-ins that create top-level windows can receive DPI notifications.</span></span> <span data-ttu-id="4d82f-290">应先创建[上下文块](#Build-a-context-block-for-incoming-thread-calls)以将线程设置为窗口所需的 DPI 感知，然后再创建窗口。</span><span class="sxs-lookup"><span data-stu-id="4d82f-290">You should create a [context block](#Build-a-context-block-for-incoming-thread-calls) to set the thread to the DPI awareness that you want for your window, then create your window.</span></span> <span data-ttu-id="4d82f-291">要正确处理 DPI 通知，需要知悉许多内容，因此，务必阅读 [Windows 上的高 DPI 桌面应用程序开发](https://docs.microsoft.com/zh-CN/windows/desktop/hidpi/high-dpi-desktop-application-development-on-windows#related-topics)，以了解更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="4d82f-291">There’s a lot to handling the DPI notifications correctly, so be sure to read [High DPI Desktop Application Development on Windows](https://docs.microsoft.com/zh-CN/windows/desktop/hidpi/high-dpi-desktop-application-development-on-windows#related-topics) for more details.</span></span>

<span data-ttu-id="4d82f-292">当某一窗口的 DPI 发生更改时，将会发送 [WM_DPICHANGED](https://msdn.microsoft.com/en-us/library/windows/desktop/dn312083(v=vs.85).aspx) 消息。</span><span class="sxs-lookup"><span data-stu-id="4d82f-292">The [WM_DPICHANGED](https://msdn.microsoft.com/en-us/library/windows/desktop/dn312083(v=vs.85).aspx) message is sent when the DPI for a window has changed.</span></span>  <span data-ttu-id="4d82f-293">在非托管代码中，此消息由 HWND 的[窗口程序](https://msdn.microsoft.com/en-us/library/windows/desktop/ms633570(v=vs.85).aspx)处理。</span><span class="sxs-lookup"><span data-stu-id="4d82f-293">In unmanaged code, this message is handled by the [Window Procedure](https://msdn.microsoft.com/en-us/library/windows/desktop/ms633570(v=vs.85).aspx) for the HWND.</span></span>  <span data-ttu-id="4d82f-294">
  [WM_DPICHANGED](https://msdn.microsoft.com/en-us/library/windows/desktop/dn312083(v=vs.85).aspx) 一文中提供了 DPI 更改处理程序示例代码。</span><span class="sxs-lookup"><span data-stu-id="4d82f-294">Sample DPI change handler code can be found in the [WM_DPICHANGED](https://msdn.microsoft.com/en-us/library/windows/desktop/dn312083(v=vs.85).aspx) article.</span></span> 

<span data-ttu-id="4d82f-295">如果 COM 加载项显示已设置为 Office 中某个窗口的父级的子窗口，则它无法接收 DPI 通知。</span><span class="sxs-lookup"><span data-stu-id="4d82f-295">COM add-ins that show child windows that are parented to a window in Office cannot receive DPI notifications.</span></span> <span data-ttu-id="4d82f-296">如果绘制错误，则用户需要使用 [Office DPI 兼容性模式](https://support.office.com/zh-CN/article/office-support-for-high-definition-displays-6720ca0e-be59-41f6-b629-1369f549279d)。</span><span class="sxs-lookup"><span data-stu-id="4d82f-296">If they are drawing incorrectly, the user will need to use [Office DPI compatibility mode](https://support.office.com/zh-CN/article/office-support-for-high-definition-displays-6720ca0e-be59-41f6-b629-1369f549279d).</span></span>

<h3 id="activex-controls"><span data-ttu-id="4d82f-297">ActiveX 控件</span><span class="sxs-lookup"><span data-stu-id="4d82f-297">ActiveX controls</span></span></h3>

<span data-ttu-id="4d82f-298">如何支持 ActiveX 控件中的 DPI 缩放取决于该控件是窗口化控件还是无窗口控件。</span><span class="sxs-lookup"><span data-stu-id="4d82f-298">How to support DPI scaling in ActiveX controls depends on whether the control is windowed or windowless.</span></span>

#### <a name="windowed-activex-controls"></a><span data-ttu-id="4d82f-299">窗口化 ActiveX 控件</span><span class="sxs-lookup"><span data-stu-id="4d82f-299">Windowed ActiveX controls</span></span>

<span data-ttu-id="4d82f-300">每次调整控件大小时，窗口化 ActiveX 控件均会收到 WM_SIZE 消息。</span><span class="sxs-lookup"><span data-stu-id="4d82f-300">Windowed ActiveX controls receive a WM_SIZE message each time the control is resized.</span></span>  <span data-ttu-id="4d82f-301">触发此事件后，事件处理程序代码将会使用该控件的 HWND 调用 [GetDpiForWindow](https://docs.microsoft.com/zh-CN/windows/desktop/api/winuser/nf-winuser-getdpiforwindow) 函数，以获取 DPI、计算缩放比例差异并按需要进行调整。</span><span class="sxs-lookup"><span data-stu-id="4d82f-301">When this event is triggered, the event handler code can call the [GetDpiForWindow](https://docs.microsoft.com/zh-CN/windows/desktop/api/winuser/nf-winuser-getdpiforwindow) function using the HWND of the control to get the DPI, calculate the scale factor differences, and adjust as needed.</span></span> 

<span data-ttu-id="4d82f-302">以下示例中启用了基于 MFC 的 ActiveX 控件，以响应 **OnSize** 事件。</span><span class="sxs-lookup"><span data-stu-id="4d82f-302">The following example enables an MFC-based ActiveX control to respond to the **OnSize** event.</span></span> 

```cpp
void ChangeWindowFontDPI(HWND hWnd, UINT dpi) 
{ 
LOGFONT fontInfo1 = { 0 }; 
// Calculate the font height based on the DPI. 
fontInfo1.lfHeight = -MulDiv(DESIRED_HEIGHT, dpi, 72); 
fontInfo1.lfQuality = CLEARTYPE_QUALITY; 
wcscpy_s(fontInfo1.lfFaceName, DESIRED_FONT_NAME); 
 
::SendMessage(hWnd, WM_SETFONT, (WPARAM)::CreateFontIndirectW(&fontInfo1), TRUE); 
} 
 
BOOL CALLBACK CMainDialog::EnumChildProc(HWND hWnd, LPARAM lParam) 
{ 
CMainDialog* _this = (CMainDialog*) lParam; 
if (_this != nullptr) 
{ 
// Calculate the scale factor difference between the old and new DPI changes. 
double scale = (((double) _this->m_newDPI) /  
   (((double) _this->m_currentDPI) / 100.0)) / 100; 
 
RECT rect = {}; 
::GetWindowRect(hWnd, &rect); 
 
POINT pt = { rect.left, rect.top }; 
::ScreenToClient(::GetParent(hWnd), &pt); 
 
// Adjust the window based on the scale changes. 
::MoveWindow(hWnd, 
pt.x * scale, 
pt.y * scale, 
(rect.right - rect.left) * scale, 
(rect.bottom - rect.top) * scale, 
TRUE); 
 
ChangeWindowFontDPI(hWnd, _this->m_newDPI); 
return TRUE; 
} 
return FALSE; 
} 
 
void CMainDialog::OnSize(UINT nType, int cx, int cy) 
{ 
CDialog::OnSize(nType, cx, cy); 
 
// Get the new DPI and enumerate the child windows that will use that value. 
m_currentDPI = ::GetDpiForWindow(this->GetSafeHwnd()); 
::EnumChildWindows(this->GetSafeHwnd(), EnumChildProc, (LPARAM)this); 
} 
```

#### <a name="windowless-activex-controls"></a><span data-ttu-id="4d82f-303">无窗口 ActiveX 控件</span><span class="sxs-lookup"><span data-stu-id="4d82f-303">Windowless ActiveX controls</span></span>

<span data-ttu-id="4d82f-304">无法确保无窗口 ActiveX 控件拥有 HWND。</span><span class="sxs-lookup"><span data-stu-id="4d82f-304">Windowless ActiveX controls are not guaranteed have an HWND.</span></span>  <span data-ttu-id="4d82f-305">将 ActiveX 控件插入到文档画布中后，该控件即处于设计模式。</span><span class="sxs-lookup"><span data-stu-id="4d82f-305">When an ActiveX control is inserted onto a document canvas, it is put into design mode.</span></span>  <span data-ttu-id="4d82f-306">在 Office 应用程序中，如果控件处于设计模式，则在 ::OnDrawll 事件中调用 hDC->GetWindow() 时，托管容器将会返回 0。</span><span class="sxs-lookup"><span data-stu-id="4d82f-306">In Office applications, the hosting container will return 0 for the call to hDC->GetWindow() in the ::OnDraw event when the control is in design mode.</span></span>  <span data-ttu-id="4d82f-307">在此情况下，无法检索到可靠的 DPI。</span><span class="sxs-lookup"><span data-stu-id="4d82f-307">A reliable DPI cannot be retrieved in this case.</span></span> 

<span data-ttu-id="4d82f-308">但是，如果控件处于运行时模式，则 Office 将在绘制控件的位置返回 HWND。</span><span class="sxs-lookup"><span data-stu-id="4d82f-308">However, when the control is in runtime mode, Office will return the HWND where the control is to be drawn.</span></span>  <span data-ttu-id="4d82f-309">在此情况下，空间开发人员可以调用 [GetDpiForWindow](https://docs.microsoft.com/zh-CN/windows/desktop/api/winuser/nf-winuser-getdpiforwindow) 并获取当前 DPI 和缩放字体、控件等。</span><span class="sxs-lookup"><span data-stu-id="4d82f-309">In this case, the control developer can call [GetDpiForWindow](https://docs.microsoft.com/zh-CN/windows/desktop/api/winuser/nf-winuser-getdpiforwindow) and get the current DPI and scale fonts, controls, and so on.</span></span> 

<h3 id="ribbon-extensibility"><span data-ttu-id="4d82f-310">自定义功能区扩展性</span><span class="sxs-lookup"><span data-stu-id="4d82f-310">Custom ribbon extensibility</span></span></h3>

<span data-ttu-id="4d82f-311">来自 Office 自定义功能区控件的任何回调将处于系统 DPI 感知的 DPI 线程感知中。</span><span class="sxs-lookup"><span data-stu-id="4d82f-311">Any callbacks from Office for custom ribbon controls will be in a DPI thread awareness of System DPI aware.</span></span>  <span data-ttu-id="4d82f-312">如果解决方案期望获得不同的 DPI 线程感知，则应使用上下文块设置预期的线程感知。</span><span class="sxs-lookup"><span data-stu-id="4d82f-312">If your solution is expecting a different DPI thread awareness, you should implement a context block to set the thread awareness as expected.</span></span> <span data-ttu-id="4d82f-313">有关详细信息，请参阅[构建上下文块](#Build-a-context-block-for-incoming-thread-calls)。</span><span class="sxs-lookup"><span data-stu-id="4d82f-313">For more information, see [Build a context block](#Build-a-context-block-for-incoming-thread-calls).</span></span>

<h3 id="ole"><span data-ttu-id="4d82f-314">OLE 客户端和服务器</span><span class="sxs-lookup"><span data-stu-id="4d82f-314">RADIUS clients and servers</span></span></h3>

<span data-ttu-id="4d82f-315">如果 OLE 服务器托管在 OLE 客户端容器内，则此时无法提供当前或受支持的 DPI 信息。</span><span class="sxs-lookup"><span data-stu-id="4d82f-315">When an OLE server is hosted within an OLE client container, you currently can’t provide current or supported DPI information.</span></span> <span data-ttu-id="4d82f-316">这可能会导致出现问题，因为当前 Windows 体系结构不支持某些父窗口到子窗口的混合模式组合。</span><span class="sxs-lookup"><span data-stu-id="4d82f-316">This can cause problems because some combinations of parent to child window mixed modes are not supported by the current Windows architecture.</span></span> <span data-ttu-id="4d82f-317">如果 Word 或 Excel 检测到有多个具有不同 DPI 缩放的监视器，则它们不支持就地激活。</span><span class="sxs-lookup"><span data-stu-id="4d82f-317">If Word or Excel detect that there are multiple monitors with different DPI scales, they will not support in-place activation.</span></span> <span data-ttu-id="4d82f-318">OLE 服务器将会进行非现场激活。</span><span class="sxs-lookup"><span data-stu-id="4d82f-318">Your OLE server will activate out-of-place.</span></span> <span data-ttu-id="4d82f-319">如果遇到 OLE 服务器交互方面的问题，则用户需要使用 [Office DPI 兼容性模式](https://support.office.com/zh-CN/article/office-support-for-high-definition-displays-6720ca0e-be59-41f6-b629-1369f549279d)。</span><span class="sxs-lookup"><span data-stu-id="4d82f-319">If you are experiencing issues with OLE server interactions, the user will need to use [Office DPI compatibility mode](https://support.office.com/zh-CN/article/office-support-for-high-definition-displays-6720ca0e-be59-41f6-b629-1369f549279d).</span></span>

<h3 id="web-add-ins"><span data-ttu-id="4d82f-320">Office Web 加载项</span><span class="sxs-lookup"><span data-stu-id="4d82f-320">Office Web Add-ins</span></span></h3>

<span data-ttu-id="4d82f-321">使用 Office JavaScript API 构建的 Office 加载项将在浏览器控件中运行。</span><span class="sxs-lookup"><span data-stu-id="4d82f-321">Office Add-ins built using the Office JavaScript API run inside a browser control.</span></span> <span data-ttu-id="4d82f-322">可以使用与任何 Web 应用程序设计中所使用的相同技术处理 DPI 缩放。</span><span class="sxs-lookup"><span data-stu-id="4d82f-322">You can handle DPI scaling using the same techniques used in any web app design.</span></span> <span data-ttu-id="4d82f-323">为高清晰度的屏幕设计网页时，可以借助多种在线资源。</span><span class="sxs-lookup"><span data-stu-id="4d82f-323">Many online resources are available to help design a web page for high resolution screens.</span></span>

## <a name="verify-that-your-solution-supports-dpi-scaling"></a><span data-ttu-id="4d82f-324">验证你的解决方案是否支持 DPI 缩放</span><span class="sxs-lookup"><span data-stu-id="4d82f-324">Verify that your solution supports DPI scaling</span></span>

<span data-ttu-id="4d82f-325">更新应用程序以支持 DPI 缩放之后，应在混合 DPI 环境中验证你的更改。</span><span class="sxs-lookup"><span data-stu-id="4d82f-325">After you have updated your application to support DPI scaling, you should validate your changes in a mixed-DPI environment.</span></span> <span data-ttu-id="4d82f-326">将解决方案的窗口从一台显示器移至具有不同 DPI 值的另一个窗口时，验证你的 UI 代码是否可以正确响应 DPI 更改。</span><span class="sxs-lookup"><span data-stu-id="4d82f-326">Validate that your UI code responds properly to DPI changes when your solution’s windows are moved from one display to another that has different DPI values.</span></span> <span data-ttu-id="4d82f-327">有关 DPI 缩放测试技术的详细信息，请参阅 [Windows 上的高 DPI 桌面应用程序开发](https://docs.microsoft.com/zh-CN/windows/desktop/hidpi/high-dpi-desktop-application-development-on-windows#related-topics)。</span><span class="sxs-lookup"><span data-stu-id="4d82f-327">For more information about DPI scaling testing techniques, see [High DPI Desktop Application Development on Windows](https://docs.microsoft.com/zh-CN/windows/desktop/hidpi/high-dpi-desktop-application-development-on-windows#related-topics).</span></span>

<span data-ttu-id="4d82f-328">此外，以下技术可能会对你有用：</span><span class="sxs-lookup"><span data-stu-id="4d82f-328">You might also find these additional techniques helpful:</span></span>

- <span data-ttu-id="4d82f-329">在笔记本电脑上，可以将主监视器设为外部监视器，然后脱开笔记本电脑。</span><span class="sxs-lookup"><span data-stu-id="4d82f-329">With a laptop, you can set the primary monitor to an external monitor, then undock the laptop.</span></span> <span data-ttu-id="4d82f-330">这将强制主监视器更改笔记本电脑显示。</span><span class="sxs-lookup"><span data-stu-id="4d82f-330">This will force the primary monitor to change to the laptop display.</span></span>
- <span data-ttu-id="4d82f-331">使用开源 [WinSpy++ 工具](https://github.com/BissetJ/winspy/releases)协助调试。</span><span class="sxs-lookup"><span data-stu-id="4d82f-331">Use the open source [WinSpy++ tool](https://github.com/BissetJ/winspy/releases) to help debug.</span></span> <span data-ttu-id="4d82f-332">可以用它来查看任何窗口的 DPI 感知设置。</span><span class="sxs-lookup"><span data-stu-id="4d82f-332">You can use it to see the DPI awareness setting of any window.</span></span>
- <span data-ttu-id="4d82f-333">可以使用远程桌面来在远程计算机上测试多台监视器，方法是在“显示”选项卡的远程会话中选择“使用所有监视器”，如下面的屏幕截图所示。</span><span class="sxs-lookup"><span data-stu-id="4d82f-333">You can use remote desktop to test multiple monitors on a remote computer by selecting Use all my monitors for the remote session on the Display tab, as shown in the following screenshot.</span></span>

![远程会话中显示有“显示”选项卡并选择“使用所有监视器”的远程桌面连接应用程序。](./media/remote-desktop-use-all-monitors.png)

## <a name="see-also"></a><span data-ttu-id="4d82f-335">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4d82f-335">See also</span></span>

### <a name="articles"></a><span data-ttu-id="4d82f-336">文章</span><span class="sxs-lookup"><span data-stu-id="4d82f-336">Articles</span></span>

- <span data-ttu-id="4d82f-337">
  [编写 DPI 感知桌面和 Win32 应用程序](https://msdn.microsoft.com/en-us/library/windows/desktop/dn469266(v=vs.85).aspx)中提供了编写 Win32 桌面应用程序的一般性概述和指南。</span><span class="sxs-lookup"><span data-stu-id="4d82f-337">[Writing DPI-Aware Desktop and Win32 Applications](https://msdn.microsoft.com/en-us/library/windows/desktop/dn469266(v=vs.85).aspx) provides a general overview and guide for writing Win32 desktop applications.</span></span> <span data-ttu-id="4d82f-338">本文中所述的许多相同技术适用于 Office 扩展性解决方案。</span><span class="sxs-lookup"><span data-stu-id="4d82f-338">Many of the same techniques described in this article will apply to Office extensibility solutions.</span></span>
- <span data-ttu-id="4d82f-339">
  [混合模式 DPI 缩放和 DPI 感知 API](https://msdn.microsoft.com/en-us/library/windows/desktop/mt744321(v=vs.85).aspx) 中提供有一个与 DPI 相关的 API 列表。</span><span class="sxs-lookup"><span data-stu-id="4d82f-339">[Mixed-Mode DPI Scaling and DPI-aware APIs](https://msdn.microsoft.com/en-us/library/windows/desktop/mt744321(v=vs.85).aspx) has a list of APIs related to DPI.</span></span>
- <span data-ttu-id="4d82f-340">[开发人员指南 - 按监视器 DPI - WPF 预览](https://github.com/Microsoft/WPF-Samples/blob/master/PerMonitorDPI/Developer%20Guide%20-%20Per%20Monitor%20DPI%20-%20WPF%20Preview.docx)介绍了构建 DPI 感知 WPF 应用程序的开发指南。</span><span class="sxs-lookup"><span data-stu-id="4d82f-340">[Developer Guide - Per Monitor DPI - WPF Preview](https://github.com/Microsoft/WPF-Samples/blob/master/PerMonitorDPI/Developer%20Guide%20-%20Per%20Monitor%20DPI%20-%20WPF%20Preview.docx) covers the WPF app development guide for building DPI-aware WPF apps.</span></span>
- <span data-ttu-id="4d82f-341">[高清晰度显示器的 Office 支持](https://support.office.com/zh-CN/article/office-support-for-high-definition-displays-6720ca0e-be59-41f6-b629-1369f549279d)中提供了相关的信息，让用户知道在因 DPI 发生更改而使 Office 解决方案不受支持时，如何设置 Office 以优化兼容性。</span><span class="sxs-lookup"><span data-stu-id="4d82f-341">[Office support for high definition displays](https://support.office.com/zh-CN/article/office-support-for-high-definition-displays-6720ca0e-be59-41f6-b629-1369f549279d) provides information about how a user can set Office to optimize for compatibility if your Office solution is not supported properly when the DPI changes.</span></span>
- <span data-ttu-id="4d82f-342">[Windows 10 周年更新的显示器缩放更改](https://blogs.technet.microsoft.com/askcore/2016/08/16/display-scaling-changes-for-the-windows-10-anniversary-update/)博客文章介绍了 Windows 10 周年更新中引入的更改。</span><span class="sxs-lookup"><span data-stu-id="4d82f-342">[Display Scaling changes for the Windows 10 Anniversary Update](https://blogs.technet.microsoft.com/askcore/2016/08/16/display-scaling-changes-for-the-windows-10-anniversary-update/) is a blog post that covers changes introduce with the Windows 10 Anniversary update.</span></span> 
- <span data-ttu-id="4d82f-343">[DPI_AWARENESS_CONTEXT 句柄](https://docs.microsoft.com/zh-CN/windows/desktop/hidpi/dpi-awareness-context)具有与 DPI_AWARENESS_CONTEXT 值和定义相关的编程详细信息。</span><span class="sxs-lookup"><span data-stu-id="4d82f-343">[DPI_AWARENESS_CONTEXT handle](https://docs.microsoft.com/zh-CN/windows/desktop/hidpi/dpi-awareness-context) has programming details on the DPI_AWARENESS_CONTEXT values and definitions.</span></span>
- <span data-ttu-id="4d82f-344">[Windows 上的高 DPI 桌面应用程序开发](https://docs.microsoft.com/zh-CN/windows/desktop/hidpi/high-dpi-desktop-application-development-on-windows#testing-your-changes)的“测试更改”部分包括了与测试相关的信息。</span><span class="sxs-lookup"><span data-stu-id="4d82f-344">[High DPI Desktop Application Development on Windows](https://docs.microsoft.com/zh-CN/windows/desktop/hidpi/high-dpi-desktop-application-development-on-windows#testing-your-changes) includes information about testing in the Testing Your Changes section.</span></span>

### <a name="code-samples"></a><span data-ttu-id="4d82f-345">代码示例</span><span class="sxs-lookup"><span data-stu-id="4d82f-345">Code samples</span></span>

- [<span data-ttu-id="4d82f-346">按窗口 DPI 感知示例</span><span class="sxs-lookup"><span data-stu-id="4d82f-346">Per-window DPI Awareness sample</span></span>](https://github.com/Microsoft/Windows-classic-samples/tree/master/Samples/DPIAwarenessPerWindow)
- [<span data-ttu-id="4d82f-347">动态 DPI 示例</span><span class="sxs-lookup"><span data-stu-id="4d82f-347">Dynamic DPI sample</span></span>](https://github.com/Microsoft/Windows-classic-samples/tree/master/Samples/DynamicDPI)
- [<span data-ttu-id="4d82f-348">按监视器感知 WPF 示例</span><span class="sxs-lookup"><span data-stu-id="4d82f-348">Per-Monitor Aware WPF sample</span></span>](https://github.com/Microsoft/Windows-classic-samples/tree/master/Samples/PerMonitorDPIAware)