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
ms.openlocfilehash: aed9120ac264a6c47c9d02502093e56d3268d08a
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33435143"
---
# <a name="ipropdata--imapiprop"></a>IPropData : IMAPIProp

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
提供检索和更改对象的属性的访问权限的功能。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapiutil  <br/> |
|公开者:  <br/> |属性数据对象  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |服务提供商和客户端应用程序  <br/> |
|接口标识符:  <br/> |IID_IMAPIPropData  <br/> |
|指针类型:  <br/> |LPPROPDATA  <br/> |
|事务模型:  <br/> |Nontransacted  <br/> |
   
## <a name="vtable-order"></a>Vtable 顺序

|||
|:-----|:-----|
|[HrSetObjAccess](ipropdata-hrsetobjaccess.md) <br/> |设置对象的访问级别。  <br/> |
|[HrSetPropAccess](ipropdata-hrsetpropaccess.md) <br/> |设置一个或多个对象属性的访问级别和状态。  <br/> |
|[HrGetPropAccess](ipropdata-hrgetpropaccess.md) <br/> |检索一个或多个对象属性的访问级别和状态。  <br/> |
|[HrAddObjProps](ipropdata-hraddobjprops.md) <br/> |将 PT_OBJECT 类型的一个或多个属性添加到对象中。  <br/> |
   
## <a name="remarks"></a>说明

**IPropData:: IMAPIProp**接口由 MAPI 实现, 并且主要由可通过调用[CreateIProp](createiprop.md)函数来访问此实现的服务提供程序使用。 
  
有关对象和属性的访问级别的详细信息, 请参阅[对象和属性的权限](permissions-for-mapi-objects-and-properties.md)。
  
## <a name="see-also"></a>另请参阅



[MAPI 接口](mapi-interfaces.md)

