---
title: IAddrBookCompareEntryIDs
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IAddrBookCompareEntryIDs
api_type:
- COM
ms.assetid: 7dabc1d3-5ea4-482f-91a9-9ef3009eddd2
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: d6f983e49132e7ab6ea402a8e32bb5ec56d1efba
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22564848"
---
# <a name="iaddrbookcompareentryids"></a>IAddrBook::CompareEntryIDs

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
比较两个条目标识符属于特定地址簿提供程序，以确定它们是否引用同一个通讯簿对象。 
  
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
  
> [输出]一个指向比较结果的结果。 如果两个条目标识符引用同一对象，则_lpulResult_的内容设置为 TRUE否则，将内容设置为 FALSE。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 呼叫成功或多个预期值返回。
    
MAPI_E_UNKNOWN_ENTRYID 
  
> 任何通讯簿提供程序无法识别一个或两个使用_lpEntryID1_或_lpEntryID2_参数传递的项标识符。 
    
## <a name="remarks"></a>注解

客户端应用程序和服务提供程序调用**CompareEntryIDs**方法比较两个条目标识符属于单个地址簿提供程序，以确定它们是否引用同一个对象。 **CompareEntryIDs**很有用，因为对象可以有多个有效项标识符。 例如，安装新版本的通讯簿提供程序后，会发生这种情况。 
  
MAPI 将传递到通讯簿提供程序，它负责条目标识符，确定相应的提供程序通过匹配的项标识符的[MAPIUID](mapiuid.md)结构与**MAPIUID**结构注册的此呼叫提供程序。 
  
如果两个条目标识符引用相同的对象，则**CompareEntryIDs**将_lpulResult_参数的内容设置为 TRUE;如果它们引用不同对象， **CompareEntryIDs**将内容设置为 FALSE。 在任一情况下， **CompareEntryIDs**返回 S_OK。 如果**CompareEntryIDs**返回一个错误，如果没有通讯簿提供程序已注册的**MAPIUID**结构相匹配的项标识符中出现，客户端和提供程序应不执行任何操作的结果比较。 他们应改为需要最保守的方法，对正在执行的操作。 
  
## <a name="see-also"></a>另请参阅



[IAddrBook : IMAPIProp](iaddrbookimapiprop.md)

