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
ms.openlocfilehash: 9e17e8ef7df33ffa248eec4195c00c77d0c49f94
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22587766"
---
# <a name="getattribimsgonistg"></a>GetAttribIMsgOnIStg

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
检索上提供[OpenIMsgOnIStg](openimsgonistg.md)函数的[IMessage](imessageimapiprop.md)对象的属性的属性。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Imessage.h  <br/> |
|通过实现：  <br/> |MAPI  <br/> |
|调用：  <br/> |客户端应用程序和消息存储提供程序  <br/> |
   
```cpp
HRESULT GetAttribIMsgOnIStg(
  LPVOID lpObject,
  LPSPropTagArray lpPropTagArray,
  LPSPropAttrArray FAR * lppPropAttrArray
);
```

## <a name="parameters"></a>参数

 _lpObject_
  
> [in]对从[OpenIMsgOnIStg](openimsgonistg.md)函数获取**IMessage**对象的指针。 
    
 _lpPropTagArray_
  
> [in]指向[SPropTagArray](sproptagarray.md)结构，其中包含数组属性标记，指示要为其检索属性的属性。 
    
 _lppPropAttrArray_
  
> [输出]为包含检索的 property 属性的返回[SPropAttrArray](spropattrarray.md)结构指针的指针。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 呼叫成功或多个预期值返回。 
    
MAPI_W_ERRORS_RETURNED 
  
> 调用成功总体上讲，但无法访问并已返回与 PT_ERROR 属性类型的一个或多个属性。
    
## <a name="remarks"></a>注解

Property 属性只能在 property 对象，即，实现的对象上访问[IMAPIProp: IUnknown](imapipropiunknown.md)接口。 使 MAPI 属性 OLE 结构化的存储对象上可用， [OpenIMsgOnIStg](openimsgonistg.md)生成[IMessage: IMAPIProp](imessageimapiprop.md) OLE **IStorage**对象上的对象。 此类对象上的属性属性可以设置或更改与[SetAttribIMsgOnIStg](setattribimsgonistg.md)和检索与**GetAttribIMsgOnIStg**。 
  
> [!NOTE]
> **GetAttribIMsgOnIStg**和**SetAttribIMsgOnIStg**请勿对所有**IMessage**对象。 它们只是有效的**IMessage**上返回**OpenIMsgOnIStg** **IStorage**对象。 
  
数目和_lppPropAttrArray_参数中的位置的属性对应于的数量和_lpPropTagArray_参数中的属性标记的位置。 
  

