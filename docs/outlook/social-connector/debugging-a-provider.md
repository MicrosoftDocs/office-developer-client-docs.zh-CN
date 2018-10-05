---
title: 调试提供程序
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: d2dfaeed-7635-4c6b-9c35-b955ca1a85e9
description: 有几种方法可以调试的 Outlook Social Connector (OSC) 提供程序：
ms.openlocfilehash: 39deb7b6c0b11460826bdbf1957ffd8404d926e5
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25386850"
---
# <a name="debugging-a-provider"></a>调试提供程序

有几种方法可以调试的 Outlook Social Connector (OSC) 提供程序： 
  
- 通过使用 Outlook 或支持的 Office 客户端应用程序中的 Office Fluent 用户界面的功能区组件中调试命令导致 OSC 各种操作。
    
- 使用 Fiddler 跟踪 API 调用和社交网络和其 OSC 提供程序之间发送的 XML
    
## <a name="debug-buttons"></a>调试按钮

OSC 提供程序扩展性提供的调试 OSC 提供程序的功能。 若要调试提供程序，创建`DebugProviders`的值在 Windows 注册表中键入 DWORD`SocialConnector`键 （如下面的行所示），并设置`DebugProviders`值设置为 1。 
  
`HKEY_CURRENT_USER\Software\Microsoft\Office\Outlook\SocialConnector`
  
默认情况下，提供程序调试处于关闭状态。 如果`DebugProviders`值不存在，或存在但处于关闭状态设置为值为 0，调试提供程序。 
  
如果已启用调试提供程序，OSC 将显示详细错误信息警报对话框时出错，发生此事件，并验证 OSC 提供程序的 XML 架构针对任何 OSC 提供程序 XML。 基于指定的 XML 字符串的命名空间，针对 OSC 1.0 架构文件，OutlookSocialProvider.xsd 验证使用 OSC 1.0 开发 OSC 提供程序。 OSC 提供程序开发使用 OSC 1.1 或更高版本的架构文件，OutlookSocialProvider_1.1.xsd 针对验证。 当您使用`DebugProviders`值，为所有已加载的提供程序，而不是特定提供程序将出现调试通知。 
  
若要显示可帮助您调试提供程序的调试按钮，创建`ShowDebugButtons`的值在 Windows 注册表中键入 DWORD`SocialConnector`键，并设置`ShowDebugButtons`值设置为 1。 若要隐藏调试命令栏按钮，将`ShowDebugButtons`为 0 的值。 
  
有关 Outlook 2010 和相 Office 2013 的客户端应用程序，调试按钮显示在资源管理器功能区的**加载项**选项卡上。 对于 Outlook 2007 和 Outlook 2003，调试按钮显示在 Outlook 资源管理器窗口的标准命令栏上。 
  
下表介绍调试按钮。
  
|**调试按钮**|**函数**|
|:-----|:-----|
|同步联系人  <br/> |使 OSC 寻求仅缓存联系人 OSC 提供程序。  <br/> |
|GAL 同步  <br/> |使 OSC 填充到 Outlook 联系人从 Exchange 全球通讯簿数据。  <br/> |
|使无效类别缓存  <br/> |使 OSC 时刷新活动源重新加载类别列表中的每个存储区。  <br/> |
   
## <a name="fiddler"></a>Fiddler

Fiddler 是线上调试工具检查的 API 调用从您的提供商发送到社交网络和社交网络发送到您的提供程序的 XML。 Fiddler 仅供以下位置下载： [Fiddler Web 调试代理](https://www.fiddler2.com/fiddler2/version.asp)。
  
## <a name="see-also"></a>另请参阅

- [快速学习开发提供程序的步骤](quick-steps-for-learning-to-develop-a-provider.md)  
- [同步朋友和活动](synchronizing-friends-and-activities.md) 
- [开发提供程序的最佳做法](best-practices-for-developing-a-provider.md)
- [OSC 典型调用序列 （英文)](osc-typical-calling-sequences.md)  
- [开发 OSC XML 架构的提供程序](developing-a-provider-with-the-osc-xml-schema.md)  
- [准备发布 OSC 提供程序](getting-ready-to-release-an-osc-provider.md)

