---
title: IABLogonCompareEntryIDs
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IABLogon.CompareEntryIDs
api_type:
- COM
ms.assetid: cb4a38ff-2fdd-40ac-a613-12c3f11a1df9
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 48ddb5a7c4e013c03138b08d9dadcdc0991faeec
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32279606"
---
# <a name="iablogoncompareentryids"></a>IABLogon::CompareEntryIDs

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
对两个条目标识符进行比较, 以确定它们是否引用同一个对象。
  
```cpp
HRESULT CompareEntryIDs(
  ULONG cbEntryID1,
  LPENTRYID lpEntryID1,
  ULONG cbEntryID2,
  LPENTRYID lpEntryID2,
  ULONG ulFlags,
  ULONG FAR * lpulRet
);
```

## <a name="parameters"></a>参数

 _cbEntryID1_
  
> 实时条目标识符中由_lpEntryID1_参数指向的字节数。 
    
 _lpEntryID1_
  
> 实时指向要比较的第一个条目标识符的指针。
    
 _cbEntryID2_
  
> 实时条目标识符中由_lpEntryID2_参数指向的字节数。 
    
 _lpEntryID2_
  
> 实时指向要比较的第二个条目标识符的指针。
    
 _ulFlags_
  
> 实时保留必须为零。
    
 _lpulRet_
  
> 排除指向比较结果的指针。 如果为 TRUE, 则指示两个条目标识符引用同一个对象;否则为 FALSE。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 条目标识符已成功比较。
    
MAPI_E_INVALID_ENTRYID 
  
> 一个或两个条目标识符不属于通讯簿提供程序。
    
## <a name="remarks"></a>注解

通讯簿提供程序实现**CompareEntryIDs**方法来比较两个条目标识符, 以确定它们是否引用同一个对象。 
  
 **CompareEntryIDs**很有用, 因为一个对象可以有多个有效的条目标识符;例如, 当您将短期条目标识符与长期条目标识符进行比较时, 可能会发生这种情况。 
  
有关如何创建条目标识符的详细信息, 请参阅[MAPI 条目标识符](mapi-entry-identifiers.md)。
  
## <a name="see-also"></a>另请参阅



[IABLogon : IUnknown](iablogoniunknown.md)

