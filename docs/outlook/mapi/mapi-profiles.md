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
ms.openlocfilehash: 9db1f8e163e44a44df1e798cebccb3639325275e
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32340080"
---
# <a name="mapi-profiles"></a>MAPI 配置文件

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
配置文件存储有关计算机上安装的服务提供商和邮件服务的信息。 对于每个会话，登录时客户端都会选择一个描述要使用的提供程序和服务的配置文件。 客户端可以从配置文件集合中选择，如果需要，将一个配置文件设置为默认值。 默认配置文件是在客户端启动会话时自动选择的配置文件，并且尚未显式指定配置文件。
  
此外，在这些主题中，你将找到有关昵称缓存的讨论，该缓存存储在二进制流中。
  
- [别名缓存](nickname-cache.md)
    
- [自动完成 Stream](autocomplete-stream.md)
    
- [二进制文件分析](https://portalvhds6gyn3khqwmgzd.blob.core.windows.net/files/NK2/NK2WithBinaryExample.pdf)
    
## <a name="profile-sections"></a>配置文件节

配置文件分为多个部分，客户端和服务提供商访问这些部分向用户显示配置文件属性或更改配置。 配置文件节是一个实现 **IProfSect** 接口的 MAPI 对象，它是一个派生自 **IMAPIProp** 且没有其他方法的接口。 有关详细信息，请参阅 [IProfSect ： IMAPIProp](iprofsectimapiprop.md)。 它的唯一用途是操作配置文件节的属性。 若要检索指向特定配置文件节的 **IProfSect** 指针，客户端和服务提供商将调用以下方法。 
  
|||
|:-----|:-----|
|客户端可以调用：  <br/> |[IMAPISession::OpenProfileSection](imapisession-openprofilesection.md) <br/> |
|服务提供商可以调用：  <br/> |[IMAPISupport::OpenProfileSection](imapisupport-openprofilesection.md) <br/> |
|客户端或提供程序可以调用：  <br/> |[IProviderAdmin::OpenProfileSection](iprovideradmin-openprofilesection.md) <br/> |
   
配置文件按层次结构进行组织，与 MAPISVC 非常类似。INF 文件。 在层次结构的顶部，有一些配置文件部分包含与配置文件有关的信息。 中间级别包括包含有关特定邮件服务的信息的部分，而较低级别包括包含有关邮件服务中某个服务提供程序的信息的节。 
  
每个配置文件具有多个必需属性，这些属性存储在配置文件的一个或多个部分中。 例如，每个配置文件都有 PR_PROFILE_NAME  ([PidTagProfileName](pidtagprofilename-canonical-property.md)) 和 **PR_SEARCH_KEY** ([PidTagSearchKey](pidtagsearchkey-canonical-property.md)) 属性。 配置文件的搜索键设置为 MAPIGUID 中定义的值。H 作为MUID_PROFILE_INSTANCE，并且始终保证在所有配置文件中是唯一的。 尽管两个配置文件可以具有相同的名称，但是它们不能具有相同的搜索键。 搜索键应视为二进制数据，而不是任何特定类型的数据。
  
邮件存储提供程序需要将邮件存储的 **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 属性包括在配置文件及其邮件存储提供程序的配置文件部分中，并保持这些条目同步。 创建邮件存储时，提供程序PR_DISPLAY_NAME配置文件部分中存储的值设置邮件存储。 
  
配置文件部分与继承自 **IMAPIProp** 的其他对象之间存在两个主要区别： 
  
- 配置文件节不支持事务。
    
- 配置文件节不支持命名属性，它们MAPI_E_NO_SUPPORT **IMAPIProp：：GetIDsFromNames** 和 **IMAPIProp：：GetNamesFromIDs** 实现返回属性。 有关详细信息，请参阅 [IMAPIProp：：GetIDsFromNames](imapiprop-getidsfromnames.md) 和 [IMAPIProp：：GetNamesFromIDs](imapiprop-getnamesfromids.md)。
    
由于配置文件节不支持事务，因此通过调用 **IMAPIProp：：CopyProps、CopyTo** 或 **SetProps** 进行的任何更改将立即生效。 有关详细信息，请参阅 [IMAPIProp：：CopyProps](imapiprop-copyprops.md)。 客户端和服务提供商可以调用配置文件节的 **IMAPIProp：：SaveChanges** 方法，该方法将成功，但不会影响配置文件节数据。 有关详细信息，请参阅 [IMAPIProp：：SaveChanges](imapiprop-savechanges.md)。 立即进行更改可能会影响服务提供商实现客户端用于向用户显示配置文件属性的属性表。 希望用户能够推迟或撤消更改的服务提供商必须使用配置文件节的副本（而不是实际节）来实现其属性表。 通过使用副本，用户可以进行更改，然后取消这些更改，使原始配置文件部分保持不变。 
  
信息在配置文件中的显示顺序会影响 MAPI 在会话中配置资源和进行分配方式。 以下分配受配置文件顺序影响：
  
- 默认邮件存储
    
- 个人通讯簿
    
- 默认邮件存储搜索路径
    
- 默认通讯簿搜索路径
    
- 传输提供程序顺序
    
MAPI 将默认邮件存储设置为配置文件中第一个邮件存储，该存储的 PR_RESOURCE_FLAGS ([PidTagResourceFlags](pidtagresourceflags-canonical-property.md)) 属性中设置了 **STATUS_DEFAULT_STORE** 标志，指示它可以是默认存储。 客户端可以通过调用 **IMAPISession：：SetDefaultStore 覆盖此设置**。 有关详细信息，请参阅 [IMAPISession：：SetDefaultStore](imapisession-setdefaultstore.md)。
  
MAPI 创建用于处理传出和传入邮件的传输顺序。 当多个传输提供程序为特定类型的邮件注册时，MAPI 将按此顺序确定哪个提供程序应处理该邮件。 MAPI 将传输顺序设置为将传输提供程序添加到配置文件中的顺序，但一个例外是，在 **PR_RESOURCE_FLAGS** 属性中设置 STATUS_XP_PREFER_LAST 标志的传输将按顺序最后放置。 客户端可以通过调用 **IMsgServiceAdmin：：MsgServiceTransportOrder 来设置传输顺序**。 有关详细信息，请参阅 [IMsgServiceAdmin：：MsgServiceTransportOrder](imsgserviceadmin-msgservicetransportorder.md)。
  
这些排序服务提供程序和邮件服务的准则有时可能会发生冲突。 如果存在冲突，代码应解决冲突。 可以使用邮件控制面板程序检查已创建的配置文件，以确定是否已根据预期配置提供程序。
  

