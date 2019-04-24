---
title: 同步好友和活动
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 6e91b765-a207-4d8c-8763-5d643ca4d0c0
description: Outlook Social Connector (.osc) 支持显示关于联系人卡片或 Outlook 人员窗格中某个人的社交网络的信息。 sharepoint Server、sharepoint Workspace、Lync 客户端和所有支持状态信息的 Office 客户端应用程序都支持联系人卡片。
ms.openlocfilehash: 0d6881c5d596519422d01ca61a00b1a68e610f2c
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32329199"
---
# <a name="synchronizing-friends-and-activities"></a>同步好友和活动

Outlook Social Connector (.osc) 支持显示关于联系人卡片或 Outlook 人员窗格中某个人的社交网络的信息。 sharepoint Server、sharepoint Workspace、Lync 客户端和所有支持状态信息的 Office 客户端应用程序都支持联系人卡片。
  
您可以使用 Office 应用程序中的协作方案中的联系人卡片来查找有关要与之进行协作的人员的详细信息。 这些方案的示例包括在 Outlook 中进行消息传递以及在 Word 中共同创作文档。 当您单击联系人卡片的 "**新增功能**" 选项卡时, 将显示有关该人员的信息。 
  
"Outlook 人员" 窗格显示有关可以成为您选定的 Outlook 项目的发件人或收件人的人员的信息。 只要您在 "人员" 窗格或 Outlook 资源管理器中的其他项目中选择了其他人, 或者在检查器中打开 outlook 项目, outlook Social Connector (.osc) 就会刷新 "人员" 窗格。 
  
为使联系人卡片或人员窗格显示所选人员的当前信息, .osc 将通过 .osc 提供程序和某种形式的缓存同步此类信息。 此同步取决于客户端计算机上安装的 .osc 提供程序、通过其 .osc 提供程序登录的社交网络, 以及这些社交网络的每个 .osc 提供程序支持的同步模式。
  
.osc 支持以不同的方式同步朋友、非朋友和非朋友的活动: 缓存同步、按需同步和混合同步。 这些同步模式之间的主要区别在于, .osc 将数据存储在用户的默认 Outlook 存储区中的文件夹中, 或存储在用户计算机上的内存中。 在每种情况下, 如本主题中所述, 在刷新数据之前, 默认的最短时间将数据保留在文件夹或内存中。 在某些情况下, 可以通过组策略自定义最小时间量。 有关控制 .osc 行为的组策略的详细信息, 请参阅 how [to manage the Outlook Social Connector by using group Policy](https://support.microsoft.com/default.aspx?scid=kb%3Ben-US%3B2020103)。
  
请注意, 如果所选的用户不是社交网络的成员, 则该 .osc 不会在联系人卡片或人员窗格中显示该人员的任何人员或活动信息。
  
## <a name="cached-synchronization"></a>缓存同步

一个 .osc 提供程序可以在用户的默认 Outlook 存储区上的特定文件夹中的社交网络上的好友存储信息, 并在指定的时间长度到期后定期更新该缓存。 文件夹中的缓存信息具有减少到社交网络的流量的优势。
  
> [!NOTE]
> 从 Outlook Social Connector 2013 开始, .osc 不再支持活动的缓存同步。 
  
### <a name="cached-synchronization-of-friends"></a>已缓存的朋友同步

如果 .osc 提供商支持对好友的缓存同步, 则 .osc 会缓存社交网络中已登录用户的朋友的信息。 该信息缓存在特定于用户的默认 outlook 存储中的社交网络的 Outlook 联系人文件夹中。 "联系人" 文件夹名称基于您的 .osc 使用[ISocialProvider:: SocialNetworkName](isocialprovider-socialnetworkname.md)属性获取的社交网络的名称。 
  
在缓存的同步中, .osc 仅存储已登录用户在社交网络上的好友的信息。 .osc 不会访问非好友的信息。
  
在社交网络中刷新 "联系人" 文件夹中的好友信息的默认间隔为每天一次, 或每1440分钟一次。 此刷新间隔也可由组策略设置, 如本主题的开头部分所述。
  
如果刷新过程中出现错误, 则根据**功能**XML 中的**contactSyncRestartInterval**元素指定的时间间隔, 进行的 .osc 重试。 此重试间隔的默认值为30分钟, 也可以通过组策略进行设置。 
  
当用户打开联系人卡片并选择 "新增**功能**" 选项卡时, "新增**功能**" 选项卡会进行刷新。 同样, 当 outlook 用户在 outlook 或 reselects 中 reselects 某个人在 "人员" 窗格中时, "人员" 窗格将会刷新。 如果缓存刷新间隔尚未过期, 则 .osc 将转到缓存以获取所选用户的任何信息。 这样可以避免使用 .osc 提供商扩展性访问社交网络的开销。 如果刷新间隔已过期, 则 .osc 将调用[ISocialPerson:: GetFriendsAndColleagues](isocialperson-getfriendsandcolleagues.md)方法获取已登录用户的当前朋友的信息, 并更新 "联系人" 文件夹中的缓存。 
  
通过在**功能**XML 中指定以下元素, .osc 提供商通知 .osc 它支持朋友的缓存同步: 
  
- **getFriends** = **true**
    
- **cacheFriends** = **true**
    
- **dynamicContactsLookup** = **false**
    
## <a name="on-demand-synchronization"></a>按需同步

当用户选择联系人卡片中的 "新增**功能**" 选项卡, 或在 outlook 的 "人员" 窗格中选择不同的 outlook 项目或其他人时, 该 .osc 将分别刷新 "联系人卡片" 或 "人员" 窗格。 如果 .osc 提供商支持人员或活动的按需同步, 则 .osc 将与内存中的缓存同步, 并在 "联系人卡片" 或 "人员" 窗格上更新详细信息, 如姓名、职务、图片和活动流。 对于按需同步, 与缓存同步不同, .osc 将尝试刷新人员的信息, 而不考虑此人是社交网络上已登录用户的朋友还是非朋友。 
  
只需人员 (或活动) 数据仅存储在内存中。 当 Office 客户端应用程序关闭时, 内存中的数据将被清除, 或者用户会刷新联系人卡片或人员窗格, 并且数据在内存中保留的时间超过刷新间隔。 请注意, 从社交网络刷新的始终是由用户刷新联系人卡片或人员窗格 (例如, 通过在 "人员" 窗格中选择其他用户, 或在 Outlook 资源管理器窗口中选择其他项目) 启动的。 

但是, 反之亦然并不总是 true —不是每个联系人卡片或人员窗格的刷新都会导致来自社交网络的刷新。 如果用户刷新联系人卡片或 "人员" 窗格, 并且人员 (或活动) 数据在内存中保留的时间超过了刷新间隔, 则 .osc 调用[ISocialSession2:: GetPeopleDetails](isocialsession2-getpeopledetails.md) (或[ISocialSession2:: GetActivitiesEx](isocialsession2-getactivitiesex.md)) 以从社交网络更新内存中的信息。 在内存中, 友元和非友元信息允许的持续时间为24小时, 活动时间为30分钟。 
  
缓存和按需同步的一个重要区别是, 按需同步可以为网络上的好友和非朋友获取人员和活动信息。 如果所选的用户是非朋友, 则如果满足以下任一要求, 则 .osc 将刷新该人员的信息和活动: 
  
- 此人是社交网络上的用户, 允许对配置文件和活动信息进行公开查看。
    
- 此人与社交网络上的登录用户位于同一网络中 (例如, 在同一网络中, 在大学校友中)。
    
按需同步人员和活动将导致来自 .osc 核心引擎的对提供程序的更多调用。 社交网络必须能够处理按需同步增加的带宽要求。
  
### <a name="specifying-xml-elements-for-on-demand-synchronization"></a>指定用于按需同步的 XML 元素

通过在**功能**XML 中指定以下元素, .osc 提供商通知 .osc 它支持对朋友和非好友的按需同步: 
  
- **getFriends** = **true**
    
- **cacheFriends** = **false**
    
- **dynamicContactsLookup** = **true**
    
.osc 提供程序通过在**功能**XML 中指定以下元素来通知 .osc 它支持对活动的按需同步: 
  
- **getActivities** = **true**
    
- **cacheActivities** = **false**
    
- **dynamicActivitiesLookupEx** = **true**
    
## <a name="hybrid-synchronization"></a>混合同步

一个 .osc 提供商可以支持朋友和非好友的混合同步。 这可以优化来自 .osc 核心引擎和 .osc 提供程序的调用、对社交网络的调用, 以实现按需同步的友元, 以及朋友数据的货币。 数据可以保留在文件夹或内存中的最小时间 (如果适用) 与缓存或按需同步模式中的限制相同。
  
> [!NOTE]
> 从 Outlook Social Connector 2013 开始, 该 .osc 仅支持对活动的按需同步, 不再支持活动的混合同步。 
  
### <a name="hybrid-synchronization-of-friends-and-non-friends"></a>朋友和非好友的混合同步

如果 .osc 提供商支持朋友和非好友的混合同步, 则 .osc 将执行以下操作: 
  
- .osc 存储有关特定于社交网络的联系人文件夹中登录用户的好友信息。
    
- .osc 将登录用户的非好友信息存储在内存中。
    
通过在**功能**XML 中指定以下元素, .osc 提供商通知 .osc 它支持朋友和非好友的混合同步: 
  
- **getFriends** = **true**
    
- **cacheFriends** = **true**
    
- **dynamicContactsLookup** = **true**
    
## <a name="synchronization-intervals"></a>同步间隔

下表汇总了在相应的缓存 (文件夹或内存) 与社交网络之间的朋友和非好友信息的同步间隔, 具体取决于受支持的同步模式。 对于混合同步模式, 请参阅适用于好友的缓存模式行, 以及非好友的点播模式行。
  
|**人员的同步模式**|**设置刷新间隔的位置**|**刷新前的默认最短时间**|**组策略替代**|
|:-----|:-----|:-----|:-----|
|Cached  <br/> |在 .osc 中设置  <br/> |1440分钟 (24 小时)  <br/> |Windows 注册表值**NetContactSyncInterval** <br/> |
|Cached  <br/> |**功能**XML 中的**contactSyncRestartInterval**元素  <br/> |如果未设置**contactSyncRestartInterval** , 则为30分钟  <br/> |Windows 注册表值**contactSyncRestartInterval** <br/> |
|按需  <br/> |在 .osc 中设置  <br/> |1440分钟 (24 小时)  <br/> |Windows 注册表值**OnlineSearchExpiryTime** <br/> |
   
下表汇总了在相应的缓存 (文件夹或内存) 与社交网络之间的好友活动和非好友活动的同步间隔, 具体取决于受支持的同步模式。 
  
|**活动的同步模式**|**设置刷新间隔的位置**|**刷新前的默认最短时间**|**组策略替代**|
|:-----|:-----|:-----|:-----|
|按需  <br/> |在 .osc 中设置  <br/> |30 分钟  <br/> |Windows 注册表值**OnlineSearchExpiryTime** <br/> |
   
以下信息适用于这两个表中列出的 Windows 注册表值:
  
- 主键`HKEY_CURRENT_USER\Software\Policies\Microsoft\Office\Outlook\SocialConnector`
    
- 值: 介于1和10080之间的 DWORD 值
    
## <a name="see-also"></a>另请参阅

- [功能 XML 示例](capabilities-xml-example.md)  
- [XML 的功能](xml-for-capabilities.md)
- [使用 .osc XML 架构开发提供程序](developing-a-provider-with-the-osc-xml-schema.md)  
- [如何: 使用组策略管理 Outlook Social Connector](https://support.microsoft.com/default.aspx?scid=kb%3Ben-US%3B2020103)

