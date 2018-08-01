---
title: IFreeBusyDataEnumBlocks
manager: soliver
ms.date: 02/18/2016
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 0cd5a5ae-118f-c7da-4eda-e97590fc39d4
description: 获取枚举忙/闲数据块的指定的时间范围内的用户界面。
ms.openlocfilehash: ab377b1029296b6b4bac68d7169dcf7b8dcd8b87
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774211"
---
# <a name="ifreebusydataenumblocks"></a>IFreeBusyData::EnumBlocks

获取枚举忙/闲数据块的指定的时间范围内的用户界面。
  
## <a name="quick-info"></a>快速信息

请参阅[IFreeBusyData](ifreebusydata.md)。
  
```cpp
HRESULT EnumBlocks( 
     IEnumFBBlock **ppenumfb,  
     FILETIME ftmStart, 
     FILETIME ftmEnd 
);

```

## <a name="parameters"></a>参数

_ppenumfb_
  
> [输出]接口来枚举忙/闲块。
    
_ftmStart_
  
> [in]枚举的开始时间。 在[FILETIME](http://msdn.microsoft.com/library/ 4af8e79a-697e-44a1-8576-fdc57726e9ef.aspx)表示。
    
_ftmEnd_
  
> [in]枚举的结束时间。 在**FILETIME**表示。 
    
## <a name="return-values"></a>返回值

如果该调用成功，则返回 S_OK否则为一个错误代码。
  
## <a name="remarks"></a>注释

此方法用于指示要为其检索详细信息的日历项目的时间范围。 缓存和[IFreeBusyData::GetFBPublishRange](ifreebusydata-getfbpublishrange.md)的后续调用中返回*ftmStart*和*ftmEnd*的值。
  
忙/闲信息的提供程序还随后可以使用返回的[IEnumFBBlock](ienumfbblock.md)接口访问枚举。 
  
## <a name="see-also"></a>另请参阅

- [IEnumFBBlock](ienumfbblock.md)
- [IFreeBusyData::GetFBPublishRange](ifreebusydata-getfbpublishrange.md)
- [IFreeBusyData::SetFBRange](ifreebusydata-setfbrange.md)
- [使用访问忙/闲数据的相对时间](how-to-use-relative-time-to-access-free-busy-data.md)

