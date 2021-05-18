---
title: IFreeBusySupportLoadFreeBusyData
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: f0baa310-7a53-07ee-0a7d-33dd1fb465c2
description: 为每个用户返回一个接口，用于枚举一个时间范围内的忙/闲数据块。
ms.openlocfilehash: e55f902117a20bfefaa5d9a2f3a067cb78ec86cb
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33411230"
---
# <a name="ifreebusysupportloadfreebusydata"></a>IFreeBusySupport::LoadFreeBusyData

为每个用户返回一个接口，用于枚举一个时间范围内的忙/闲数据块。 
  
## <a name="quick-info"></a>快速信息

请参阅 [IFreeBusySupport](ifreebusysupport.md)。
  
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
  
> [in]要返回 [的 IFreeBusyData](ifreebusydata.md) 接口的数量。 
    
_rgfbuser_
  
> [in]要检索其数据的忙/闲用户的数组。
    
_prgfbdata_
  
> [in][out]对应于 [FBUser](fbuser.md)结构的 _rgfbuser_ 数组的 **IFreeBusyData** 接口的数组。 
    
   > [!NOTE]
   > 此指针数组由调用方分配，由调用方释放。 当调用方使用它们完成操作时，将释放指向的实际接口。 
  
_phrStatus_
  
> [out]用于检索每个相应的 **IFreeBusyData** 接口的 **HRESULT** 结果数组。 该值可能为 NULL。 如果相应的  _prgfbdata_ S_OK，则结果设置为"值"。 
    
_pcRead_
  
>  [out]已找到 **IFreeBusyData** 接口的实际用户数。 
    
## <a name="return-values"></a>返回值

如果该调用成功，则返回 S_OK否则为一个错误代码。
  
## <a name="see-also"></a>另请参阅

- [常量 (忙/闲 API) ](constants-free-busy-api.md)

