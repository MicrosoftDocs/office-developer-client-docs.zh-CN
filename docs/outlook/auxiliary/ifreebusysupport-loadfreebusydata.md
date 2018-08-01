---
title: IFreeBusySupportLoadFreeBusyData
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: f0baa310-7a53-07ee-0a7d-33dd1fb465c2
description: 返回，为每个指定的用户，用于枚举忙/闲时间范围内的数据块的接口。
ms.openlocfilehash: 9af5a40da9f0a831de7346b44cee9ca004c02300
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774209"
---
# <a name="ifreebusysupportloadfreebusydata"></a>IFreeBusySupport::LoadFreeBusyData

返回，为每个指定的用户，用于枚举忙/闲时间范围内的数据块的接口。 
  
## <a name="quick-info"></a>快速信息

请参阅[IFreeBusySupport](ifreebusysupport.md)。
  
```cpp
HRESULT LoadFreeBusyData( 
    ULONG cMax,  
    FBUser *rgfbuser, 
    IFreeBusyData **prgfbdata,  
    HRESULT *phrStatus, 
    ULONG *pcRead 
);
```

## <a name="parameters"></a>参数

_cMax_
  
> [in][IFreeBusyData](ifreebusydata.md)接口返回数。 
    
_rgfbuser_
  
> [in]忙/闲信息的用户来检索数据的数组。
    
_prgfbdata_
  
> [in][输出]**IFreeBusyData**接口对应的[FBUser](fbuser.md)结构_rgfbuser_数组的数组。 
    
   > [!NOTE]
   > 此数组指针是呼叫者分配并释放呼叫者。 当呼叫者完成与他们发布指向的实际接口。 
  
_phrStatus_
  
> [输出]用于检索每个相应**IFreeBusyData**接口的**HRESULT**结果的数组。 值可能是 NULL。 结果设置为 S_OK 相应_prgfbdata_是否有效。 
    
_pcRead_
  
>  [输出]实际已为其找到**IFreeBusyData**接口的用户数。 
    
## <a name="return-values"></a>返回值

如果该调用成功，则返回 S_OK否则为一个错误代码。
  
## <a name="see-also"></a>另请参阅

- [常量 (忙/闲 API)](constants-free-busy-api.md)

