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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: b161c8c0da78b5ca872b87cad9a297169426d4cd
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22565002"
---
# <a name="iablogoncompareentryids"></a>IABLogon::CompareEntryIDs

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
比较两个条目标识符来确定它们是否引用同一个对象。
  
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
  
> [in]在_lpEntryID1_参数指向的项标识符的字节数。 
    
 _lpEntryID1_
  
> [in]指向要进行比较的第一个条目标识符的指针。
    
 _cbEntryID2_
  
> [in]在_lpEntryID2_参数指向的项标识符的字节数。 
    
 _lpEntryID2_
  
> [in]指向要进行比较的第二个条目标识符的指针。
    
 _ulFlags_
  
> [in]保留;必须为零。
    
 _lpulRet_
  
> [输出]一个指向比较结果的结果。 TRUE 表示的两个条目标识符引用同一对象;否则为返回 FALSE。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功比较的项标识符。
    
MAPI_E_INVALID_ENTRYID 
  
> 一个或两个条目标识符不属于通讯簿提供程序。
    
## <a name="remarks"></a>注解

通讯簿提供程序实现**CompareEntryIDs**方法比较两个条目标识符来确定它们是否引用同一个对象。 
  
 **CompareEntryIDs**很有用，因为对象可以有多个有效项标识符;例如，比较具有长期的项标识符的短期条目标识符时，可能发生这种情况。 
  
有关如何创建条目标识符的详细信息，请参阅[MAPI 条目标识符](mapi-entry-identifiers.md)。
  
## <a name="see-also"></a>另请参阅



[IABLogon : IUnknown](iablogoniunknown.md)

