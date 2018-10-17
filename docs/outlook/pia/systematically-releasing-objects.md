---
title: 系统性释放对象
TOCTitle: Systematically releasing objects
ms:assetid: d4cd1d8e-aae6-483b-a4d8-1656171e838d
ms:mtpsurl: https://msdn.microsoft.com/library/Bb623945(v=office.15)
ms:contentKeyID: 55119785
ms.date: 07/24/2014
mtps_version: v=office.15
ms.openlocfilehash: 812f720b3ebab1100040802d7593548063497297
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25406832"
---
# <a name="systematically-releasing-objects"></a>系统性释放对象

本主题总结了针对使用 Outlook 的加载项开发人员和 IT 管理员的加载项关闭建议。 有关详细信息，请参阅 [Outlook 2010 中有关关闭的更改](https://msdn.microsoft.com/library/ee720183\(v=office.15\))。

## <a name="add-in-shutdown-changes-in-outlook"></a>Outlook 中的加载项关闭更改

从 Outlook 2010 开始，Outlook 默认不标示已关闭的加载项。 具体而言，Outlook 在快速关闭期间不再调用 **IDTExtensibility2** 接口的 **OnBeginShutdown(Array)** 和 **OnDisconnection(ext\_DisconnectMode, Array)** 方法。 同样，在关闭 Outlook 时，使用 Visual Studio 2010 或更高版本中的 Office 开发工具编写的 Outlook 加载项不再调用 ThisAddin\_Shutdown 方法。 

停止调用这些方法的原因是：大多数加载项执行的都是类似释放引用这样的简单任务，如果在这些事件运行期间某些加载项以同步方式生成 Web 服务调用或其他长时间运行的操作，则会显著地延迟关闭 Outlook。 进行此更改后，Outlook 会比在过去关闭时表现更好。

## <a name="recommendations-for-add-in-shutdown-for-developers"></a>针对开发人员的加载项关闭建议

开发人员务必要遵守以下有关加载项关闭的建议，以确保最终用户继续从快速响应的 Outlook 关闭体验中受益。

- 加载项应继续实现 OnBeginShutdown 和 OnDisconnection 方法或 ThisAddin\_Shutdown 以释引用和分配的内存，因为会出现以下情况：管理员可能通过组策略恢复为缓慢关闭，或者用户可能通过“**COM 加载项**” 对话框手动断开与加载项的连接。

- 加载项开发人员应仅执行在关闭期间绝对必须执行的任务。

- 加载项开发人员应评估其加载项在各种方案中和控制 Outlook 关闭的不同 Windows 注册表设置下的性能，并主动地修改其加载项以适合于 Outlook。

## <a name="recommendations-for-add-in-shutdown-for-it-administrators"></a>针对 IT 管理员的加载项关闭建议

对于 IT 管理员，如果企业中已部署有加载项但无法升级这些加载项使其变得与新的关闭 Outlook 机制兼容，IT 管理员可以借助于几个 Windows 注册表设置来还原为缓慢关闭行为。

### <a name="individual-add-in-setting"></a>单个的加载项设置

作为加载项部署的一部分，IT 管理员可以启用各个 Outlook 加载项的关闭通知。尽管您无法通过组策略来实现这一点，但是如果您对于特定加载项具有向后兼容性要求，则会大有帮助。

通过在 HKCU 或 HKLM 注册表配置单元中进行加载项注册（为加载项注册添加其他值），可以为每个加载项配置此设置。以单行的形式键入以下文本：

`HKCU\Software\Microsoft\Office\Outlook\Add-ins\<ProgID>[RequireShutdownNotification]=dword:0x1`

通过将此值设置为 0x1，可使加载项在 Outlook 关闭期间接收被阻止的回调。 此设置会对 Outlook 的关闭性能造成影响，应作为部署的一部分进行评估。 此设置仅在加载项与新的关闭机制之间存在重大兼容性问题时使用。 如果将此值设置为 0x0，则会使用 Outlook 的默认行为。

### <a name="global-setting"></a>全局设置

IT 管理员可以通过组策略在全局范围内为所有加载项启用关闭通知。 如果组织具有大量内部解决方案或桌面，且它们都需要部署此设置以确保推出 Outlook 时的兼容性，则建议执行此操作。

请使用此设置更改关闭机制，以匹配 Outlook 2007 使用的机制。 你可以通过组策略部署此设置，也可以为每个用户或每台计算机部署此设置。 以单行格式键入以下文本：

`HKCU\Policies\Microsoft\Office\Outlook\15.0\Options\Shutdown[AddinFastShutdownBehavior]=dword:0x1`

通过将 AddinFastShutdownBehavior 设置为 0x1，可为所有加载项启用关闭通知。如果将此值设置为 0x0，则会使用 Outlook 的默认行为。

