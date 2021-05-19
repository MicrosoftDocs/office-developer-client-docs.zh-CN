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
# <a name="handle-high-dpi-and-dpi-scaling-in-your-office-solution"></a>在 Office 解决方案中处理高 DPI 和 DPI 缩放

许多计算机和显示器配置现在都支持高 DPI（每英寸点数）分辨率，并且可以连接具有不同大小和像素密度的多个监视器。 这要求用户将应用移动到具有不同 DPI 的监视器时调整应用程序，或者更改缩放级别。 不支持 DPI 缩放的应用程序在低 DPI 监视器上可能看起来很好，但在高 DPI 监视器上将显得模糊不清。 

Office 2016 应用程序（如 Word 和 Excel）已更新，以响应缩放比例的更改。 然而，你的 Office 解决方案还必须响应更改，以便在 DPI 更改时正确进行绘制。 本文介绍 Office 如何支持动态 DPI，以及你可以采取哪些步骤来确保 Office 可扩展性解决方案在处理 DPI 缩放时带来最佳查看体验。 

## <a name="dpi-scaling-symptoms-in-your-solution"></a>解决方案中的 DPI 缩放症状

当应用程序从一个显示器移动到另一个具有不同 DPI 的显示器时，Windows 会应用 DPI 缩放。 例如，将应用程序拖动到其他显示器或插接笔记本电脑时会发生这种情况。 如果 DPI 缩放对你的 Office 解决方案造成不良影响，你将看到以下一个或多个症状：

- Windows 在错误位置绘制或者大小调整不正确。
- 按钮和标签等元素显示在解决方案窗口的错误位置。
- 字体和图像显得太小、太大或位于错误位置。

DPI 缩放可能会影响以下类型的 Office 解决方案：

- VSTO 加载项
- 自定义任务窗格
- COM 加载项
- ActiveX 控件
- 功能区扩展
- Ole 服务器
- Office Web 加载项

## <a name="windows-dpi-awareness-modes"></a>Windows DPI 感知模式

在整篇文章中，我们将引用 Windows 支持的 DPI 感知模式。 每种 DPI 感知模式都支持不同的功能，如下表所述。 这是有关这些模式的简化描述，用于介绍 Office 如何为其提供支持。 有关 DPI 感知模式的详细信息，请参阅 [Windows 上的高 DPI 桌面应用程序开发](https://docs.microsoft.com/windows/desktop/hidpi/high-dpi-desktop-application-development-on-windows)。

|模式  |说明  |DPI 发生更改时  |
|---------|---------|---------|
|非 DPI 感知 |  应用程序始终呈现为如同在 DPI 值为 96 的显示器上显示。 |  应用程序在主显示器和辅助显示器上将位图拉伸到预期大小。    |
|系统 DPI 感知 |  应用程序将在 Windows 登录时检测主连接监视器的 DPI，但无法响应 DPI 更改。 有关详细信息，请参阅本文中的配置Windows[修复](#configure-windows-to-fix-blurry-apps)模糊应用部分。  | 当移动到具有不同 DPI 的新显示器时，应用程序将拉伸位图。    |
|按监视器 DPI 感知 |  应用程序能够在 DPI 发生更改时正确地进行重绘。  |   Windows 会将 DPI 通知发送到应用程序中的顶级窗口，以便在 DPI 发生更改时进行重绘。     |
|按监视器 v2 |  应用程序能够在 DPI 发生更改时正确地进行重绘。  |   Windows 将同时向顶级窗口和子窗口发送 DPI 通知，以便应用程序能够在 DPI 发生更改时进行重绘。 |

## <a name="how-office-supports-dpi-scaling"></a>Office 如何支持 DPI 缩放

决定 Office 解决方案如何处理 DPI 缩放的最重要因素是你的解决方案是顶级窗口还是子窗口。 下图显示了作为顶级窗口或子窗口运行的 Office 解决方案的一些示例，以及它们将在 Windows 2018 年 4 月更新 (1803) 及更高版本中使用的 DPI 感知模式。

![Excel 将 ActiveX 控件和自定义任务窗格托管为子窗口。 单独的 VSTO/COM 加载项作为顶级窗口运行。 Office 是顶级窗口。](./media/office-dpi-awareness-for-solution-types.png)

在此图中：
- COM/VSTO 顶级窗口是“按监视器 DPI 感知”。
- ActiveX 控件子窗口是“系统 DPI 感知”。
- Office 顶级窗口是“按监视器 DPI 感知”。
- 自定义任务窗格子窗口是“系统 DPI 感知”。

## <a name="managing-thread-dpi-context"></a>管理线程 DPI 上下文

当主机 Office 应用启动时，其主线程将在“按监视器 DPI 感知”上下文中运行。 当你的解决方案代码创建线程或从 Office 接收调用时，你需要管理线程 DPI 上下文。

### <a name="creating-new-threads-with-the-correct-dpi-context"></a>使用正确的 DPI 上下文创建新线程

如果你的解决方案创建了其他线程，则 Office 将强制该线程进入“按监视器 DPI 感知”上下文。 如果你的代码需要不同的上下文，则需要使用 [SetThreadDpiAwarenessContext](https://docs.microsoft.com/windows/desktop/api/winuser/nf-winuser-setthreaddpiawarenesscontext) 函数设置预期的线程 DPI 感知。 

### <a name="build-a-context-block-for-incoming-thread-calls"></a>为传入的线程调用构建上下文块

![该图显示 Office 应用中的上下文块，它在调用顶级窗口时将线程切换到系统感知上下文。](./media/thread-dpi-awareness-context-block.png)

你的解决方案将与其主机 Office 应用进行交互，因此你可以对 Office 中的解决方案进行传入调用，例如事件回调。 当 Office 调用你的解决方案时，它有一个上下文块，用于强制线程上下文位于“系统 DPI 感知”上下文中。 你必须更改线程上下文，使其匹配窗口的 DPI 感知。 你可以实施类似的上下文块以切换传入调用的线程上下文。 使用 [SetThreadDpiAwarenessContext](https://docs.microsoft.com/windows/desktop/api/winuser/nf-winuser-setthreaddpiawarenesscontext) 函数更改上下文，使其匹配窗口上下文。 

> [!NOTE]
> 在调用解决方案代码之外的其他组件之前，上下文块应该会还原原始 DPI 线程上下文。

#### <a name="managed-code-context-block"></a>托管代码上下文块

以下示例代码显示了如何构建自己的上下文块。

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

#### <a name="native-code-context-block"></a>本机代码上下文块

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

<h2 id="top-level-window-management">顶级窗口管理</h2>

当 Office 应用程序启动时，将以 DPI_AWARENESS_CONTEXT_PER_MONITOR_AWARE 的形式调用 [SetThreadDpiAwarenessContext](https://docs.microsoft.com/windows/desktop/api/winuser/nf-winuser-setthreaddpiawarenesscontext)。 在此上下文中，DPI 更改将发送到以“按监视器 DPI 感知”形式运行的进程中的任何顶级窗口的 HWND。 顶级窗口是指 Office 应用程序窗口以及由解决方案创建的任何其他顶级窗口。 将 Office 应用程序移动到新显示器时，系统会通知它，以便它能够按照新显示器的 DPI 正确地进行动态缩放和绘制。 你的 Office 解决方案可以创建处于任何 DPI 感知模式的顶级窗口。 顶级窗口还可以通过侦听 Windows 更改消息来响应 DPI 更改。

如果已创建作为顶级窗口父级的子窗口，则你也可以将它们设置为任何 DPI 感知模式。 但是，如果使用“按监视器 DPI 感知”模式，则子窗口将不会收到 DPI 更改通知。  有关 Windows DPI 感知模式的详细信息，请参阅 [Windows 上的高 DPI 桌面应用程序开发](https://docs.microsoft.com/windows/desktop/hidpi/high-dpi-desktop-application-development-on-windows)。

## <a name="child-window-management"></a>子窗口管理

使用 ActiveX 控件和自定义任务窗格时，Office 会为你的解决方案创建子窗口。 你可以创建其他子窗口，但必须知道父窗口 DPI 感知。 Office 在“按监视器 DPI 感知”模式下运行，这意味着解决方案中的任何子窗口都不会收到 DPI 更改通知。 仅“按监视器 v2”模式支持向子窗口发送 DPI 更改（Office 不支持“按监视器 v2”）。 但是，对于 ActiveX 控件，有一种解决方法。 有关详细信息，请参阅本文后面的 [ActiveX 控件](#activex-controls)部分。

> [!NOTE]
> 如果子窗口创建了顶级窗口，则可以为新的顶级窗口使用任何 DPI 感知模式。 有关管理顶级窗口的详细信息，请参阅本文的[顶级窗口管理](#top-level-window-management)部分。

您将看到应用于子窗口的两种不同的 DPI 模式，具体取决于运行的 Windows 10 Office 版本。

### <a name="office-dpi-behavior-on-windows-fall-creators-update-1709"></a>Windows Fall Creators Update (1709) 中的 Office DPI 行为

由于 Office 应用使用按监视器感知模式，因此还将在“按监视器 DPI 感知”模式下为解决方案创建子窗口。 这意味着 Windows 希望在采用新 DPI 进行绘制时更新解决方案。  由于窗口无法收到 DPI 更改通知，因此你的解决方案 UI 可能不正确。 

![该图显示在 Windows Fall Creators Update (1709) 的“按监视器 DPI 感知”上下文中运行的子窗口。](./media/office-dpi-behavior-on-windows-fall-creators-update.png)

### <a name="office-dpi-behavior-on-windows-april-2018-update-1803"></a>Windows 2018 年 4 月更新 (1803) 中的 Office DPI 行为

对于 Windows 2018 年 4 月更新 (1803) 及更高版本，Office DPI 托管行为在某些情况下会使用混合模式 DPI 缩放。 这允许系统 DPI 感知窗口成为设置为“按监视器 DPI 感知”的 Office 窗口的父级。 这有助于确保在 DPI 发生更改和窗口位图拉伸时提高兼容性。 经过位图拉伸的窗口可能仍模糊不清。

![该图显示在 Windows 2018 年 4 月更新 (1803) 的“系统 DPI 感知”上下文中运行的子窗口。](./media/office-dpi-behavior-on-windows-april-2018-update.png)

创建新的子窗口时，请确保它们匹配其父窗口的 DPI 感知。 可以使用 [GetWindowDpiAwarenessContext](https://docs.microsoft.com/windows/desktop/api/winuser/nf-winuser-getwindowdpiawarenesscontext) 函数获取父窗口的 DPI 感知。 有关 DPI 感知一致性的详细信息，请参阅 [Windows 上的高 DPI 桌面应用程序开发](https://docs.microsoft.com/windows/desktop/hidpi/high-dpi-desktop-application-development-on-windows#related-topics)中的“强制重置整个进程的 DPI 感知”部分。

> [!NOTE]
> 你不能依赖于进程 DPI 感知，因为它可能会返回 [PROCESS_SYSTEM_DPI_AWARE](https://docs.microsoft.com/windows/desktop/api/shellscalingapi/ne-shellscalingapi-process_dpi_awareness)，即使应用程序主线程 DPI 感知上下文为 [DPI_AWARENESS_CONTEXT_PER_MONITOR_AWARE](https://docs.microsoft.com/windows/desktop/hidpi/dpi-awareness-context) 也是如此。 使用 [GetThreadDpiAwarenessContext](https://docs.microsoft.com/windows/desktop/api/winuser/nf-winuser-getthreaddpiawarenesscontext) 函数获取线程 DPI 感知上下文。

## <a name="office-and-windows-dpi-compatibility-settings"></a>Office 和 Windows DPI 兼容性设置

当用户遇到无法正确呈现的加载项或解决方案时，某些兼容性设置可帮助解决该问题。

<h3 id="office-compatibility">配置 Office 以优化兼容性</h3>

当移动到具有不同 DPI 缩放比例的其他屏幕时，Office 提供了用于优化兼容性的设置。 兼容模式可禁用 DPI 缩放，以便在移动到使用不同 DPI 缩放比例的显示器时，Office 中的所有内容都会进行位图拉伸。 

兼容模式强制Office DPI 感知模式运行。 这会导致应用程序窗口出现位图拉伸，并会导致外观模糊。 你的Office解决方案无法控制此设置，因为用户选择了它。 使用显示兼容性模式可解决大多数绘图问题。 有关详细信息，请参阅Office[高清晰度显示器的支持](https://support.office.com/en-us/article/office-support-for-high-definition-displays-6720ca0e-be59-41f6-b629-1369f549279d)。 

### <a name="configure-windows-to-fix-blurry-apps"></a>配置Windows修复模糊应用

Windows 10 (版本 1803) 及更高版本都有一个设置来修复应用，以便它们不会模糊。 如果解决方案未正确呈现，这是要尝试的另一个设置。 你的Office解决方案无法控制此设置，因为用户选择了它。 有关详细信息，请参阅修复在应用中显得模糊[Windows 10。](https://support.microsoft.com/en-us/help/4091364/windows-10-fix-blurry-apps)

## <a name="how-to-support-dpi-scaling-in-your-solution"></a>如何在解决方案中支持 DPI 缩放

某些解决方案可以接收和响应 DPI 更改。 如果一些用户无法接收通知，则有一个解决方法。 下表列出了每种解决方案类型的详细信息。

<table>
    <thead>
        <tr>
            <th>解决方案类型</th>
            <th>窗口类型</th>
            <th>可以响应 DPI 缩放</th>
            <th>更多详细信息</th>
        </tr>
    </thead>
<tbody>
    <tr>
        <td rowspan="2"><a href="#vsto-add-ins">VSTO加载项</a></td>
        <td>Top 及其后代</td>
        <td>是</td>
        <td>请参阅<a href="#vsto-add-ins">VSTO外接程序指南</a>。</td>
    </tr>
<tr>
        <td>父窗口Office子窗口</td>
        <td>否</td>
        <td>请参阅<a href="#office-compatibility">配置Office以优化兼容性</a>。</td>
</tr>
    <tr>
        <td rowspan="2"><a href="#custom-task-panes">自定义任务窗格</a></td>
        <td>Top 及其后代</td>
        <td>是</td>
        <td>请参阅 <a href="#top-level-window-management">顶级窗口指南</a>。</td>
    </tr>
<tr>
        <td>父窗口Office子窗口</td>
        <td>否</td>
        <td>请参阅<a href="#office-compatibility">配置Office以优化兼容性</a>。</td>
</tr>
    <tr>
        <td rowspan="2"><a href="#com-add-ins">COM 加载项</a></td>
        <td>Top 及其后代</td>
        <td>是</td>
        <td>请参阅 <a href="#com-add-ins">COM 加载项指南</a>。</td>
    </tr>
<tr>
        <td>父窗口Office子窗口</td>
        <td>否</td>
        <td>请参阅<a href="#office-compatibility">配置Office以优化兼容性</a>。</td>
</tr>
    <tr>
        <td rowspan="2"><a href="#activex-controls">ActiveX 控件</a></td>
        <td>Top 及其后代</td>
        <td>是</td>
        <td>请参阅<a href="#activex-controls">ActiveX控制指南</a>。</td>
    </tr>
    <tr>
        <td>父窗口Office子窗口</td>
        <td>是</td>
    </tr>
    <tr>
        <td><a href="#web-add-ins">Web 加载项</a></td>
        <td>不适用</td>
        <td>是</td>
        <td>请参阅<a href="#web-add-ins">Office Web 外接程序指南</a>。</td>
    </tr>
    <tr>
        <td><a href="#ribbon-extensibility">功能区扩展</a></td>
        <td>NA</td>
        <td>NA</td>
        <td>请参阅 <a href="#ribbon-extensibility">功能区扩展指南</a>。</td>
    </tr>
    <tr>
        <td><a href="#ole">OLE 服务器或客户端</a></td>
        <td>NA</td>
        <td>NA</td>
        <td>请参阅 <a href="#ole">OLE 服务器/客户端指南</a>。</td>
    </tr>
</tbody>
</table>

<h3 id="vsto-add-ins">VSTO加载项</h3>

如果VSTO加载项创建父窗口作为父窗口，Office窗口的 DPI 感知相匹配。 你可以使用 [GetWindowdpiAwarenessContext](https://docs.microsoft.com/windows/desktop/api/winuser/nf-winuser-getwindowdpiawarenesscontext) 函数来获取父窗口的 DPI 感知。 子窗口不会收到任何 DPI 更改通知。 如果解决方案未正确呈现，用户将需要将Office置于兼容模式。

对于加载项创建的任何VSTO窗口，你可以将其设置为任何 DPI 感知模式。 以下示例代码演示如何设置所需的 DPI 感知，以及如何响应 DPI 更改。 你还需要调整你的app.config，如在窗体中支持高 DPI Windows[中所述](https://docs.microsoft.com/dotnet/framework/winforms/high-dpi-support-in-windows-forms)。 

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

<h3 id="custom-task-panes">自定义任务窗格</h3>

自定义任务窗格由自定义任务窗格创建为子Office。 在 Windows Fall Creators Update (1709) 上运行时，自定义任务窗格将采用与 Office 相同的 DPI 感知模式运行。 当在 2018 Windows 1803 (及更高版本) ，自定义任务窗格将使用系统 DPI 感知模式运行。 

由于自定义任务窗格是子窗口，因此它们无法接收 DPI 通知。 如果他们的绘图不正确，用户将需要使用 DPI [Office模式](https://support.office.com/en-us/article/office-support-for-high-definition-displays-6720ca0e-be59-41f6-b629-1369f549279d)。
如果你的自定义任务窗格创建了顶级窗口，这些窗口可以在任何 DPI 感知模式下运行并接收 DPI 更改通知。 有关详细信息，请参阅 [本文中的顶级](#top-level-window-management) 窗口管理部分。

<h3 id="com-add-ins">COM 加载项</h3>

创建顶级窗口的 COM 加载项可以接收 DPI 通知。 应创建 [上下文块](#build-a-context-block-for-incoming-thread-calls) ，将线程设置为希望用于窗口的 DPI 感知，然后创建窗口。 需要正确处理 DPI 通知有很多，因此请务必阅读 windows 上的高[DPI](https://docs.microsoft.com/windows/desktop/hidpi/high-dpi-desktop-application-development-on-windows#related-topics)桌面应用程序Windows了解更多详细信息。

当 [WM_DPICHANGED](https://docs.microsoft.com/windows/desktop/hidpi/wm-dpichanged) DPI 发生更改时，将发送该邮件。  在非托管代码中，此消息由 HWND 的 [Window 过程](https://docs.microsoft.com/windows/desktop/winmsg/using-window-procedures) 处理。  示例 DPI 更改处理程序代码可在本文WM_DPICHANGED找到。 

显示父窗口的 COM 加载项，这些子窗口位于 Office无法接收 DPI 通知。 如果他们的绘图不正确，用户将需要使用 DPI [Office模式](https://support.office.com/article/office-support-for-high-definition-displays-6720ca0e-be59-41f6-b629-1369f549279d)。

<h3 id="activex-controls">ActiveX 控件</h3>

如何支持控件中的 DPI 缩放ActiveX控件是窗口控件还是无窗口控件。

#### <a name="windowed-activex-controls"></a>窗口ActiveX控件

窗口ActiveX控件每次WM_SIZE大小时会收到一条警告消息。  触发此事件时，事件处理程序代码可以使用控件的 HWND 调用 [GetDpiForWindow](https://docs.microsoft.com/windows/desktop/api/winuser/nf-winuser-getdpiforwindow) 函数，获取 DPI、计算比例系数差异并根据需要进行调整。 

以下示例使基于 MFC 的ActiveX控件能够响应 **OnSize** 事件。 

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

#### <a name="windowless-activex-controls"></a>无窗口ActiveX控件

无窗口ActiveX控件不能保证具有 HWND。  将ActiveX插入文档画布上时，该控件将进入设计模式。  在 Office 应用程序中，当控件在设计模式下时，托管容器将为在 ：：OnDraw 事件中调用 hDC->GetWindow () 返回 0。  在这种情况下，无法检索可靠的 DPI。 

但是，当控件在运行时模式下时，Office将返回要绘制控件的 HWND。  在这种情况下，控件开发人员可以调用 [GetDpiForWindow](https://docs.microsoft.com/windows/desktop/api/winuser/nf-winuser-getdpiforwindow) 并获取当前的 DPI 和缩放字体、控件等。 

<h3 id="ribbon-extensibility">自定义功能区扩展性</h3>

来自自定义功能Office控件的任何回调都将在系统 DPI 感知的 DPI 线程感知中。  如果你的解决方案需要不同的 DPI 线程感知，你应该实现上下文块来设置线程感知预期。 有关详细信息，请参阅生成 [上下文块](#build-a-context-block-for-incoming-thread-calls)。

<h3 id="ole">OLE 客户端和服务器</h3>

当 OLE 服务器托管在 OLE 客户端容器内时，当前无法提供当前或受支持的 DPI 信息。 这可能会导致问题，因为当前窗口体系结构不支持父窗口到子窗口混合模式Windows组合。 如果 Word 或 Excel检测到存在多个 DPI 缩放比例不同的监视器，则它们不支持就地激活。 OLE 服务器将就地激活。 如果遇到 OLE 服务器交互问题，用户将需要使用[DPI Office模式](https://support.office.com/article/office-support-for-high-definition-displays-6720ca0e-be59-41f6-b629-1369f549279d)。

<h3 id="web-add-ins">OfficeWeb 加载项</h3>

Office使用 JavaScript API Office加载项在浏览器控件内运行。 可以使用在任何 Web 应用设计中使用的相同技术处理 DPI 缩放。 许多联机资源都可用于帮助为高分辨率屏幕设计网页。

## <a name="verify-that-your-solution-supports-dpi-scaling"></a>验证解决方案是否支持 DPI 缩放

更新应用程序以支持 DPI 缩放后，应在混合 DPI 环境中验证更改。 验证当解决方案的窗口从一个显示器移动到另一个具有不同的 DPI 值的显示器时，你的 UI 代码是否正确响应 DPI 更改。 有关 DPI 缩放测试技术详细信息，请参阅上一个上的高 DPI 桌面[应用程序Windows。](https://docs.microsoft.com/windows/desktop/hidpi/high-dpi-desktop-application-development-on-windows#related-topics)

您可能还发现这些附加技术非常有用：

- 使用笔记本电脑，可以将主监视器设置为外部监视器，然后取消停靠该笔记本电脑。 这将强制主监视器更改为笔记本电脑显示器。
- 使用开源 [WinSpy++ 工具](https://github.com/BissetJ/winspy/releases) 帮助调试。 可以使用它查看任何窗口的 DPI 感知设置。
- 通过在"显示"选项卡上选择"使用远程会话的所有监视器"，可以使用远程桌面测试远程计算机上多个监视器，如以下屏幕截图所示。

![显示显示选项卡并选择使用远程会话的所有我的监视器的远程桌面连接应用。](./media/remote-desktop-use-all-monitors.png)

## <a name="see-also"></a>另请参阅

### <a name="articles"></a>文章

- [开发 WPF Per-Monitor DPI-Aware](https://docs.microsoft.com/windows/desktop/hidpi/declaring-managed-apps-dpi-aware) 提供了编写 Win32 桌面应用程序的一般概述和指南。 本文中介绍的许多相同技术将适用于Office解决方案。
- [混合模式 DPI 缩放和 DPI 感知 API](https://docs.microsoft.com/windows/desktop/hidpi/high-dpi-improvements-for-desktop-applications) 具有与 DPI 相关的 API 列表。
- [开发人员指南 - 按监视器 DPI - WPF 预览](https://github.com/Microsoft/WPF-Samples/blob/master/PerMonitorDPI/Developer%20Guide%20-%20Per%20Monitor%20DPI%20-%20WPF%20Preview.docx) 涵盖用于生成 DPI 感知 WPF 应用的 WPF 应用开发指南。
- [Office高](https://support.office.com/article/Office-support-for-high-definition-displays-6720ca0e-be59-41f6-b629-1369f549279d)清晰度显示器提供了当 DPI 更改时无法正确支持 Office 解决方案时，用户如何设置 Office 以优化兼容性的信息。
- [Display Scaling changes for the Windows 10 Anniversary Update](https://blogs.technet.microsoft.com/askcore/2016/08/16/display-scaling-changes-for-the-windows-10-anniversary-update/)是一篇博客文章，介绍了 Windows 10 周年更新引入的更改。 
- [DPI_AWARENESS_CONTEXT句柄](https://docs.microsoft.com/windows/desktop/hidpi/dpi-awareness-context) 具有有关DPI_AWARENESS_CONTEXT和定义的编程详细信息。
- [系统上的高 DPI 桌面应用程序Windows"](https://docs.microsoft.com/windows/desktop/hidpi/high-dpi-desktop-application-development-on-windows#testing-your-changes)测试更改"部分包含有关测试的信息。

### <a name="code-samples"></a>代码示例

- [按窗口 DPI 感知示例](https://github.com/Microsoft/Windows-classic-samples/tree/master/Samples/DPIAwarenessPerWindow)
- [动态 DPI 示例](https://github.com/Microsoft/Windows-classic-samples/tree/master/Samples/DynamicDPI)
- [每监视器感知 WPF 示例](https://github.com/Microsoft/Windows-classic-samples/tree/master/Samples/PerMonitorDPIAware)
