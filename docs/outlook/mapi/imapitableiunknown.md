---
title: IMAPITable IUnknown
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPITable
api_type:
- COM
ms.assetid: f25be2b1-0f94-4a0c-b29d-d2201dc70ab7
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 0ffaf5909c978059343067c93a2b30f5969327e4
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775721"
---
# <a name="imapitable--iunknown"></a>IMAPITable : IUnknown

  
  
**适用于**： Outlook 
  
提供一个表的只读视图。 客户端和服务提供商使用**IMAPITable**来操作表的显示的方式。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapidefs.h  <br/> |
|由公开：  <br/> |Table 对象  <br/> |
|通过实现：  <br/> |服务提供商和 MAPI  <br/> |
|调用：  <br/> |客户端应用程序，服务提供商  <br/> |
|接口标识符：  <br/> |IID_IMAPITable  <br/> |
|指针类型：  <br/> |LPMAPITABLE  <br/> |
   
## <a name="vtable-order"></a>Vtable 顺序排列

|||
|:-----|:-----|
|[时出错](imapitable-getlasterror.md) <br/> |返回[MAPIERROR](mapierror.md)结构包含有关在表格的上一个错误。  <br/> |
|[建议](imapitable-advise.md) <br/> |注册接收影响表指定事件的通知。  <br/> |
|[取消通知](imapitable-unadvise.md) <br/> |取消发送通知之前设置与对**IMAPITable::Advise**方法的调用。  <br/> |
|[GetStatus](imapitable-getstatus.md) <br/> |返回表的状态和类型。  <br/> |
|[SetColumns](imapitable-setcolumns.md) <br/> |定义的特定属性和属性的顺序显示为表中的列。  <br/> |
|[QueryColumns](imapitable-querycolumns.md) <br/> |返回表格列的列表。  <br/> |
|[GetRowCount](imapitable-getrowcount.md) <br/> |返回表中的总行数。  <br/> |
|[SeekRow](imapitable-seekrow.md) <br/> |将光标移到表中的特定位置。  <br/> |
|[SeekRowApprox](imapitable-seekrowapprox.md) <br/> |将光标移到表中大约小数位置。  <br/> |
|[QueryPosition](imapitable-queryposition.md) <br/> |检索当前表行位置的指针，根据分数的值。  <br/> |
|[FindRow](imapitable-findrow.md) <br/> |与特定的搜索条件匹配的表中查找的下一行。  <br/> |
|[限制](imapitable-restrict.md) <br/> |筛选器应用于表格，从而减少了设置为仅与指定的条件匹配这些行的行。  <br/> |
|[CreateBookmark](imapitable-createbookmark.md) <br/> |标记表的当前位置。  <br/> |
|[FreeBookmark](imapitable-freebookmark.md) <br/> |释放与一个书签关联的内存。  <br/> |
|[SortTable](imapitable-sorttable.md) <br/> |基于排序条件的表的行进行排序。  <br/> |
|[QuerySortOrder](imapitable-querysortorder.md) <br/> |检索当前表格排序顺序。  <br/> |
|[QueryRows](imapitable-queryrows.md) <br/> |从表中，开始在当前光标位置返回一个或多个行。  <br/> |
|[中止](imapitable-abort.md) <br/> |停止当前正在进行任何异步操作表。  <br/> |
|[ExpandRow](imapitable-expandrow.md) <br/> |展开折叠的表类别，添加属于到表视图类别的叶行。  <br/> |
|[CollapseRow](imapitable-collapserow.md) <br/> |折叠的扩展的表类别，删除属于表视图中的类别的叶行。  <br/> |
|[WaitForCompletion](imapitable-waitforcompletion.md) <br/> |挂起处理，直到完成一个或多个异步正在进行的操作在表上。  <br/> |
|[GetCollapseState](imapitable-getcollapsestate.md) <br/> |返回要重新生成当前的必需数据折叠或展开分类表的状态。  <br/> |
|[SetCollapseState](imapitable-setcollapsestate.md) <br/> |重建使用以前**IMAPITable::GetCollapseState**方法调用已保存的数据分类表的当前展开还是折叠状态。  <br/> |
   
## <a name="see-also"></a>另请参阅



[MAPI 接口](mapi-interfaces.md)

