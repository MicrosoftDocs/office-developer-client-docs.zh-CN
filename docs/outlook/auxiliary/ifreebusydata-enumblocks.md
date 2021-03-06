---
title: IFreeBusyDataEnumBlocks
manager: soliver
ms.date: 02/18/2016
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 0cd5a5ae-118f-c7da-4eda-e97590fc39d4
description: 获取一个接口，该接口枚举指定时间范围内用户的忙/闲数据块。
ms.openlocfilehash: 51a77b2f47166628db07259ef841e0d6173ee370
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32317554"
---
# <a name="ifreebusydataenumblocks"></a>IFreeBusyData::EnumBlocks

获取一个接口，该接口枚举指定时间范围内用户的忙/闲数据块。
  
## <a name="quick-info"></a>快速信息

请参阅 [IFreeBusyData](ifreebusydata.md)。
  
```cpp
HRESULT EnumBlocks( 
     IEnumFBBlock **ppenumfb,  
     FILETIME ftmStart, 
     FILETIME ftmEnd 
);

```

## <a name="parameters"></a>参数

_ppenumfb_
  
> [out]用于枚举忙/闲块的接口。
    
_ftmStart_
  
> [in]枚举的开始时间。 它用 [FILETIME 表示](https://msdn.microsoft.com/library/ 4af8e79a-697e-44a1-8576-fdc57726e9ef.aspx)。
    
_ftmEnd_
  
> [in]枚举的结束时间。 它用 **FILETIME 表示**。 
    
## <a name="return-values"></a>返回值

如果该调用成功，则返回 S_OK否则为一个错误代码。
  
## <a name="remarks"></a>备注

此方法用于指示要检索其详细信息的日历项目的时区。 *ftmStart* 和 *ftmEnd* 的值在 [IFreeBusyData：：GetFBPublishRange](ifreebusydata-getfbpublishrange.md)的后续调用中缓存并返回。
  
忙/闲提供程序随后还可使用返回的 [IEnumFBBlock](ienumfbblock.md) 接口访问枚举。 
  
## <a name="see-also"></a>另请参阅

- [IEnumFBBlock](ienumfbblock.md)
- [IFreeBusyData::GetFBPublishRange](ifreebusydata-getfbpublishrange.md)
- [IFreeBusyData::SetFBRange](ifreebusydata-setfbrange.md)
- [使用访问忙/闲数据的相对时间](how-to-use-relative-time-to-access-free-busy-data.md)

