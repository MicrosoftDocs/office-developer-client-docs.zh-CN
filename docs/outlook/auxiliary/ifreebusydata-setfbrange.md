---
title: IFreeBusyDataSetFBRange
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 4e7147ea-0eb0-324a-80d8-4f0eef654c32
description: 设置用户的忙/闲数据块枚举的时间范围。
ms.openlocfilehash: 4647453acb0e530521aa808f7f017e3e311644bb
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33421660"
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
  
> 实时忙/闲信息开始的相对时间值。 此值是自1601年1月1日以来的分钟数。
    
_rtmEnd_
  
> 实时忙/闲信息结束的相对时间值。 此值是自1601年1月1日以来的分钟数。
    
## <a name="return-values"></a>返回值

如果该调用成功，则返回 S_OK否则为一个错误代码。
  
## <a name="remarks"></a>说明

此方法用于指示要检索其详细信息的日历项目的时间范围。 *ftmStart*和*ftmEnd*的值在随后对[IFreeBusyData:: GetFBPublishRange](ifreebusydata-getfbpublishrange.md)的调用中进行缓存和返回。
  
## <a name="see-also"></a>另请参阅

- [IFreeBusyData::EnumBlocks](ifreebusydata-enumblocks.md)
- [IFreeBusyData::GetFBPublishRange](ifreebusydata-getfbpublishrange.md)
- [使用访问忙/闲数据的相对时间](how-to-use-relative-time-to-access-free-busy-data.md)

