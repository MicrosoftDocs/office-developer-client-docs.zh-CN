---
title: MAPI 配置文件
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 493c87a4-317d-47ec-850b-342cac59594b
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 7f241fde8aedeae9debc66f728ee21c1c6bed6fb
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776286"
---
# <a name="mapi-profiles"></a>MAPI 配置文件

  
  
**适用于**： Outlook 
  
一个配置文件存储有关服务提供商和消息服务的计算机上安装的信息。 对于每个会话，客户端登录时选择介绍要使用的提供程序和服务的一个配置文件。 客户端都可以选择配置文件的集合中，并如果需要，建立一个为默认值。 当客户端启动会话和未显式指定一个配置文件时自动选择的配置文件的默认配置文件。
  
此外在这些主题中，您将了解讨论昵称缓存，存储在二进制流。
  
- [别名缓存](nickname-cache.md)
    
- [自动完成流](autocomplete-stream.md)
    
- [分析的二进制文件](http://portalvhds6gyn3khqwmgzd.blob.core.windows.net/files/NK2/NK2WithBinaryExample.pdf)
    
## <a name="profile-sections"></a>配置文件节

配置文件可分为部分的客户端和服务提供商访问向用户显示配置文件属性，或进行配置更改。 配置文件部分是实现**IProfSect**接口的 MAPI 对象、 派生自**IMAPIProp** ，没有任何其他方法的接口。 有关详细信息，请参阅[IProfSect: IMAPIProp](iprofsectimapiprop.md)。 其唯一用途是操作配置文件节的属性。 若要检索到特定配置文件部分**IProfSect**指针，客户端和服务提供商，请调用以下方法。 
  
|||
|:-----|:-----|
|客户端可以调用：  <br/> |[IMAPISession::OpenProfileSection](imapisession-openprofilesection.md) <br/> |
|服务提供商可以呼叫：  <br/> |[IMAPISupport::OpenProfileSection](imapisupport-openprofilesection.md) <br/> |
|客户端或提供程序可以呼叫：  <br/> |[IProviderAdmin::OpenProfileSection](iprovideradmin-openprofilesection.md) <br/> |
   
配置文件分层组织得多 MAPISVC 类似。INF 文件。 在层次结构的顶部，有包含相关的配置文件信息的配置文件部分。 中间级别包括各节包含有关特定消息服务的信息和较低级别包括各节包含有关之一的消息服务的服务提供商信息。 
  
每个配置文件具有存储在一个或多个配置文件的节中的多个必需的属性。 例如，每个配置文件将具有**PR_PROFILE_NAME** ([PidTagProfileName](pidtagprofilename-canonical-property.md)) 和**PR_SEARCH_KEY** ([PidTagSearchKey](pidtagsearchkey-canonical-property.md)) 属性。 配置文件的搜索键设置为 MAPIGUID 中定义的值。作为 MUID_PROFILE_INSTANCE H，始终能保证所有配置文件中是唯一的。 尽管两个配置文件可以具有相同的名称，但他们不能具有相同的搜索键。 搜索键应视为二进制数据，而不是任何特定类型的数据。
  
消息存储提供程序所需的配置文件配置文件各节中包括其消息存储**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 属性和其消息存储提供程序并为保持同步这些条目。 时创建的消息存储、 提供程序设置**PR_DISPLAY_NAME**基于这些配置文件各节中存储的值。 
  
有配置文件部分和继承**IMAPIProp**其他对象的两个主要区别： 
  
- 配置文件部分不支持事务。
    
- 配置文件部分不支持命名的属性，返回 MAPI_E_NO_SUPPORT 从其**IMAPIProp::GetIDsFromNames**和**IMAPIProp::GetNamesFromIDs**实现。 有关详细信息，请参阅[IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md)和[IMAPIProp::GetNamesFromIDs](imapiprop-getnamesfromids.md)。
    
因为配置文件部分不支持事务，通过调用**IMAPIProp::CopyProps**，所做的任何更改**CopyTo**或**SetProps**立即生效。 有关详细信息，请参阅[IMAPIProp::CopyProps](imapiprop-copyprops.md)。 客户端和服务提供商可以调用配置文件节的**IMAPIProp::SaveChanges**方法和它会成功，但它不会影响的配置文件部分数据。 有关详细信息，请参阅[IMAPIProp::SaveChanges](imapiprop-savechanges.md)。 具有立即发生的更改会影响服务提供程序如何实现属性工作表的客户端用于向用户显示配置文件属性。 希望用户能够推迟或撤消更改的服务提供商必须实现其属性表与配置文件而不是实际的节的节的副本。 通过使用副本，用户可以进行更改，然后更高版本取消这些更改中，保留原始的配置文件部分不变。 
  
信息配置文件中的显示的顺序将影响 MAPI 如何配置资源和会话中进行工作分配。 下面的工作分配受 profile 顺序：
  
- 默认邮件存储区
    
- 个人通讯簿
    
- 默认消息存储搜索路径
    
- 默认通讯簿搜索路径
    
- 传输提供程序的顺序
    
MAPI 设置默认的邮件存储为具有其**PR_RESOURCE_FLAGS** ([PidTagResourceFlags](pidtagresourceflags-canonical-property.md)) 属性，指示它可以是默认存储中设置 STATUS_DEFAULT_STORE 标志的配置文件中的第一个邮件存储。 客户端可以通过调用**IMAPISession::SetDefaultStore**覆盖此设置。 有关详细信息，请参阅[IMAPISession::SetDefaultStore](imapisession-setdefaultstore.md)。
  
MAPI 创建用于处理传出和传入邮件传输顺序。 当多个传输提供程序已注册为特定类型的一条消息时，MAPI 将使用此顺序来确定哪些提供程序应处理邮件。 MAPI 设置传输顺序为其提供程序已添加到有一个例外-STATUS_XP_PREFER_LAST 标志设置其**PR_RESOURCE_FLAGS**属性中的传输配置文件传输的顺序的放置上次的顺序。 客户端可以通过调用**IMsgServiceAdmin::MsgServiceTransportOrder**设置传输顺序。 有关详细信息，请参阅[IMsgServiceAdmin::MsgServiceTransportOrder](imsgserviceadmin-msgservicetransportorder.md)。
  
排序服务提供商和消息服务这些准则有时可能会发生冲突。 如果没有冲突，则代码应解决冲突。 您可以使用邮件控制面板程序检查已创建以确定是否按预期方式已配置提供程序的配置文件。
  

