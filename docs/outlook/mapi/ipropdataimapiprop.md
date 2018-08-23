---
title: IPropData IMAPIProp
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IPropData
api_type:
- COM
ms.assetid: 30b8ae9e-0c0c-4468-b286-29e083696fed
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: c320b2c42b9a14c6dc428fc3df59991528cdbe36
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22592568"
---
# <a name="ipropdata--imapiprop"></a>IPropData : IMAPIProp

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
提供能够检索和更改对象的属性的访问。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapiutil.h  <br/> |
|由公开：  <br/> |属性的数据对象  <br/> |
|通过实现：  <br/> |MAPI  <br/> |
|调用：  <br/> |服务提供商和客户端应用程序  <br/> |
|接口标识符：  <br/> |IID_IMAPIPropData  <br/> |
|指针类型：  <br/> |LPPROPDATA  <br/> |
|事务模型：  <br/> |Nontransacted  <br/> |
   
## <a name="vtable-order"></a>Vtable 顺序排列

|||
|:-----|:-----|
|[HrSetObjAccess](ipropdata-hrsetobjaccess.md) <br/> |设置该对象的访问级别。  <br/> |
|[HrSetPropAccess](ipropdata-hrsetpropaccess.md) <br/> |设置访问级别和一个或多个对象的属性的状态。  <br/> |
|[HrGetPropAccess](ipropdata-hrgetpropaccess.md) <br/> |检索的访问级别和一个或多个对象的属性的状态。  <br/> |
|[HrAddObjProps](ipropdata-hraddobjprops.md) <br/> |添加到对象类型 PT_OBJECT 的一个或多个属性。  <br/> |
   
## <a name="remarks"></a>注解

**IPropData::IMAPIProp**接口是由 MAPI 实现，主要由服务提供商访问此实现通过调用[CreateIProp](createiprop.md)函数。 
  
有关访问级别上对象和属性的详细信息，请参阅[权限对象和属性](permissions-for-mapi-objects-and-properties.md)。
  
## <a name="see-also"></a>另请参阅



[MAPI 接口](mapi-interfaces.md)

