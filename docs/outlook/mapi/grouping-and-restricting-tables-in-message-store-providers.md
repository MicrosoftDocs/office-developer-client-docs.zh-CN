---
title: 分组和限制邮件存储区提供程序中的表
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 01df4be4-98a1-4159-a06d-9ccf4337198f
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 33c76cdd0e7850f82949349ac2e5bb0dd4e056ef
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775041"
---
# <a name="grouping-and-restricting-tables-in-message-store-providers"></a>分组和限制邮件存储区提供程序中的表

  
  
**适用于**： Outlook 
  
客户端应用程序经常允许用户一些控制文件夹的内容的显示方式。 通常情况下，用户可以选择一个或多个邮件属性的值根据分组的邮件，或者可以选择要排除匹配特定条件的邮件。 这通过使用[IMAPITable: IUnknown](imapitableiunknown.md)接口。 客户端应用程序可以限制用户指定任何条件返回从表的行。 因此，一条消息存储提供程序需要实现以下**IMAPITable**方法。 
  
|IMAPITable * * 方法 * *|**说明**|
|:-----|:-----|
|[IMAPITable::FindRow](imapitable-findrow.md) <br/> |返回表格符合指定的条件的行。  <br/> |
|[IMAPITable::QueryColumns](imapitable-querycolumns.md) <br/> |返回表或当前使用的列组中的列集。  <br/> |
|[IMAPITable::QueryRows](imapitable-queryrows.md) <br/> |从表中，从给定位置开始返回一个或多个行。  <br/> |
|[IMAPITable::Restrict](imapitable-restrict.md) <br/> |应用限制到表中，以便对**FindRow**后续调用返回仅与限制匹配的行。  <br/> |
|[IMAPITable::SetColumns](imapitable-setcolumns.md) <br/> |指定表中检索行时应返回的列。  <br/> |
   
限制可能会很复杂实现;有关详细信息，请参阅[有关限制](about-restrictions.md)。 有关实现表的详细信息，请参阅[MAPI 表](mapi-tables.md)。
  
## <a name="see-also"></a>另请参阅



[邮件存储区功能](message-store-features.md)

