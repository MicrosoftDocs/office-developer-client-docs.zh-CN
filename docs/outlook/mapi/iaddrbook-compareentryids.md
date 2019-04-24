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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32348886"
---
# <a name="iaddrbookcompareentryids"></a>IAddrBook::CompareEntryIDs

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
对属于特定通讯簿提供程序的两个条目标识符进行比较, 以确定它们是否引用相同的通讯簿对象。 
  
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
  
> 排除指向比较结果的指针。 如果两个条目标识符引用同一个对象, 则_lpulResult_的内容设置为 TRUE; 否则为 false。否则, 内容将设置为 FALSE。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功, 并返回了所需的值或值。
    
MAPI_E_UNKNOWN_ENTRYID 
  
> 任何通讯簿提供程序都不能识别使用_lpEntryID1_或_lpEntryID2_参数传入的一个或两个条目标识符。 
    
## <a name="remarks"></a>注解

客户端应用程序和服务提供程序调用**CompareEntryIDs**方法来比较属于单个通讯簿提供程序的两个条目标识符, 以确定它们是否引用同一个对象。 **CompareEntryIDs**很有用, 因为一个对象可以有多个有效的条目标识符。 例如, 在安装新版本的通讯簿提供程序后, 可能会发生这种情况。 
  
MAPI 将此调用传递给负责条目标识符的通讯簿提供程序, 通过将条目标识符中的[MAPIUID](mapiuid.md)结构与注册的**MAPIUID**结构进行匹配来确定相应的提供程序。provider. 
  
如果两个条目标识符引用同一个对象, 则**CompareEntryIDs**会将_lpulResult_参数的内容设置为 TRUE;如果这些对象引用不同的对象, 则**CompareEntryIDs**会将内容设置为 FALSE。 在这两种情况下, **CompareEntryIDs**返回 S_OK。 如果**CompareEntryIDs**返回一个错误, 如果没有通讯簿提供程序注册了一个与条目标识符中的 MAPIUID 结构匹配的**** 结构, 则客户端和提供程序不应执行任何操作, 具体取决于而言. 而是应对执行的操作采取最保守的方法。 
  
## <a name="see-also"></a>另请参阅



[IAddrBook : IMAPIProp](iaddrbookimapiprop.md)

