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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33422458"
---
# <a name="setting-a-table-position-with-a-bookmark"></a>使用书签设置表格位置

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
书签是一种资源，用于指示表格中的特定位置。 通过设置书签，可以在以后返回到一个位置，这是一项可显著提高表操作性能的功能。 MAPI 定义三个标准书签： 
  
|||
|:-----|:-----|
|BOOKMARK_CURRENT  <br/> |指向表格中的当前行。  <br/> |
|BOOKMARK_BEGINNING  <br/> |指向表格中的第一行。  <br/> |
|BOOKMARK_END  <br/> |指向表格中的最后一行。  <br/> |
   
表实现程序需要支持这些标准书签，并且还可以支持其他书签。 但是，由于书签是资源和资源受到限制，因此书签用户应尽快释放它们。 
  
 **在当前表格位置设置书签**
  
- 调用 [IMAPITable：：CreateBookmark](imapitable-createbookmark.md)。 有时，内存不足，无法分配新书签，从而导致 **CreateBookmark** 返回MAPI_E_UNABLE_TO_COMPLETE错误值。 
    
 **释放书签**
  
- 调用 [IMAPITable：：FreeBookmark](imapitable-freebookmark.md)。
    
 **将光标移到书签位置**
  
- 调用 [IMAPITable：：SeekRow](imapitable-seekrow.md)。 **SeekRow** 为搜索位置建立BOOKMARK_CURRENT值。 **例如，SeekRow** 可用于将表格从当前位置放置十行或从头开始放置。 客户端或服务提供商可以查找表的当前、开头或结尾，或者与预定义书签关联的任何其他位置。 它们可以向前或向后移动，并且操作限制为指定的行数。 一般来说，调用方使用 **SeekRow** 搜索的行数不应超过 50 个; [IMAPITable：：SeekRowApprox](imapitable-seekrowapprox.md) 应该与更多的行一起使用。 
    
## <a name="see-also"></a>另请参阅



[MAPI 表](mapi-tables.md)

