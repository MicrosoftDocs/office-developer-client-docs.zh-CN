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
  
配置文件存储有关安装在计算机上的服务提供程序和邮件服务的信息。 对于每个会话, 登录时客户端将选择一个描述要使用的提供程序和服务的配置文件。 客户端可以从一组配置文件中进行选择, 如果需要, 则将其设置为默认值。 默认配置文件是在客户端启动会话且未显式指定配置文件时自动选择的配置文件。
  
此外, 在这些主题中, 您将找到昵称缓存的讨论, 它存储在二进制流中。
  
- [别名缓存](nickname-cache.md)
    
- [自动完成流](autocomplete-stream.md)
    
- [二进制文件分析](https://portalvhds6gyn3khqwmgzd.blob.core.windows.net/files/NK2/NK2WithBinaryExample.pdf)
    
## <a name="profile-sections"></a>配置文件节

配置文件分为几个部分, 客户端和服务提供程序可以访问它们, 以向用户显示配置文件属性或进行配置更改。 profile 节是一个 MAPI 对象, 该对象实现**IProfSect**接口, 该接口是从**IMAPIProp**派生的接口, 没有其他方法。 有关详细信息, 请参阅[IProfSect: IMAPIProp](iprofsectimapiprop.md)。 它的唯一用途是操作 profile 节的属性。 若要检索指向特定配置文件部分的**IProfSect**指针, 客户端和服务提供程序将调用以下方法。 
  
|||
|:-----|:-----|
|客户端可以调用:  <br/> |[IMAPISession::OpenProfileSection](imapisession-openprofilesection.md) <br/> |
|服务提供商可以调用:  <br/> |[IMAPISupport::OpenProfileSection](imapisupport-openprofilesection.md) <br/> |
|客户端或提供程序可以调用:  <br/> |[IProviderAdmin::OpenProfileSection](iprovideradmin-openprofilesection.md) <br/> |
   
配置文件的组织方式与 mapisvc.inf 的组织结构非常相似。INF 文件。 在层次结构的顶部, 存在包含与配置文件相关的信息的配置文件部分。 中间级别包括包含有关特定邮件服务的信息的部分和更低级别的部分, 其中包含有关邮件服务中的某个服务提供程序的信息的部分。 
  
每个配置文件都有多个必需属性, 这些属性存储在配置文件的一个或多个部分中。 例如, 每个配置文件都具有**PR_PROFILE_NAME** ([PidTagProfileName](pidtagprofilename-canonical-property.md)) 和**PR_SEARCH_KEY** ([PidTagSearchKey](pidtagsearchkey-canonical-property.md)) 属性。 配置文件的搜索键设置为在 MAPIGUID 中定义的值。H as MUID_PROFILE_INSTANCE, 并且始终保证在所有配置文件中都是唯一的。 虽然两个配置文件可以具有相同的名称, 但它们不能具有相同的搜索关键字。 应将搜索关键字视为二进制数据, 而不是任何特定类型的数据。
  
邮件存储提供程序需要将其邮件存储区的**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 属性包括在配置文件的配置文件部分以及它们的邮件存储提供程序中, 以使这些条目保持同步。 创建邮件存储区时, 提供程序将根据存储在这些配置文件节中的值设置**PR_DISPLAY_NAME** 。 
  
从**IMAPIProp**继承的配置文件节和其他对象之间有两个主要区别: 
  
- 配置文件分区不支持事务。
    
- 配置文件节不支持命名属性, 从其**IMAPIProp:: GetIDsFromNames**和**IMAPIProp:: GetNamesFromIDs**实现中返回 MAPI_E_NO_SUPPORT。 有关详细信息, 请参阅[IMAPIProp:: GetIDsFromNames](imapiprop-getidsfromnames.md)和[IMAPIProp:: GetNamesFromIDs](imapiprop-getnamesfromids.md)。
    
由于配置文件节不支持事务, 因此对**IMAPIProp:: CopyProps**、 **CopyTo**或**SetProps**的调用所做的任何更改都将立即生效。 有关详细信息, 请参阅[IMAPIProp:: CopyProps](imapiprop-copyprops.md)。 客户端和服务提供程序可以调用 profile 节的**IMAPIProp:: SaveChanges**方法, 它将会成功, 但不会影响配置文件节数据。 有关详细信息, 请参阅[IMAPIProp:: SaveChanges](imapiprop-savechanges.md)。 如果立即进行更改, 则可能会影响服务提供程序实现客户端用来向用户显示配置文件属性的属性表的方式。 希望用户能够推迟或撤消更改的服务提供程序必须使用配置文件节的副本 (而不是真实的节) 来实现其属性表。 通过使用副本, 用户可以进行更改, 然后取消这些更改, 使原始配置文件分区保持不变。 
  
信息在配置文件中的显示顺序会影响 MAPI 在会话中配置资源和在会话中进行工作分配的方式。 以下工作分配受配置文件顺序的影响:
  
- 默认邮件存储
    
- 个人通讯簿
    
- 默认邮件存储搜索路径
    
- 默认通讯簿搜索路径
    
- 传输提供程序顺序
    
MAPI 将默认邮件存储在其**PR_RESOURCE_FLAGS** ([PidTagResourceFlags](pidtagresourceflags-canonical-property.md)) 属性中设置了 STATUS_DEFAULT_STORE 标志的配置文件中的第一个邮件存储区中, 这表示它可以是默认存储区。 客户端可以通过调用**IMAPISession:: SetDefaultStore**替代此设置。 有关详细信息, 请参阅[IMAPISession:: SetDefaultStore](imapisession-setdefaultstore.md)。
  
MAPI 为处理传出和传入的邮件创建传输顺序。 当多个传输提供程序为特定类型的邮件注册时, MAPI 将使用此顺序来确定应处理邮件的提供程序。 MAPI 将传输顺序设置为将传输提供程序添加到配置文件中的顺序, 但有一个例外, 在其**PR_RESOURCE_FLAGS**属性中设置 STATUS_XP_PREFER_LAST 标志的传输将位于顺序中的最后。 客户端可以通过调用**IMsgServiceAdmin:: MsgServiceTransportOrder**设置传输顺序。 有关详细信息, 请参阅[IMsgServiceAdmin:: MsgServiceTransportOrder](imsgserviceadmin-msgservicetransportorder.md)。
  
这些用于订购服务提供商和邮件服务的准则有时可能会发生冲突。 如果存在冲突, 代码应解决冲突。 可以使用 "邮件" 控制面板程序检查已创建的配置文件, 以确定是否已按预期配置了提供程序。
  

