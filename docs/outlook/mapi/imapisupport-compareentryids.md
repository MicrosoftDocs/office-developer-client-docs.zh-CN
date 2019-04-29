---
title: IMAPISupportCompareEntryIDs
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPISupport.CompareEntryIDs
api_type:
- COM
ms.assetid: be6991d9-6353-4838-bc6b-39de51a94d8d
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 6c79943792c8c17ee007c39b5c5c215a6fbc0699
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33431041"
---
# <a name="imapisupportcompareentryids"></a>IMAPISupport::CompareEntryIDs

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
对两个条目标识符进行比较, 以确定它们是否引用同一个对象。 
  
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
  
> 实时条目标识符中由_lpEntryID1_参数指向的字节数。 
    
 _lpEntryID1_
  
> 实时指向要比较的第一个条目标识符的指针。
    
 _cbEntryID2_
  
> 实时条目标识符中由_lpEntryID2_参数指向的字节数。 
    
 _lpEntryID2_
  
> 实时指向要比较的第二个条目标识符的指针。
    
 _ulFlags_
  
> 实时保留必须为零。
    
 _lpulResult_
  
> 排除指向比较结果的指针。 如果两个条目标识符引用同一个对象, 则为 TRUE; 否则为 false。否则为 FALSE。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 比较成功。
    
MAPI_E_UNKNOWN_ENTRYID 
  
> 指定为参数的输入标识符中的一个或两个都不引用有效的对象, 这可能是因为它们当前未打开且不可用。
    
## <a name="remarks"></a>说明

为通讯簿和邮件存储提供程序支持对象实现了**IMAPISupport:: CompareEntryIDs**方法。 **CompareEntryIDs**对属于单个服务提供程序的两个条目标识符进行比较, 以确定它们是否引用同一个对象。 MAPI 提取条目标识符中的[MAPIUID](mapiuid.md)部分, 以确定负责这些对象的服务提供程序。 然后, MAPI 将调用其登录对象的**CompareEntryIDs**方法来执行比较。 
  
## <a name="notes-to-callers"></a>给调用方的说明

 **CompareEntryIDs**很有用, 因为一个对象可以有多个有效的条目标识符。 例如, 在安装新版本的服务提供程序后, 可能会发生这种情况。 
  
如果**CompareEntryIDs**返回错误, 则不根据比较结果执行任何操作。 而是采取尽可能保守的方法。 例如, 如果一个或两个条目标识符包含无效的**MAPIUID**结构, **CompareEntryIDs**可能会失败。 
  
## <a name="see-also"></a>另请参阅



[MAPIUID](mapiuid.md)
  
[IMAPISupport : IUnknown](imapisupportiunknown.md)

