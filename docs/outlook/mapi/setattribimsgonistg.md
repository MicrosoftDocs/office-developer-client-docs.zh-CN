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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33428828"
---
# <a name="setattribimsgonistg"></a>SetAttribIMsgOnIStg

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
设置或更改[OpenIMsgOnIStg](openimsgonistg.md)函数提供的[IMessage](imessageimapiprop.md)对象的属性属性。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Imessage.h  <br/> |
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
  
> [in]指向要设置其属性的对象的指针。 
    
 _lpPropTags_
  
> [in]指向 [SPropTagArray](sproptagarray.md) 结构的指针，该结构包含一组指示要设置的属性属性的属性标记。 
    
 _lpPropAttrs_
  
> [in]指向列出要设置的属性属性的 [SPropAttrArray](spropattrarray.md) 结构的指针。 
    
 _lppPropProblems_
  
> [out]指向返回的包含一组属性问题的 [SPropProblemArray](spropproblemarray.md) 结构的指针。 此结构标识 **SetAttribIMsgOnIStg** 能够设置某些属性（而不是所有属性）时遇到的问题。 如果在  _lppPropProblems_ 参数中传递指向 NULL 的指针，则即使未设置某些属性，也将不会返回任何属性问题数组。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功并返回了预期值。
    
MAPI_W_ERRORS_RETURNED 
  
> 调用整体成功，但无法访问一个或多个属性，并且返回的属性类型为 PT_ERROR。
    
## <a name="remarks"></a>备注

只能在属性对象（即实现 [IMAPIProp ： IUnknown](imapipropiunknown.md) 接口的对象）上访问属性属性。 若要使 MAPI 属性在 OLE 结构化存储对象上可用 [，OpenIMsgOnIStg](openimsgonistg.md)在 OLE **IStorage** 对象顶部构建 [IMessage ： IMAPIProp](imessageimapiprop.md)对象。 可以使用 **SetAttribIMsgOnIStg** 设置或更改此类对象的属性属性，然后使用 [GetAttribIMsgOnIStg 进行检索](getattribimsgonistg.md)。 
  
 **注意****GetAttribIMsgOnIStg** 和 **SetAttribIMsgOnIStg** 不在所有 **IMessage** 对象上操作。 它们仅对 **OpenIMsgOnIStg** 返回的 **IMessage**-on- **IStorage** 对象有效。 
  
在  _lpPropAttrs_ 参数中，属性的数量和位置必须与在  _lpPropTags_ 参数中传递的属性标记的数量和位置相匹配。 
  
**SetAttribIMsgOnIStg** 函数用于使邮件属性在 **IMessage** 架构需要时为只读。 示例邮件存储提供程序会使用它来达到此目的。 有关详细信息， [请参阅邮件](mapi-messages.md)。 
  

