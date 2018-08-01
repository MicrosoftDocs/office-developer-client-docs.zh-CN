---
title: IFreeBusyDataSetFBRange
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 4e7147ea-0eb0-324a-80d8-4f0eef654c32
description: 设置用户的忙/闲数据块枚举的时间范围。
ms.openlocfilehash: 84a25a2dd43f594caa075d90e4f183086452184a
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774224"
---
# <a name="ifreebusydatasetfbrange"></a>IFreeBusyData::SetFBRange

设置用户的忙/闲数据块枚举的时间范围。
  
## <a name="quick-info"></a>快速信息

请参阅[IFreeBusyData](ifreebusydata.md)。
  
```cpp
HRESULT SetFBRange(
     LONG rtmStart,
     LONG rtmEnd
);
```

## <a name="parameters"></a>参数

_rtmStart_
  
> [in]忙/闲信息的开始相对时间值。 此值是自 1601 年 1 月 1 日以来的分钟数。
    
_rtmEnd_
  
> [in]忙/闲信息的末尾相对时间值。 此值是自 1601 年 1 月 1 日以来的分钟数。
    
## <a name="return-values"></a>返回值

如果该调用成功，则返回 S_OK否则为一个错误代码。
  
## <a name="remarks"></a>注释

此方法用于指示要为其检索详细信息的日历项目的时间范围。 缓存和[IFreeBusyData::GetFBPublishRange](ifreebusydata-getfbpublishrange.md)的后续调用中返回*ftmStart*和*ftmEnd*的值。
  
## <a name="see-also"></a>另请参阅

- [IFreeBusyData::EnumBlocks](ifreebusydata-enumblocks.md)
- [IFreeBusyData::GetFBPublishRange](ifreebusydata-getfbpublishrange.md)
- [使用访问忙/闲数据的相对时间](how-to-use-relative-time-to-access-free-busy-data.md)

