---
title: 无人参与 RPA 环境中Office无人参与Microsoft 365自动化的注意事项
ms.date: 03/30/2020
ms.audience: Developer
localization_priority: Normal
description: 无人参与 RPA 环境中Office无人参与Microsoft 365自动化的注意事项。
ms.openlocfilehash: 576217fc85f2980a6d2451e3f930296ea4c11a56
ms.sourcegitcommit: 007aa2ceb4f569201c3f4372de5c83b6c61f8875
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2020
ms.locfileid: "43103046"
---
# <a name="considerations-for-unattended-automation-of-office-in-the-microsoft-365-for-unattended-rpa-environment"></a>无人参与 RPA 环境中Office无人参与Microsoft 365自动化的注意事项

尽管 Microsoft 365 for unattended RPA 提供了一个允许自动执行 Office 且不存在用户的许可，但 Office 的所有当前版本都经过设计和测试，可在客户端工作站上作为最终用户产品运行，同时存在一个用户以与应用程序界面交互。 由于在没有用户存在的情况下使用应用程序而导致的意外行为不是缺陷。 如果要在此配置Office，则必须准备好在应用程序逻辑中考虑这些意外行为。

本文概述了无人参与自动化的一些注意事项Office使用这种方法时提供帮助。 但是，请注意，此配置Office"AS IS"，并且必须说明这些意外行为。 此处提供的信息并不详尽，不保证解决所有客户端的所有问题。 我们建议您在部署之前全面测试解决方案。

## <a name="common-problems-in-unattended-automation"></a>无人参与自动化中的常见问题

如果要在没有用户Office的情况下使用应用程序，请注意以下区域，其中Office的行为可能不同于预期。 若要使解决方案成功运行，它必须解决这些问题并尽可能降低其影响。 在构建应用程序时，请仔细考虑这些问题。

### <a name="interactive-ui-elements"></a>交互式 UI 元素

Office应用程序假定它们以交互方式运行。 如果发生意外错误，或者完成函数时需要未指定的参数，Office 旨在提示用户显示一个对话框，询问用户希望如何继续。 在无人参与自动化中，这可能会导致应用程序在应用程序停止时显示为"挂起"，直到收到此输入。 如果要通过公用 API 自动Office，可以通过正确配置[Application.DisplayAlerts](https://docs.microsoft.com/office/vba/api/word.application.displayalerts)和[Application.AutomationSecurity](https://docs.microsoft.com/office/vba/api/word.application.automationsecurity)等属性来抑制其中许多警报。 代码应设计为随时识别和处理阻止警报。

### <a name="user-identity"></a>用户标识

Office运行时，应用程序需要用户标识，即使应用程序是通过自动化启动的。 此用户标识可能会导致以下任意或全部：

- 存在必须处理的其他登录 UI。
- 无法根据每用户访问权限打开和/或编辑的文件。
- 对文件元数据的意外更改 (例如，某些文件属性将基于自动应用程序实例应用程序实例的用户标识进行更新) 。

各种方法都有助于缓解这些问题;例如，运行 [文档检查器](https://docs.microsoft.com/office/vba/library-reference/concepts/using-the-document-inspector) 以删除元数据。 根据你的方案考虑这些方法是否合适。

### <a name="server-side-security"></a>服务器端安全性

在无人Office并处理任意文件内容时，该环境中没有其他特定保护可用于阻止加载和运行存储在这些文件中的宏。 Office无法防止您无意中从代码中运行宏，或防止您启动另一台可能运行宏的服务器。 可以使用 [Application.AutomationSecurity](https://docs.microsoft.com/office/vba/api/word.application.automationsecurity) 等属性来缓解此风险，但应确保仅加载受信任内容。

此外，Office许多组件 (简单 MAPI、WinInet 和 MSDAIPP) ，这些组件可以缓存客户端身份验证信息以加快处理速度。 当Office自动化服务器端并处理多个文件时，如果为该会话缓存了身份验证信息，则一个客户端可以使用另一个客户端的缓存凭据。 因此，客户端可以通过模拟其他用户获得未授予的访问权限。

### <a name="ui-changes"></a>UI 更改

Office中的 UI 元素在很大程度上是稳定的，但任何 UI 元素的特定位置都无法保证，并且可能会随着系统设计的不断发展而发生变化，以纳入用户反馈并满足客户需求。 任何自动化的逻辑都必须考虑到这一点。 这些更改可能会导致按钮或组选项卡命名更改、选项卡之间的命令移动、新选项卡的添加或删除与功能弃用策略一致的命令。 这些更改可以在 UI 中以及应用程序提供的辅助功能信息中发生，因为修改该信息以提高可用性并考虑持续的客户反馈，并且可能会在不同时间为不同用户推出这些更改。

即使没有产品更改，系统环境之间的差异 (如屏幕大小/分辨率/DPI) 可能会导致项目在屏幕上的位置发生变化。 依赖于屏幕坐标来模拟用户输入的任何方法都必须考虑这些更改并相应地进行调整。

### <a name="single-threading"></a>单线程

Office应用程序是基于 STA 的不可重新访问的应用程序，旨在为单个客户端提供各种但资源密集型功能。 应用程序使用全局资源，如内存映射文件、全局加载项或模板以及共享自动化服务器。 如果应用程序在多客户端环境中配置，这可限制可同时运行的实例数，并可能导致竞争条件。 如果计划运行任意 Office 应用程序的多个实例，则应该计划在虚拟机级别隔离它们，以确保生成的解决方案的稳定性。

### <a name="resiliency-and-stability"></a>复原和稳定性

即使考虑到上述考虑事项，如果应用程序以模拟用户输入的方式自动化，或者对于明显超出交互用法的会话长度，它们可能会遇到在以交互方式运行时不存在的问题。 在此上下文中Office解决方案应主动构建机制，以监视应用程序的状态，并根据需要 (和/或运行应用程序) 虚拟机重新启动它们。

## <a name="suggested-alternatives"></a>建议的备选方法

Microsoft 强烈建议推荐一些无需在Office安装和运行客户端的替代方法，这些替代方法可以比此配置中的自动化更高效、更快速地执行常见任务。 在将 Office用作项目中的服务器端组件之前，请考虑其他方法。

### <a name="microsoft-graph"></a>Microsoft Graph

Microsoft Graph API 提供对作为 Microsoft 云一部分的用户和解决方案可用的服务、数据和智能的访问，包括许多支持无人参与自动化需求的服务：访问用户的邮件/日历/联系人/文件、文档转换、Excel 工作簿计算等。 这些服务专为无人参与使用和大规模访问设计，并使用标准 RESTful API 语法。 有关 Microsoft Graph以及如何使用它处理用户数据的信息，请访问以下内容：

- [Microsoft Graph 概述](https://docs.microsoft.com/graph/overview) 
- [Microsoft Graph 入门](https://developer.microsoft.com/graph/get-started)
- [下载另一种格式的文件 (](https://docs.microsoft.com/graph/api/driveitem-get-content-format?view=graph-rest-1.0&tabs=http) 文件转换) 
- [在 Microsoft Excel中Graph (](https://docs.microsoft.com/graph/api/resources/excel?view=graph-rest-1.0)工作簿详细信息) 

### <a name="open-xml-file-formats"></a>Open XML 文件格式

许多自动化任务都涉及文档创建或编辑。 Office支持 Open XML 文件格式，使开发人员能够使用 ISO 29500 国际标准中定义的标准 XML 和 ZIP 技术创建、编辑、读取和转换文件内容。 可以通过任何 ZIP/XML 工具（包括 Microsoft .NET 3.x framework 中的 System.IO.Package.IO 命名空间）操作这些文件格式。 直接编辑文件格式是建议和支持的方法，用于处理对Office文件所做的更改。

Microsoft 提供了一个 SDK，用于处理 .NET 3.x Framework 中的 Open XML 文件格式。 有关 SDK 以及如何使用 SDK 创建或编辑 Open XML 文件的信息，请访问以下内容：

- [了解 Open XML 文件格式](https://docs.microsoft.com/office/open-xml/understanding-the-open-xml-file-formats)
- [欢迎使用 Open XML SDK 2.5 for Office](https://docs.microsoft.com/office/open-xml/open-xml-sdk)
