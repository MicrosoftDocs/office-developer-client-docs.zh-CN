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
ms.openlocfilehash: fbe6dc9364ee953661d574b70bcd225abcfe7a81
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32321649"
---
# <a name="imapiformmgr--iunknown"></a>IMAPIFormMgr : IUnknown

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
使表单查看者能够获取和激活表单服务器的相关信息。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapiform  <br/> |
|公开者:  <br/> |表单管理器对象  <br/> |
|实现者：  <br/> |表单库提供程序  <br/> |
|调用者：  <br/> |表单查看器  <br/> |
|接口标识符:  <br/> |IID_IMAPIFormMgr  <br/> |
|指针类型:  <br/> |LPMAPIFORMMGR  <br/> |
   
## <a name="vtable-order"></a>Vtable 顺序

|||
|:-----|:-----|
|[LoadForm](imapiformmgr-loadform.md) <br/> |启动窗体以打开现有邮件。  <br/> |
|[ResolveMessageClass](imapiformmgr-resolvemessageclass.md) <br/> |将邮件类别解析为表单容器中的窗体, 并返回该窗体的窗体信息对象。  <br/> |
|[ResolveMultipleMessageClasses](imapiformmgr-resolvemultiplemessageclasses.md) <br/> |将一组消息类解析为表单容器中的表单, 并返回这些表单的表单信息对象的数组。  <br/> |
|[CalcFormPropSet](imapiformmgr-calcformpropset.md) <br/> |返回一组窗体使用的属性的数组。  <br/> |
|[CreateForm](imapiformmgr-createform.md) <br/> |启动窗体以根据窗体的邮件类创建新邮件。  <br/> |
|[SelectForm](imapiformmgr-selectform.md) <br/> |显示一个对话框, 使用户能够选择窗体, 并返回描述该窗体的窗体信息对象。  <br/> |
|[SelectMultipleForms](imapiformmgr-selectmultipleforms.md) <br/> |显示一个对话框, 允许用户选择多个窗体, 并返回描述这些窗体的窗体信息对象的数组。  <br/> |
|[SelectFormContainer](imapiformmgr-selectformcontainer.md) <br/> |显示一个对话框, 使用户可以选择表单容器, 并为用户选定的容器对象返回一个接口。  <br/> |
|[OpenFormContainer](imapiformmgr-openformcontainer.md) <br/> |打开特定表单容器的[IMAPIFormContainer](imapiformcontaineriunknown.md)接口。  <br/> |
|[PrepareForm](imapiformmgr-prepareform.md) <br/> |下载用于打开的表单。  <br/> |
|[IsInConflict](imapiformmgr-isinconflict.md) <br/> |确定表单是否可以处理自己的邮件冲突。  <br/> |
|[GetLastError](imapiformmgr-getlasterror.md) <br/> |返回一个[MAPIERROR](mapierror.md)结构, 该结构包含上一个错误发生于表单管理器对象的相关信息。  <br/> |
   
## <a name="see-also"></a>另请参阅



[MAPI 接口](mapi-interfaces.md)

