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
ms.openlocfilehash: 6393de45dbfd130e15a0678f2b6a7f18968dfa03
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22573213"
---
# <a name="mapi-tables"></a>MAPI 表
  
**适用于**： Outlook 2013 |Outlook 2016 
  
MAPI 表是一个 MAPI 对象，用于查看属于特定类型的其他 MAPI 对象的属性的集合。 MAPI 表行和列的格式结构化表示对象和代表对象的属性的每个列的每个行。 通常在每行中包含的属性之一是**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 属性，可用于打开和修改该对象的标识符。 
  
由于行包含属性值，从表中检索行是类似于直接从行代表的对象中获取一组属性。 这两种操作导致的检索属性值数组中。 主要区别在于处理的长字符串和二进制文件的属性。 以包含在表中，某些表实施截断为 255 个字节这些属性。 直接从对象中检索，完整的值时始终可用。
  
表被实现的地址簿和消息存储提供程序和 MAPI，具体取决于表和其中的对象类型。 消息存储提供程序实现文件夹和邮件的信息包括文件夹中每个文件夹内容表。 通讯簿提供程序实现通讯簿容器和显示其组织的层次结构表。 MAPI 实现多个不同的表、 一些以供客户端应用程序、 一些由服务提供程序，使用和一些用于这二者。 状态表是唯一的 MAPI 最终提供表中，但行组成除了 MAPI 服务提供商的所有类型的贡献。 
  
下图显示一个表的常见用途之一 MAPI 中： 显示文件夹的内容。 在右侧显示的是两个邮件可能显示典型消息客户端应用程序中。 显示包含四个部分有关每个邮件的信息： 发件人、 收件人、 主题和消息文本。 每条信息对应于邮件的属性。
  
在左侧是包含这两个消息的内容表的视图。 而内容表可能具有十行，因为该文件夹具有十个邮件，其中每一行包含三个以上列多，则此特定视图仅限于只有两个行和三列。
  
下表显示为表视图设置的列组成的属性。
  
|**属性**|**说明**|
|:-----|:-----|
|**PR_SENDER_NAME**([PidTagSenderName](pidtagsendername-canonical-property.md))  <br/> |发件人姓名  <br/> |
|**PR_ORIGINAL_DELIVERY_TIME**([PidTagOriginalDeliveryTime](pidtagoriginaldeliverytime-canonical-property.md))  <br/> |日期和时间发送邮件时  <br/> |
|**PR_SUBJECT**([PidTagSubject](pidtagsubject-canonical-property.md))  <br/> |邮件主题行  <br/> |
   
请注意的消息中显示的属性集不是表中显示的列集相同。 表的实施，在这种情况下一条消息存储提供程序，默认顺序中的列的供应品默认设置。 客户端可以请求其他列或拒绝默认模板，修改此列集，并要求，它们订购特定方式。 客户端也可以订购行中，根据的一个或多个列的值对它们进行排序。
  
**使用表格显示文件夹内容**
  
![使用表以显示文件夹内容](media/amapi_54.gif "使用表以显示文件夹内容")
  
有两个接口用于处理表：
  
- [IMAPITable: IUnknown](imapitableiunknown.md)提供客户端和服务提供商的基础数据的表中，使他们能够查看和更改仅在演示文稿只读的视图。 多个用户可以访问同时**IMAPITable**相同的数据。 通过 MAPI 和服务提供商实现**IMAPITable** 。 
    
- [ITableData: IUnknown](itabledataiunknown.md)提供客户端和服务提供商读/写访问的基础数据的表中，从而允许进行永久更改。 **IMAPITable**是由 MAPI 实现，主要由服务提供商访问通过调用[CreateTable](createtable.md)函数。 **ITableData**实现包含表格的所有数据和任何相关限制在内存中，使其适合使用非常大的表。 复合限制和复杂操作，例如分类不受支持。 
    
## <a name="see-also"></a>另请参阅

- [MAPI 概念](mapi-concepts.md)

