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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: c939189c2c8f7d3147c3146f55deac0e032ce9df
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775605"
---
# <a name="imapisupportcompareentryids"></a>IMAPISupport::CompareEntryIDs

  
  
**适用于**： Outlook 
  
比较两个条目标识符来确定它们是否引用同一个对象。 
  
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
  
> [in]在_lpEntryID1_参数指向的项标识符的字节数。 
    
 _lpEntryID1_
  
> [in]指向要进行比较的第一个条目标识符的指针。
    
 _cbEntryID2_
  
> [in]在_lpEntryID2_参数指向的项标识符的字节数。 
    
 _lpEntryID2_
  
> [in]指向要进行比较的第二个条目标识符的指针。
    
 _ulFlags_
  
> [in]保留;必须为零。
    
 _lpulResult_
  
> [输出]一个指向比较结果的结果。 如果两个条目标识符引用同一对象，则为 TRUE否则为返回 FALSE。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 比较成功。
    
MAPI_E_UNKNOWN_ENTRYID 
  
> 一个或两个条目标识符指定为参数引用不是有效对象，可能是因为它们当前未打开和不可用。
    
## <a name="remarks"></a>说明

对于通讯簿和消息存储提供程序支持对象实现**IMAPISupport::CompareEntryIDs**方法。 **CompareEntryIDs**比较两个条目标识符属于单个服务提供程序确定它们是否引用同一个对象。 MAPI 从条目标识符，以确定服务提供程序负责为对象中提取[MAPIUID](mapiuid.md)部分。 MAPI 然后调用其登录对象**CompareEntryIDs**方法来执行比较。 
  
## <a name="notes-to-callers"></a>给调用方的说明

 **CompareEntryIDs**很有用，因为对象可以有多个有效项标识符。 例如，安装新版本的服务提供商之后，会发生这种情况。 
  
如果**CompareEntryIDs**返回一个错误，不会根据比较结果的任何操作。 相反，可能需要最保守的方法。 如果一个或两个条目标识符，如包含无效的**MAPIUID**结构， **CompareEntryIDs**可能会失败。 
  
## <a name="see-also"></a>另请参阅



[MAPIUID](mapiuid.md)
  
[IMAPISupport : IUnknown](imapisupportiunknown.md)

