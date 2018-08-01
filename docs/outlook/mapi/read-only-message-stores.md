---
title: 只读邮件存储区
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 752ff2d6-ca64-4507-adf1-4c054c321203
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: f82c213b6e0737c27c4e979fc90109b38b0746f0
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778599"
---
# <a name="read-only-message-stores"></a>只读邮件存储区

  
  
**适用于**： Outlook 
  
只读消息存储区是一中既 MAPI 客户端也 MAPI 后台处理程序可以创建、 修改或删除的邮件存储区中的对象。 有许多为什么您可能希望实现的只读消息存储的原因。 例如，credit 报告公司无法使用只读存储允许其客户或员工，请参阅但不能更改单个 credit 报告。 选择生成只读消息存储有意义的存储提供程序的结构和存储本身。 例如，只读消息存储不能具有发件箱文件夹中，因为然后 MAPI 客户端将在该文件夹中创建新的待发邮件的请求。 同样，它是存储提供程序负责确保基础存储机制的完整性。
  
有三个可以设置的消息存储**PR_STORE_SUPPORT_MASK** ([PidTagStoreSupportMask](pidtagstoresupportmask-canonical-property.md)) 属性中支持的只读访问权限的不同级别的标志。 STORE_READONLY 标志指示所有[IMAPIProp: IUnknown](imapipropiunknown.md)消息存储中的对象上的接口是只读的。 STORE_MODIFY_OK 标志指示可能修改邮件存储区中的现有消息，但不是能创建新的文件夹和消息。 STORE_CREATE_OK 标志指示新邮件和文件夹可能创建，但指示有关是否可修改现有对象执行任何操作。 
  
这一事实的 MAPI 客户端和 MAPI 后台处理程序可能无法在创建、 修改或删除消息存储中的对象并不意味着基础存储机制的内容永远不会更改。 也不意味着存储提供程序永远不需要的权限写入基础存储机制。 在某些情况下这些以下两种情况可能会应用，但不是在只读状态消息的一般情况下存储。 存储提供程序需要和存储提供程序发生变化基础存储机制中的数据的访问级别的主要取决于存储提供程序的特定特性。
  
例如，如果要编写可让 CD-ROM 设备上存储的数据库 MAPI 客户端访问的存储提供程序，不能更改基础存储机制和存储提供程序可以具有对它的只读权限。 如果，但是，要编写的存储提供程序为公用文件夹数据库，MAPI 客户端只读访问权限，但需要跟踪的每个用户的邮件的读/未读状态的存储提供程序的存储提供程序需要将新数据写入基础存储机制。 但是，在既示例中的存储提供程序以往不必要创建、 修改或删除文件夹或 MAPI 客户端或 MAPI 后台处理程序的请求的消息。
  
简短的列表的存储提供程序需要将数据写入否则是只读的基础存储机制的原因是，如下所示：
  
- 存储邮件的读/未读状态。
    
- 若要实现读取/nonread 通知。 
    
- 存储视图。
    
- 为缓存持久的用户定义的文件夹的排序顺序索引。
    
- 存储 （支持[IMAPIFolder::SaveContentsSort](imapifolder-savecontentssort.md)） 的文件夹的内容的排序顺序。
    
- 存储搜索条件、 状态和结果中，如果搜索消息存储提供程序支持搜索 （支持[IMAPIContainer::SetSearchCriteria](imapicontainer-setsearchcriteria.md)）。
    
如果您的消息存储提供程序可以从不数据写入基础存储机制，它将需要通过使用基础存储机制之外的独立存储机制来实现这些功能。 例如，只读消息存储提供程序无法存储中用户的计算机上的文件存储中的邮件的读/未读状态。 此策略其他的难度，但也可能是只读的消息的唯一 feasable 方式存储提供程序实现的一些功能。 例如，保持同步使用中的消息存储对象的单独的存储机制的内容是更加难以比直接在消息存储本身中存储的读/未读状态。
  
搜索显示另一复杂只读消息存储提供程序。 客户端使用的消息存储对象**PR_FINDER_ENTRYID** ([PidTagFinderEntryId](pidtagfinderentryid-canonical-property.md)) 属性中指定的文件夹，找到用于搜索结果的文件夹。 只读消息存储提供程序通常无法安装一个永久的搜索结果文件夹到邮件存储区。 在这种情况下，消息存储提供程序应存储它才能识别客户端打开文件夹，以便它可以动态创建而不是读取从搜索结果文件夹时的**PR_FINDER_ENTRYID**属性中的项标识符基础存储机制。 但是，因为许多只读消息存储提供程序动态创建它们的所有文件夹，这通常是不太多负担。 
  
消息存储提供程序是只读的这一事实将公布的存储提供程序对象**PR_STORE_SUPPORT_MASK**属性中。 但是，不数量对客户端尊重属性;存储提供程序的代码应同时实施基础存储机制只读状态。 
  
## <a name="see-also"></a>另请参阅



[开发 MAPI 邮件存储区提供程序](developing-a-mapi-message-store-provider.md)

