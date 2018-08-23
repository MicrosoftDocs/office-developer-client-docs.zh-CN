---
title: SetAttribIMsgOnIStg
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.SetAttribIMsgOnIStg
api_type:
- COM
ms.assetid: 683d0d00-1b93-445d-86ff-180a3e6d2323
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 076fb4946af9a80e53fb8452d720c22b351f5ef6
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22572520"
---
# <a name="setattribimsgonistg"></a>SetAttribIMsgOnIStg

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
设置或更改的属性由[OpenIMsgOnIStg](openimsgonistg.md)函数提供[IMessage](imessageimapiprop.md)对象的属性。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Imessage.h  <br/> |
|通过实现：  <br/> |MAPI  <br/> |
|调用：  <br/> |客户端应用程序和消息存储提供程序  <br/> |
   
```cpp
HRESULT SetAttribIMsgOnIStg(
  LPVOID lpObject,
  LPSPropTagArray lpPropTags,
  LPSPropAttrArray lpPropAttrs,
  LPSPropProblemArray FAR * lppPropProblems
);
```

## <a name="parameters"></a>参数

 _lpObject_
  
> [in]指向属性设置的属性的对象的指针。 
    
 _lpPropTags_
  
> [in]指向包含属性标记，指示属性设置的属性的属性的数组[SPropTagArray](sproptagarray.md)结构。 
    
 _lpPropAttrs_
  
> [in]指向列出属性属性设置[SPropAttrArray](spropattrarray.md)结构。 
    
 _lppPropProblems_
  
> [输出]返回[SPropProblemArray](spropproblemarray.md)结构包含一组属性问题的指针。 此结构标识**SetAttribIMsgOnIStg**已能够设置某些属性，而不是全部如果遇到问题。 如果_lppPropProblems_参数中传递为 NULL 的指针，即使未设置某些属性，则返回没有属性问题数组。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 呼叫成功或多个预期值返回。
    
MAPI_W_ERRORS_RETURNED 
  
> 调用成功总体上讲，但无法访问并已返回与 PT_ERROR 属性类型的一个或多个属性。
    
## <a name="remarks"></a>注解

Property 属性只能在 property 对象，即，实现的对象上访问[IMAPIProp: IUnknown](imapipropiunknown.md)接口。 使 MAPI 属性 OLE 结构化的存储对象上可用， [OpenIMsgOnIStg](openimsgonistg.md)生成[IMessage: IMAPIProp](imessageimapiprop.md) OLE **IStorage**对象上的对象。 此类对象上的属性属性可以设置或更改与**SetAttribIMsgOnIStg**和检索与[GetAttribIMsgOnIStg](getattribimsgonistg.md)。 
  
 **注释****GetAttribIMsgOnIStg**和**SetAttribIMsgOnIStg**请勿对所有**IMessage**对象。 它们只是有效的**IMessage**上返回**OpenIMsgOnIStg** **IStorage**对象。 
  
在_lpPropAttrs_参数的数量和位置的属性必须匹配的数量和_lpPropTags_参数中传递的属性标记的位置。 
  
**SetAttribIMsgOnIStg**函数用于只读时所需的**IMessage**架构进行邮件属性。 示例邮件存储提供程序将使用它实现此目的。 有关详细信息，请参阅[消息](mapi-messages.md)。 
  

