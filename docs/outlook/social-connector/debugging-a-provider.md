---
title: 调试提供程序
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: d2dfaeed-7635-4c6b-9c35-b955ca1a85e9
description: 可以通过多种方式在 OSC (调试 Outlook Social Connector) 程序：
ms.openlocfilehash: 39deb7b6c0b11460826bdbf1957ffd8404d926e5
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32281067"
---
# <a name="debugging-a-provider"></a>调试提供程序

可以通过多种方式在 OSC (调试 Outlook Social Connector) 程序： 
  
- 通过使用 Outlook 中 Office Fluent 用户界面的功能区组件中的调试命令或支持 Office 客户端应用程序，使 OSC 采取各种操作。
    
- 使用 Fiddler 跟踪社交网络及其 OSC 提供程序之间发送的 API 调用和 XML
    
## <a name="debug-buttons"></a>调试按钮

OSC 提供程序扩展性提供调试 OSC 提供程序的功能。 若要调试提供程序，在 Windows 注册表中的键 (下创建一个 DWORD 类型的值，如下面的) 所示，将该值设置为  `DebugProviders`  `SocialConnector`  `DebugProviders` 1。 
  
`HKEY_CURRENT_USER\Software\Microsoft\Office\Outlook\SocialConnector`
  
默认情况下，提供程序调试是关闭的。 如果  `DebugProviders` 值不存在，或者它存在并设置为值 0，则关闭提供程序调试。 
  
如果提供程序调试已打开，则 OSC 会在发生错误时显示一个包含详细错误信息的警报对话框，并针对 OSC 提供程序 XML 架构验证任何 OSC 提供程序 XML。 根据为 XML 字符串指定的命名空间，根据 OSC 1.0 架构文件 OutlookSocialProvider.xsd 验证使用 OSC 1.0 开发的 OSC 提供程序。 根据架构文件 OutlookSocialProvider_1.1.xsd 验证使用 OSC 1.1 或更高版本开发的 OSC 提供程序。 使用 值时，将显示所有加载的提供程序（而不是特定提供程序）  `DebugProviders` 的调试警报。 
  
若要显示有助于调试提供程序的调试按钮，可在 Windows 注册表中的项下创建一个 DWORD 类型的值，将该值  `ShowDebugButtons`  `SocialConnector` 设置为  `ShowDebugButtons` 1。 若要隐藏调试命令栏按钮，请将其  `ShowDebugButtons` 值设置为 0。 
  
对于自 Office 2013 以来的 Outlook 2010 和客户端应用程序，调试按钮显示在浏览器功能区的"加载项"选项卡上。 对于 Outlook 2007 和 Outlook 2003，调试按钮显示在 Outlook 资源管理器窗口的标准命令栏上。 
  
下表介绍了调试按钮。
  
|**"调试"按钮**|**Function**|
|:-----|:-----|
|同步联系人  <br/> |使 OSC 仅向 OSC 提供程序请求缓存的联系人。  <br/> |
|GAL 同步  <br/> |使 OSC 向 Outlook 联系人填充 Exchange 全局地址列表中的数据。  <br/> |
|类别缓存无效  <br/> |导致 OSC 在刷新活动源时重新加载每个存储的类别列表。  <br/> |
   
## <a name="fiddler"></a>Fiddler

Fiddler 是一款线路调试工具，用于检查从提供程序发送到社交网络的 API 调用，以及社交网络发送到提供程序的 XML。 Fiddler 可从 [Fiddler Web 调试代理 下载](https://www.fiddler2.com/fiddler2/version.asp)。
  
## <a name="see-also"></a>另请参阅

- [学习开发提供程序的快速步骤](quick-steps-for-learning-to-develop-a-provider.md)  
- [同步好友和活动](synchronizing-friends-and-activities.md) 
- [开发提供程序的最佳实践](best-practices-for-developing-a-provider.md)
- [OSC 典型调用序列](osc-typical-calling-sequences.md)  
- [使用 OSC XML 架构开发提供程序](developing-a-provider-with-the-osc-xml-schema.md)  
- [准备发布 OSC 提供程序](getting-ready-to-release-an-osc-provider.md)

