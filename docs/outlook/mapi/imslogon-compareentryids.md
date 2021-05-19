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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33410131"
---
# <a name="imslogoncompareentryids"></a>IMSLogon::CompareEntryIDs

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
比较两个条目标识符以确定它们是否引用同一个对象。 MAPI 仅在要比较的两个条目标识符 (UID) 唯一标识符由该提供程序处理时，才将此调用引用到服务提供商。
  
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
  
> [in]  _lpEntryID1_ 参数指向的条目标识符的大小（以字节为单位  _）。_
    
 _lpEntryID1_
  
> [in]指向要比较的第一个条目标识符的指针。
    
 _cbEntryID2_
  
> [in]  _lpEntryID2_ 参数指向的条目标识符的大小（以字节为单位  _）。_
    
 _lpEntryID2_
  
> [in]指向要比较的第二个条目标识符的指针。
    
 _ulFlags_
  
> [in]保留;必须为零。
    
 _lpulResult_
  
> [out]指向比较结果的返回结果的指针。 如果两个条目标识符引用同一个对象，则其为 TRUE;否则为 FALSE。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功并返回了预期值。
    
## <a name="remarks"></a>备注

邮件存储提供程序实现 **IMSLogon：：CompareEntryIDs** 方法，以比较消息存储中给定条目的两个条目标识符，以确定它们是否引用同一对象。 如果两个条目标识符引用同一个对象，则 **CompareEntryIDs** 将  _lpulResult_ 参数设置为 TRUE;如果它们引用不同的对象， **则 CompareEntryIDs** 将  _lpulResult 设置_ 为 FALSE。 
  
 **CompareEntryIDs** 非常有用，因为对象可以具有多个有效的条目标识符。 例如，安装邮件存储提供程序的新版本后，可能会发生这种情况。 
  
## <a name="see-also"></a>另请参阅



[IMSLogon : IUnknown](imslogoniunknown.md)

