---
title: 同步好友和活动
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 6e91b765-a207-4d8c-8763-5d643ca4d0c0
description: 在联系人卡片或 Outlook 人员窗格中，Outlook Social Connector (OSC) 支持从社交网络有关联系人的显示信息。 SharePoint Server、 SharePoint Workspace，Lync 客户端和所有 Office 客户端应用程序支持的状态信息的支持联系人卡片。
ms.openlocfilehash: 0d6881c5d596519422d01ca61a00b1a68e610f2c
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25399156"
---
# <a name="synchronizing-friends-and-activities"></a>同步好友和活动

在联系人卡片或 Outlook 人员窗格中，Outlook Social Connector (OSC) 支持从社交网络有关联系人的显示信息。 SharePoint Server、 SharePoint Workspace，Lync 客户端和所有 Office 客户端应用程序支持的状态信息的支持联系人卡片。
  
您可以使用 Office 应用程序中的协作方案中的联系人卡片以找出有关正在与协作的人员的详细信息。 这些方案的示例包括在 Outlook 中消息和 Word 中的文档的共同创作。 当您单击**新增**选项卡的联系人卡片中，此人的显示信息。 
  
Outlook 人员窗格显示有关可以是发件人或收件人的所选 Outlook 项目的某个人的信息。 每当您选择人员窗格或在 Outlook 资源管理器，另一个项目中的其他人或在检查器中打开 Outlook 项目，则 Outlook Social Connector (OSC) 刷新人员窗格。 
  
为要显示当前所选人员信息的联系人卡片或人员窗格，OSC 将通过 OSC 提供程序和某种形式的缓存此类信息同步。 此同步取决于客户端计算机安装的 OSC 提供程序、 社交网络您已登录到其 OSC 提供程序和每个 OSC 提供程序这些社交网络支持同步模式。
  
OSC 支持同步朋友、 非朋友和活动朋友和非朋友不同的方式： 缓存同步、 按需同步和混合同步。 之间同步这些模式的主要区别是 OSC 存储数据的位置 — 是否处于中用户的默认 Outlook 存储，或在用户的计算机上的内存中的文件夹。 在每种情况下本主题中所述没有数据仍保留在文件夹或内存刷新数据之前将默认最短时间。 在某些情况下，可以通过组策略自定义的最小时间量。 有关组策略对 OSC 行为进行控制的详细信息，请参阅[如何管理 Outlook Social Connector 使用组策略](https://support.microsoft.com/default.aspx?scid=kb%3Ben-US%3B2020103)。
  
请注意，是否所选的人员不是社交网络的成员，OSC 不显示任何人或活动信息的人员的联系人卡片或人员窗格中。
  
## <a name="cached-synchronization"></a>高速缓存的同步

OSC 提供程序可以在用户的默认 Outlook 存储上的特定文件夹中的社交网络存储信息朋友和过期指定的时间长度之后定期更新该缓存。 缓存文件夹中的信息的优点的减少到社交网络流量。
  
> [!NOTE]
> Outlook Social Connector 2013 中启动 OSC 不再支持活动缓存的的同步。 
  
### <a name="cached-synchronization-of-friends"></a>朋友的缓存的同步

如果 OSC 提供程序支持用于朋友缓存的同步，OSC 缓存社交网络上朋友登录用户的信息。 在 Outlook 联系人文件夹的特定于用户的默认 Outlook 存储区中的社交网络中会缓存信息。 联系人文件夹名基于使用[ISocialProvider::SocialNetworkName](isocialprovider-socialnetworkname.md)属性来获取 OSC 的社交网络的名称。 
  
在缓存同步 OSC 社交网络上存储的仅登录用户的好友的信息。 OSC 不会访问非朋友信息。
  
OSC 后，刷新的从社交网络的朋友的信息联系人文件夹的默认时间间隔为每天一次 （或 1440 分钟一次）。 如下所述，本主题的开头，则还可以通过组策略设置此刷新间隔。
  
如果刷新期间发生错误，OSC 重试**contactSyncRestartInterval**元素的**功能**XML 中指定的时间间隔。 此重试时间间隔的默认值为 30 分钟，和也可通过组策略设置。 
  
当用户打开联系人卡片，并选择**新增**选项卡时，刷新**新增**选项卡。 同样，当 Outlook 用户 reselects Outlook 中的项目或 reselects 人员窗格上的人员，则刷新人员窗格。 如果未过期缓存刷新间隔，OSC 转到缓存以获取所选用户的任何信息。 这可以避免使用 OSC 提供程序扩展性访问社交网络的开销。 如果刷新间隔时间已过期，OSC 调用[ISocialPerson::GetFriendsAndColleagues](isocialperson-getfriendsandcolleagues.md)方法来获取对登录用户的当前朋友的信息，并更新联系人文件夹中的缓存。 
  
OSC 提供程序通知 OSC 它支持缓存的同步朋友通过**功能**XML 中指定以下元素： 
  
- **getFriends** = **，则返回 true**
    
- **cacheFriends** = **，则返回 true**
    
- **dynamicContactsLookup** = **false**
    
## <a name="on-demand-synchronization"></a>按需同步

当用户在联系人卡片中，选择**新增**选项卡，或在 Outlook 中的人员窗格中选择一个不同的 Outlook 项目或另一个人时，OSC 刷新的联系人卡片或人员窗格分别。 如果 OSC 提供程序支持的人员或活动的按需同步，OSC 与在内存中，缓存同步，并更新详细信息，例如名称、 标题、 图片和活动流，在联系人卡片或人员窗格。 按需同步，与缓存同步不同 OSC 尝试刷新无论其是否朋友或非朋友社交网络上的登录用户的人员的信息。 
  
点播人 （或活动） 数据存储在仅限内存中。 Office 客户端应用程序已关闭，或用户会刷新的联系人卡片或人员窗格和停留的时间会超过刷新间隔时间的内存中的数据时，为清除状态内存中的数据。 请注意与社交网络刷新总是由用户 （例如，通过在人员窗格中，选择不同的用户或在 Outlook 资源管理器窗口中选择不同的项目） 刷新的联系人卡片或人员窗格。 

但是，反向并不总是 true — 不是每个刷新的联系人卡片或人员窗格一定会导致从社交网络刷新。 OSC 到如果用户刷新联系人卡片或人员窗格和个人 （或活动） 数据一直超过刷新间隔为在内存中，调用[ISocialSession2::GetPeopleDetails](isocialsession2-getpeopledetails.md) （或[ISocialSession2::GetActivitiesEx](isocialsession2-getactivitiesex.md)）更新社交网络从内存中的信息。 在内存中的好朋友和非朋友信息的允许的段为 24 小时数，以及活动，30 分钟。 
  
缓存和按需同步的一个重要区别是按需同步可以在网络上朋友和非朋友提取了人和活动的信息。 如果所选的人员，非朋友 OSC 刷新信息和活动的人员如果满足下列要求之一： 
  
- 人员是社交网络上的用户，并允许查看公共配置文件和活动的信息。
    
- 此人位于相同的网络上的社交网络 （例如，在同一网络上的大学校友） 登录的用户。
    
OSC 核心引擎从多个调用提供程序生成的人员和活动的按需同步。 社交网络必须能够处理增加的带宽要求的按需同步。
  
### <a name="specifying-xml-elements-for-on-demand-synchronization"></a>指定 XML 元素的按需同步

OSC 提供程序通知 OSC 它支持通过**功能**XML 中指定以下元素按需同步朋友和非朋友组成： 
  
- **getFriends** = **，则返回 true**
    
- **cacheFriends** = **false**
    
- **dynamicContactsLookup** = **，则返回 true**
    
OSC 提供程序通知 OSC 它支持按需活动同步通过**功能**XML 中指定以下元素： 
  
- **getActivities** = **，则返回 true**
    
- **cacheActivities** = **false**
    
- **dynamicActivitiesLookupEx** = **，则返回 true**
    
## <a name="hybrid-synchronization"></a>混合同步

OSC 提供程序可以支持混合同步朋友和非朋友。 这可以优化之间 OSC 核心引擎和 OSC 提供程序，到社交网络中的按需同步朋友和朋友的数据的货币呼叫的呼叫。 在缓存或按需同步模式下的限制相同数据可以保持在文件夹或内存中，如果适用的最短时间。
  
> [!NOTE]
> Outlook Social Connector 2013 中启动 OSC 支持仅按需同步的活动，不再支持混合同步的活动。 
  
### <a name="hybrid-synchronization-of-friends-and-non-friends"></a>朋友和非朋友的混合同步

如果 OSC 提供程序支持的朋友和非朋友混合同步，OSC 执行以下任务： 
  
- OSC 社交网络特定联系人文件夹中存储的朋友登录用户的信息。
    
- OSC 存储在内存中的非朋友登录用户的信息。
    
OSC 提供程序通知 OSC 它支持通过**功能**XML 中指定以下元素的朋友混合同步和非朋友组成： 
  
- **getFriends** = **，则返回 true**
    
- **cacheFriends** = **，则返回 true**
    
- **dynamicContactsLookup** = **，则返回 true**
    
## <a name="synchronization-intervals"></a>同步间隔

下表总结了朋友和非好友信息 （文件夹或内存） 的相应缓存和社交网络，具体取决于支持的同步模式之间的同步间隔。 对于混合同步模式，请参阅朋友缓存模式的行和非朋友点播模式的行。
  
|**人员的同步模式**|**其中设置刷新间隔**|**默认刷新前的最短时间**|**组策略覆盖**|
|:-----|:-----|:-----|:-----|
|Cached  <br/> |OSC 中设置  <br/> |1440 分钟 （24 小时）  <br/> |Windows 注册表值**NetContactSyncInterval** <br/> |
|Cached  <br/> |**功能**XML 中的**contactSyncRestartInterval**元素  <br/> |如果未设置**contactSyncRestartInterval** 30 分钟  <br/> |Windows 注册表值**contactSyncRestartInterval** <br/> |
|按需  <br/> |OSC 中设置  <br/> |1440 分钟 （24 小时）  <br/> |Windows 注册表值**OnlineSearchExpiryTime** <br/> |
   
下表总结了好友的活动和非朋友相应缓存 （文件夹或内存） 和社交网络，具体取决于支持的同步模式之间的同步间隔。 
  
|**活动的同步模式**|**其中设置刷新间隔**|**默认刷新前的最短时间**|**组策略覆盖**|
|:-----|:-----|:-----|:-----|
|按需  <br/> |OSC 中设置  <br/> |30 分钟  <br/> |Windows 注册表值**OnlineSearchExpiryTime** <br/> |
   
以下信息适用于两个表中列出的 Windows 注册表值：
  
- 键：`HKEY_CURRENT_USER\Software\Policies\Microsoft\Office\Outlook\SocialConnector`
    
- 1 和 10080 之间的值： DWORD 值
    
## <a name="see-also"></a>另请参阅

- [功能 XML 示例](capabilities-xml-example.md)  
- [功能 XML](xml-for-capabilities.md)
- [开发 OSC XML 架构的提供程序](developing-a-provider-with-the-osc-xml-schema.md)  
- [如何使用组策略管理 Outlook Social Connector](https://support.microsoft.com/default.aspx?scid=kb%3Ben-US%3B2020103)

