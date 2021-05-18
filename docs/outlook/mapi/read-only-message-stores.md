---
title: Read-Only邮件存储
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 752ff2d6-ca64-4507-adf1-4c054c321203
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 957a7f92963b97e5421bc801a3b046f098d6a08e
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33405336"
---
# <a name="read-only-message-stores"></a>Read-Only邮件存储

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
只读邮件存储是 MAPI 客户端和 MAPI 后台处理程序均无法创建、修改或删除邮件存储中的对象的存储。 您可能希望实现只读邮件存储的原因有很多。 例如，信用报告公司可以使用只读存储区来允许其客户或员工查看但不更改个人信用报告。 选择使只读邮件存储对存储提供程序的结构和存储本身具有一些影响。 例如，只读邮件存储不能有发件箱文件夹，因为 MAPI 客户端会请求在文件夹中新建传出邮件。 同样，存储提供程序有责任确保基础存储机制的完整性。
  
可以在邮件存储的 **PR_STORE_SUPPORT_MASK** ([PidTagStoreSupportMask](pidtagstoresupportmask-canonical-property.md)) 属性中设置三个标志，它们支持不同级别的只读访问。 the STORE_READONLY flag indicates that all [IMAPIProp ： IUnknown](imapipropiunknown.md) interfaces on objects in the message store are read-only. the STORE_MODIFY_OK flag indicates that existing messages in the message store may be modified， but new folders and messages may not be created. the STORE_CREATE_OK flag indicates that new messages and folders may be created， but indicates nothing about whether existing objects may be modified. 
  
MAPI 客户端和 MAPI 后台处理程序可能无法创建、修改或删除邮件存储中的对象这一事实并不意味着基础存储机制的内容永远不会更改。 也不表示存储提供程序永远不需要对基础存储机制的写入权限。 在某些情况下，这两个条件可能适用，但在只读邮件存储的一般情况下不适用。 存储提供程序所需的访问级别以及您的存储提供程序是否更改基础存储机制中的数据主要取决于存储提供程序的特定性质。
  
例如，如果要编写存储提供程序以向 MAPI 客户端授予对 CD-ROM 设备上存储的数据库的访问权限，则基础存储机制无法更改，并且您的存储提供程序可以具有该存储提供程序的只读权限。 但是，如果要编写存储提供程序以向 MAPI 客户端授予对公用文件夹数据库的只读访问权限，但存储提供程序需要跟踪每个用户的邮件的读/未读状态，则存储提供程序将需要将新数据写入基础存储机制。 但是，在两个示例中，存储提供程序都不需要根据 MAPI 客户端或 MAPI 后台处理程序的请求创建、修改或删除文件夹或邮件。
  
存储提供程序需要将数据写入以其他方式为只读的基础存储机制的原因的简短列表如下：
  
- 存储邮件的读/未读状态。
    
- 实现读/非读通知。 
    
- 存储视图。
    
- 缓存用户定义的文件夹排序订单的永久索引。
    
- 若要存储文件夹内容的排序顺序， ([IMAPIFolder：：SaveContentsSort](imapifolder-savecontentssort.md)) 。
    
- 若要存储搜索条件、搜索状态和结果，如果邮件存储提供程序支持支持 [IMAPIContainer：：SetSearchCriteria](imapicontainer-setsearchcriteria.md) (搜索) 。
    
如果邮件存储提供程序永远不能将数据写入基础存储机制，则需要使用基础存储机制之外的单独存储机制来实现这些功能。 例如，只读邮件存储提供程序可以在用户计算机的文件中存储邮件的已读/未读状态。 此策略存在其他困难，但可能是只读邮件存储提供程序实现某些功能的唯一可行方法。 例如，保持独立存储机制的内容与邮件存储中的对象同步比直接在邮件存储本身中存储已读/未读状态困难。
  
搜索为只读邮件存储提供程序提供了额外的复杂性。 客户端使用邮件存储对象的 PR_FINDER_ENTRYID ([PidTagFinderEntryId](pidtagfinderentryid-canonical-property.md)) 属性中指定的文件夹来查找用于搜索结果的文件夹。  只读邮件存储提供程序通常无法将永久搜索结果文件夹安装到邮件存储中。 在这种情况下，邮件存储提供程序应在 **PR_FINDER_ENTRYID** 属性中存储一个条目标识符，客户端打开文件夹时可以识别该标识符，以便它可以动态地创建搜索结果文件夹，而不是从基础存储机制中读取一个。 但是，由于许多只读邮件存储提供程序会动态创建其所有文件夹，因此这通常不会带来太多负担。 
  
邮件存储提供程序为只读这一事实在存储提供程序对象的 PR_STORE_SUPPORT_MASK **属性中** 公布。 但是，不依靠客户端来遵守该属性;存储提供程序的代码应强制执行基础存储机制的只读状态。 
  
## <a name="see-also"></a>另请参阅



[开发 MAPI 邮件存储提供程序](developing-a-mapi-message-store-provider.md)

