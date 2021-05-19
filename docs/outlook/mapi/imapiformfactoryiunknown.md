---
title: IMAPIFormFactory IUnknown
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIFormFactory
api_type:
- COM
ms.assetid: 637be364-c393-430a-84b3-2c96aa553c22
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: c60b542852653bd617b5b9f604bbc44d575e5cb3
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32342117"
---
# <a name="imapiformfactory--iunknown"></a>IMAPIFormFactory : IUnknown

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
支持在分布式计算环境中使用可配置的运行时表单。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapiform.h  <br/> |
|公开者：  <br/> |表单工厂对象  <br/> |
|实现者：  <br/> |表单服务器  <br/> |
|调用者：  <br/> |表单查看器  <br/> |
|接口标识符：  <br/> |IID_IMAPIFormFactory  <br/> |
|指针类型：  <br/> |LPMAPIFORMFACTORY  <br/> |
   
## <a name="vtable-order"></a>Vtable 顺序

|||
|:-----|:-----|
|[CreateClassFactory](imapiformfactory-createclassfactory.md) <br/> |返回窗体的类工厂对象。  <br/> |
|[GetLastError](imapiformfactory-getlasterror.md) <br/> |返回 [一个 MAPIERROR](mapierror.md) 结构，其中包含有关表单工厂对象发生的上一个错误的信息。  <br/> |
|[LockServer](imapiformfactory-lockserver.md) <br/> |将打开的表单服务器保留到内存中。  <br/> |
   
## <a name="remarks"></a>备注

**IMAPIFormFactory** 接口基于 [IClassFactory](https://msdn.microsoft.com/library/ms694364%28VS.85%29.aspx)接口，并且实现 **IMAPIFormFactory** 的对象还应从 **IClassFactory 继承**。
  
 **IMAPIFormFactory** 是表单查看器在表单服务器支持多个邮件类（即多个表单对象类型）时 (创建新的表单对象的接口) 。 
  
## <a name="see-also"></a>另请参阅



[MAPI 接口](mapi-interfaces.md)

