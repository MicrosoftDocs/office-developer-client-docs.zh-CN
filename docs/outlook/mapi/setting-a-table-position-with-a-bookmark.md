---
title: 使用书签设置表格位置
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 56ab37f9-5aa6-4e9d-9dc8-b3d95aa19f35
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: f0b041cecca92c0ced32631c67c72fcafdab2a16
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32351231"
---
# <a name="setting-a-table-position-with-a-bookmark"></a>使用书签设置表格位置

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
书签是指示表格中的特定位置的资源。 通过设置书签, 可以在以后返回到某个位置, 这是一种可以显著提高表操作性能的功能。 MAPI 定义了三个标准书签: 
  
|||
|:-----|:-----|
|BOOKMARK_CURRENT  <br/> |指向表中的当前行。  <br/> |
|BOOKMARK_BEGINNING  <br/> |指向表格中的第一行。  <br/> |
|BOOKMARK_END  <br/> |指向表中的最后一行。  <br/> |
   
表实施者需要支持这些标准书签, 也可以支持其他书签。 但是, 由于书签是资源和资源受到限制, 因此用户应尽快释放它们。 
  
 **在当前表格位置设置书签**
  
- 调用[IMAPITable:: CreateBookmark](imapitable-createbookmark.md)。 偶尔会有内存不足, 无法分配新书签, 从而导致**CreateBookmark**返回 MAPI_E_UNABLE_TO_COMPLETE 错误值。 
    
 **释放书签**
  
- 调用[IMAPITable:: FreeBookmark](imapitable-freebookmark.md)。
    
 **将光标移动到已加书签的位置**
  
- 调用[IMAPITable:: SeekRow](imapitable-seekrow.md)。 **SeekRow**为 BOOKMARK_CURRENT 位置建立新值。 例如, 可以使用**SeekRow**将表中的10行定位在当前位置或从头开始。 客户端或服务提供程序可以查找表的当前、开头或结尾, 或与预定义的书签关联的任何其他位置。 它们可以向前或向后移动, 并将操作限制为指定的行数。 通常情况下, 呼叫者在**SeekRow**中查找的行数不超过50。[IMAPITable:: SeekRowApprox](imapitable-seekrowapprox.md)应与较大的行数一起使用。 
    
## <a name="see-also"></a>另请参阅



[MAPI 表](mapi-tables.md)

