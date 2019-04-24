---
title: IFreeBusySupportLoadFreeBusyData
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: f0baa310-7a53-07ee-0a7d-33dd1fb465c2
description: 对于每个指定的用户, 返回一个用于枚举某个时间范围内的忙/闲数据块的接口。
ms.openlocfilehash: e55f902117a20bfefaa5d9a2f3a067cb78ec86cb
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32319402"
---
# <a name="ifreebusysupportloadfreebusydata"></a>IFreeBusySupport::LoadFreeBusyData

对于每个指定的用户, 返回一个用于枚举某个时间范围内的忙/闲数据块的接口。 
  
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
  
> 实时要返回的[IFreeBusyData](ifreebusydata.md)接口的数目。 
    
_rgfbuser_
  
> 实时要为其检索数据的忙/闲用户数组。
    
_prgfbdata_
  
> 实时排除与[FBUser](fbuser.md)结构的_rgfbuser_数组相对应的**IFreeBusyData**接口的数组。 
    
   > [!NOTE]
   > 此指针数组由呼叫者分配并由呼叫者释放。 当调用方完成时, 指向的实际接口将释放。 
  
_phrStatus_
  
> 排除用于检索每个相应的**IFreeBusyData**接口的**HRESULT**结果的数组。 值可以为 NULL。 如果相应的_prgfbdata_有效, 则将结果设置为 S_OK。 
    
_pcRead_
  
>  排除已找到其**IFreeBusyData**接口的实际用户数。 
    
## <a name="return-values"></a>返回值

如果该调用成功，则返回 S_OK否则为一个错误代码。
  
## <a name="see-also"></a>另请参阅

- [常量 (忙/闲 API)](constants-free-busy-api.md)

