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
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 7eb65bbae2fca6648c3a701dfa5c83c5bf297ec5
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32309602"
---
# <a name="ipersistmessage--iunknown"></a>IPersistMessage : IUnknown

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
使表单查看者能够处理表单的存储并在各种状态之间切换。
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapiform  <br/> |
|公开者:  <br/> |持久化邮件对象  <br/> |
|实现者：  <br/> |表单对象  <br/> |
|调用者：  <br/> |表单查看器  <br/> |
|接口标识符:  <br/> |IID_IPersistMessage  <br/> |
|指针类型:  <br/> |LPPERSISTMESSAGE  <br/> |
   
## <a name="vtable-order"></a>Vtable 顺序

|||
|:-----|:-----|
|[GetLastError](ipersistmessage-getlasterror.md) <br/> |返回一个[MAPIERROR](mapierror.md)结构, 该结构包含有关 form 对象中的前一个错误的信息。  <br/> |
|[GetClassID](ipersistmessage-getclassid.md) <br/> |返回一个标识符, 表示可以管理窗体的窗体服务器。  <br/> |
|[IsDirty](ipersistmessage-isdirty.md) <br/> |检查表单的上次保存以来所做的更改。  <br/> |
|[InitNew](ipersistmessage-initnew.md) <br/> |初始化新邮件。  <br/> |
|[Load](ipersistmessage-load.md) <br/> |为指定的邮件加载窗体。  <br/> |
|[Save](ipersistmessage-save.md) <br/> |将修订后的表单重新保存到从中加载或创建该表单的邮件中。  <br/> |
|[SaveCompleted](ipersistmessage-savecompleted.md) <br/> |通知表单保存操作已完成。  <br/> |
|[HandsOffMessage](ipersistmessage-handsoffmessage.md) <br/> |使窗体释放其当前的邮件。  <br/> |
   
## <a name="remarks"></a>注解

所有表单都必须实现**IPersistMessage**接口。 
  
 **IPersistMessage**的工作方式类似于 OLE [IPersistStorage](https://msdn.microsoft.com/library/1c1a20fc-c101-4cbc-a7a6-30613aa387d7%28Office.15%29.aspx)接口。 有关详细信息, 请参阅**IPersistStorage**方法。 
  
## <a name="see-also"></a>另请参阅



[MAPI 接口](mapi-interfaces.md)

