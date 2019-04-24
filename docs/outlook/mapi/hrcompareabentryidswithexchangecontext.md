---
title: HrCompareABEntryIDsWithExchangeContext
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: e537c25f-51b5-4f06-a20a-44ee540b9a1f
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 4bada5913623e2eb463a9e72347bd31eb22c414b
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32348074"
---
# <a name="hrcompareabentryidswithexchangecontext"></a>HrCompareABEntryIDsWithExchangeContext

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
在多个 Exchange 配置文件中安全地比较两个通讯簿**entryid** 。 此函数是[IAddrBook:: CompareEntryIDs](iaddrbook-compareentryids.md)的替代函数。
  
|||
|:-----|:-----|
|标头文件：  <br/> |abhelp  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |客户端应用程序和服务提供程序  <br/> |
   
```cpp
HRESULT HrCompareABEntryIDsWithExchangeContext(
  LPMAPISESSION pmsess,
  const MAPIUID *pEmsmdbUID,
  LPADRBOOK pAddrBook,
  ULONG cbEntryID1,
  LPENTRYID lpEntryID1,
  ULONG cbEntryID2,
  LPENTRYID lpEntryID2,
  ULONG ulFlags,
  ULONG * lpulResult
);
```

## <a name="parameters"></a>参数

 _pmsess_
  
> 实时登录的**IMAPISession**。 它不能为 NULL。
    
 _pEmsmdbUID_
  
> 实时指向**emsmdbUID**的指针, 该链接标识包含此函数应用于显示条目标识符详细信息的 exchange 通讯簿提供程序的 exchange 服务。 如果传入条目标识符不是 Exchange 通讯簿提供程序条目标识符, 则此参数将被忽略, 并且函数调用的行为就像[IAddrBook::D etails](iaddrbook-details.md)。 如果此参数为 NULL 或零 MAPIUID, 则此函数的行为类似于[IAddrBook::D etails](iaddrbook-details.md)。
    
 _pAddrBook_
  
> 实时用于打开条目标识符的通讯簿。 它不能为 NULL。
    
 _cbEntryID1_
  
> 实时由_lpEntryID1_参数指定的第一个条目标识符的字节数。 
    
 _lpEntryID1_
  
> 实时指向表示要比较的通讯簿条目的第一个条目标识符的指针。
    
 _cbEntryID2_
  
> 实时由_lpEntryID2_参数指定的第二个条目标识符的字节数。 
    
 _lpEntryID2_
  
> 实时一个指向比较中使用的第二个条目标识符的指针, 该标识符代表要比较的通讯簿条目。
    
 _ulFlags_
  
> 实时保留必须为零。
    
 _lpulResult_
  
> 排除指向包含比较结果的位置的指针。 
    

