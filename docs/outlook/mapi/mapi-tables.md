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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32355832"
---
# <a name="mapi-tables"></a>MAPI 表
  
**适用于**：Outlook 2013 | Outlook 2016 
  
mapi 表是一个 mapi 对象, 用于查看属于特定类型的其他 MAPI 对象的属性的集合。 MAPI 表以行和列的格式进行构造, 每行表示一个对象, 每个列代表对象的一个属性。 其中一个属性通常包含在每一行中是**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 属性, 它是一个可用于打开和修改对象的标识符。 
  
由于行包含属性值, 从表中检索行类似于从行表示的对象中直接获取一组属性。 这两个操作都会导致检索属性值数组。 主要区别在于长字符串和二进制属性的处理。 若要包含在表中, 某些表实现程序会将这些属性截断为255字节。 从对象中直接检索时, 完整值始终可用。
  
根据表的类型和表中的对象, 按通讯簿和邮件存储提供程序和 MAPI 实现表。 邮件存储提供程序实现文件夹和内容表, 每个文件夹包含有关该文件夹中邮件的信息。 通讯簿提供程序实现通讯簿容器和显示其组织的层次结构表。 MAPI 实现了几个不同的表, 可供客户端应用程序使用, 一些可供服务提供商使用, 并且可供二者使用。 在 mapi 中, 状态表的唯一性最终会提供表, 但这些行是由除 MAPI 之外的所有类型的服务提供商所做的贡献组成。 
  
下图显示了 MAPI 中的表格的常用用途之一: 显示文件夹的内容。 右侧显示两条消息, 如典型的邮件客户端应用程序中所示。 显示内容包含四条有关每封邮件的信息: 发件人、收件人、主题和邮件正文。 每条信息与邮件的属性相对应。
  
左侧是包含这两封邮件的内容表的视图。 由于文件夹包含10行, 而内容表可能有10行, 因为每行包含的列数多于三列, 所以此特定视图仅限于两行和三列。
  
下表显示了组成表视图的列集的属性。
  
|**属性**|**说明**|
|:-----|:-----|
|**PR_SENDER_NAME**([PidTagSenderName](pidtagsendername-canonical-property.md))  <br/> |发件人姓名  <br/> |
|**PR_ORIGINAL_DELIVERY_TIME**([PidTagOriginalDeliveryTime](pidtagoriginaldeliverytime-canonical-property.md))  <br/> |发送邮件的日期和时间  <br/> |
|**PR_SUBJECT**([PidTagSubject](pidtagsubject-canonical-property.md))  <br/> |邮件主题行  <br/> |
   
请注意, 消息中显示的属性集与表中显示的一组列不同。 表的实施者 (在这种情况下, 为邮件存储提供程序) 按默认顺序提供一组默认的列。 客户端可以修改此列集, 请求其他列或拒绝默认列, 并要求以特定方式对其进行排序。 客户端还可以对行进行排序, 并根据一个或多个列的值对它们进行排序。
  
**使用表格显示文件夹内容**
  
![使用表格显示文件夹内容](media/amapi_54.gif "使用表格显示文件夹内容")
  
有两种用于处理表的接口:
  
- [IMAPITable: IUnknown](imapitableiunknown.md)为客户端和服务提供程序提供了表的基础数据的只读视图, 从而允许用户只查看和更改演示文稿。 多个用户可以与**IMAPITable**同时访问相同的数据。 **IMAPITable**由 MAPI 和服务提供商实现。 
    
- [ITableData: IUnknown](itabledataiunknown.md)为客户端和服务提供程序提供对表的基础数据的读/写访问权限, 从而使其可以进行永久性更改。 **IMAPITable**由 MAPI 实现, 主要由可通过调用[CreateTable](createtable.md)函数访问它的服务提供商使用。 **ITableData**实现保留表的所有数据以及内存中的任何关联限制, 使其不适合用于非常大的表。 不支持复合限制和复杂操作 (如分类)。 
    
## <a name="see-also"></a>另请参阅

- [MAPI 概念](mapi-concepts.md)

