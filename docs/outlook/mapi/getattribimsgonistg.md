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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33439994"
---
# <a name="getattribimsgonistg"></a>GetAttribIMsgOnIStg

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
检索[由 OpenIMsgOnIStg](openimsgonistg.md)函数提供的[IMessage](imessageimapiprop.md)对象的属性属性。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Imessage.h  <br/> |
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
  
> [in]指向从 [OpenIMsgOnIStg](openimsgonistg.md)函数获取的 **IMessage** 对象的指针。 
    
 _lpPropTagArray_
  
> [in]指向 [SPropTagArray](sproptagarray.md) 结构的指针，其中包含指示要检索其属性的属性标记数组。 
    
 _lppPropAttrArray_
  
> [out]指向返回的 [SPropAttrArray](spropattrarray.md) 结构（包含检索的属性属性）的指针的指针。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功并返回了预期值。 
    
MAPI_W_ERRORS_RETURNED 
  
> 调用整体成功，但无法访问一个或多个属性，并且返回的属性类型为 PT_ERROR。
    
## <a name="remarks"></a>备注

只能在属性对象（即实现 [IMAPIProp ： IUnknown](imapipropiunknown.md) 接口的对象）上访问属性属性。 若要使 MAPI 属性在 OLE 结构化存储对象上可用 [，OpenIMsgOnIStg](openimsgonistg.md)在 OLE **IStorage** 对象顶部构建 [IMessage ： IMAPIProp](imessageimapiprop.md)对象。 可以使用 [SetAttribIMsgOnIStg](setattribimsgonistg.md) 设置或更改此类对象的属性属性，然后使用 **GetAttribIMsgOnIStg 进行检索**。 
  
> [!NOTE]
> **GetAttribIMsgOnIStg** 和 **SetAttribIMsgOnIStg** 不在所有 **IMessage** 对象上操作。 它们仅对 **OpenIMsgOnIStg** 返回的 **IMessage**-on- **IStorage** 对象有效。 
  
_lppPropAttrArray_ 参数中属性的数量和位置对应于 _lpPropTagArray_ 参数中属性标记的数量和位置。 
  

