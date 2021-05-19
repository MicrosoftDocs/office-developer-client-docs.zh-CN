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
ms.openlocfilehash: d6a13799da4ef9315f9c23317fa18853d71c72f9
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33420113"
---
# <a name="imapitable--iunknown"></a>IMAPITable : IUnknown

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
提供表的只读视图。 客户端和服务提供商使用 **IMAPITable** 操作表的显示方式。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapidefs.h  <br/> |
|公开者：  <br/> |Table 对象  <br/> |
|实现者：  <br/> |服务提供程序和 MAPI  <br/> |
|调用者：  <br/> |客户端应用程序、服务提供商  <br/> |
|接口标识符：  <br/> |IID_IMAPITable  <br/> |
|指针类型：  <br/> |LPMAPITABLE  <br/> |
   
## <a name="vtable-order"></a>Vtable 顺序

|||
|:-----|:-----|
|[GetLastError](imapitable-getlasterror.md) <br/> |返回 [一个 MAPIERROR](mapierror.md) 结构，其中包含有关表上上一个错误的信息。  <br/> |
|[建议](imapitable-advise.md) <br/> |注册以接收影响表的指定事件的通知。  <br/> |
|[非企业](imapitable-unadvise.md) <br/> |取消发送以前通过调用 **IMAPITable：：Advise** 方法设置的通知。  <br/> |
|[GetStatus](imapitable-getstatus.md) <br/> |返回表的状态和类型。  <br/> |
|[SetColumns](imapitable-setcolumns.md) <br/> |定义要作为表格中的列显示的属性的特定属性和顺序。  <br/> |
|[QueryColumns](imapitable-querycolumns.md) <br/> |返回表格的列列表。  <br/> |
|[GetRowCount](imapitable-getrowcount.md) <br/> |返回表中的总行数。  <br/> |
|[SeekRow](imapitable-seekrow.md) <br/> |将光标移到表格中的特定位置。  <br/> |
|[SeekRowApprox](imapitable-seekrowapprox.md) <br/> |将光标移到表格中的近似小数位置。  <br/> |
|[QueryPosition](imapitable-queryposition.md) <br/> |基于小数值检索游标的当前表格行位置。  <br/> |
|[FindRow](imapitable-findrow.md) <br/> |查找表中与特定搜索条件匹配的下一行。  <br/> |
|[Restrict](imapitable-restrict.md) <br/> |将筛选器应用于表，从而将行设置为仅与指定条件匹配的行。  <br/> |
|[CreateBookmark](imapitable-createbookmark.md) <br/> |标记表的当前位置。  <br/> |
|[FreeBookmark](imapitable-freebookmark.md) <br/> |释放与书签关联的内存。  <br/> |
|[SortTable](imapitable-sorttable.md) <br/> |根据排序条件对表的行进行排序。  <br/> |
|[QuerySortOrder](imapitable-querysortorder.md) <br/> |检索表的当前排序顺序。  <br/> |
|[QueryRows](imapitable-queryrows.md) <br/> |从表中的一行或多行，从当前光标位置开始。  <br/> |
|[中止](imapitable-abort.md) <br/> |停止表当前正在执行的任何异步操作。  <br/> |
|[ExpandRow](imapitable-expandrow.md) <br/> |展开折叠的表类别，将属于该类别的叶行添加到表视图中。  <br/> |
|[CollapseRow](imapitable-collapserow.md) <br/> |折叠展开的表类别，从表视图中删除属于该类别的叶行。  <br/> |
|[WaitForCompletion](imapitable-waitforcompletion.md) <br/> |在表上的一个或多个异步操作完成之前暂停处理。  <br/> |
|[GetCollapseState](imapitable-getcollapsestate.md) <br/> |返回重新生成分类表的当前折叠或展开状态所需的数据。  <br/> |
|[SetCollapseState](imapitable-setcollapsestate.md) <br/> |使用之前调用 **IMAPITable：：GetCollapseState** 方法保存的数据重新生成分类表的当前展开或折叠状态。  <br/> |
   
## <a name="see-also"></a>另请参阅



[MAPI 接口](mapi-interfaces.md)

