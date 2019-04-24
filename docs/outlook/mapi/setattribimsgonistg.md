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
ms.openlocfilehash: 852ce31ba5ab02ff8f05dee25c9b32acb73130ec
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32337966"
---
# <a name="setattribimsgonistg"></a>SetAttribIMsgOnIStg

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
设置或更改[OpenIMsgOnIStg](openimsgonistg.md)函数提供的[IMessage](imessageimapiprop.md)对象的属性属性。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Imessage  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |客户端应用程序和邮件存储提供程序  <br/> |
   
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
  
> 实时指向要为其设置属性属性的对象的指针。 
    
 _lpPropTags_
  
> 实时指向[SPropTagArray](sproptagarray.md)结构的指针, 该结构包含指明要为其设置属性属性的属性标记的数组。 
    
 _lpPropAttrs_
  
> 实时指向列表要设置的属性属性的[SPropAttrArray](spropattrarray.md)结构的指针。 
    
 _lppPropProblems_
  
> 排除指向包含一组属性问题的返回的[SPropProblemArray](spropproblemarray.md)结构的指针。 此结构确定在**SetAttribIMsgOnIStg**能够设置某些属性 (而非全部) 的情况下遇到的问题。 如果在_lppPropProblems_参数中传递指向 NULL 的指针, 则即使未设置某些属性, 也不会返回任何属性问题数组。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功, 并返回了所需的值或值。
    
MAPI_W_ERRORS_RETURNED 
  
> 调用全部成功, 但无法访问一个或多个属性, 并使用 PT_ERROR 的属性类型返回。
    
## <a name="remarks"></a>注解

只能在属性对象 (即实现[IMAPIProp: IUnknown](imapipropiunknown.md)接口的对象) 上访问属性属性。 若要使 MAPI 属性在 ole 结构化存储对象上可用, [OpenIMsgOnIStg](openimsgonistg.md)在 ole **IStorage**对象的顶部生成[IMessage: IMAPIProp](imessageimapiprop.md)对象。 此类对象上的属性属性可以使用**SetAttribIMsgOnIStg**进行设置或更改, 并可使用[GetAttribIMsgOnIStg](getattribimsgonistg.md)进行检索。 
  
 **注释****GetAttribIMsgOnIStg**和**SetAttribIMsgOnIStg**不对所有**IMessage**对象进行操作。 它们仅对**OpenIMsgOnIStg**返回的**IMessage** **IStorage**对象有效。 
  
在_lpPropAttrs_参数中, 属性的数目和位置必须与_lpPropTags_参数中传递的属性标记的编号和位置相匹配。 
  
**SetAttribIMsgOnIStg**函数用于在**IMessage**架构需要时使邮件属性成为只读的。 示例邮件存储提供程序将使用它来实现此目的。 有关详细信息, 请参阅[消息](mapi-messages.md)。 
  

