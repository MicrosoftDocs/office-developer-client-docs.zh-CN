---
title: IMAPIFormContainer IUnknown
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIFormContainer
api_type:
- COM
ms.assetid: 437c8a75-1121-4919-8bd4-d57c0d6f4b9a
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 208af28307a60615ecafda0992881c5df36aa56f
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32342187"
---
# <a name="imapiformcontainer--iunknown"></a>IMAPIFormContainer : IUnknown

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
管理表单库中的表单。 此接口用于创建特定于应用程序的表单库。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapiform  <br/> |
|公开者:  <br/> |表单容器对象  <br/> |
|实现者：  <br/> |表单库提供程序  <br/> |
|调用者：  <br/> |客户端应用程序  <br/> |
|接口标识符:  <br/> |IID_IMAPIFormContainer  <br/> |
|指针类型:  <br/> |LPMAPIFORMCONTAINER  <br/> |
   
## <a name="vtable-order"></a>Vtable 顺序

|||
|:-----|:-----|
|[InstallForm](imapiformcontainer-installform.md) <br/> |将表单安装到表单容器中。  <br/> |
|[RemoveForm](imapiformcontainer-removeform.md) <br/> |从表单容器中删除特定的窗体。  <br/> |
|[ResolveMessageClass](imapiformcontainer-resolvemessageclass.md) <br/> |将邮件类别解析为表单容器中的窗体, 并返回该窗体的窗体信息对象。  <br/> |
|[ResolveMultipleMessageClasses](imapiformcontainer-resolvemultiplemessageclasses.md) <br/> |将一组消息类解析为表单容器中的窗体, 并返回这些窗体的窗体信息对象的数组。  <br/> |
|[CalcFormPropSet](imapiformcontainer-calcformpropset.md) <br/> |返回安装在表单容器中的所有表单所使用的属性的数组。  <br/> |
|[GetDisplay](imapiformcontainer-getdisplay.md) <br/> |返回表单容器的显示名称。  <br/> |
|[GetLastError](imapiformcontainer-getlasterror.md) <br/> |返回一个[MAPIERROR](mapierror.md)结构, 其中包含有关在表单容器对象中发生的上一个错误的信息。  <br/> |
   
## <a name="see-also"></a>另请参阅



[MAPI 接口](mapi-interfaces.md)

