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
ms.openlocfilehash: 651ef6a7c1af70c75a85e13414c4fd7632d30290
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775415"
---
# <a name="imapiformfactory--iunknown"></a>IMAPIFormFactory : IUnknown

  
  
**适用于**： Outlook 
  
支持在分布式计算环境中的可配置的运行时窗体。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapiform.h  <br/> |
|由公开：  <br/> |窗体中心对象  <br/> |
|通过实现：  <br/> |表单服务器  <br/> |
|调用：  <br/> |表单查看器  <br/> |
|接口标识符：  <br/> |IID_IMAPIFormFactory  <br/> |
|指针类型：  <br/> |LPMAPIFORMFACTORY  <br/> |
   
## <a name="vtable-order"></a>Vtable 顺序排列

|||
|:-----|:-----|
|[CreateClassFactory](imapiformfactory-createclassfactory.md) <br/> |返回窗体类工厂对象。  <br/> |
|[时出错](imapiformfactory-getlasterror.md) <br/> |返回一个[MAPIERROR](mapierror.md)结构，其中包含有关前面对窗体中心对象发生的错误的信息。  <br/> |
|[LockServer](imapiformfactory-lockserver.md) <br/> |在内存中保留的打开的窗体服务器。  <br/> |
   
## <a name="remarks"></a>说明

**IMAPIFormFactory**接口基于[IClassFactory](http://msdn.microsoft.com/en-us/library/ms694364%28VS.85%29.aspx)接口，并实现**IMAPIFormFactory**对象应还继承**IClassFactory**。
  
 **IMAPIFormFactory**是表单查看器用于创建新表单对象时窗体服务器支持多个邮件类的接口 （即，多个窗体的对象的类型）。 
  
## <a name="see-also"></a>另请参阅



[MAPI 接口](mapi-interfaces.md)

