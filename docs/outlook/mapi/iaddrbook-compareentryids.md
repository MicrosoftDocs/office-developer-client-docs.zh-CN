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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: b6abecc298df7a86afff9338752a15615c73b3a4
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33424257"
---
# <a name="iaddrbookcompareentryids"></a>IAddrBook::CompareEntryIDs

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
比较属于特定通讯簿提供程序的两个条目标识符，以确定它们是否引用同一通讯簿对象。 
  
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
  
> [in]  _lpEntryID1_ 参数指向的条目标识符中的字节计数。 
    
 _lpEntryID1_
  
> [in]指向要比较的第一个条目标识符的指针。
    
 _cbEntryID2_
  
> [in]  _lpEntryID2_ 参数指向的条目标识符中的字节计数。 
    
 _lpEntryID2_
  
> [in]指向要比较的第二个条目标识符的指针。
    
 _ulFlags_
  
> [in]保留;必须为零。
    
 _lpulResult_
  
> [out]指向比较结果的指针。 如果两个条目标识符引用同一个对象，则  _lpulResult_ 的内容将设置为 TRUE;否则，内容将设置为 FALSE。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功并返回了预期值。
    
MAPI_E_UNKNOWN_ENTRYID 
  
> 任何通讯簿提供程序无法识别使用  _lpEntryID1_ 或  _lpEntryID2_ 参数传入的一个或两个条目标识符。 
    
## <a name="remarks"></a>备注

客户端应用程序和服务提供商调用 **CompareEntryIDs** 方法来比较属于单个通讯簿提供程序的两个条目标识符，以确定它们是否引用同一个对象。 **CompareEntryIDs** 非常有用，因为对象可以具有多个有效的条目标识符。 例如，安装通讯簿提供程序的新版本后，可能会出现此情况。 
  
MAPI 将此调用传递给负责条目标识符的通讯簿提供程序，通过匹配条目标识符中的 [MAPIUID](mapiuid.md) 结构与提供程序注册的 **MAPIUID** 结构来确定相应的提供程序。 
  
如果两个条目标识符引用同一个对象，则 **CompareEntryIDs** 将  _lpulResult_ 参数的内容设置为 TRUE;如果它们引用不同的对象， **则 CompareEntryIDs** 将内容设置为 FALSE。 在任一情况下 **，CompareEntryIDs** 都S_OK。 如果 **CompareEntryIDs** 返回错误，如果没有通讯簿提供程序注册与条目标识符中的 MAPIUID 结构匹配的 **MAPIUID** 结构，则客户端和提供程序不应根据比较结果执行任何操作。 相反，他们应采用最保守的方法来执行所执行的操作。 
  
## <a name="see-also"></a>另请参阅



[IAddrBook : IMAPIProp](iaddrbookimapiprop.md)

