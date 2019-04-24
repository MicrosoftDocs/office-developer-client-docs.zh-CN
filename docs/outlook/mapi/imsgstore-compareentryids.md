---
title: IMsgStoreCompareEntryIDs
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMsgStore.CompareEntryIDs
api_type:
- COM
ms.assetid: 33d70748-0d3f-4be4-bcb5-7ec048887944
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 2a2439bae79b497f018391983e2c4b03a35eee70
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32348788"
---
# <a name="imsgstorecompareentryids"></a>IMsgStore::CompareEntryIDs

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
对两个条目标识符进行比较, 以确定它们是否引用邮件存储区中的相同条目。 仅当该提供程序处理两个条目标识符中的唯一标识符 (uid) 时, MAPI 才会将此调用传递给服务提供程序。
  
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
  
> 实时条目标识符中由_lpEntryID1_参数指向的字节数 _。_
    
 _lpEntryID1_
  
> 实时指向要比较的第一个条目标识符的指针。
    
 _cbEntryID2_
  
> 实时条目标识符中由_lpEntryID2_参数指向的字节数 _。_
    
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
  
> 指定为参数的输入标识符中的一个或两个都不引用对象, 原因可能是相应的对象尚未打开, 并且目前不可用。
    
## <a name="remarks"></a>注解

**IMsgStore:: CompareEntryIDs**方法对属于邮件存储的两个条目标识符进行比较, 以确定它们是否引用同一个对象。 
  
## <a name="notes-to-callers"></a>给调用方的说明

 **CompareEntryIDs**很有用, 因为一个对象可以有多个有效条目标识符 (例如, 在安装了新版本的邮件存储提供程序之后)。 
  
如果**CompareEntryIDs**返回错误, 则不根据比较结果执行任何操作。 而是采取尽可能保守的方法。 例如, 如果一个或两个条目标识符包含一个无效的**MAPIUID**, **CompareEntryIDs**可能会失败。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|BaseDialog  <br/> |CBaseDialog:: OnCompareEntryIDs  <br/> |MFCMAPI 使用**IMsgStore:: CompareEntryIDs**方法来比较条目 id。  <br/> |
   
## <a name="see-also"></a>另请参阅



[MAPIUID](mapiuid.md)
  
[IMsgStore : IMAPIProp](imsgstoreimapiprop.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

