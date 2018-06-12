---
title: IPersistMessage IUnknown
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IPersistMessage
api_type:
- COM
ms.assetid: 40ec6dd4-2206-4e59-aafe-53aaf693f973
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 62fb2b069a50408713eea741cf837c421a749fcd
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776010"
---
# <a name="ipersistmessage--iunknown"></a>IPersistMessage: IUnknown

  
  
**适用于**： Outlook 
  
启用表单查看器处理存储窗体和各种状态间转换。
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapiform.h  <br/> |
|由公开：  <br/> |保留消息对象  <br/> |
|通过实现：  <br/> |窗体对象  <br/> |
|调用：  <br/> |表单查看器  <br/> |
|接口标识符：  <br/> |IID_IPersistMessage  <br/> |
|指针类型：  <br/> |LPPERSISTMESSAGE  <br/> |
   
## <a name="vtable-order"></a>Vtable 顺序排列

|||
|:-----|:-----|
|[时出错](ipersistmessage-getlasterror.md) <br/> |返回一个[MAPIERROR](mapierror.md)结构，其中包含有关表单对象中前面的错误的信息。  <br/> |
|[GetClassID](ipersistmessage-getclassid.md) <br/> |返回表示可以管理窗体的窗体服务器的标识符。  <br/> |
|[IsDirty](ipersistmessage-isdirty.md) <br/> |检查自上次保存以来所做的更改的表单。  <br/> |
|[丢失](ipersistmessage-initnew.md) <br/> |初始化新邮件。  <br/> |
|[加载](ipersistmessage-load.md) <br/> |加载指定的消息的窗体。  <br/> |
|[Save](ipersistmessage-save.md) <br/> |将修订后的表单保存回其已加载或创建的邮件。  <br/> |
|[SaveCompleted](ipersistmessage-savecompleted.md) <br/> |通知窗体的保存操作已完成。  <br/> |
|[HandsOffMessage](ipersistmessage-handsoffmessage.md) <br/> |使窗体释放其当前邮件。  <br/> |
   
## <a name="remarks"></a>备注

实现**IPersistMessage**接口所需的所有表单。 
  
 **IPersistMessage**同样适用于 OLE [IPersistStorage](http://msdn.microsoft.com/library/1c1a20fc-c101-4cbc-a7a6-30613aa387d7%28Office.15%29.aspx)接口。 有关详细信息，请参阅**IPersistStorage**方法。 
  
## <a name="see-also"></a>另请参阅



[MAPI 接口](mapi-interfaces.md)

