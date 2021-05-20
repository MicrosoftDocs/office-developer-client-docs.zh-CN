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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33438370"
---
# <a name="iablogoncompareentryids"></a>IABLogon::CompareEntryIDs

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
比较两个条目标识符以确定它们是否引用同一个对象。
  
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
  
> [in]  _lpEntryID1_ 参数指向的条目标识符中的字节计数。 
    
 _lpEntryID1_
  
> [in]指向要比较的第一个条目标识符的指针。
    
 _cbEntryID2_
  
> [in]  _lpEntryID2_ 参数指向的条目标识符中的字节计数。 
    
 _lpEntryID2_
  
> [in]指向要比较的第二个条目标识符的指针。
    
 _ulFlags_
  
> [in]保留;必须为零。
    
 _lpulRet_
  
> [out]指向比较结果的指针。 如果为 TRUE，则指示两个条目标识符引用同一个对象;否则为 FALSE。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功比较条目标识符。
    
MAPI_E_INVALID_ENTRYID 
  
> 一个或两个条目标识符不属于通讯簿提供程序。
    
## <a name="remarks"></a>备注

通讯簿提供程序实现 **CompareEntryIDs** 方法来比较两个条目标识符，以确定它们是否引用同一个对象。 
  
 **CompareEntryIDs** 非常有用，因为对象可以具有多个有效的条目标识符;例如，将短期条目标识符与长期条目标识符进行比较时，可能会出现此情况。 
  
若要详细了解如何创建条目标识符，请参阅 [MAPI 条目标识符](mapi-entry-identifiers.md)。
  
## <a name="see-also"></a>另请参阅



[IABLogon : IUnknown](iablogoniunknown.md)

