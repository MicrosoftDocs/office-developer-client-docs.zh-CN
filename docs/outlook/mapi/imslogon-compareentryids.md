---
title: IMSLogonCompareEntryIDs
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMSLogon.CompareEntryIDs
api_type:
- COM
ms.assetid: 481812d6-8e94-4510-b288-55501dd5757c
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 4196ed8b949ecb9e23c4bd34380db9cc5a369e23
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32348725"
---
# <a name="imslogoncompareentryids"></a>IMSLogon::CompareEntryIDs

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
对两个条目标识符进行比较, 以确定它们是否引用同一个对象。 MAPI 仅当该提供程序处理两个条目标识符中的唯一标识符 (uid) 时, 才会将此调用指向服务提供程序。
  
```cpp
HRESULT CompareEntryIDs(
  ULONG cbEntryID1,
  LPENTRYID lpEntryID1,
  ULONG cbEntryID2,
  LPENTRYID lpEntryID2,
  ULONG ulFlags,
  ULONG FAR * lpulResult
);
```

## <a name="parameters"></a>参数

 _cbEntryID1_
  
> 实时由_lpEntryID1_参数指向的条目标识符的大小 (以字节为单位) _。_
    
 _lpEntryID1_
  
> 实时指向要比较的第一个条目标识符的指针。
    
 _cbEntryID2_
  
> 实时由_lpEntryID2_参数指向的条目标识符的大小 (以字节为单位) _。_
    
 _lpEntryID2_
  
> 实时指向要比较的第二个条目标识符的指针。
    
 _ulFlags_
  
> 实时保留必须为零。
    
 _lpulResult_
  
> 排除指向比较的返回结果的指针。 如果两个条目标识符引用同一个对象, 则为 TRUE; 否则为 false。否则为 FALSE。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功, 并返回了所需的值或值。
    
## <a name="remarks"></a>注解

邮件存储提供程序实现**IMSLogon:: CompareEntryIDs**方法, 以比较邮件存储区中给定条目的两个条目标识符, 以确定它们是否引用同一个对象。 如果两个条目标识符引用同一个对象, 则**CompareEntryIDs**会将_lpulResult_参数设置为 TRUE;如果这些对象引用不同的对象, 则**CompareEntryIDs**会将_lpulResult_设置为 FALSE。 
  
 **CompareEntryIDs**很有用, 因为一个对象可以有多个有效的条目标识符。 例如, 在安装了新版本的邮件存储提供程序后, 可能会发生这种情况。 
  
## <a name="see-also"></a>另请参阅



[IMSLogon : IUnknown](imslogoniunknown.md)

