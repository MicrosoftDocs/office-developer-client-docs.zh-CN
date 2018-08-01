---
title: 通过书签设置表位置
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 56ab37f9-5aa6-4e9d-9dc8-b3d95aa19f35
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: d53f15cb439494ae99ff45509ed14c0928756d8f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778756"
---
# <a name="setting-a-table-position-with-a-bookmark"></a>通过书签设置表位置

  
  
**适用于**： Outlook 
  
书签是指示表中的特定位置的资源。 设置书签使得以后，一种功能，可以显著提高性能的表操作返回的位置。 MAPI 定义三个标准书签： 
  
|||
|:-----|:-----|
|BOOKMARK_CURRENT  <br/> |指向表中的当前行。  <br/> |
|BOOKMARK_BEGINNING  <br/> |指向表中的第一行。  <br/> |
|BOOKMARK_END  <br/> |点的最后一个表格中的行。  <br/> |
   
表实施支持这些标准书签所需，而且还可以支持其他人。 但是，因为资源是有限书签是资源以及书签用户应释放它们尽快。 
  
 **在表当前位置设置书签**
  
- 调用[IMAPITable::CreateBookmark](imapitable-createbookmark.md)。 偶尔会有内存不足，无法分配新书签，导致**CreateBookmark**返回 MAPI_E_UNABLE_TO_COMPLETE 错误值。 
    
 **以释放书签**
  
- 调用[IMAPITable::FreeBookmark](imapitable-freebookmark.md)。
    
 **若要将光标移到的书签的位置**
  
- 调用[IMAPITable::SeekRow](imapitable-seekrow.md)。 **SeekRow**建立 BOOKMARK_CURRENT 位置的新值。 **SeekRow**可，例如，若要从当前位置定位表 10 行或重新开始开头。 客户端或服务提供商可以查找到当前，从开始，或结束的表或任何其他相关联的预定义的书签的位置。 它们可以移动中向前或向后和限制操作到指定的行数。 一般来说，呼叫者应寻求通过与**SeekRow**; 不能超过 50 行[IMAPITable::SeekRowApprox](imapitable-seekrowapprox.md)应与更大的行数。 
    
## <a name="see-also"></a>另请参阅



[MAPI 表](mapi-tables.md)

