---
title: UlPropSize
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.UlPropSize
api_type:
- COM
ms.assetid: 240f1144-0805-4cd1-9e7d-f2a550a2f160
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: bc00270b167c9f7317fa466d790d5020d961676f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779020"
---
# <a name="ulpropsize"></a>UlPropSize

  
  
**适用于**： Outlook 
  
返回的单个属性值的大小。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapidefs.h  <br/> |
|通过实现：  <br/> |MAPI  <br/> |
|调用：  <br/> |客户端应用程序和服务提供商  <br/> |
   
```cpp
ULONG UlPropSize(
  LPSPropValue lpSPropValue
);
```

## <a name="parameters"></a>参数

 _lpSPropValue_
  
> [in]指向[SPropValue](spropvalue.md)结构定义要测量的属性。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 呼叫成功或多个预期值返回。 
    
MAPI_E_CALL_FAILED 
  
> 意外或未知的原点出现错误，无法完成操作。
    
## <a name="remarks"></a>备注

**UlPropSize**函数返回的大小，以字节为单位指定的属性的属性值。 它将忽略**SPropValue**结构的其余部分的大小。 
  

