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
ms.openlocfilehash: fa439d0a6fa59bac787f09c3f894a750948a0a3e
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775410"
---
# <a name="imapiforminfo--imapiprop"></a>IMAPIFormInfo : IMAPIProp

  
  
**适用于**： Outlook 
  
提供客户端应用程序访问的特定于窗体定义的属性。 通过将表单信息保持在独立的对象，表单库提供程序可以描述客户端的表单，而不激活窗体。
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapiform.h  <br/> |
|由公开：  <br/> |窗体信息对象  <br/> |
|通过实现：  <br/> |窗体库提供程序  <br/> |
|调用：  <br/> |客户端应用程序  <br/> |
|接口标识符：  <br/> |IID_IMAPIFormInfo  <br/> |
|指针类型：  <br/> |LPMAPIFORMINFO  <br/> |
|事务模型：  <br/> |Nontransacted  <br/> |
   
## <a name="vtable-order"></a>Vtable 顺序排列

|||
|:-----|:-----|
|[CalcFormPropSet](imapiforminfo-calcformpropset.md) <br/> |向窗体使用的属性的完整集合中返回的指针。  <br/> |
|[CalcVerbSet](imapiforminfo-calcverbset.md) <br/> |到谓词窗体所使用的完整集合中返回的指针。  <br/> |
|[MakeIconFromBinary](imapiforminfo-makeiconfrombinary.md) <br/> |生成来自窗体的 icon 属性的图标。  <br/> |
|[SaveForm](imapiforminfo-saveform.md) <br/> |配置文件中保存窗体特定的说明。  <br/> |
|[OpenFormContainer](imapiforminfo-openformcontainer.md) <br/> |返回到安装了特定的窗体的窗体容器的指针。  <br/> |
   
## <a name="remarks"></a>说明

与大多数 MapiForm.h 标头文件中定义的接口，不同**IMAPIFormInfo**从[IMAPIProp](imapipropiunknown.md)接口继承，因为它导出通过调用[IMAPIProp::GetProps](imapiprop-getprops.md)方法的大多数表单信息。 
  
## <a name="see-also"></a>另请参阅



[MAPI 接口](mapi-interfaces.md)

