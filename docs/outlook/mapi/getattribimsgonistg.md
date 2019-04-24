---
title: GetAttribIMsgOnIStg
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.GetAttribIMsgOnIStg
api_type:
- COM
ms.assetid: bb27b28a-b2bd-4d4a-b0bb-0692f3de8e16
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 16e85eabc067bd82f5fb89c917afaf2831c75673
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32300467"
---
# <a name="getattribimsgonistg"></a>GetAttribIMsgOnIStg

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
检索[OpenIMsgOnIStg](openimsgonistg.md)函数提供的[IMessage](imessageimapiprop.md)对象上属性的属性。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Imessage  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |客户端应用程序和邮件存储提供程序  <br/> |
   
```cpp
HRESULT GetAttribIMsgOnIStg(
  LPVOID lpObject,
  LPSPropTagArray lpPropTagArray,
  LPSPropAttrArray FAR * lppPropAttrArray
);
```

## <a name="parameters"></a>参数

 _lpObject_
  
> 实时指向从[OpenIMsgOnIStg](openimsgonistg.md)函数获取的**IMessage**对象的指针。 
    
 _lpPropTagArray_
  
> 实时指向[SPropTagArray](sproptagarray.md)结构的指针, 该结构包含一个指明要检索其属性的属性的属性标记数组。 
    
 _lppPropAttrArray_
  
> 排除指向指向包含检索到的属性属性的返回[SPropAttrArray](spropattrarray.md)结构的指针的指针。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功, 并返回了所需的值或值。 
    
MAPI_W_ERRORS_RETURNED 
  
> 调用全部成功, 但无法访问一个或多个属性, 并使用 PT_ERROR 的属性类型返回。
    
## <a name="remarks"></a>注解

只能在属性对象 (即实现[IMAPIProp: IUnknown](imapipropiunknown.md)接口的对象) 上访问属性属性。 若要使 MAPI 属性在 ole 结构化存储对象上可用, [OpenIMsgOnIStg](openimsgonistg.md)在 ole **IStorage**对象的顶部生成[IMessage: IMAPIProp](imessageimapiprop.md)对象。 此类对象上的属性属性可以使用[SetAttribIMsgOnIStg](setattribimsgonistg.md)进行设置或更改, 并可使用**GetAttribIMsgOnIStg**进行检索。 
  
> [!NOTE]
> **GetAttribIMsgOnIStg**和**SetAttribIMsgOnIStg**不对所有**IMessage**对象进行操作。 它们仅对**OpenIMsgOnIStg**返回的**IMessage** **IStorage**对象有效。 
  
_lppPropAttrArray_参数中属性的数目和位置对应于_lpPropTagArray_参数中的属性标记的编号和位置。 
  

