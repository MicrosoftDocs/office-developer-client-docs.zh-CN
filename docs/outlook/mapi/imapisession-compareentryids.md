---
title: IMAPISessionCompareEntryIDs
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPISession.CompareEntryIDs
api_type:
- COM
ms.assetid: 319f10e9-db8d-4d16-aa1f-6cf5fef493eb
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 4dfde82aa843072168288f4e0b0084dfccd5cd2b
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32338456"
---
# <a name="imapisessioncompareentryids"></a>IMAPISession::CompareEntryIDs

  
  
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
  
> 指定为参数的一个或两个条目标识符不引用对象, 这可能是因为这些对象当前未打开且不可用。
    
## <a name="remarks"></a>注解

**IMAPISession:: CompareEntryIDs**方法对属于单个服务提供程序的两个条目标识符进行比较, 以确定它们是否引用同一个对象。 MAPI 提取条目标识符中的[MAPIUID](mapiuid.md)部分, 以确定负责对象的服务提供程序, 然后调用其登录对象的**CompareEntryIDs**方法来执行比较。 
  
## <a name="notes-to-callers"></a>给调用方的说明

**CompareEntryIDs**方法很有用, 因为一个对象可以有多个有效的条目标识符。 例如, 在安装新版本的服务提供程序后, 可能会发生这种情况。 
  
如果**CompareEntryIDs**返回错误, 则不根据比较结果执行任何操作。 而是采取尽可能保守的方法。 例如, 如果一个或两个条目标识符包含一个无效的**MAPIUID**, **CompareEntryIDs**可能会失败。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|BaseDialog  <br/> |CbaseDialog:: OnCompareEntryIDs  <br/> |MFCMAPI 使用**IMAPISession:: CompareEntryIDs**方法来比较用户输入的两个条目 id。  <br/> |
   
## <a name="see-also"></a>另请参阅



[MAPIUID](mapiuid.md)
  
[IMAPISession : IUnknown](imapisessioniunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

