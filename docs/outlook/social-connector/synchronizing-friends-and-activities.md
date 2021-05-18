---
title: 同步好友和活动
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 6e91b765-a207-4d8c-8763-5d643ca4d0c0
description: osC Outlook Social Connector (OSC) 支持从社交网络显示有关联系人卡片或"联系人"窗格中Outlook的信息。 SharePoint支持SharePoint信息的服务器、Office工作区、Lync 客户端以及所有支持联系人卡片的客户端应用程序。
ms.openlocfilehash: 0d6881c5d596519422d01ca61a00b1a68e610f2c
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32329199"
---
# <a name="synchronizing-friends-and-activities"></a>同步好友和活动

osC Outlook Social Connector (OSC) 支持从社交网络显示有关联系人卡片或"联系人"窗格中Outlook的信息。 SharePoint支持SharePoint信息的服务器、Office工作区、Lync 客户端以及所有支持联系人卡片的客户端应用程序。
  
可以在 Office 应用程序中的协作方案中使用联系人卡片，详细了解要协作的人。 这些方案的示例包括 word 中的Outlook和共同创作文档。 单击联系人卡片 **的"** 新增功能"选项卡时，将显示此人的信息。 
  
The Outlook People Pane displays information about a person who can be a sender or recipient of an Outlook item you have selected. 每当在人员窗格中选择其他人或 Outlook 资源管理器中的另一个项目，或在检查器中打开 Outlook 项目时，Outlook Social Connector (OSC) 将刷新人员窗格。 
  
若要使联系人卡片或人员窗格显示选定人员的当前信息，OSC 会通过 OSC 提供程序和某种形式的缓存来同步这些信息。 此同步取决于安装在客户端计算机上的 OSC 提供程序、您通过其 OSC 提供程序登录的社交网络，以及这些社交网络的每个 OSC 提供程序支持的同步模式。
  
OSC 支持以不同方式同步好友、非好友和活动：缓存同步、按需同步和混合同步。 这些同步模式之间的主要区别是 OSC 存储数据的位置，即数据是位于用户的默认 Outlook 存储中的文件夹中，还是用户计算机的内存中。 在本主题中介绍的每种情况下，数据在刷新前的默认最短时间保留在文件夹或内存中。 在某些情况下，组策略可以自定义最短时间。 有关控制 OSC 行为的组策略详细信息，请参阅如何使用组策略管理[Outlook Social Connector。](https://support.microsoft.com/default.aspx?scid=kb%3Ben-US%3B2020103)
  
请注意，如果选定人员不是社交网络的成员，OSC 不会在联系人卡片或人员窗格中显示此人的任何人员或活动信息。
  
## <a name="cached-synchronization"></a>缓存同步

OSC 提供程序可以将社交网络上好友的信息存储在用户默认 Outlook 存储上的特定文件夹中，并定期在指定的时间长度到期后更新该缓存。 Caching文件夹中存储信息具有减少到社交网络的流量的优势。
  
> [!NOTE]
> 从 Outlook Social Connector 2013 开始，OSC 不再支持缓存的活动同步。 
  
### <a name="cached-synchronization-of-friends"></a>好友的缓存同步

如果 OSC 提供程序支持好友的缓存同步，OSC 将缓存社交网络上已登录用户的好友信息。 该信息缓存在用户的默认Outlook中特定于该社交网络的联系人Outlook文件夹中。 联系人文件夹名称基于社交网络的名称，OSC 通过使用 [ISocialProvider：：SocialNetworkName](isocialprovider-socialnetworkname.md) 属性获取该名称。 
  
在缓存同步中，OSC 仅存储已登录用户的好友在社交网络上的信息。 OSC 不访问非好友的信息。
  
OSC 从社交网络刷新好友信息的联系人文件夹的默认间隔为每天一次 (或每 1440 分钟一) 。 也可按组策略设置此刷新间隔，如本主题开头部分所讨论。
  
如果在刷新期间发生错误，OSC 将按 **contactSyncRestartInterval** 元素在功能 XML 中指定的间隔 **重试** 。 此重试间隔的默认值为 30 分钟，也可由组策略设置。 
  
当用户打开联系人卡片并选择"新增功能"选项卡时，"**新增功能"** 选项卡将刷新。 同样，当用户Outlook用户重新选择用户中的项目Outlook或重新选择人员窗格中的某个人员时，人员窗格将刷新。 如果缓存刷新间隔尚未过期，OSC 将转到缓存以获取所选用户的任何信息。 这可以避免使用 OSC 提供程序扩展性访问社交网络的开销。 如果刷新间隔已过期，OSC 将调用 [ISocialPerson：：GetFriendsAndColleagues](isocialperson-getfriendsandcolleagues.md) 方法来获取登录用户的当前好友信息，并更新联系人文件夹中的缓存。 
  
OSC 提供程序在功能 **XML** 中指定以下元素，以通知 OSC 它支持好友的缓存同步： 
  
- **getFriends**  = **true**
    
- **cacheFriends**  = **true**
    
- **dynamicContactsLookup**  = **false**
    
## <a name="on-demand-synchronization"></a>按需同步

当用户在联系人卡片中选择"新增功能"选项卡，或在 Outlook 的"人员"窗格中选择不同的 Outlook 项目或其他人员时，OSC 会分别刷新联系人卡片或人员窗格。 如果 OSC 提供程序支持人员或活动的按需同步，OSC 将与内存中的缓存同步，并更新联系人卡片或人员窗格中的详细信息，如姓名、标题、图片和活动流。 对于按需同步，与缓存同步不同，OSC 会尝试刷新该用户的信息，而不管该用户是社交网络上已登录用户的好友还是非好友。 
  
按需人员 (或) 数据存储在内存中。 当 Office 客户端应用程序关闭，或者用户导致刷新联系人卡片或人员窗格，并且数据在内存中的保持时间长于刷新间隔时，将清除内存中的数据。 请注意，从社交网络刷新始终由用户刷新联系人卡片或人员窗格（例如 (通过在人员窗格中选择其他用户或在 Outlook 资源管理器窗口) 中选择其他项目）启动。 

但是，反过来并不总是如此-并非每次刷新联系人卡片或人员窗格都会从社交网络刷新。 如果用户刷新联系人卡片或人员窗格，并且人员 (或活动) 数据在内存中的保持时间超过刷新间隔，OSC 将调用 [ISocialSession2：：GetPeopleDetails](isocialsession2-getpeopledetails.md) (或 [ISocialSession2：：GetActivitiesEx](isocialsession2-getactivitiesex.md)) 以从社交网络更新内存中的信息。 内存中的好友和非好友信息允许的时间段为 24 小时，活动允许的时间段为 30 分钟。 
  
缓存同步和按需同步之间的一个重要区别在于，按需同步可以提取网络上好友和非好友的人和活动信息。 如果所选人员不是好友，则 OSC 将刷新此人的信息和活动（如果满足以下任一要求）： 
  
- 人员是社交网络上的用户，并允许公开查看个人资料和活动信息。
    
- 该用户与该社交网络上的登录用户位于同一网络中 (例如，在同一网络中供大学) 。
    
人员与活动的按需同步导致从 OSC 核心引擎对提供程序进行更多调用。 社交网络必须能够处理按需同步增加的带宽要求。
  
### <a name="specifying-xml-elements-for-on-demand-synchronization"></a>指定 XML 元素进行按需同步

OSC 提供程序通过指定功能 **XML** 中的以下元素来通知 OSC 它支持好友和非好友的按需同步： 
  
- **getFriends**  = **true**
    
- **cacheFriends**  = **false**
    
- **dynamicContactsLookup**  = **true**
    
OSC 提供程序通过指定功能 XML 中的以下元素来通知 OSC 它支持 **按需同步** 活动： 
  
- **getActivities**  = **true**
    
- **cacheActivities**  = **false**
    
- **dynamicActivitiesLookupEx**  = **true**
    
## <a name="hybrid-synchronization"></a>混合同步

OSC 提供程序可以支持好友和非好友的混合同步。 这可优化 OSC 核心引擎和 OSC 提供程序之间的调用、对社交网络的呼叫（用于按需好友同步）以及好友数据的货币。 数据可在文件夹或内存中保留的最小时间（如果适用）与缓存或按需同步模式中的限制相同。
  
> [!NOTE]
> 从 Outlook Social Connector 2013 开始，OSC 仅支持按需同步活动，不再支持活动的混合同步。 
  
### <a name="hybrid-synchronization-of-friends-and-non-friends"></a>好友和非好友的混合同步

如果 OSC 提供程序支持好友和非好友的混合同步，OSC 将执行以下操作： 
  
- OSC 将登录用户的好友信息存储在特定于社交网络的联系人文件夹中。
    
- OSC 在内存中存储已登录用户的非好友的信息。
    
OSC 提供程序通过指定功能 XML 中的以下元素来通知 OSC 它支持好友和非好友的 **混合** 同步： 
  
- **getFriends**  = **true**
    
- **cacheFriends**  = **true**
    
- **dynamicContactsLookup**  = **true**
    
## <a name="synchronization-intervals"></a>同步间隔

下表总结了相应缓存 (文件夹或内存) 与社交网络之间的好友和非好友信息的同步间隔，具体取决于支持的同步模式。 对于混合同步模式，请引用好友的缓存模式的行，以及针对非好友的按需模式的行。
  
|**人员同步模式**|**设置刷新间隔时**|**刷新前的默认最短时间**|**组策略覆盖**|
|:-----|:-----|:-----|:-----|
|Cached  <br/> |在 OSC 内设置  <br/> |1440 分钟 (24 小时)   <br/> |Windows注册表值 **NetContactSyncInterval** <br/> |
|Cached  <br/> |功能 **XML****中的 contactSyncRestartInterval** 元素  <br/> |如果未设置 **contactSyncRestartInterval，** 则 30 分钟  <br/> |Windows注册表值 **contactSyncRestartInterval** <br/> |
|按需  <br/> |在 OSC 内设置  <br/> |1440 分钟 (24 小时)   <br/> |Windows注册表值 **OnlineSearchExpiryTime** <br/> |
   
下表总结了相应缓存 (文件夹或内存) 与社交网络之间好友和非好友活动的同步间隔，具体取决于支持的同步模式。 
  
|**活动的同步模式**|**设置刷新间隔时**|**刷新前的默认最短时间**|**组策略覆盖**|
|:-----|:-----|:-----|:-----|
|按需  <br/> |在 OSC 内设置  <br/> |30 分钟  <br/> |Windows注册表值 **OnlineSearchExpiryTime** <br/> |
   
以下信息适用于两Windows中列出的注册表值：
  
- 键：  `HKEY_CURRENT_USER\Software\Policies\Microsoft\Office\Outlook\SocialConnector`
    
- 值：介于 1 和 10080 之间的 DWORD 值
    
## <a name="see-also"></a>另请参阅

- [Capabilities XML 示例](capabilities-xml-example.md)  
- [功能的 XML](xml-for-capabilities.md)
- [使用 OSC XML 架构开发提供程序](developing-a-provider-with-the-osc-xml-schema.md)  
- [如何使用组策略Outlook社交连接器](https://support.microsoft.com/default.aspx?scid=kb%3Ben-US%3B2020103)

