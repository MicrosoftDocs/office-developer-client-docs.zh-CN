---
title: IFreeBusyDataGetFBPublishRange
manager: soliver
ms.date: 09/23/2016
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 1a8bbe0c-17d1-9349-4c63-f257faf4edda
description: 获取一个预设的时间范围的忙/闲信息的用户数据块枚举。
ms.openlocfilehash: 2a322a43da38a0b902789f4c83baaabd769154c7
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774206"
---
# <a name="ifreebusydatagetfbpublishrange"></a>IFreeBusyData::GetFBPublishRange

获取一个预设的时间范围的忙/闲信息的用户数据块枚举。
  
## <a name="quick-info"></a>快速信息

请参阅[IFreeBusyData](ifreebusydata.md)。
  
```cpp
HRESULT GetFBPublishRange( 
     LONG *prtmStart,  
     LONG *prtmEnd 
);

```

## <a name="parameters"></a>参数

_prtmStart_
  
> [输出]忙/闲信息的开始相对时间值。 此值是自 1601 年 1 月 1 日以来的分钟数。
    
_prtmEnd_
  
> [输出]忙/闲信息的末尾相对时间值。 此值是自 1601 年 1 月 1 日以来的分钟数。
    
## <a name="return-values"></a>返回值

如果该调用成功，则返回 S_OK否则为一个错误代码。
  
## <a name="remarks"></a>注释

忙/闲信息的提供程序调用[IFreeBusyData::EnumBlocks](ifreebusydata-enumblocks.md)或[IFreeBusyData::SetFBRange](ifreebusydata-setfbrange.md)设置枚举的时间范围。 如果尚未调用[IFreeBusyData::EnumBlocks](ifreebusydata-enumblocks.md)或[IFreeBusyData::SetFBRange](ifreebusydata-setfbrange.md) ，必须 00:00:00Z 1601 年 4 月 1 日和年 8 月 31 日 4500 11:59:59Z 之间设置**prtmStart**和**prtmEnd**的默认值分别。 此外，您不应设置为大于结束时间的开始时间。 
  
**IFreeBusyData::GetFBPublishRange**必须返回**IFreeBusyData::EnumBlocks**或**IFreeBusyData::SetFBRange**最近呼叫的时间范围的缓存的值设置。 
  
## <a name="see-also"></a>另请参阅

- [使用访问忙/闲数据的相对时间](how-to-use-relative-time-to-access-free-busy-data.md)
- [IFreeBusyData::EnumBlocks](ifreebusydata-enumblocks.md)
- [IFreeBusyData::SetFBRange](ifreebusydata-setfbrange.md)

