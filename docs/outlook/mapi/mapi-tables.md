---
title: MAPI 表
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 7974cae1-10f1-42e9-8be4-c02f2bd86714
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 840c34a64cd0478be8f208799653b9916f50079d
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33437082"
---
# <a name="mapi-tables"></a>MAPI 表
  
**适用于**：Outlook 2013 | Outlook 2016 
  
MAPI 表是一个 MAPI 对象，用于查看属于特定类型其他 MAPI 对象的属性的集合。 MAPI 表采用行和列格式进行构造，其中每一行代表一个对象，每一列代表对象的属性。 通常包含在每行中的属性之一是 PR_ENTRYID  ([PidTagEntryId](pidtagentryid-canonical-property.md)) 属性，一个可用于打开和修改对象的标识符。 
  
由于行包含属性值，因此从表中检索行与直接从该行表示的对象获取一组属性相似。 这两个操作都会导致检索属性值数组。 主要区别是处理长字符串和二进制属性。 为了包含在表中，某些表实施者将这些属性截断为 255 个字节。 直接从对象检索时，完整值始终可用。
  
表由通讯簿和邮件存储提供程序以及 MAPI 实现，具体取决于表的类型及其中的对象。 邮件存储提供程序为包含有关文件夹中的邮件信息的每个文件夹实现文件夹和内容表。 通讯簿提供程序实现通讯簿容器和显示其组织的层次结构表。 MAPI 实现了几个不同的表，一些表供客户端应用程序使用，一些表供服务提供商使用，另一些表供两者使用。 状态表是唯一的，因为 MAPI 最终提供表，但这些行由所有类型的服务提供商除 MAPI 之外的贡献组成。 
  
下图显示了 MAPI 中频繁使用的表之一：显示文件夹的内容。 右侧是两条消息的显示，这两条消息可能显示在典型的邮件客户端应用程序中。 显示包含有关每封邮件的四条信息：发件人、收件人、主题和邮件文本。 每段信息对应于邮件的一个属性。
  
左侧是包含这两条消息的内容表的视图。 而 contents 表可能有十行，因为该文件夹包含十个邮件，每行包含三列以上，所以此特定视图只能包含两行和三列。
  
下表显示了为表视图设置的列的属性。
  
|**属性**|**说明**|
|:-----|:-----|
|**PR_SENDER_NAME (** [PidTagSenderName](pidtagsendername-canonical-property.md))   <br/> |发件人名称  <br/> |
|**PR_ORIGINAL_DELIVERY_TIME (** [PidTagOriginalDeliveryTime](pidtagoriginaldeliverytime-canonical-property.md))   <br/> |邮件发送的日期和时间  <br/> |
|**PR_SUBJECT (** [PidTagSubject)](pidtagsubject-canonical-property.md)  <br/> |邮件主题行  <br/> |
   
请注意，邮件中显示的属性集与表中显示的列集不同。 表的实现程序（本例中为邮件存储提供程序）按默认顺序提供一组默认列。 客户端可以修改此列集，请求其他列或拒绝默认列，并请求以特定方式对列进行排序。 客户端还可以对行进行排序，根据一列或多列的值对行进行排序。
  
**使用表格显示文件夹内容**
  
![使用表显示文件夹]使用(media/amapi_54.gif "表来显示文件夹内容")
  
有两个接口用于处理表：
  
- [IMAPITable ：IUnknown](imapitableiunknown.md) 为客户端和服务提供商提供表基础数据的只读视图，从而允许他们仅查看和更改演示文稿。 多个用户可以使用 **IMAPITable** 同时访问相同的数据。 **IMAPITable** 由 MAPI 和服务提供商实现。 
    
- [ITableData ：IUnknown](itabledataiunknown.md) 为客户端和服务提供商提供对表的基础数据的读/写访问权限，从而允许它们进行永久性更改。 **IMAPITable** 由 MAPI 实现，主要由通过调用 [CreateTable](createtable.md) 函数访问它的服务提供商使用。 **ITableData** 实现在内存中保留表的所有数据和任何关联的限制，从而不适合用于非常大的表。 复合限制和复杂操作（如分类）不受支持。 
    
## <a name="see-also"></a>另请参阅

- [MAPI 概念](mapi-concepts.md)

