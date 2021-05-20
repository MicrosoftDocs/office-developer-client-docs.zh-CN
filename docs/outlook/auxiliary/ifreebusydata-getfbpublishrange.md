---
title: IFreeBusyDataGetFBPublishRange
manager: soliver
ms.date: 09/23/2016
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 1a8bbe0c-17d1-9349-4c63-f257faf4edda
description: 获取用户的忙/闲数据块枚举的预设时间范围。
ms.openlocfilehash: 26951ea6a885f8d0e5e6a2fb5bcf9a63069c7f44
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33430075"
---
# <a name="ifreebusydatagetfbpublishrange"></a>IFreeBusyData::GetFBPublishRange

获取用户的忙/闲数据块枚举的预设时间范围。
  
## <a name="quick-info"></a>快速信息

请参阅 [IFreeBusyData](ifreebusydata.md)。
  
```cpp
HRESULT GetFBPublishRange( 
     LONG *prtmStart,  
     LONG *prtmEnd 
);

```

## <a name="parameters"></a>参数

_prtmStart_
  
> [out]忙/闲信息开始的相对时间值。 此值是自 1601 年 1 月 1 日起的分钟数。
    
_prtmEnd_
  
> [out]忙/闲信息结尾的相对时间值。 此值是自 1601 年 1 月 1 日起的分钟数。
    
## <a name="return-values"></a>返回值

如果该调用成功，则返回 S_OK否则为一个错误代码。
  
## <a name="remarks"></a>备注

忙/闲提供程序调用 [IFreeBusyData：：EnumBlocks](ifreebusydata-enumblocks.md) 或 [IFreeBusyData：：SetFBRange](ifreebusydata-setfbrange.md) 来设置枚举的时区。 如果未调用 [IFreeBusyData：：EnumBlocks](ifreebusydata-enumblocks.md) 或 [IFreeBusyData：：SetFBRange，](ifreebusydata-setfbrange.md) 则必须分别在 1601 年 4 月 1 日 00：00：00Z 和 4500 11：59：59Z 之间设置 **prtmStart** 和 **prtmEnd** 的默认值。 此外，不应将开始时间设置为大于结束时间。 
  
**IFreeBusyData：：GetFBPublishRange** 必须返回最近一次调用 **IFreeBusyData：：EnumBlocks** 或 **IFreeBusyData：：SetFBRange** 设置的时区的缓存值。 
  
## <a name="see-also"></a>另请参阅

- [使用访问忙/闲数据的相对时间](how-to-use-relative-time-to-access-free-busy-data.md)
- [IFreeBusyData::EnumBlocks](ifreebusydata-enumblocks.md)
- [IFreeBusyData::SetFBRange](ifreebusydata-setfbrange.md)

