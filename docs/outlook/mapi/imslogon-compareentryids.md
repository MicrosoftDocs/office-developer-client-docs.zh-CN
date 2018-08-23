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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: c5b2d7db745cc270c0be7ee2184e86c6a4f97aad
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22594297"
---
# <a name="imslogoncompareentryids"></a>IMSLogon::CompareEntryIDs

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
比较两个条目标识符来确定它们是否引用同一个对象。 仅当要比较两个条目 identifiers 中的唯一标识符 (Uid) 处理该服务提供商，MAPI 引用到的服务提供此呼叫。
  
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
  
> [in]大小，以字节为单位的项标识符_lpEntryID1_参数指向 _。_
    
 _lpEntryID1_
  
> [in]指向要进行比较的第一个条目标识符的指针。
    
 _cbEntryID2_
  
> [in]大小，以字节为单位的项标识符_lpEntryID2_参数指向 _。_
    
 _lpEntryID2_
  
> [in]指向要进行比较的第二个条目标识符的指针。
    
 _ulFlags_
  
> [in]保留;必须为零。
    
 _lpulResult_
  
> [输出]一个指向的比较结果返回的结果。 如果两个条目标识符引用同一对象，则为 TRUE否则为返回 FALSE。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 呼叫成功或多个预期值返回。
    
## <a name="remarks"></a>注解

消息存储提供程序实现**IMSLogon::CompareEntryIDs**方法比较两个条目中的消息存储，以确定它们是否引用同一个对象的给定项标识符。 如果两个条目标识符引用相同的对象，则**CompareEntryIDs**将_lpulResult_参数设置为 TRUE;如果它们引用不同对象， **CompareEntryIDs**将_lpulResult_设置为 FALSE。 
  
 **CompareEntryIDs**很有用，因为对象可以有多个有效项标识符。 这可能会发生，例如，安装新版本的消息存储提供程序。 
  
## <a name="see-also"></a>另请参阅



[IMSLogon : IUnknown](imslogoniunknown.md)

