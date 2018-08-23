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
ms.openlocfilehash: a397ac9110429911755552298ffe244343d54a8a
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22583727"
---
# <a name="imapiprop--iunknown"></a>IMAPIProp : IUnknown

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
使客户端、 服务提供商和 MAPI 处理属性。 支持属性的所有对象都实现此接口。
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapidefs.h  <br/> |
|由公开：  <br/> |没有对象直接公开此接口。  <br/> |
|通过实现：  <br/> |服务提供商和 MAPI  <br/> |
|调用：  <br/> |客户端应用程序、 服务提供商和 MAPI  <br/> |
|接口标识符：  <br/> |IID_IMAPIProp  <br/> |
|指针类型：  <br/> |LPMAPIPROP  <br/> |
|事务模型：  <br/> |从不实现抽象类  <br/> |
   
## <a name="vtable-order"></a>Vtable 顺序排列

|||
|:-----|:-----|
|[时出错](imapiprop-getlasterror.md) <br/> |返回一个[MAPIERROR](mapierror.md)结构，其中包含有关前面的错误的信息。  <br/> |
|[SaveChanges](imapiprop-savechanges.md) <br/> |使永久自上次保存操作对对象进行的任何更改。  <br/> |
|[GetProps](imapiprop-getprops.md) <br/> |检索一个或多个对象的属性的属性值。  <br/> |
|[GetPropList](imapiprop-getproplist.md) <br/> |返回所有属性的属性标记。  <br/> |
|[OpenProperty](imapiprop-openproperty.md) <br/> |返回可用于访问属性的接口的指针。  <br/> |
|[SetProps](imapiprop-setprops.md) <br/> |更新一个或多个属性。  <br/> |
|[DeleteProps](imapiprop-deleteprops.md) <br/> |从对象中删除一个或多个属性。  <br/> |
|[CopyTo](imapiprop-copyto.md) <br/> |复制或移动的所有属性，特别是排除属性除外。  <br/> |
|[CopyProps](imapiprop-copyprops.md) <br/> |复制或移动所选的属性。  <br/> |
|[GetNamesFromIDs](imapiprop-getnamesfromids.md) <br/> |提供对应于一个或多个属性标识符的属性名称。  <br/> |
|[GetIDsFromNames](imapiprop-getidsfromnames.md) <br/> |提供属性的标识符的对应于一个或多个属性的名称。  <br/> |
   
## <a name="remarks"></a>注解

 **IMAPIProp**是以下接口的基接口： 
  
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

