---
title: 系统性释放对象
TOCTitle: Systematically releasing objects
ms:assetid: d4cd1d8e-aae6-483b-a4d8-1656171e838d
ms:mtpsurl: https://msdn.microsoft.com/library/Bb623945(v=office.15)
ms:contentKeyID: 55119785
ms.date: 07/24/2014
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 5d71ffbdbd10657832a319e1e669f38f311ad99f
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32319241"
---
# <a name="systematically-releasing-objects"></a><span data-ttu-id="1a3c1-102">系统性释放对象</span><span class="sxs-lookup"><span data-stu-id="1a3c1-102">Systematically releasing objects</span></span>

<span data-ttu-id="1a3c1-103">本主题总结了针对使用 Outlook 的加载项开发人员和 IT 管理员的加载项关闭建议。</span><span class="sxs-lookup"><span data-stu-id="1a3c1-103">This topic summarizes add-in shutdown recommendations for add-in developers and IT administrators that use Outlook.</span></span> <span data-ttu-id="1a3c1-104">有关详细信息，请参阅 [Outlook 2010 中有关关闭的更改](https://msdn.microsoft.com/library/ee720183\(v=office.15\))。</span><span class="sxs-lookup"><span data-stu-id="1a3c1-104">For more information, see [Shutdown Changes for Outlook 2010](https://msdn.microsoft.com/library/ee720183\(v=office.15\)).</span></span>

## <a name="add-in-shutdown-changes-in-outlook"></a><span data-ttu-id="1a3c1-105">Outlook 中的加载项关闭更改</span><span class="sxs-lookup"><span data-stu-id="1a3c1-105">Add-in shutdown changes in Outlook</span></span>

<span data-ttu-id="1a3c1-106">从 Outlook 2010 开始，Outlook 默认不标示已关闭的加载项。</span><span class="sxs-lookup"><span data-stu-id="1a3c1-106">Starting in Outlook 2010, Outlook, by default, does not signal add-ins that it is shutting down.</span></span> <span data-ttu-id="1a3c1-107">具体而言，Outlook 在快速关闭期间不再调用 **IDTExtensibility2** 接口的 **OnBeginShutdown(Array)** 和 **OnDisconnection(ext\_DisconnectMode, Array)** 方法。</span><span class="sxs-lookup"><span data-stu-id="1a3c1-107">Specifically, Outlook no longer calls the **OnBeginShutdown(Array)** and **OnDisconnection(ext\_DisconnectMode, Array)** methods of the **IDTExtensibility2** interface during fast shutdown.</span></span> <span data-ttu-id="1a3c1-108">同样，在关闭 Outlook 时，使用 Visual Studio 2010 或更高版本中的 Office 开发工具编写的 Outlook 加载项不再调用 ThisAddin\_Shutdown 方法。</span><span class="sxs-lookup"><span data-stu-id="1a3c1-108">Similarly, an Outlook add-in, written with Office development tools in Visual Studio 2010 or a later version, no longer calls the ThisAddin\_Shutdown method when Outlook is shutting down.</span></span> 

<span data-ttu-id="1a3c1-109">停止调用这些方法的原因是：大多数加载项执行的都是类似释放引用这样的简单任务，如果在这些事件运行期间某些加载项以同步方式生成 Web 服务调用或其他长时间运行的操作，则会显著地延迟关闭 Outlook。</span><span class="sxs-lookup"><span data-stu-id="1a3c1-109">The reason to stop calling these methods is that while a majority of add-ins perform simple tasks like releasing references, some add-ins make Web service calls or other long-running operations synchronously during these events, significantly delaying Outlook from shutting down.</span></span> <span data-ttu-id="1a3c1-110">进行此更改后，Outlook 会比在过去关闭时表现更好。</span><span class="sxs-lookup"><span data-stu-id="1a3c1-110">As a result of this change, Outlook works better than it has in the past when shutting down.</span></span>

## <a name="recommendations-for-add-in-shutdown-for-developers"></a><span data-ttu-id="1a3c1-111">针对开发人员的加载项关闭建议</span><span class="sxs-lookup"><span data-stu-id="1a3c1-111">Recommendations for add-in shutdown for developers</span></span>

<span data-ttu-id="1a3c1-112">开发人员务必要遵守以下有关加载项关闭的建议，以确保最终用户继续从快速响应的 Outlook 关闭体验中受益。</span><span class="sxs-lookup"><span data-stu-id="1a3c1-112">It is important that developers observe the following recommendations for add-in shutdown to ensure that end users continue to benefit from a fast and responsive Outlook shutdown experience.</span></span>

- <span data-ttu-id="1a3c1-113">加载项应继续实现 OnBeginShutdown 和 OnDisconnection 方法或 ThisAddin\_Shutdown 以释引用和分配的内存，因为会出现以下情况：管理员可能通过组策略恢复为缓慢关闭，或者用户可能通过“**COM 加载项**” 对话框手动断开与加载项的连接。</span><span class="sxs-lookup"><span data-stu-id="1a3c1-113">Add-ins should continue to implement the OnBeginShutdown and OnDisconnection methods or ThisAddin\_Shutdown to release references and allocated memory, because there are scenarios in which administrators might revert to slow shutdown through group policy, or the user might manually disconnect your add-in through the **COM Add-ins** dialog box.</span></span>

- <span data-ttu-id="1a3c1-114">加载项开发人员应仅执行在关闭期间绝对必须执行的任务。</span><span class="sxs-lookup"><span data-stu-id="1a3c1-114">Add-in developers should only perform tasks that absolutely must take place during shutdown.</span></span>

- <span data-ttu-id="1a3c1-115">加载项开发人员应评估其加载项在各种方案中和控制 Outlook 关闭的不同 Windows 注册表设置下的性能，并主动地修改其加载项以适合于 Outlook。</span><span class="sxs-lookup"><span data-stu-id="1a3c1-115">Add-in developers should evaluate the performance of their add-ins in various scenarios and under different Windows registry settings that control Outlook shutdown, and proactively modify their add-ins to work with Outlook.</span></span>

## <a name="recommendations-for-add-in-shutdown-for-it-administrators"></a><span data-ttu-id="1a3c1-116">针对 IT 管理员的加载项关闭建议</span><span class="sxs-lookup"><span data-stu-id="1a3c1-116">Recommendations for add-in shutdown for IT administrators</span></span>

<span data-ttu-id="1a3c1-117">对于 IT 管理员，如果企业中已部署有加载项但无法升级这些加载项使其变得与新的关闭 Outlook 机制兼容，IT 管理员可以借助于几个 Windows 注册表设置来还原为缓慢关闭行为。</span><span class="sxs-lookup"><span data-stu-id="1a3c1-117">For IT administrators, if there are add-ins that are already deployed in an enterprise and cannot be upgraded to become compatible with the new shutdown Outlook mechanism, IT administrators can resort to a couple of Windows registry settings to revert to the slow shutdown behavior.</span></span>

### <a name="individual-add-in-setting"></a><span data-ttu-id="1a3c1-118">单个的加载项设置</span><span class="sxs-lookup"><span data-stu-id="1a3c1-118">Individual add-in setting</span></span>

<span data-ttu-id="1a3c1-p104">作为加载项部署的一部分，IT 管理员可以启用各个 Outlook 加载项的关闭通知。尽管您无法通过组策略来实现这一点，但是如果您对于特定加载项具有向后兼容性要求，则会大有帮助。</span><span class="sxs-lookup"><span data-stu-id="1a3c1-p104">IT administrators can enable shutdown notifications to individual Outlook add-ins as part of the add-in deployment. Although you cannot do this through group policy, it is useful if you have backward-compatibility requirements for specific add-ins.</span></span>

<span data-ttu-id="1a3c1-p105">通过在 HKCU 或 HKLM 注册表配置单元中进行加载项注册（为加载项注册添加其他值），可以为每个加载项配置此设置。以单行的形式键入以下文本：</span><span class="sxs-lookup"><span data-stu-id="1a3c1-p105">Configure this setting for each add-in through the add-in registration in the HKCU or the HKLM registry hives, by adding an additional value to the add-in registration. Type the following text as a single line:</span></span>

`HKCU\Software\Microsoft\Office\Outlook\Add-ins\<ProgID>[RequireShutdownNotification]=dword:0x1`

<span data-ttu-id="1a3c1-123">通过将此值设置为 0x1，可使加载项在 Outlook 关闭期间接收被阻止的回调。</span><span class="sxs-lookup"><span data-stu-id="1a3c1-123">Setting this value to 0x1 enables the add-in to receive blocked callbacks during Outlook shutdown.</span></span> <span data-ttu-id="1a3c1-124">此设置会对 Outlook 的关闭性能造成影响，应作为部署的一部分进行评估。</span><span class="sxs-lookup"><span data-stu-id="1a3c1-124">This has an impact on the performance of Outlook shutdown and should be evaluated as part of a deployment.</span></span> <span data-ttu-id="1a3c1-125">此设置仅在加载项与新的关闭机制之间存在重大兼容性问题时使用。</span><span class="sxs-lookup"><span data-stu-id="1a3c1-125">This setting should be used only if an add-in has significant compatibility issues with the new shutdown mechanism.</span></span> <span data-ttu-id="1a3c1-126">如果将此值设置为 0x0，则会使用 Outlook 的默认行为。</span><span class="sxs-lookup"><span data-stu-id="1a3c1-126">Setting the value to 0x0 uses the default behavior of Outlook.</span></span>

### <a name="global-setting"></a><span data-ttu-id="1a3c1-127">全局设置</span><span class="sxs-lookup"><span data-stu-id="1a3c1-127">Global setting</span></span>

<span data-ttu-id="1a3c1-128">IT 管理员可以通过组策略在全局范围内为所有加载项启用关闭通知。</span><span class="sxs-lookup"><span data-stu-id="1a3c1-128">IT administrators can enable shutdown notifications globally for all add-ins through group policy.</span></span> <span data-ttu-id="1a3c1-129">如果组织具有大量内部解决方案或桌面，且它们都需要部署此设置以确保推出 Outlook 时的兼容性，则建议执行此操作。</span><span class="sxs-lookup"><span data-stu-id="1a3c1-129">This is recommended for organizations that have a large number of internal solutions or desktops that need to deploy this setting to ensure compatibility during a rollout of Outlook.</span></span>

<span data-ttu-id="1a3c1-130">请使用此设置更改关闭机制，以匹配 Outlook 2007 使用的机制。</span><span class="sxs-lookup"><span data-stu-id="1a3c1-130">Use this setting to change the shutdown mechanism to match that used by Outlook 2007.</span></span> <span data-ttu-id="1a3c1-131">你可以通过组策略部署此设置，也可以为每个用户或每台计算机部署此设置。</span><span class="sxs-lookup"><span data-stu-id="1a3c1-131">You can deploy the setting through group policy, either per user or per computer.</span></span> <span data-ttu-id="1a3c1-132">以单行格式键入以下文本：</span><span class="sxs-lookup"><span data-stu-id="1a3c1-132">Type the following text as a single line:</span></span>

`HKCU\Policies\Microsoft\Office\Outlook\15.0\Options\Shutdown[AddinFastShutdownBehavior]=dword:0x1`

<span data-ttu-id="1a3c1-133">通过将 AddinFastShutdownBehavior 设置为 0x1，可为所有加载项启用关闭通知。如果将此值设置为 0x0，则会使用 Outlook 的默认行为。</span><span class="sxs-lookup"><span data-stu-id="1a3c1-133">Setting AddinFastShutdownBehavior to 0x1 enables shutdown notifications for all add-ins. Setting the value to 0x0 uses the default behavior of Outlook.</span></span>

