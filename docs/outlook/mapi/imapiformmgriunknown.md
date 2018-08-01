---
title: IMAPIFormMgr IUnknown
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIFormMgr
api_type:
- COM
ms.assetid: 8cbd1a42-7de6-43e0-8c77-7711773843d5
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 4fdd50a1108a6546445516664b01fb0f994fbfdb
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775443"
---
# <a name="imapiformmgr--iunknown"></a>IMAPIFormMgr : IUnknown

  
  
**适用于**： Outlook 
  
启用表单查看器获取有关的信息和激活窗体服务器。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapiform.h  <br/> |
|由公开：  <br/> |窗体管理器对象  <br/> |
|通过实现：  <br/> |窗体库提供程序  <br/> |
|调用：  <br/> |表单查看器  <br/> |
|接口标识符：  <br/> |IID_IMAPIFormMgr  <br/> |
|指针类型：  <br/> |LPMAPIFORMMGR  <br/> |
   
## <a name="vtable-order"></a>Vtable 顺序排列

|||
|:-----|:-----|
|[LoadForm](imapiformmgr-loadform.md) <br/> |启动打开现有邮件窗体。  <br/> |
|[ResolveMessageClass](imapiformmgr-resolvemessageclass.md) <br/> |将邮件类解析为其表单中的窗体容器中，并返回该窗体的窗体信息对象。  <br/> |
|[ResolveMultipleMessageClasses](imapiformmgr-resolvemultiplemessageclasses.md) <br/> |将一组的邮件类解析为其的窗体中的窗体容器中，并返回这些表单的信息对象的窗体的数组。  <br/> |
|[CalcFormPropSet](imapiformmgr-calcformpropset.md) <br/> |返回一个数组的一组表单使用的属性。  <br/> |
|[CreateForm](imapiformmgr-createform.md) <br/> |启动表单创建新邮件基于窗体的邮件类别。  <br/> |
|[SelectForm](imapiformmgr-selectform.md) <br/> |显示一个对话框，允许用户选择一个窗体，并返回描述该窗体的窗体信息对象。  <br/> |
|[SelectMultipleForms](imapiformmgr-selectmultipleforms.md) <br/> |显示一个对话框，使用户能够选择多个表单，并返回介绍这些表单的信息对象的窗体的数组。  <br/> |
|[SelectFormContainer](imapiformmgr-selectformcontainer.md) <br/> |显示一个对话框，使用户能够选择窗体容器，并返回对 container 对象选定的用户界面。  <br/> |
|[OpenFormContainer](imapiformmgr-openformcontainer.md) <br/> |打开特定窗体容器[IMAPIFormContainer](imapiformcontaineriunknown.md)界面。  <br/> |
|[PrepareForm](imapiformmgr-prepareform.md) <br/> |下载用于打开的表单。  <br/> |
|[IsInConflict](imapiformmgr-isinconflict.md) <br/> |确定窗体是否可以处理其自己的邮件冲突。  <br/> |
|[时出错](imapiformmgr-getlasterror.md) <br/> |返回一个[MAPIERROR](mapierror.md)结构，其中包含有关前面对窗体管理器对象发生的错误的信息。  <br/> |
   
## <a name="see-also"></a>另请参阅



[MAPI 接口](mapi-interfaces.md)

