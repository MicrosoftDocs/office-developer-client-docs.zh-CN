---
title: 调试提供程序
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: d2dfaeed-7635-4c6b-9c35-b955ca1a85e9
description: '您可以通过多种方式来调试 Outlook Social Connector (.osc) 提供程序:'
ms.openlocfilehash: 39deb7b6c0b11460826bdbf1957ffd8404d926e5
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32281067"
---
# <a name="debugging-a-provider"></a>调试提供程序

您可以通过多种方式来调试 Outlook Social Connector (.osc) 提供程序: 
  
- 通过在 Outlook 或支持的 office 客户端应用程序的 office 熟知用户界面的功能区组件中使用调试命令, 可以使 .osc 执行各种操作。
    
- 通过使用 Fiddler 跟踪在社交网络及其 .osc 提供程序之间发送的 API 调用和 XML
    
## <a name="debug-buttons"></a>调试按钮

.osc 提供程序扩展性提供了调试 .osc 提供程序的功能。 若要调试提供程序, 请`DebugProviders`在注册表`SocialConnector`项下的 Windows 注册表中创建一个 DWORD 类型的值 (如下面的行所示), `DebugProviders`并将值设置为1。 
  
`HKEY_CURRENT_USER\Software\Microsoft\Office\Outlook\SocialConnector`
  
默认情况下, 提供程序调试处于关闭状态。 如果`DebugProviders`值不存在或存在, 并且设置为值 0, 则表示提供程序调试处于关闭状态。 
  
如果启用了提供程序调试, 则在发生错误时, .osc 将显示一个警报对话框, 其中包含详细错误信息, 并针对 .osc 提供程序 xml 架构验证任何 .osc 提供程序 xml。 根据为 XML 字符串指定的命名空间, 使用 .osc 1.0 开发的 .osc 提供程序将针对 .osc 1.0 架构文件 OutlookSocialProvider 进行验证。 使用 .osc 1.1 或更高版本开发的一个 .osc 提供程序针对架构文件 outlooksocialprovider_ 1.1 进行了验证。 使用此`DebugProviders`值时, 将对所有已加载的提供程序 (而不是特定的提供程序) 显示调试警报。 
  
若要显示可帮助您调试提供程序的调试按钮, 请`ShowDebugButtons`在注册表`SocialConnector`项下的 Windows 注册表中创建一个 DWORD 类型的值, `ShowDebugButtons`并将值设置为1。 若要隐藏调试命令栏按钮, 请将`ShowDebugButtons`该值设置为0。 
  
对于 Outlook 2010 和自 Office 2013 之后的客户端应用程序, "调试" 按钮将显示在浏览器功能区的 "**加载项**" 选项卡上。 对于 outlook 2007 和 outlook 2003, 调试按钮显示在 Outlook 资源管理器窗口的标准命令栏上。 
  
下表介绍了调试按钮。
  
|**调试按钮**|**Function**|
|:-----|:-----|
|同步联系人  <br/> |使 .osc 仅为缓存的联系人请求 .osc 提供程序。  <br/> |
|GAL 同步  <br/> |使 .osc 向 Outlook 联系人填充 Exchange 全局地址列表中的数据。  <br/> |
|使类别缓存无效  <br/> |使 .osc 在刷新活动源时重新加载每个存储的类别列表。  <br/> |
   
## <a name="fiddler"></a>Fiddler

Fiddler 是一种调试工具, 用于检查从提供商发送到社交网络的 API 调用, 以及由社交网络发送给提供程序的 XML。 Fiddler 可在[Fiddler Web 调试代理](https://www.fiddler2.com/fiddler2/version.asp)中进行下载。
  
## <a name="see-also"></a>另请参阅

- [学习开发提供程序的快速步骤](quick-steps-for-learning-to-develop-a-provider.md)  
- [同步好友和活动](synchronizing-friends-and-activities.md) 
- [开发提供程序的最佳实践](best-practices-for-developing-a-provider.md)
- [.osc 典型调用序列](osc-typical-calling-sequences.md)  
- [使用 .osc XML 架构开发提供程序](developing-a-provider-with-the-osc-xml-schema.md)  
- [准备发布一个 .osc 提供程序](getting-ready-to-release-an-osc-provider.md)

