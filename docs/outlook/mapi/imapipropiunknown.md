---
title: IMAPIProp IUnknown
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIProp
api_type:
- COM
ms.assetid: 3c9e4e05-cd3a-4b56-9dff-879e33ff6fd5
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 6b0a8923ee5efe22584170ce9853698885527ee8
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32282469"
---
# <a name="imapiprop--iunknown"></a>IMAPIProp : IUnknown

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
使客户端、服务提供程序和 MAPI 能够使用属性。 所有支持属性的对象都实现此接口。
  
|||
|:-----|:-----|
|标头文件：  <br/> |mapidefs。h  <br/> |
|公开者:  <br/> |无对象直接公开此接口。  <br/> |
|实现者：  <br/> |服务提供商和 MAPI  <br/> |
|调用者：  <br/> |客户端应用程序、服务提供程序和 MAPI  <br/> |
|接口标识符:  <br/> |IID_IMAPIProp  <br/> |
|指针类型:  <br/> |LPMAPIPROP  <br/> |
|事务模型:  <br/> |抽象类, 从未实现  <br/> |
   
## <a name="vtable-order"></a>Vtable 顺序

|||
|:-----|:-----|
|[GetLastError](imapiprop-getlasterror.md) <br/> |返回一个[MAPIERROR](mapierror.md)结构, 该结构包含上一个错误的相关信息。  <br/> |
|[SaveChanges](imapiprop-savechanges.md) <br/> |使自上次保存操作后对对象进行的任何更改成为永久性的。  <br/> |
|[GetProps](imapiprop-getprops.md) <br/> |检索对象的一个或多个属性的属性值。  <br/> |
|[GetPropList](imapiprop-getproplist.md) <br/> |返回所有属性的属性标记。  <br/> |
|[OpenProperty](imapiprop-openproperty.md) <br/> |返回指向可用于访问属性的接口的指针。  <br/> |
|[SetProps](imapiprop-setprops.md) <br/> |更新一个或多个属性。  <br/> |
|[DeleteProps](imapiprop-deleteprops.md) <br/> |从对象中删除一个或多个属性。  <br/> |
|[CopyTo](imapiprop-copyto.md) <br/> |复制或移动所有属性, 但特殊排除的属性除外。  <br/> |
|[CopyProps](imapiprop-copyprops.md) <br/> |复制或移动选定的属性。  <br/> |
|[GetNamesFromIDs](imapiprop-getnamesfromids.md) <br/> |提供与一个或多个属性标识符相对应的属性名称。  <br/> |
|[GetIDsFromNames](imapiprop-getidsfromnames.md) <br/> |提供与一个或多个属性名称对应的属性标识符。  <br/> |
   
## <a name="remarks"></a>注解

 **IMAPIProp**是以下接口的基接口: 
  
- [IAttach](iattachimapiprop.md)
    
- [IMailUser](imailuserimapiprop.md)
    
- [IMAPIContainer](imapicontainerimapiprop.md)
    
- [IMAPIFormInfo](imapiforminfoimapiprop.md)
    
- [IMAPIStatus](imapistatusimapiprop.md)
    
- [IMessage](imessageimapiprop.md)
    
- [IMsgStore](imsgstoreimapiprop.md)
    
- [IProfSect](iprofsectimapiprop.md)
    
- [IPropData](ipropdataimapiprop.md)
    
## <a name="see-also"></a>另请参阅



[MAPI 接口](mapi-interfaces.md)

