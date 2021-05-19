---
title: 在 Office 解决方案中处理高 DPI 和 DPI 缩放
description: 更新 Office 解决方案（如自定义任务窗格或 ActiveX 控件）以支持高 DPI 监视器。
ms.date: 03/09/2019
localization_priority: Normal
ms.openlocfilehash: 78179b958bc57137c0565b8b1ca5feb40f61fe0e
ms.sourcegitcommit: 939bd9686ba41a8f94b82e004ed84b9054d9c7cf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/28/2020
ms.locfileid: "48293476"
---
# <a name="handle-high-dpi-and-dpi-scaling-in-your-office-solution"></a><span data-ttu-id="05746-103">在 Office 解决方案中处理高 DPI 和 DPI 缩放</span><span class="sxs-lookup"><span data-stu-id="05746-103">Handle high DPI and DPI scaling in your Office solution</span></span>

<span data-ttu-id="05746-104">许多计算机和显示器配置现在都支持高 DPI（每英寸点数）分辨率，并且可以连接具有不同大小和像素密度的多个监视器。</span><span class="sxs-lookup"><span data-stu-id="05746-104">Many computer and display configurations now support high DPI (dots-per-inch) resolutions, and can connect multiple monitors with different sizes and pixel densities.</span></span> <span data-ttu-id="05746-105">这要求用户将应用移动到具有不同 DPI 的监视器时调整应用程序，或者更改缩放级别。</span><span class="sxs-lookup"><span data-stu-id="05746-105">This requires applications to adjust when the user moves the app to a monitor with a different DPI, or changes the zoom level.</span></span> <span data-ttu-id="05746-106">不支持 DPI 缩放的应用程序在低 DPI 监视器上可能看起来很好，但在高 DPI 监视器上将显得模糊不清。</span><span class="sxs-lookup"><span data-stu-id="05746-106">Applications that don’t support DPI scaling might look fine on low DPI monitors, but will look stretched and blurry when shown on a high DPI monitor.</span></span> 

<span data-ttu-id="05746-107">Office 2016 应用程序（如 Word 和 Excel）已更新，以响应缩放比例的更改。</span><span class="sxs-lookup"><span data-stu-id="05746-107">Office 2016 applications, such as Word and Excel, have been updated to respond to changes in scale factor.</span></span> <span data-ttu-id="05746-108">然而，你的 Office 解决方案还必须响应更改，以便在 DPI 更改时正确进行绘制。</span><span class="sxs-lookup"><span data-stu-id="05746-108">However, your Office solution must also respond to changes to draw correctly when the DPI changes.</span></span> <span data-ttu-id="05746-109">本文介绍 Office 如何支持动态 DPI，以及你可以采取哪些步骤来确保 Office 可扩展性解决方案在处理 DPI 缩放时带来最佳查看体验。</span><span class="sxs-lookup"><span data-stu-id="05746-109">This article describes how Office supports dynamic DPI, and what steps you can take to ensure the best viewing experience for your Office extensibility solution to handle DPI scaling.</span></span> 

## <a name="dpi-scaling-symptoms-in-your-solution"></a><span data-ttu-id="05746-110">解决方案中的 DPI 缩放症状</span><span class="sxs-lookup"><span data-stu-id="05746-110">DPI scaling symptoms in your solution</span></span>

<span data-ttu-id="05746-111">当应用程序从一个显示器移动到另一个具有不同 DPI 的显示器时，Windows 会应用 DPI 缩放。</span><span class="sxs-lookup"><span data-stu-id="05746-111">Windows applies DPI scaling when an application is moved from one display to another display with a different DPI.</span></span> <span data-ttu-id="05746-112">例如，将应用程序拖动到其他显示器或插接笔记本电脑时会发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="05746-112">This happens in scenarios such as dragging an application to a different monitor or docking your laptop.</span></span> <span data-ttu-id="05746-113">如果 DPI 缩放对你的 Office 解决方案造成不良影响，你将看到以下一个或多个症状：</span><span class="sxs-lookup"><span data-stu-id="05746-113">If your Office solution is adversely affected by DPI scaling, you will see one or more of the following symptoms:</span></span>

- <span data-ttu-id="05746-114">Windows 在错误位置绘制或者大小调整不正确。</span><span class="sxs-lookup"><span data-stu-id="05746-114">The windows draw in the wrong location or have incorrect sizing.</span></span>
- <span data-ttu-id="05746-115">按钮和标签等元素显示在解决方案窗口的错误位置。</span><span class="sxs-lookup"><span data-stu-id="05746-115">Elements such as buttons and labels appear in the wrong location in your solution’s window.</span></span>
- <span data-ttu-id="05746-116">字体和图像显得太小、太大或位于错误位置。</span><span class="sxs-lookup"><span data-stu-id="05746-116">Fonts and images appear too small, too large or in the wrong location.</span></span>

<span data-ttu-id="05746-117">DPI 缩放可能会影响以下类型的 Office 解决方案：</span><span class="sxs-lookup"><span data-stu-id="05746-117">The following types of Office solutions can be affected by DPI scaling:</span></span>

- <span data-ttu-id="05746-118">VSTO 加载项</span><span class="sxs-lookup"><span data-stu-id="05746-118">VSTO Add-ins</span></span>
- <span data-ttu-id="05746-119">自定义任务窗格</span><span class="sxs-lookup"><span data-stu-id="05746-119">Custom task panes</span></span>
- <span data-ttu-id="05746-120">COM 加载项</span><span class="sxs-lookup"><span data-stu-id="05746-120">COM Add-ins</span></span>
- <span data-ttu-id="05746-121">ActiveX 控件</span><span class="sxs-lookup"><span data-stu-id="05746-121">ActiveX controls</span></span>
- <span data-ttu-id="05746-122">功能区扩展</span><span class="sxs-lookup"><span data-stu-id="05746-122">Ribbon extensions</span></span>
- <span data-ttu-id="05746-123">Ole 服务器</span><span class="sxs-lookup"><span data-stu-id="05746-123">Ole servers</span></span>
- <span data-ttu-id="05746-124">Office Web 加载项</span><span class="sxs-lookup"><span data-stu-id="05746-124">Office web add-ins</span></span>

## <a name="windows-dpi-awareness-modes"></a><span data-ttu-id="05746-125">Windows DPI 感知模式</span><span class="sxs-lookup"><span data-stu-id="05746-125">Windows DPI awareness modes</span></span>

<span data-ttu-id="05746-126">在整篇文章中，我们将引用 Windows 支持的 DPI 感知模式。</span><span class="sxs-lookup"><span data-stu-id="05746-126">Throughout this article we’ll refer to the DPI awareness modes that Windows supports.</span></span> <span data-ttu-id="05746-127">每种 DPI 感知模式都支持不同的功能，如下表所述。</span><span class="sxs-lookup"><span data-stu-id="05746-127">Each DPI awareness mode supports different capabilities, as described in the following table.</span></span> <span data-ttu-id="05746-128">这是有关这些模式的简化描述，用于介绍 Office 如何为其提供支持。</span><span class="sxs-lookup"><span data-stu-id="05746-128">This is a simplified description of the modes to explain how Office solutions support them.</span></span> <span data-ttu-id="05746-129">有关 DPI 感知模式的详细信息，请参阅 [Windows 上的高 DPI 桌面应用程序开发](https://docs.microsoft.com/windows/desktop/hidpi/high-dpi-desktop-application-development-on-windows)。</span><span class="sxs-lookup"><span data-stu-id="05746-129">For more information about the DPI awareness modes, see [High DPI Desktop Application Development on Windows](https://docs.microsoft.com/windows/desktop/hidpi/high-dpi-desktop-application-development-on-windows).</span></span>

|<span data-ttu-id="05746-130">模式</span><span class="sxs-lookup"><span data-stu-id="05746-130">Mode</span></span>  |<span data-ttu-id="05746-131">说明</span><span class="sxs-lookup"><span data-stu-id="05746-131">Description</span></span>  |<span data-ttu-id="05746-132">DPI 发生更改时</span><span class="sxs-lookup"><span data-stu-id="05746-132">When DPI changes</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="05746-133">非 DPI 感知</span><span class="sxs-lookup"><span data-stu-id="05746-133">DPI unaware</span></span> |  <span data-ttu-id="05746-134">应用程序始终呈现为如同在 DPI 值为 96 的显示器上显示。</span><span class="sxs-lookup"><span data-stu-id="05746-134">Application always renders as if it is on a display with a DPI value of 96.</span></span> |  <span data-ttu-id="05746-135">应用程序在主显示器和辅助显示器上将位图拉伸到预期大小。</span><span class="sxs-lookup"><span data-stu-id="05746-135">Application is bitmap stretched to expected size on primary and secondary displays.</span></span>    |
|<span data-ttu-id="05746-136">系统 DPI 感知</span><span class="sxs-lookup"><span data-stu-id="05746-136">System DPI aware</span></span> |  <span data-ttu-id="05746-137">应用程序将在 Windows 登录时检测主连接监视器的 DPI，但无法响应 DPI 更改。</span><span class="sxs-lookup"><span data-stu-id="05746-137">Application detects the DPI of the primary connected monitor at Windows login but cannot respond to DPI changes.</span></span> <span data-ttu-id="05746-138">有关详细信息，请参阅本文中的配置Windows[修复](#configure-windows-to-fix-blurry-apps)模糊应用部分。</span><span class="sxs-lookup"><span data-stu-id="05746-138">For more information, see the [Configure Windows to fix blurry apps](#configure-windows-to-fix-blurry-apps) section in this article.</span></span>  | <span data-ttu-id="05746-139">当移动到具有不同 DPI 的新显示器时，应用程序将拉伸位图。</span><span class="sxs-lookup"><span data-stu-id="05746-139">Application is bitmap stretched when moved to a new display with a different DPI.</span></span>    |
|<span data-ttu-id="05746-140">按监视器 DPI 感知</span><span class="sxs-lookup"><span data-stu-id="05746-140">Per Monitor DPI aware</span></span> |  <span data-ttu-id="05746-141">应用程序能够在 DPI 发生更改时正确地进行重绘。</span><span class="sxs-lookup"><span data-stu-id="05746-141">Application is capable of redrawing itself correctly when the DPI changes.</span></span>  |   <span data-ttu-id="05746-142">Windows 会将 DPI 通知发送到应用程序中的顶级窗口，以便在 DPI 发生更改时进行重绘。</span><span class="sxs-lookup"><span data-stu-id="05746-142">Windows will send DPI notifications to top-level windows in the application so that it can redraw when the DPI changes.</span></span>     |
|<span data-ttu-id="05746-143">按监视器 v2</span><span class="sxs-lookup"><span data-stu-id="05746-143">Per Monitor v2</span></span> |  <span data-ttu-id="05746-144">应用程序能够在 DPI 发生更改时正确地进行重绘。</span><span class="sxs-lookup"><span data-stu-id="05746-144">Application is capable of redrawing itself correctly when the DPI changes.</span></span>  |   <span data-ttu-id="05746-145">Windows 将同时向顶级窗口和子窗口发送 DPI 通知，以便应用程序能够在 DPI 发生更改时进行重绘。</span><span class="sxs-lookup"><span data-stu-id="05746-145">Windows will send DPI notifications to both top-level and child windows so that the application can redraw when the DPI changes.</span></span> |

## <a name="how-office-supports-dpi-scaling"></a><span data-ttu-id="05746-146">Office 如何支持 DPI 缩放</span><span class="sxs-lookup"><span data-stu-id="05746-146">How Office supports DPI scaling</span></span>

<span data-ttu-id="05746-147">决定 Office 解决方案如何处理 DPI 缩放的最重要因素是你的解决方案是顶级窗口还是子窗口。</span><span class="sxs-lookup"><span data-stu-id="05746-147">The most significant factor in determining how your Office solution can handle DPI scaling is whether your solution is a top-level window, or a child window.</span></span> <span data-ttu-id="05746-148">下图显示了作为顶级窗口或子窗口运行的 Office 解决方案的一些示例，以及它们将在 Windows 2018 年 4 月更新 (1803) 及更高版本中使用的 DPI 感知模式。</span><span class="sxs-lookup"><span data-stu-id="05746-148">The following picture shows a few examples of Office solutions running as top-level or child windows, and which DPI awareness mode they will use on Windows April 2018 Update (1803) and later.</span></span>

![Excel 将 ActiveX 控件和自定义任务窗格托管为子窗口。](./media/office-dpi-awareness-for-solution-types.png)

<span data-ttu-id="05746-152">在此图中：</span><span class="sxs-lookup"><span data-stu-id="05746-152">In this image:</span></span>
- <span data-ttu-id="05746-153">COM/VSTO 顶级窗口是“按监视器 DPI 感知”。</span><span class="sxs-lookup"><span data-stu-id="05746-153">The COM/VSTO top-level window is Per Monitor DPI aware.</span></span>
- <span data-ttu-id="05746-154">ActiveX 控件子窗口是“系统 DPI 感知”。</span><span class="sxs-lookup"><span data-stu-id="05746-154">The ActiveX control child window is System DPI aware.</span></span>
- <span data-ttu-id="05746-155">Office 顶级窗口是“按监视器 DPI 感知”。</span><span class="sxs-lookup"><span data-stu-id="05746-155">The Office top-level window is Per Monitor DPI aware.</span></span>
- <span data-ttu-id="05746-156">自定义任务窗格子窗口是“系统 DPI 感知”。</span><span class="sxs-lookup"><span data-stu-id="05746-156">The custom task pane child window is System DPI aware.</span></span>

## <a name="managing-thread-dpi-context"></a><span data-ttu-id="05746-157">管理线程 DPI 上下文</span><span class="sxs-lookup"><span data-stu-id="05746-157">Managing thread DPI context</span></span>

<span data-ttu-id="05746-158">当主机 Office 应用启动时，其主线程将在“按监视器 DPI 感知”上下文中运行。</span><span class="sxs-lookup"><span data-stu-id="05746-158">When the host Office app starts, its main thread runs in Per Monitor DPI aware context.</span></span> <span data-ttu-id="05746-159">当你的解决方案代码创建线程或从 Office 接收调用时，你需要管理线程 DPI 上下文。</span><span class="sxs-lookup"><span data-stu-id="05746-159">When your solution code creates threads, or receives calls from Office, you need to manage the thread DPI context.</span></span>

### <a name="creating-new-threads-with-the-correct-dpi-context"></a><span data-ttu-id="05746-160">使用正确的 DPI 上下文创建新线程</span><span class="sxs-lookup"><span data-stu-id="05746-160">Creating new threads with the correct DPI context</span></span>

<span data-ttu-id="05746-161">如果你的解决方案创建了其他线程，则 Office 将强制该线程进入“按监视器 DPI 感知”上下文。</span><span class="sxs-lookup"><span data-stu-id="05746-161">If your solution creates additional threads, Office will force the threads into Per Monitor DPI aware context.</span></span> <span data-ttu-id="05746-162">如果你的代码需要不同的上下文，则需要使用 [SetThreadDpiAwarenessContext](https://docs.microsoft.com/windows/desktop/api/winuser/nf-winuser-setthreaddpiawarenesscontext) 函数设置预期的线程 DPI 感知。</span><span class="sxs-lookup"><span data-stu-id="05746-162">If your code expects a different context, you need to use the [SetThreadDpiAwarenessContext](https://docs.microsoft.com/windows/desktop/api/winuser/nf-winuser-setthreaddpiawarenesscontext) function to set the expected thread DPI awareness.</span></span> 

### <a name="build-a-context-block-for-incoming-thread-calls"></a><span data-ttu-id="05746-163">为传入的线程调用构建上下文块</span><span class="sxs-lookup"><span data-stu-id="05746-163">Build a context block for incoming thread calls</span></span>

![该图显示 Office 应用中的上下文块，它在调用顶级窗口时将线程切换到系统感知上下文。](./media/thread-dpi-awareness-context-block.png)

<span data-ttu-id="05746-165">你的解决方案将与其主机 Office 应用进行交互，因此你可以对 Office 中的解决方案进行传入调用，例如事件回调。</span><span class="sxs-lookup"><span data-stu-id="05746-165">Your solution will interact with its host Office app, so you will have incoming calls to your solution from Office such as event callbacks.</span></span> <span data-ttu-id="05746-166">当 Office 调用你的解决方案时，它有一个上下文块，用于强制线程上下文位于“系统 DPI 感知”上下文中。</span><span class="sxs-lookup"><span data-stu-id="05746-166">When Office calls your solution, it has a context block that forces the thread context to be in System DPI Aware context.</span></span> <span data-ttu-id="05746-167">你必须更改线程上下文，使其匹配窗口的 DPI 感知。</span><span class="sxs-lookup"><span data-stu-id="05746-167">You must change the thread context to match the DPI awareness of your window.</span></span> <span data-ttu-id="05746-168">你可以实施类似的上下文块以切换传入调用的线程上下文。</span><span class="sxs-lookup"><span data-stu-id="05746-168">You can implement a similar context block to switch the thread context on incoming calls.</span></span> <span data-ttu-id="05746-169">使用 [SetThreadDpiAwarenessContext](https://docs.microsoft.com/windows/desktop/api/winuser/nf-winuser-setthreaddpiawarenesscontext) 函数更改上下文，使其匹配窗口上下文。</span><span class="sxs-lookup"><span data-stu-id="05746-169">Use the [SetThreadDpiAwarenessContext](https://docs.microsoft.com/windows/desktop/api/winuser/nf-winuser-setthreaddpiawarenesscontext) function to change the context to match your window context.</span></span> 

> [!NOTE]
> <span data-ttu-id="05746-170">在调用解决方案代码之外的其他组件之前，上下文块应该会还原原始 DPI 线程上下文。</span><span class="sxs-lookup"><span data-stu-id="05746-170">Your context block should restore the original DPI thread context before calling other components outside of your solution code.</span></span>

#### <a name="managed-code-context-block"></a><span data-ttu-id="05746-171">托管代码上下文块</span><span class="sxs-lookup"><span data-stu-id="05746-171">Managed code context block</span></span>

<span data-ttu-id="05746-172">以下示例代码显示了如何构建自己的上下文块。</span><span class="sxs-lookup"><span data-stu-id="05746-172">The following example code shows how to construct your own context block.</span></span>

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
        }

        private static DPI_AWARENESS_CONTEXT DPI_AWARENESS_CONTEXT_HANDLE = IntPtr.Zero;

        public static readonly DPI_AWARENESS_CONTEXT DPI_AWARENESS_CONTEXT_INVALID = IntPtr.Zero;
        public static readonly DPI_AWARENESS_CONTEXT DPI_AWARENESS_CONTEXT_UNAWARE = new IntPtr(-1);
        public static readonly DPI_AWARENESS_CONTEXT DPI_AWARENESS_CONTEXT_SYSTEM_AWARE = new IntPtr(-2);
        public static readonly DPI_AWARENESS_CONTEXT DPI_AWARENESS_CONTEXT_PER_MONITOR_AWARE = new IntPtr(-3);
        public static readonly DPI_AWARENESS_CONTEXT DPI_AWARENESS_CONTEXT_PER_MONITOR_AWARE_V2 = new IntPtr(-4);

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

#### <a name="native-code-context-block"></a><span data-ttu-id="05746-173">本机代码上下文块</span><span class="sxs-lookup"><span data-stu-id="05746-173">Native code context block</span></span>

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

<h2 id="top-level-window-management"><span data-ttu-id="05746-174">顶级窗口管理</span><span class="sxs-lookup"><span data-stu-id="05746-174">Top-level window management</span></span></h2>

<span data-ttu-id="05746-175">当 Office 应用程序启动时，将以 DPI_AWARENESS_CONTEXT_PER_MONITOR_AWARE 的形式调用 [SetThreadDpiAwarenessContext](https://docs.microsoft.com/windows/desktop/api/winuser/nf-winuser-setthreaddpiawarenesscontext)。</span><span class="sxs-lookup"><span data-stu-id="05746-175">When Office applications start, a call is made to [SetThreadDpiAwarenessContext](https://docs.microsoft.com/windows/desktop/api/winuser/nf-winuser-setthreaddpiawarenesscontext) as DPI_AWARENESS_CONTEXT_PER_MONITOR_AWARE.</span></span> <span data-ttu-id="05746-176">在此上下文中，DPI 更改将发送到以“按监视器 DPI 感知”形式运行的进程中的任何顶级窗口的 HWND。</span><span class="sxs-lookup"><span data-stu-id="05746-176">In this context, DPI changes are sent to the HWND of any top-level windows in the process that are running as Per Monitor DPI aware.</span></span> <span data-ttu-id="05746-177">顶级窗口是指 Office 应用程序窗口以及由解决方案创建的任何其他顶级窗口。</span><span class="sxs-lookup"><span data-stu-id="05746-177">Top-level windows are the Office application window, and any additional top-level windows created by your solution.</span></span> <span data-ttu-id="05746-178">将 Office 应用程序移动到新显示器时，系统会通知它，以便它能够按照新显示器的 DPI 正确地进行动态缩放和绘制。</span><span class="sxs-lookup"><span data-stu-id="05746-178">When an Office application is moved to a new display, it gets notified so that it can dynamically scale and draw correctly in the DPI of the new display.</span></span> <span data-ttu-id="05746-179">你的 Office 解决方案可以创建处于任何 DPI 感知模式的顶级窗口。</span><span class="sxs-lookup"><span data-stu-id="05746-179">Your Office solution can create top-level windows that are in any DPI awareness mode.</span></span> <span data-ttu-id="05746-180">顶级窗口还可以通过侦听 Windows 更改消息来响应 DPI 更改。</span><span class="sxs-lookup"><span data-stu-id="05746-180">Your top-level windows can also respond to DPI changes by listening to Windows messages for the changes.</span></span>

<span data-ttu-id="05746-181">如果已创建作为顶级窗口父级的子窗口，则你也可以将它们设置为任何 DPI 感知模式。</span><span class="sxs-lookup"><span data-stu-id="05746-181">If you create child windows that are parented to your top-level window, you can also set them to any DPI awareness mode.</span></span> <span data-ttu-id="05746-182">但是，如果使用“按监视器 DPI 感知”模式，则子窗口将不会收到 DPI 更改通知。</span><span class="sxs-lookup"><span data-stu-id="05746-182">However, if you use Per Monitor DPI aware mode, your child windows will not receive DPI change notifications.</span></span>  <span data-ttu-id="05746-183">有关 Windows DPI 感知模式的详细信息，请参阅 [Windows 上的高 DPI 桌面应用程序开发](https://docs.microsoft.com/windows/desktop/hidpi/high-dpi-desktop-application-development-on-windows)。</span><span class="sxs-lookup"><span data-stu-id="05746-183">For more information about Windows DPI awareness modes, see [High DPI Desktop Application Development on Windows](https://docs.microsoft.com/windows/desktop/hidpi/high-dpi-desktop-application-development-on-windows).</span></span>

## <a name="child-window-management"></a><span data-ttu-id="05746-184">子窗口管理</span><span class="sxs-lookup"><span data-stu-id="05746-184">Child window management</span></span>

<span data-ttu-id="05746-185">使用 ActiveX 控件和自定义任务窗格时，Office 会为你的解决方案创建子窗口。</span><span class="sxs-lookup"><span data-stu-id="05746-185">When working with ActiveX controls and custom task panes, Office creates the child window for your solution.</span></span> <span data-ttu-id="05746-186">你可以创建其他子窗口，但必须知道父窗口 DPI 感知。</span><span class="sxs-lookup"><span data-stu-id="05746-186">You can create additional child windows, but you have to be aware of the parent window DPI awareness.</span></span> <span data-ttu-id="05746-187">Office 在“按监视器 DPI 感知”模式下运行，这意味着解决方案中的任何子窗口都不会收到 DPI 更改通知。</span><span class="sxs-lookup"><span data-stu-id="05746-187">Office runs in Per Monitor DPI awareness mode, which means any child windows in your solution will not get DPI change notifications.</span></span> <span data-ttu-id="05746-188">仅“按监视器 v2”模式支持向子窗口发送 DPI 更改（Office 不支持“按监视器 v2”）。</span><span class="sxs-lookup"><span data-stu-id="05746-188">Only Per Monitor v2 mode supports sending DPI changes to child windows (Office does not support Per Monitor v2).</span></span> <span data-ttu-id="05746-189">但是，对于 ActiveX 控件，有一种解决方法。</span><span class="sxs-lookup"><span data-stu-id="05746-189">However, for ActiveX controls, there is a workaround.</span></span> <span data-ttu-id="05746-190">有关详细信息，请参阅本文后面的 [ActiveX 控件](#activex-controls)部分。</span><span class="sxs-lookup"><span data-stu-id="05746-190">For more information, see the [ActiveX controls](#activex-controls) section later in this article.</span></span>

> [!NOTE]
> <span data-ttu-id="05746-191">如果子窗口创建了顶级窗口，则可以为新的顶级窗口使用任何 DPI 感知模式。</span><span class="sxs-lookup"><span data-stu-id="05746-191">If your child window creates a top-level window, you can use any DPI awareness mode for the new top-level window.</span></span> <span data-ttu-id="05746-192">有关管理顶级窗口的详细信息，请参阅本文的[顶级窗口管理](#top-level-window-management)部分。</span><span class="sxs-lookup"><span data-stu-id="05746-192">For more information about managing top-level windows, see the [Top-level window management](#top-level-window-management) section in this article.</span></span>

<span data-ttu-id="05746-193">您将看到应用于子窗口的两种不同的 DPI 模式，具体取决于运行的 Windows 10 Office 版本。</span><span class="sxs-lookup"><span data-stu-id="05746-193">You will see two different DPI modes applied to your child window, depending on which version of Windows 10 Office is running on.</span></span>

### <a name="office-dpi-behavior-on-windows-fall-creators-update-1709"></a><span data-ttu-id="05746-194">Windows Fall Creators Update (1709) 中的 Office DPI 行为</span><span class="sxs-lookup"><span data-stu-id="05746-194">Office DPI behavior on Windows Fall Creators Update (1709)</span></span>

<span data-ttu-id="05746-195">由于 Office 应用使用按监视器感知模式，因此还将在“按监视器 DPI 感知”模式下为解决方案创建子窗口。</span><span class="sxs-lookup"><span data-stu-id="05746-195">Because Office apps use Per Monitor awareness mode, your solution’s child windows will also be created in Per Monitor DPI awareness mode.</span></span> <span data-ttu-id="05746-196">这意味着 Windows 希望在采用新 DPI 进行绘制时更新解决方案。</span><span class="sxs-lookup"><span data-stu-id="05746-196">This means Windows expects your solution to update when drawing in a new DPI.</span></span>  <span data-ttu-id="05746-197">由于窗口无法收到 DPI 更改通知，因此你的解决方案 UI 可能不正确。</span><span class="sxs-lookup"><span data-stu-id="05746-197">Because your window cannot get DPI change notifications, your solution’s UI might be incorrect.</span></span> 

![该图显示在 Windows Fall Creators Update (1709) 的“按监视器 DPI 感知”上下文中运行的子窗口。](./media/office-dpi-behavior-on-windows-fall-creators-update.png)

### <a name="office-dpi-behavior-on-windows-april-2018-update-1803"></a><span data-ttu-id="05746-199">Windows 2018 年 4 月更新 (1803) 中的 Office DPI 行为</span><span class="sxs-lookup"><span data-stu-id="05746-199">Office DPI behavior on Windows April 2018 Update (1803)</span></span>

<span data-ttu-id="05746-200">对于 Windows 2018 年 4 月更新 (1803) 及更高版本，Office DPI 托管行为在某些情况下会使用混合模式 DPI 缩放。</span><span class="sxs-lookup"><span data-stu-id="05746-200">With Windows April 2018 (1803) update and later, The Office DPI hosting behavior uses mixed-mode DPI scaling for some scenarios.</span></span> <span data-ttu-id="05746-201">这允许系统 DPI 感知窗口成为设置为“按监视器 DPI 感知”的 Office 窗口的父级。</span><span class="sxs-lookup"><span data-stu-id="05746-201">This allows System DPI Aware windows to be parented to Office windows set to Per Monitor DPI aware.</span></span> <span data-ttu-id="05746-202">这有助于确保在 DPI 发生更改和窗口位图拉伸时提高兼容性。</span><span class="sxs-lookup"><span data-stu-id="05746-202">This helps to ensure improved compatibility when the DPI changes when the windows are bitmap stretched.</span></span> <span data-ttu-id="05746-203">经过位图拉伸的窗口可能仍模糊不清。</span><span class="sxs-lookup"><span data-stu-id="05746-203">The windows might still be blurry from the bitmap stretching.</span></span>

![该图显示在 Windows 2018 年 4 月更新 (1803) 的“系统 DPI 感知”上下文中运行的子窗口。](./media/office-dpi-behavior-on-windows-april-2018-update.png)

<span data-ttu-id="05746-205">创建新的子窗口时，请确保它们匹配其父窗口的 DPI 感知。</span><span class="sxs-lookup"><span data-stu-id="05746-205">When you create new child windows, be sure they match the DPI awareness of their parent window.</span></span> <span data-ttu-id="05746-206">可以使用 [GetWindowDpiAwarenessContext](https://docs.microsoft.com/windows/desktop/api/winuser/nf-winuser-getwindowdpiawarenesscontext) 函数获取父窗口的 DPI 感知。</span><span class="sxs-lookup"><span data-stu-id="05746-206">You can use the [GetWindowDpiAwarenessContext](https://docs.microsoft.com/windows/desktop/api/winuser/nf-winuser-getwindowdpiawarenesscontext) function to get the DPI awareness of the parent window.</span></span> <span data-ttu-id="05746-207">有关 DPI 感知一致性的详细信息，请参阅 [Windows 上的高 DPI 桌面应用程序开发](https://docs.microsoft.com/windows/desktop/hidpi/high-dpi-desktop-application-development-on-windows#related-topics)中的“强制重置整个进程的 DPI 感知”部分。</span><span class="sxs-lookup"><span data-stu-id="05746-207">For more information about DPI awareness consistency, see the “Forced reset of process-wide DPI awareness” section in [High DPI Desktop Application Development on Windows](https://docs.microsoft.com/windows/desktop/hidpi/high-dpi-desktop-application-development-on-windows#related-topics).</span></span>

> [!NOTE]
> <span data-ttu-id="05746-208">你不能依赖于进程 DPI 感知，因为它可能会返回 [PROCESS_SYSTEM_DPI_AWARE](https://docs.microsoft.com/windows/desktop/api/shellscalingapi/ne-shellscalingapi-process_dpi_awareness)，即使应用程序主线程 DPI 感知上下文为 [DPI_AWARENESS_CONTEXT_PER_MONITOR_AWARE](https://docs.microsoft.com/windows/desktop/hidpi/dpi-awareness-context) 也是如此。</span><span class="sxs-lookup"><span data-stu-id="05746-208">You can’t rely on the Process DPI Awareness as it might return [PROCESS_SYSTEM_DPI_AWARE](https://docs.microsoft.com/windows/desktop/api/shellscalingapi/ne-shellscalingapi-process_dpi_awareness) even when the application main thread DPI awareness context is [DPI_AWARENESS_CONTEXT_PER_MONITOR_AWARE](https://docs.microsoft.com/windows/desktop/hidpi/dpi-awareness-context).</span></span> <span data-ttu-id="05746-209">使用 [GetThreadDpiAwarenessContext](https://docs.microsoft.com/windows/desktop/api/winuser/nf-winuser-getthreaddpiawarenesscontext) 函数获取线程 DPI 感知上下文。</span><span class="sxs-lookup"><span data-stu-id="05746-209">Use the [GetThreadDpiAwarenessContext](https://docs.microsoft.com/windows/desktop/api/winuser/nf-winuser-getthreaddpiawarenesscontext) function to get the thread DPI awareness context.</span></span>

## <a name="office-and-windows-dpi-compatibility-settings"></a><span data-ttu-id="05746-210">Office 和 Windows DPI 兼容性设置</span><span class="sxs-lookup"><span data-stu-id="05746-210">Office and Windows DPI compatibility settings</span></span>

<span data-ttu-id="05746-211">当用户遇到无法正确呈现的加载项或解决方案时，某些兼容性设置可帮助解决该问题。</span><span class="sxs-lookup"><span data-stu-id="05746-211">When users encounter add-ins or solutions that are not rendering correctly, some compatibility settings can help correct the problem.</span></span>

<h3 id="office-compatibility"><span data-ttu-id="05746-212">配置 Office 以优化兼容性</span><span class="sxs-lookup"><span data-stu-id="05746-212">Configure Office to optimize for compatibility</span></span></h3>

<span data-ttu-id="05746-213">当移动到具有不同 DPI 缩放比例的其他屏幕时，Office 提供了用于优化兼容性的设置。</span><span class="sxs-lookup"><span data-stu-id="05746-213">Office has a setting to optimize for compatibility when moving to different DPI scales on different screens.</span></span> <span data-ttu-id="05746-214">兼容模式可禁用 DPI 缩放，以便在移动到使用不同 DPI 缩放比例的显示器时，Office 中的所有内容都会进行位图拉伸。</span><span class="sxs-lookup"><span data-stu-id="05746-214">The compatibility mode disables DPI scaling so that everything in Office is bitmap stretched when moved to a display using different DPI scaling.</span></span> 

<span data-ttu-id="05746-215">兼容模式强制Office DPI 感知模式运行。</span><span class="sxs-lookup"><span data-stu-id="05746-215">The compatibility mode forces Office to run in System DPI aware mode.</span></span> <span data-ttu-id="05746-216">这会导致应用程序窗口出现位图拉伸，并会导致外观模糊。</span><span class="sxs-lookup"><span data-stu-id="05746-216">This causes application windows to bitmap stretch and can have a side effect of a blurry appearance.</span></span> <span data-ttu-id="05746-217">你的Office解决方案无法控制此设置，因为用户选择了它。</span><span class="sxs-lookup"><span data-stu-id="05746-217">Your Office solution cannot control this setting because the user chooses it.</span></span> <span data-ttu-id="05746-218">使用显示兼容性模式可解决大多数绘图问题。</span><span class="sxs-lookup"><span data-stu-id="05746-218">Using the display compatibility mode solves most drawing problems.</span></span> <span data-ttu-id="05746-219">有关详细信息，请参阅Office[高清晰度显示器的支持](https://support.office.com/en-us/article/office-support-for-high-definition-displays-6720ca0e-be59-41f6-b629-1369f549279d)。</span><span class="sxs-lookup"><span data-stu-id="05746-219">For more information, see [Office support for high definition displays](https://support.office.com/en-us/article/office-support-for-high-definition-displays-6720ca0e-be59-41f6-b629-1369f549279d).</span></span> 

### <a name="configure-windows-to-fix-blurry-apps"></a><span data-ttu-id="05746-220">配置Windows修复模糊应用</span><span class="sxs-lookup"><span data-stu-id="05746-220">Configure Windows to fix blurry apps</span></span>

<span data-ttu-id="05746-221">Windows 10 (版本 1803) 及更高版本都有一个设置来修复应用，以便它们不会模糊。</span><span class="sxs-lookup"><span data-stu-id="05746-221">Windows 10 (Version 1803) and later has a setting to fix apps so they’re not blurry.</span></span> <span data-ttu-id="05746-222">如果解决方案未正确呈现，这是要尝试的另一个设置。</span><span class="sxs-lookup"><span data-stu-id="05746-222">This is another setting to try if your solution is not rendering correctly.</span></span> <span data-ttu-id="05746-223">你的Office解决方案无法控制此设置，因为用户选择了它。</span><span class="sxs-lookup"><span data-stu-id="05746-223">Your Office solution cannot control this setting because the user chooses it.</span></span> <span data-ttu-id="05746-224">有关详细信息，请参阅修复在应用中显得模糊[Windows 10。](https://support.microsoft.com/en-us/help/4091364/windows-10-fix-blurry-apps)</span><span class="sxs-lookup"><span data-stu-id="05746-224">For more information, see [Fix apps that appear blurry in Windows 10](https://support.microsoft.com/en-us/help/4091364/windows-10-fix-blurry-apps).</span></span>

## <a name="how-to-support-dpi-scaling-in-your-solution"></a><span data-ttu-id="05746-225">如何在解决方案中支持 DPI 缩放</span><span class="sxs-lookup"><span data-stu-id="05746-225">How to support DPI scaling in your solution</span></span>

<span data-ttu-id="05746-226">某些解决方案可以接收和响应 DPI 更改。</span><span class="sxs-lookup"><span data-stu-id="05746-226">Some solutions can receive and respond to DPI changes.</span></span> <span data-ttu-id="05746-227">如果一些用户无法接收通知，则有一个解决方法。</span><span class="sxs-lookup"><span data-stu-id="05746-227">Some have a workaround if they cannot receive notifications.</span></span> <span data-ttu-id="05746-228">下表列出了每种解决方案类型的详细信息。</span><span class="sxs-lookup"><span data-stu-id="05746-228">The following table lists the details for each solution type.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="05746-229">解决方案类型</span><span class="sxs-lookup"><span data-stu-id="05746-229">Solution Type</span></span></th>
            <th><span data-ttu-id="05746-230">窗口类型</span><span class="sxs-lookup"><span data-stu-id="05746-230">Window type</span></span></th>
            <th><span data-ttu-id="05746-231">可以响应 DPI 缩放</span><span class="sxs-lookup"><span data-stu-id="05746-231">Can respond to DPI scaling</span></span></th>
            <th><span data-ttu-id="05746-232">更多详细信息</span><span class="sxs-lookup"><span data-stu-id="05746-232">More details</span></span></th>
        </tr>
    </thead>
<tbody>
    <tr>
        <td rowspan="2"><span data-ttu-id="05746-233"><a href="#vsto-add-ins">VSTO加载项</a></span><span class="sxs-lookup"><span data-stu-id="05746-233"><a href="#vsto-add-ins">VSTO Add-in</a></span></span></td>
        <td><span data-ttu-id="05746-234">Top 及其后代</span><span class="sxs-lookup"><span data-stu-id="05746-234">Top and its descendants</span></span></td>
        <td><span data-ttu-id="05746-235">是</span><span class="sxs-lookup"><span data-stu-id="05746-235">Yes</span></span></td>
        <td><span data-ttu-id="05746-236">请参阅<a href="#vsto-add-ins">VSTO外接程序指南</a>。</span><span class="sxs-lookup"><span data-stu-id="05746-236">See <a href="#vsto-add-ins">VSTO add-in guidance</a>.</span></span></td>
    </tr>
<tr>
        <td><span data-ttu-id="05746-237">父窗口Office子窗口</span><span class="sxs-lookup"><span data-stu-id="05746-237">Child parented to Office window</span></span></td>
        <td><span data-ttu-id="05746-238">否</span><span class="sxs-lookup"><span data-stu-id="05746-238">No</span></span></td>
        <td><span data-ttu-id="05746-239">请参阅<a href="#office-compatibility">配置Office以优化兼容性</a>。</span><span class="sxs-lookup"><span data-stu-id="05746-239">See <a href="#office-compatibility">Configure Office to optimize for compatibility</a>.</span></span></td>
</tr>
    <tr>
        <td rowspan="2"><span data-ttu-id="05746-240"><a href="#custom-task-panes">自定义任务窗格</a></span><span class="sxs-lookup"><span data-stu-id="05746-240"><a href="#custom-task-panes">Custom task pane</a></span></span></td>
        <td><span data-ttu-id="05746-241">Top 及其后代</span><span class="sxs-lookup"><span data-stu-id="05746-241">Top and its descendants</span></span></td>
        <td><span data-ttu-id="05746-242">是</span><span class="sxs-lookup"><span data-stu-id="05746-242">Yes</span></span></td>
        <td><span data-ttu-id="05746-243">请参阅 <a href="#top-level-window-management">顶级窗口指南</a>。</span><span class="sxs-lookup"><span data-stu-id="05746-243">See <a href="#top-level-window-management">top-level window guidance</a>.</span></span></td>
    </tr>
<tr>
        <td><span data-ttu-id="05746-244">父窗口Office子窗口</span><span class="sxs-lookup"><span data-stu-id="05746-244">Child parented to Office window</span></span></td>
        <td><span data-ttu-id="05746-245">否</span><span class="sxs-lookup"><span data-stu-id="05746-245">No</span></span></td>
        <td><span data-ttu-id="05746-246">请参阅<a href="#office-compatibility">配置Office以优化兼容性</a>。</span><span class="sxs-lookup"><span data-stu-id="05746-246">See <a href="#office-compatibility">Configure Office to optimize for compatibility</a>.</span></span></td>
</tr>
    <tr>
        <td rowspan="2"><span data-ttu-id="05746-247"><a href="#com-add-ins">COM 加载项</a></span><span class="sxs-lookup"><span data-stu-id="05746-247"><a href="#com-add-ins">COM Add-in</a></span></span></td>
        <td><span data-ttu-id="05746-248">Top 及其后代</span><span class="sxs-lookup"><span data-stu-id="05746-248">Top and its descendants</span></span></td>
        <td><span data-ttu-id="05746-249">是</span><span class="sxs-lookup"><span data-stu-id="05746-249">Yes</span></span></td>
        <td><span data-ttu-id="05746-250">请参阅 <a href="#com-add-ins">COM 加载项指南</a>。</span><span class="sxs-lookup"><span data-stu-id="05746-250">See <a href="#com-add-ins">COM Add-in guidance</a>.</span></span></td>
    </tr>
<tr>
        <td><span data-ttu-id="05746-251">父窗口Office子窗口</span><span class="sxs-lookup"><span data-stu-id="05746-251">Child parented to Office window</span></span></td>
        <td><span data-ttu-id="05746-252">否</span><span class="sxs-lookup"><span data-stu-id="05746-252">No</span></span></td>
        <td><span data-ttu-id="05746-253">请参阅<a href="#office-compatibility">配置Office以优化兼容性</a>。</span><span class="sxs-lookup"><span data-stu-id="05746-253">See <a href="#office-compatibility">Configure Office to optimize for compatibility</a>.</span></span></td>
</tr>
    <tr>
        <td rowspan="2"><span data-ttu-id="05746-254"><a href="#activex-controls">ActiveX 控件</a></span><span class="sxs-lookup"><span data-stu-id="05746-254"><a href="#activex-controls">ActiveX control</a></span></span></td>
        <td><span data-ttu-id="05746-255">Top 及其后代</span><span class="sxs-lookup"><span data-stu-id="05746-255">Top and its descendants</span></span></td>
        <td><span data-ttu-id="05746-256">是</span><span class="sxs-lookup"><span data-stu-id="05746-256">Yes</span></span></td>
        <td><span data-ttu-id="05746-257">请参阅<a href="#activex-controls">ActiveX控制指南</a>。</span><span class="sxs-lookup"><span data-stu-id="05746-257">See <a href="#activex-controls">ActiveX control guidance</a>.</span></span></td>
    </tr>
    <tr>
        <td><span data-ttu-id="05746-258">父窗口Office子窗口</span><span class="sxs-lookup"><span data-stu-id="05746-258">Child parented to Office window</span></span></td>
        <td><span data-ttu-id="05746-259">是</span><span class="sxs-lookup"><span data-stu-id="05746-259">Yes</span></span></td>
    </tr>
    <tr>
        <td><span data-ttu-id="05746-260"><a href="#web-add-ins">Web 加载项</a></span><span class="sxs-lookup"><span data-stu-id="05746-260"><a href="#web-add-ins">Web Add-in</a></span></span></td>
        <td><span data-ttu-id="05746-261">不适用</span><span class="sxs-lookup"><span data-stu-id="05746-261">NA</span></span></td>
        <td><span data-ttu-id="05746-262">是</span><span class="sxs-lookup"><span data-stu-id="05746-262">Yes</span></span></td>
        <td><span data-ttu-id="05746-263">请参阅<a href="#web-add-ins">Office Web 外接程序指南</a>。</span><span class="sxs-lookup"><span data-stu-id="05746-263">See <a href="#web-add-ins">Office web add-in guidance</a>.</span></span></td>
    </tr>
    <tr>
        <td><span data-ttu-id="05746-264"><a href="#ribbon-extensibility">功能区扩展</a></span><span class="sxs-lookup"><span data-stu-id="05746-264"><a href="#ribbon-extensibility">Ribbon extension</a></span></span></td>
        <td><span data-ttu-id="05746-265">NA</span><span class="sxs-lookup"><span data-stu-id="05746-265">NA</span></span></td>
        <td><span data-ttu-id="05746-266">NA</span><span class="sxs-lookup"><span data-stu-id="05746-266">NA</span></span></td>
        <td><span data-ttu-id="05746-267">请参阅 <a href="#ribbon-extensibility">功能区扩展指南</a>。</span><span class="sxs-lookup"><span data-stu-id="05746-267">See <a href="#ribbon-extensibility">Ribbon extension guidance</a>.</span></span></td>
    </tr>
    <tr>
        <td><span data-ttu-id="05746-268"><a href="#ole">OLE 服务器或客户端</a></span><span class="sxs-lookup"><span data-stu-id="05746-268"><a href="#ole">OLE server or client</a></span></span></td>
        <td><span data-ttu-id="05746-269">NA</span><span class="sxs-lookup"><span data-stu-id="05746-269">NA</span></span></td>
        <td><span data-ttu-id="05746-270">NA</span><span class="sxs-lookup"><span data-stu-id="05746-270">NA</span></span></td>
        <td><span data-ttu-id="05746-271">请参阅 <a href="#ole">OLE 服务器/客户端指南</a>。</span><span class="sxs-lookup"><span data-stu-id="05746-271">See <a href="#ole">OLE server/client guidance</a>.</span></span></td>
    </tr>
</tbody>
</table>

<h3 id="vsto-add-ins"><span data-ttu-id="05746-272">VSTO加载项</span><span class="sxs-lookup"><span data-stu-id="05746-272">VSTO add-in</span></span></h3>

<span data-ttu-id="05746-273">如果VSTO加载项创建父窗口作为父窗口，Office窗口的 DPI 感知相匹配。</span><span class="sxs-lookup"><span data-stu-id="05746-273">If your VSTO add-in creates child windows that are parented to any Office windows, be sure they match the DPI awareness of their parent window.</span></span> <span data-ttu-id="05746-274">你可以使用 [GetWindowdpiAwarenessContext](https://docs.microsoft.com/windows/desktop/api/winuser/nf-winuser-getwindowdpiawarenesscontext) 函数来获取父窗口的 DPI 感知。</span><span class="sxs-lookup"><span data-stu-id="05746-274">You can use the [GetWindowdpiAwarenessContext](https://docs.microsoft.com/windows/desktop/api/winuser/nf-winuser-getwindowdpiawarenesscontext) function to get the DPI awareness of the parent window.</span></span> <span data-ttu-id="05746-275">子窗口不会收到任何 DPI 更改通知。</span><span class="sxs-lookup"><span data-stu-id="05746-275">Your child windows will not get any DPI change notifications.</span></span> <span data-ttu-id="05746-276">如果解决方案未正确呈现，用户将需要将Office置于兼容模式。</span><span class="sxs-lookup"><span data-stu-id="05746-276">If your solution is not rendering correctly, users will need to put Office into compatibility mode.</span></span>

<span data-ttu-id="05746-277">对于加载项创建的任何VSTO窗口，你可以将其设置为任何 DPI 感知模式。</span><span class="sxs-lookup"><span data-stu-id="05746-277">For any top-level windows your VSTO add-in creates, you can set them to any DPI awareness mode.</span></span> <span data-ttu-id="05746-278">以下示例代码演示如何设置所需的 DPI 感知，以及如何响应 DPI 更改。</span><span class="sxs-lookup"><span data-stu-id="05746-278">The following sample code shows how to set up the desired DPI awareness, and how to respond to DPI changes.</span></span> <span data-ttu-id="05746-279">你还需要调整你的app.config，如在窗体中支持高 DPI Windows[中所述](https://docs.microsoft.com/dotnet/framework/winforms/high-dpi-support-in-windows-forms)。</span><span class="sxs-lookup"><span data-stu-id="05746-279">You will also need to adjust your app.config, as described in the [High DPI support in Windows Forms](https://docs.microsoft.com/dotnet/framework/winforms/high-dpi-support-in-windows-forms) article.</span></span> 

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

<h3 id="custom-task-panes"><span data-ttu-id="05746-280">自定义任务窗格</span><span class="sxs-lookup"><span data-stu-id="05746-280">Custom task panes</span></span></h3>

<span data-ttu-id="05746-281">自定义任务窗格由自定义任务窗格创建为子Office。</span><span class="sxs-lookup"><span data-stu-id="05746-281">A custom task pane is created as a child window by Office.</span></span> <span data-ttu-id="05746-282">在 Windows Fall Creators Update (1709) 上运行时，自定义任务窗格将采用与 Office 相同的 DPI 感知模式运行。</span><span class="sxs-lookup"><span data-stu-id="05746-282">When running on Windows Fall Creators Update (1709), your custom task pane will run using the same DPI awareness mode as Office.</span></span> <span data-ttu-id="05746-283">当在 2018 Windows 1803 (及更高版本) ，自定义任务窗格将使用系统 DPI 感知模式运行。</span><span class="sxs-lookup"><span data-stu-id="05746-283">When running on Windows April 2018 Update (1803) and later, your custom task pane will run using System DPI awareness mode.</span></span> 

<span data-ttu-id="05746-284">由于自定义任务窗格是子窗口，因此它们无法接收 DPI 通知。</span><span class="sxs-lookup"><span data-stu-id="05746-284">Because custom task panes are child windows, they cannot receive DPI notifications.</span></span> <span data-ttu-id="05746-285">如果他们的绘图不正确，用户将需要使用 DPI [Office模式](https://support.office.com/en-us/article/office-support-for-high-definition-displays-6720ca0e-be59-41f6-b629-1369f549279d)。</span><span class="sxs-lookup"><span data-stu-id="05746-285">If they are drawing incorrectly, the user will need to use [Office DPI compatibility mode](https://support.office.com/en-us/article/office-support-for-high-definition-displays-6720ca0e-be59-41f6-b629-1369f549279d).</span></span>
<span data-ttu-id="05746-286">如果你的自定义任务窗格创建了顶级窗口，这些窗口可以在任何 DPI 感知模式下运行并接收 DPI 更改通知。</span><span class="sxs-lookup"><span data-stu-id="05746-286">If your custom task pane creates top-level windows, those windows can run in any DPI awareness mode and receive DPI change notifications.</span></span> <span data-ttu-id="05746-287">有关详细信息，请参阅 [本文中的顶级](#top-level-window-management) 窗口管理部分。</span><span class="sxs-lookup"><span data-stu-id="05746-287">For more information, see the [Top-level window management](#top-level-window-management) section in this article.</span></span>

<h3 id="com-add-ins"><span data-ttu-id="05746-288">COM 加载项</span><span class="sxs-lookup"><span data-stu-id="05746-288">COM add-ins</span></span></h3>

<span data-ttu-id="05746-289">创建顶级窗口的 COM 加载项可以接收 DPI 通知。</span><span class="sxs-lookup"><span data-stu-id="05746-289">COM add-ins that create top-level windows can receive DPI notifications.</span></span> <span data-ttu-id="05746-290">应创建 [上下文块](#build-a-context-block-for-incoming-thread-calls) ，将线程设置为希望用于窗口的 DPI 感知，然后创建窗口。</span><span class="sxs-lookup"><span data-stu-id="05746-290">You should create a [context block](#build-a-context-block-for-incoming-thread-calls) to set the thread to the DPI awareness that you want for your window, then create your window.</span></span> <span data-ttu-id="05746-291">需要正确处理 DPI 通知有很多，因此请务必阅读 windows 上的高[DPI](https://docs.microsoft.com/windows/desktop/hidpi/high-dpi-desktop-application-development-on-windows#related-topics)桌面应用程序Windows了解更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="05746-291">There’s a lot to handling the DPI notifications correctly, so be sure to read [High DPI Desktop Application Development on Windows](https://docs.microsoft.com/windows/desktop/hidpi/high-dpi-desktop-application-development-on-windows#related-topics) for more details.</span></span>

<span data-ttu-id="05746-292">当 [WM_DPICHANGED](https://docs.microsoft.com/windows/desktop/hidpi/wm-dpichanged) DPI 发生更改时，将发送该邮件。</span><span class="sxs-lookup"><span data-stu-id="05746-292">The [WM_DPICHANGED](https://docs.microsoft.com/windows/desktop/hidpi/wm-dpichanged) message is sent when the DPI for a window has changed.</span></span>  <span data-ttu-id="05746-293">在非托管代码中，此消息由 HWND 的 [Window 过程](https://docs.microsoft.com/windows/desktop/winmsg/using-window-procedures) 处理。</span><span class="sxs-lookup"><span data-stu-id="05746-293">In unmanaged code, this message is handled by the [Window Procedure](https://docs.microsoft.com/windows/desktop/winmsg/using-window-procedures) for the HWND.</span></span>  <span data-ttu-id="05746-294">示例 DPI 更改处理程序代码可在本文WM_DPICHANGED找到。</span><span class="sxs-lookup"><span data-stu-id="05746-294">Sample DPI change handler code can be found in the WM_DPICHANGED article.</span></span> 

<span data-ttu-id="05746-295">显示父窗口的 COM 加载项，这些子窗口位于 Office无法接收 DPI 通知。</span><span class="sxs-lookup"><span data-stu-id="05746-295">COM add-ins that show child windows that are parented to a window in Office cannot receive DPI notifications.</span></span> <span data-ttu-id="05746-296">如果他们的绘图不正确，用户将需要使用 DPI [Office模式](https://support.office.com/article/office-support-for-high-definition-displays-6720ca0e-be59-41f6-b629-1369f549279d)。</span><span class="sxs-lookup"><span data-stu-id="05746-296">If they are drawing incorrectly, the user will need to use [Office DPI compatibility mode](https://support.office.com/article/office-support-for-high-definition-displays-6720ca0e-be59-41f6-b629-1369f549279d).</span></span>

<h3 id="activex-controls"><span data-ttu-id="05746-297">ActiveX 控件</span><span class="sxs-lookup"><span data-stu-id="05746-297">ActiveX controls</span></span></h3>

<span data-ttu-id="05746-298">如何支持控件中的 DPI 缩放ActiveX控件是窗口控件还是无窗口控件。</span><span class="sxs-lookup"><span data-stu-id="05746-298">How to support DPI scaling in ActiveX controls depends on whether the control is windowed or windowless.</span></span>

#### <a name="windowed-activex-controls"></a><span data-ttu-id="05746-299">窗口ActiveX控件</span><span class="sxs-lookup"><span data-stu-id="05746-299">Windowed ActiveX controls</span></span>

<span data-ttu-id="05746-300">窗口ActiveX控件每次WM_SIZE大小时会收到一条警告消息。</span><span class="sxs-lookup"><span data-stu-id="05746-300">Windowed ActiveX controls receive a WM_SIZE message each time the control is resized.</span></span>  <span data-ttu-id="05746-301">触发此事件时，事件处理程序代码可以使用控件的 HWND 调用 [GetDpiForWindow](https://docs.microsoft.com/windows/desktop/api/winuser/nf-winuser-getdpiforwindow) 函数，获取 DPI、计算比例系数差异并根据需要进行调整。</span><span class="sxs-lookup"><span data-stu-id="05746-301">When this event is triggered, the event handler code can call the [GetDpiForWindow](https://docs.microsoft.com/windows/desktop/api/winuser/nf-winuser-getdpiforwindow) function using the HWND of the control to get the DPI, calculate the scale factor differences, and adjust as needed.</span></span> 

<span data-ttu-id="05746-302">以下示例使基于 MFC 的ActiveX控件能够响应 **OnSize** 事件。</span><span class="sxs-lookup"><span data-stu-id="05746-302">The following example enables an MFC-based ActiveX control to respond to the **OnSize** event.</span></span> 

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

#### <a name="windowless-activex-controls"></a><span data-ttu-id="05746-303">无窗口ActiveX控件</span><span class="sxs-lookup"><span data-stu-id="05746-303">Windowless ActiveX controls</span></span>

<span data-ttu-id="05746-304">无窗口ActiveX控件不能保证具有 HWND。</span><span class="sxs-lookup"><span data-stu-id="05746-304">Windowless ActiveX controls are not guaranteed have an HWND.</span></span>  <span data-ttu-id="05746-305">将ActiveX插入文档画布上时，该控件将进入设计模式。</span><span class="sxs-lookup"><span data-stu-id="05746-305">When an ActiveX control is inserted onto a document canvas, it is put into design mode.</span></span>  <span data-ttu-id="05746-306">在 Office 应用程序中，当控件在设计模式下时，托管容器将为在 ：：OnDraw 事件中调用 hDC->GetWindow () 返回 0。</span><span class="sxs-lookup"><span data-stu-id="05746-306">In Office applications, the hosting container will return 0 for the call to hDC->GetWindow() in the ::OnDraw event when the control is in design mode.</span></span>  <span data-ttu-id="05746-307">在这种情况下，无法检索可靠的 DPI。</span><span class="sxs-lookup"><span data-stu-id="05746-307">A reliable DPI cannot be retrieved in this case.</span></span> 

<span data-ttu-id="05746-308">但是，当控件在运行时模式下时，Office将返回要绘制控件的 HWND。</span><span class="sxs-lookup"><span data-stu-id="05746-308">However, when the control is in runtime mode, Office will return the HWND where the control is to be drawn.</span></span>  <span data-ttu-id="05746-309">在这种情况下，控件开发人员可以调用 [GetDpiForWindow](https://docs.microsoft.com/windows/desktop/api/winuser/nf-winuser-getdpiforwindow) 并获取当前的 DPI 和缩放字体、控件等。</span><span class="sxs-lookup"><span data-stu-id="05746-309">In this case, the control developer can call [GetDpiForWindow](https://docs.microsoft.com/windows/desktop/api/winuser/nf-winuser-getdpiforwindow) and get the current DPI and scale fonts, controls, and so on.</span></span> 

<h3 id="ribbon-extensibility"><span data-ttu-id="05746-310">自定义功能区扩展性</span><span class="sxs-lookup"><span data-stu-id="05746-310">Custom ribbon extensibility</span></span></h3>

<span data-ttu-id="05746-311">来自自定义功能Office控件的任何回调都将在系统 DPI 感知的 DPI 线程感知中。</span><span class="sxs-lookup"><span data-stu-id="05746-311">Any callbacks from Office for custom ribbon controls will be in a DPI thread awareness of System DPI aware.</span></span>  <span data-ttu-id="05746-312">如果你的解决方案需要不同的 DPI 线程感知，你应该实现上下文块来设置线程感知预期。</span><span class="sxs-lookup"><span data-stu-id="05746-312">If your solution is expecting a different DPI thread awareness, you should implement a context block to set the thread awareness as expected.</span></span> <span data-ttu-id="05746-313">有关详细信息，请参阅生成 [上下文块](#build-a-context-block-for-incoming-thread-calls)。</span><span class="sxs-lookup"><span data-stu-id="05746-313">For more information, see [Build a context block](#build-a-context-block-for-incoming-thread-calls).</span></span>

<h3 id="ole"><span data-ttu-id="05746-314">OLE 客户端和服务器</span><span class="sxs-lookup"><span data-stu-id="05746-314">OLE clients and servers</span></span></h3>

<span data-ttu-id="05746-315">当 OLE 服务器托管在 OLE 客户端容器内时，当前无法提供当前或受支持的 DPI 信息。</span><span class="sxs-lookup"><span data-stu-id="05746-315">When an OLE server is hosted within an OLE client container, you currently can’t provide current or supported DPI information.</span></span> <span data-ttu-id="05746-316">这可能会导致问题，因为当前窗口体系结构不支持父窗口到子窗口混合模式Windows组合。</span><span class="sxs-lookup"><span data-stu-id="05746-316">This can cause problems because some combinations of parent to child window mixed modes are not supported by the current Windows architecture.</span></span> <span data-ttu-id="05746-317">如果 Word 或 Excel检测到存在多个 DPI 缩放比例不同的监视器，则它们不支持就地激活。</span><span class="sxs-lookup"><span data-stu-id="05746-317">If Word or Excel detect that there are multiple monitors with different DPI scales, they will not support in-place activation.</span></span> <span data-ttu-id="05746-318">OLE 服务器将就地激活。</span><span class="sxs-lookup"><span data-stu-id="05746-318">Your OLE server will activate out-of-place.</span></span> <span data-ttu-id="05746-319">如果遇到 OLE 服务器交互问题，用户将需要使用[DPI Office模式](https://support.office.com/article/office-support-for-high-definition-displays-6720ca0e-be59-41f6-b629-1369f549279d)。</span><span class="sxs-lookup"><span data-stu-id="05746-319">If you are experiencing issues with OLE server interactions, the user will need to use [Office DPI compatibility mode](https://support.office.com/article/office-support-for-high-definition-displays-6720ca0e-be59-41f6-b629-1369f549279d).</span></span>

<h3 id="web-add-ins"><span data-ttu-id="05746-320">OfficeWeb 加载项</span><span class="sxs-lookup"><span data-stu-id="05746-320">Office Web Add-ins</span></span></h3>

<span data-ttu-id="05746-321">Office使用 JavaScript API Office加载项在浏览器控件内运行。</span><span class="sxs-lookup"><span data-stu-id="05746-321">Office Add-ins built using the Office JavaScript API run inside a browser control.</span></span> <span data-ttu-id="05746-322">可以使用在任何 Web 应用设计中使用的相同技术处理 DPI 缩放。</span><span class="sxs-lookup"><span data-stu-id="05746-322">You can handle DPI scaling using the same techniques used in any web app design.</span></span> <span data-ttu-id="05746-323">许多联机资源都可用于帮助为高分辨率屏幕设计网页。</span><span class="sxs-lookup"><span data-stu-id="05746-323">Many online resources are available to help design a web page for high resolution screens.</span></span>

## <a name="verify-that-your-solution-supports-dpi-scaling"></a><span data-ttu-id="05746-324">验证解决方案是否支持 DPI 缩放</span><span class="sxs-lookup"><span data-stu-id="05746-324">Verify that your solution supports DPI scaling</span></span>

<span data-ttu-id="05746-325">更新应用程序以支持 DPI 缩放后，应在混合 DPI 环境中验证更改。</span><span class="sxs-lookup"><span data-stu-id="05746-325">After you have updated your application to support DPI scaling, you should validate your changes in a mixed-DPI environment.</span></span> <span data-ttu-id="05746-326">验证当解决方案的窗口从一个显示器移动到另一个具有不同的 DPI 值的显示器时，你的 UI 代码是否正确响应 DPI 更改。</span><span class="sxs-lookup"><span data-stu-id="05746-326">Validate that your UI code responds properly to DPI changes when your solution’s windows are moved from one display to another that has different DPI values.</span></span> <span data-ttu-id="05746-327">有关 DPI 缩放测试技术详细信息，请参阅上一个上的高 DPI 桌面[应用程序Windows。](https://docs.microsoft.com/windows/desktop/hidpi/high-dpi-desktop-application-development-on-windows#related-topics)</span><span class="sxs-lookup"><span data-stu-id="05746-327">For more information about DPI scaling testing techniques, see [High DPI Desktop Application Development on Windows](https://docs.microsoft.com/windows/desktop/hidpi/high-dpi-desktop-application-development-on-windows#related-topics).</span></span>

<span data-ttu-id="05746-328">您可能还发现这些附加技术非常有用：</span><span class="sxs-lookup"><span data-stu-id="05746-328">You might also find these additional techniques helpful:</span></span>

- <span data-ttu-id="05746-329">使用笔记本电脑，可以将主监视器设置为外部监视器，然后取消停靠该笔记本电脑。</span><span class="sxs-lookup"><span data-stu-id="05746-329">With a laptop, you can set the primary monitor to an external monitor, then undock the laptop.</span></span> <span data-ttu-id="05746-330">这将强制主监视器更改为笔记本电脑显示器。</span><span class="sxs-lookup"><span data-stu-id="05746-330">This will force the primary monitor to change to the laptop display.</span></span>
- <span data-ttu-id="05746-331">使用开源 [WinSpy++ 工具](https://github.com/BissetJ/winspy/releases) 帮助调试。</span><span class="sxs-lookup"><span data-stu-id="05746-331">Use the open source [WinSpy++ tool](https://github.com/BissetJ/winspy/releases) to help debug.</span></span> <span data-ttu-id="05746-332">可以使用它查看任何窗口的 DPI 感知设置。</span><span class="sxs-lookup"><span data-stu-id="05746-332">You can use it to see the DPI awareness setting of any window.</span></span>
- <span data-ttu-id="05746-333">通过在"显示"选项卡上选择"使用远程会话的所有监视器"，可以使用远程桌面测试远程计算机上多个监视器，如以下屏幕截图所示。</span><span class="sxs-lookup"><span data-stu-id="05746-333">You can use remote desktop to test multiple monitors on a remote computer by selecting Use all my monitors for the remote session on the Display tab, as shown in the following screenshot.</span></span>

![显示显示选项卡并选择使用远程会话的所有我的监视器的远程桌面连接应用。](./media/remote-desktop-use-all-monitors.png)

## <a name="see-also"></a><span data-ttu-id="05746-335">另请参阅</span><span class="sxs-lookup"><span data-stu-id="05746-335">See also</span></span>

### <a name="articles"></a><span data-ttu-id="05746-336">文章</span><span class="sxs-lookup"><span data-stu-id="05746-336">Articles</span></span>

- <span data-ttu-id="05746-337">[开发 WPF Per-Monitor DPI-Aware](https://docs.microsoft.com/windows/desktop/hidpi/declaring-managed-apps-dpi-aware) 提供了编写 Win32 桌面应用程序的一般概述和指南。</span><span class="sxs-lookup"><span data-stu-id="05746-337">[Developing a Per-Monitor DPI-Aware WPF Application](https://docs.microsoft.com/windows/desktop/hidpi/declaring-managed-apps-dpi-aware) provides a general overview and guide for writing Win32 desktop applications.</span></span> <span data-ttu-id="05746-338">本文中介绍的许多相同技术将适用于Office解决方案。</span><span class="sxs-lookup"><span data-stu-id="05746-338">Many of the same techniques described in this article will apply to Office extensibility solutions.</span></span>
- <span data-ttu-id="05746-339">[混合模式 DPI 缩放和 DPI 感知 API](https://docs.microsoft.com/windows/desktop/hidpi/high-dpi-improvements-for-desktop-applications) 具有与 DPI 相关的 API 列表。</span><span class="sxs-lookup"><span data-stu-id="05746-339">[Mixed-Mode DPI Scaling and DPI-aware APIs](https://docs.microsoft.com/windows/desktop/hidpi/high-dpi-improvements-for-desktop-applications) has a list of APIs related to DPI.</span></span>
- <span data-ttu-id="05746-340">[开发人员指南 - 按监视器 DPI - WPF 预览](https://github.com/Microsoft/WPF-Samples/blob/master/PerMonitorDPI/Developer%20Guide%20-%20Per%20Monitor%20DPI%20-%20WPF%20Preview.docx) 涵盖用于生成 DPI 感知 WPF 应用的 WPF 应用开发指南。</span><span class="sxs-lookup"><span data-stu-id="05746-340">[Developer Guide - Per Monitor DPI - WPF Preview](https://github.com/Microsoft/WPF-Samples/blob/master/PerMonitorDPI/Developer%20Guide%20-%20Per%20Monitor%20DPI%20-%20WPF%20Preview.docx) covers the WPF app development guide for building DPI-aware WPF apps.</span></span>
- <span data-ttu-id="05746-341">[Office高](https://support.office.com/article/Office-support-for-high-definition-displays-6720ca0e-be59-41f6-b629-1369f549279d)清晰度显示器提供了当 DPI 更改时无法正确支持 Office 解决方案时，用户如何设置 Office 以优化兼容性的信息。</span><span class="sxs-lookup"><span data-stu-id="05746-341">[Office support for high definition displays](https://support.office.com/article/Office-support-for-high-definition-displays-6720ca0e-be59-41f6-b629-1369f549279d) provides information about how a user can set Office to optimize for compatibility if your Office solution is not supported properly when the DPI changes.</span></span>
- <span data-ttu-id="05746-342">[Display Scaling changes for the Windows 10 Anniversary Update](https://blogs.technet.microsoft.com/askcore/2016/08/16/display-scaling-changes-for-the-windows-10-anniversary-update/)是一篇博客文章，介绍了 Windows 10 周年更新引入的更改。</span><span class="sxs-lookup"><span data-stu-id="05746-342">[Display Scaling changes for the Windows 10 Anniversary Update](https://blogs.technet.microsoft.com/askcore/2016/08/16/display-scaling-changes-for-the-windows-10-anniversary-update/) is a blog post that covers changes introduce with the Windows 10 Anniversary update.</span></span> 
- <span data-ttu-id="05746-343">[DPI_AWARENESS_CONTEXT句柄](https://docs.microsoft.com/windows/desktop/hidpi/dpi-awareness-context) 具有有关DPI_AWARENESS_CONTEXT和定义的编程详细信息。</span><span class="sxs-lookup"><span data-stu-id="05746-343">[DPI_AWARENESS_CONTEXT handle](https://docs.microsoft.com/windows/desktop/hidpi/dpi-awareness-context) has programming details on the DPI_AWARENESS_CONTEXT values and definitions.</span></span>
- <span data-ttu-id="05746-344">[系统上的高 DPI 桌面应用程序Windows"](https://docs.microsoft.com/windows/desktop/hidpi/high-dpi-desktop-application-development-on-windows#testing-your-changes)测试更改"部分包含有关测试的信息。</span><span class="sxs-lookup"><span data-stu-id="05746-344">[High DPI Desktop Application Development on Windows](https://docs.microsoft.com/windows/desktop/hidpi/high-dpi-desktop-application-development-on-windows#testing-your-changes) includes information about testing in the Testing Your Changes section.</span></span>

### <a name="code-samples"></a><span data-ttu-id="05746-345">代码示例</span><span class="sxs-lookup"><span data-stu-id="05746-345">Code samples</span></span>

- [<span data-ttu-id="05746-346">按窗口 DPI 感知示例</span><span class="sxs-lookup"><span data-stu-id="05746-346">Per-window DPI Awareness sample</span></span>](https://github.com/Microsoft/Windows-classic-samples/tree/master/Samples/DPIAwarenessPerWindow)
- [<span data-ttu-id="05746-347">动态 DPI 示例</span><span class="sxs-lookup"><span data-stu-id="05746-347">Dynamic DPI sample</span></span>](https://github.com/Microsoft/Windows-classic-samples/tree/master/Samples/DynamicDPI)
- [<span data-ttu-id="05746-348">每监视器感知 WPF 示例</span><span class="sxs-lookup"><span data-stu-id="05746-348">Per-Monitor Aware WPF sample</span></span>](https://github.com/Microsoft/Windows-classic-samples/tree/master/Samples/PerMonitorDPIAware)
