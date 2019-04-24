---
title: IMAPIFormInfo IMAPIProp
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIFormInfo
api_type:
- COM
ms.assetid: a9fda518-11ba-42aa-85ef-dd2279e0319d
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 3913cb04f1f2f61ba6835b704f430d872756b227
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32321733"
---
# <a name="imapiforminfo--imapiprop"></a>IMAPIFormInfo : IMAPIProp

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
为客户端应用程序提供特定于表单定义的属性的访问权限。 通过将表单信息保存在单独的对象中, 表单库提供程序可以向客户端说明表单, 而无需激活表单。
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapiform  <br/> |
|公开者:  <br/> |表单信息对象  <br/> |
|实现者：  <br/> |表单库提供程序  <br/> |
|调用者：  <br/> |客户端应用程序  <br/> |
|接口标识符:  <br/> |IID_IMAPIFormInfo  <br/> |
|指针类型:  <br/> |LPMAPIFORMINFO  <br/> |
|事务模型:  <br/> |Nontransacted  <br/> |
   
## <a name="vtable-order"></a>Vtable 顺序

|||
|:-----|:-----|
|[CalcFormPropSet](imapiforminfo-calcformpropset.md) <br/> |返回一个指针, 该指针指向表单使用的完整属性集。  <br/> |
|[CalcVerbSet](imapiforminfo-calcverbset.md) <br/> |返回一个指针, 指向表单使用的完整的一组谓词。  <br/> |
|[MakeIconFromBinary](imapiforminfo-makeiconfrombinary.md) <br/> |从窗体的图标属性生成图标。  <br/> |
|[SaveForm](imapiforminfo-saveform.md) <br/> |在配置文件中保存特定窗体的说明。  <br/> |
|[OpenFormContainer](imapiforminfo-openformcontainer.md) <br/> |返回一个指针, 指向在其中安装特定表单的表单容器。  <br/> |
   
## <a name="remarks"></a>注解

与 MapiForm 头文件中定义的大多数接口不同, **IMAPIFormInfo**继承自[IMAPIProp](imapipropiunknown.md)接口, 因为它通过调用[IMAPIProp:: GetProps](imapiprop-getprops.md)方法导出大部分表单信息。 
  
## <a name="see-also"></a>另请参阅



[MAPI 接口](mapi-interfaces.md)

