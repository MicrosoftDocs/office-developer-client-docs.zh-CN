---
title: 只读邮件存储
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
# <a name="read-only-message-stores"></a>只读邮件存储

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
只读邮件存储区是 mapi 客户端和 mapi 后台处理程序都不能创建、修改或删除邮件存储区中的对象。 您可能希望实现只读邮件存储区的原因有很多。 例如, 信用报告公司可以使用只读存储, 以允许其客户或员工看到但不能更改单个信用报告。 选择使只读邮件存储区具有对存储提供程序的结构和存储本身的影响。 例如, 只读邮件存储区不能有 "发件箱" 文件夹, 因为 MAPI 客户端会请求在该文件夹中创建新的传出邮件。 同样, 存储提供程序负责确保基础存储机制的完整性。
  
可以在邮件存储区的**PR_STORE_SUPPORT_MASK** ([PidTagStoreSupportMask](pidtagstoresupportmask-canonical-property.md)) 属性中设置三个标志, 这些标志支持不同的只读访问级别。 STORE_READONLY 标志指示邮件存储区中的对象上的所有[IMAPIProp: IUnknown](imapipropiunknown.md)接口都是只读的。 STORE_MODIFY_OK 标志指示可以修改邮件存储区中的现有邮件, 但可能不会创建新的文件夹和邮件。 STORE_CREATE_OK 标志指示可以创建新的邮件和文件夹, 但不会指示是否可以修改现有对象。 
  
mapi 客户端和 mapi 后台处理程序可能无法在邮件存储区中创建、修改或删除对象, 这并不意味着基础存储机制的内容永远不会发生变化。 也不意味着您的存储提供程序永远不需要对基础存储机制的写入权限。 在某些情况下, 可能会应用这两个条件, 但不是只读邮件存储区的常规情况。 您的存储提供程序所需的访问级别, 以及您的存储提供程序是否曾在基础存储机制中更改数据, 这主要取决于您的存储提供程序的特定性质。
  
例如, 如果您要编写存储提供程序以向 MAPI 客户端授予对存储在 cd-rom 设备上的数据库的访问权限, 则基础存储机制将无法更改, 并且您的存储提供程序可以对其具有只读权限。 但是, 如果您要编写存储提供程序以向 MAPI 客户端授予对公用文件夹数据库的只读访问权限, 但存储提供程序需要跟踪每个用户的邮件的已读/未读状态, 则存储提供程序将需要将新数据写入到基础存储机制。 但是, 在任何示例中, 存储提供程序都不需要在 mapi 客户端或 mapi 后台处理程序的请求中创建、修改或删除文件夹或邮件。
  
存储提供程序将数据写入到基础存储机制的简单原因 (如其他只读) 的简短列表如下所示:
  
- 存储邮件的已读/未读状态。
    
- 实现读取/未读通知。 
    
- 以存储视图。
    
- 为用户定义的文件夹排序顺序缓存持久索引。
    
- 存储文件夹内容的排序顺序 (支持[IMAPIFolder:: SaveContentsSort](imapifolder-savecontentssort.md))。
    
- 如果邮件存储区提供程序支持搜索 (支持[IMAPIContainer:: SetSearchCriteria](imapicontainer-setsearchcriteria.md)), 则存储搜索条件、搜索状态和结果。
    
如果您的邮件存储区提供程序永远无法向基础存储机制写入数据, 则需要在基础存储机制之外使用单独的存储机制来实现这些功能。 例如, 只读邮件存储提供程序可以将存储中的邮件的已读/未读状态存储在用户计算机上的文件中。 此策略带来了其他困难, 但可能是只读邮件存储提供程序实现某些功能的唯一 feasable 方式。 例如, 保持与邮件存储区中的对象同步的单独存储机制的内容比直接在邮件存储本身中存储已读/未读状态更难。
  
搜索为只读邮件存储提供程序带来了额外的更复杂之处。 客户端使用邮件存储对象的**PR_FINDER_ENTRYID** ([PidTagFinderEntryId](pidtagfinderentryid-canonical-property.md)) 属性中指定的文件夹查找用于搜索结果的文件夹。 只读邮件存储提供程序通常无法将永久搜索结果文件夹安装到邮件存储中。 在这种情况下, 邮件存储提供程序应将条目标识符存储在**PR_FINDER_ENTRYID**属性中, 当客户端打开文件夹时它可以识别, 以便它可以动态创建搜索结果文件夹, 而不是从基础存储机制。 但是, 由于许多只读邮件存储区提供程序动态地创建所有文件夹, 这通常不是太多的负担。 
  
您的邮件存储提供程序为只读这一事实将在存储提供程序对象的**PR_STORE_SUPPORT_MASK**属性中公布。 但是, 不要在客户端上计数以遵守该属性;您的存储提供程序的代码应强制实施基础存储机制的只读状态。 
  
## <a name="see-also"></a>另请参阅



[开发 MAPI 邮件存储提供程序](developing-a-mapi-message-store-provider.md)

