---
title: Microsoft 365 中 Office 无人参与自动化的注意事项（针对无人参与的 RPA 环境）
ms.date: 03/30/2020
ms.audience: Developer
localization_priority: Normal
description: Microsoft 365 中 Office 无人参与自动化的注意事项（针对无人参与的 RPA 环境）。
ms.openlocfilehash: 576217fc85f2980a6d2451e3f930296ea4c11a56
ms.sourcegitcommit: 007aa2ceb4f569201c3f4372de5c83b6c61f8875
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2020
ms.locfileid: "43103046"
---
# <a name="considerations-for-unattended-automation-of-office-in-the-microsoft-365-for-unattended-rpa-environment"></a>Microsoft 365 中 Office 无人参与自动化的注意事项（针对无人参与的 RPA 环境）

尽管 Microsoft 365 for 无人参与的 RPA 提供了一个许可证，该许可证可实现 Office 自动化功能，并且所有当前版本的 Office 都设计和测试为在客户端工作站上以最终用户产品的形式运行，用户可与应用程序的接口进行交互。 在没有用户的情况下使用应用程序导致的意外行为不存在缺陷。 如果要在此配置中运行 Office，则必须准备在应用程序逻辑中考虑这些意外行为。

本文概述了 Office 无人参与自动化的一些注意事项，以帮助你使用此方法。 但是，请注意，此配置中的 Office 的使用严格为 "按原样"，并且必须考虑这些意外行为。 此处提供的信息并不详尽，并不保证能够解决所有客户端的所有问题。 我们鼓励你在部署之前全面测试你的解决方案。

## <a name="common-problems-in-unattended-automation"></a>无人参与的自动化中的常见问题

如果要在没有用户的情况下使用 Office，请注意 Office 的行为与预期不同的以下方面。 若要成功运行您的解决方案，它必须解决这些问题，并尽可能最大限度地减少它们的影响。 生成应用程序时，请仔细考虑这些问题。

### <a name="interactive-ui-elements"></a>交互式 UI 元素

Office 应用程序假定它们以交互方式运行。 如果发生意外错误，或者如果需要一个未指定的参数来完成某个函数，则 Office 将向用户提示一个对话框，询问用户要继续执行的操作。 在无人参与的自动化中，这可能会导致应用程序在应用程序停止时显示为 "挂起"，直到它接收到此输入。 如果您通过其公共 Api 实现 Office 自动化，则可以通过相应地配置[DisplayAlerts](https://docs.microsoft.com/office/vba/api/word.application.displayalerts)和[AutomationSecurity](https://docs.microsoft.com/office/vba/api/word.application.automationsecurity)等属性来抑制其中的许多警报。 您的代码应能够随时识别和处理阻止警报。

### <a name="user-identity"></a>用户标识

运行应用程序时，Office 应用程序需要用户标识，即使应用程序是通过 "自动化" 启动的也是如此。 此用户标识可能导致以下任一或所有内容：

- 必须处理的其他登录 UI 是否存在。
- 无法基于每个用户的访问权限打开和/或编辑的文件。
- 对文件元数据的意外更改（例如，某些文件属性将根据自动应用程序实例的用户标识的标识进行更新）。

各种方法可帮助缓解这些问题;例如，运行[文档检查器](https://docs.microsoft.com/office/vba/library-reference/concepts/using-the-document-inspector)以删除元数据。 根据您的应用场景，考虑这些方法是否适用。

### <a name="server-side-security"></a>服务器端安全性

在运行 Office 无人参与并处理任意文件内容时，该环境中没有其他特定的保护可用于阻止加载和运行这些文件中存储的宏。 Office 无法防止您无意中从代码运行宏，或从启动可能运行宏的另一台服务器上运行宏。 您可以使用[AutomationSecurity](https://docs.microsoft.com/office/vba/api/word.application.automationsecurity)之类的属性来缓解此风险，但您应确保仅加载受信任的内容。

此外，Office 使用可缓存客户端身份验证信息以加快处理速度的许多组件（如简单 MAPI、WinInet 和 MSDAIPP.DSO）。 当 Office 自动服务器端和处理多个文件时，如果已为该会话缓存了身份验证信息，则一个客户端可以使用其他客户端的缓存凭据。 因此，客户端可以通过模拟其他用户获取未授予访问权限。

### <a name="ui-changes"></a>UI 更改

Office 中的 UI 元素在很大程度上是稳定的，但不能保证任何 UI 元素的特定位置，并且可能会随着产品设计的发展而发生变化，以合并用户反馈并满足客户需求。 任何自动化的逻辑都必须考虑这一点。 这些更改可能会导致按钮或组选项卡命名更改、命令在选项卡之间移动、添加新选项卡或在与我们的功能弃用策略相一致的情况下删除命令。 这些更改既可以在 UI 中进行，也可以在应用程序提供的辅助功能信息中进行，因为修改该信息以提高日常客户反馈的可用性和帐户，并且可能会在不同时间为不同的用户进行滚动。

即使不进行产品更改，系统环境（如屏幕大小/分辨率/DPI）之间的差异也会导致屏幕上的项目位置发生变化。 任何依靠屏幕坐标模拟用户输入的方法都必须考虑这些更改并相应地进行调整。

### <a name="single-threading"></a>单线程

Office 应用程序是不能重入的、基于 STA 的应用程序，旨在为单个客户端提供不同但占用资源的功能。 应用程序使用全局资源，如内存映射文件、全局外接程序或模板以及共享的自动化服务器。 这样可以限制可并发运行的实例数，如果应用程序在 multiclient 环境中进行配置，可能会导致出现争用条件。 如果打算运行多个 Office 应用程序的多个实例，则应计划在虚拟机级别隔离这些实例，以确保生成的解决方案的稳定性。

### <a name="resiliency-and-stability"></a>恢复能力和稳定性

即使在上述注意事项的情况下，如果应用程序以模拟用户输入的方式自动进行，或者对于明显超过交互使用率的会话长度，它们可能会遇到交互运行时不存在的问题。 在此上下文中利用 Office 的解决方案应主动构建用于监视应用程序状态的机制，并在必要时重新启动应用程序的状态（和/或正在运行的虚拟机）。

## <a name="suggested-alternatives"></a>建议的替代方法

Microsoft 强烈建议一些备选方案，这些备选方案不要求安装 Office 并在服务器端运行，并且可以更高效地执行常见任务，且比此配置中的自动化更快。 在将 Office 作为项目中的服务器端组件之前，请考虑替代方法。

### <a name="microsoft-graph"></a>Microsoft Graph

Microsoft Graph API 提供了对可供 Microsoft 云的用户和解决方案使用的服务、数据和智能的访问，包括支持无人参与自动化需求的许多服务：访问用户的邮件/日历/联系人/文件、文档转换、Excel 工作簿计算等。 这些服务旨在实现无人值守的使用和高规模访问，并利用标准的 RESTful API 语法。 有关 Microsoft Graph 以及如何使用它来处理用户数据的详细信息，请访问以下内容：

- [Microsoft Graph 概述](https://docs.microsoft.com/graph/overview) 
- [Microsoft Graph 入门](https://developer.microsoft.com/graph/get-started)
- [下载另一种格式的文件](https://docs.microsoft.com/graph/api/driveitem-get-content-format?view=graph-rest-1.0&tabs=http)（文件转换）
- [在 Microsoft Graph 中使用 Excel](https://docs.microsoft.com/graph/api/resources/excel?view=graph-rest-1.0) （工作簿详细信息）

### <a name="open-xml-file-formats"></a>Open XML 文件格式

许多自动化任务涉及文档创建或编辑。 Office 支持 Open XML 文件格式，使开发人员能够使用 ISO 29500 国际标准中定义的标准 XML 和 ZIP 技术创建、编辑、读取和转换文件内容。 可以通过任何 ZIP/XML 工具（包括 Microsoft .NET 3 System.IO.Package.IO Framework 中的命名空间）操作这些文件格式。 若要从服务处理 Office 文件的更改，建议直接编辑文件格式。

Microsoft 提供了一个 SDK，用于处理 .NET 3. x Framework 中的 Open XML 文件格式。 有关 SDK 以及如何使用 SDK 创建或编辑 Open XML 文件的详细信息，请访问以下内容：

- [了解 Open XML 文件格式](https://docs.microsoft.com/office/open-xml/understanding-the-open-xml-file-formats)
- [欢迎使用 Open XML SDK 2.5 for Office](https://docs.microsoft.com/office/open-xml/open-xml-sdk)
