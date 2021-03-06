---
title: 对邮件存储提供程序中的表进行分组和限制
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 01df4be4-98a1-4159-a06d-9ccf4337198f
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 8a45a9fd0d40c16d110fd52be1ac1117e1dd4d04
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33428982"
---
# <a name="grouping-and-restricting-tables-in-message-store-providers"></a>对邮件存储提供程序中的表进行分组和限制

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
客户端应用程序通常允许用户对文件夹内容的显示方式进行一些控制。 通常，用户可以选择根据一个或多个邮件属性的值对邮件进行分组，也可以选择排除匹配特定条件的邮件。 这是通过使用 [IMAPITable ： IUnknown](imapitableiunknown.md) 接口完成。 客户端应用程序可以将从表返回的行限制为用户指定的任何条件。 因此，邮件存储提供程序需要实现以下 **IMAPITable** 方法。 
  
|IMAPITable** 方法**|**说明**|
|:-----|:-----|
|[IMAPITable::FindRow](imapitable-findrow.md) <br/> |返回与指定条件匹配的表行。  <br/> |
|[IMAPITable::QueryColumns](imapitable-querycolumns.md) <br/> |返回表中的列集或当前使用的列集。  <br/> |
|[IMAPITable::QueryRows](imapitable-queryrows.md) <br/> |从给定位置开始，从表格中返回一行或多行。  <br/> |
|[IMAPITable::Restrict](imapitable-restrict.md) <br/> |对表应用限制，以便对 **FindRow** 的后续调用仅返回与限制匹配的行。  <br/> |
|[IMAPITable::SetColumns](imapitable-setcolumns.md) <br/> |指定从表中检索行时应返回的列。  <br/> |
   
实施限制可能很复杂;有关详细信息，请参阅关于 [限制](about-restrictions.md)。 有关实现表的信息，请参阅[MAPI Tables。](mapi-tables.md)
  
## <a name="see-also"></a>另请参阅



[邮件存储功能](message-store-features.md)

