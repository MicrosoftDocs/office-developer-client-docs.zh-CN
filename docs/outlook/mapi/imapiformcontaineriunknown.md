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
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 39f255a277403073132dfd3cd21c995eefe904c9
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775400"
---
# <a name="imapiformcontainer--iunknown"></a>IMAPIFormContainer: IUnknown

  
  
**适用于**： Outlook 
  
管理表单库中的窗体。 此接口用于创建特定于应用程序的表单库。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapiform.h  <br/> |
|由公开：  <br/> |窗体的容器对象  <br/> |
|通过实现：  <br/> |窗体库提供程序  <br/> |
|调用：  <br/> |客户端应用程序  <br/> |
|接口标识符：  <br/> |IID_IMAPIFormContainer  <br/> |
|指针类型：  <br/> |LPMAPIFORMCONTAINER  <br/> |
   
## <a name="vtable-order"></a>Vtable 顺序排列

|||
|:-----|:-----|
|[InstallForm](imapiformcontainer-installform.md) <br/> |将窗体安装到窗体容器。  <br/> |
|[RemoveForm](imapiformcontainer-removeform.md) <br/> |从窗体容器中删除特定的窗体。  <br/> |
|[ResolveMessageClass](imapiformcontainer-resolvemessageclass.md) <br/> |解析为其窗体的窗体容器中的邮件类，并返回该窗体的窗体信息对象。  <br/> |
|[ResolveMultipleMessageClasses](imapiformcontainer-resolvemultiplemessageclasses.md) <br/> |解析为其在窗体容器中的窗体的邮件类的一组，并返回这些表单的信息对象的窗体的数组。  <br/> |
|[CalcFormPropSet](imapiformcontainer-calcformpropset.md) <br/> |返回一个数组由安装窗体容器中的所有窗体的属性。  <br/> |
|[GetDisplay](imapiformcontainer-getdisplay.md) <br/> |返回一个窗体容器的显示名称。  <br/> |
|[时出错](imapiformcontainer-getlasterror.md) <br/> |返回包含有关以前对窗体容器对象发生的错误的信息的[MAPIERROR](mapierror.md)结构。  <br/> |
   
## <a name="see-also"></a>另请参阅



[MAPI 接口](mapi-interfaces.md)

