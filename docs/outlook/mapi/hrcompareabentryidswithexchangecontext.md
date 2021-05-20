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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33436431"
---
# <a name="hrcompareabentryidswithexchangecontext"></a>HrCompareABEntryIDsWithExchangeContext

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
在多通讯簿 **配置文件** 中安全地比较两个Exchange条目。 此函数是 [IAddrBook：：CompareEntryIDs 的替换函数](iaddrbook-compareentryids.md)。
  
|||
|:-----|:-----|
|标头文件：  <br/> |abhelp.h  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |客户端应用程序和服务提供商  <br/> |
   
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
  
> [in]登录的 **IMAPISession**。 它不能为 NULL。
    
 _pEmsmdbUID_
  
> [in]指向 **emsmdbUID** 的指针，标识包含 Exchange 通讯簿提供程序的 Exchange Service，此函数应该使用该提供程序在条目标识符上显示详细信息。 如果传入条目标识符不是通讯簿Exchange标识符，则忽略此参数，并且函数调用的行为类似于[IAddrBook：:D etails](iaddrbook-details.md)。 如果此参数为 NULL 或零 MAPIUID，则此函数的行为类似于 [IAddrBook：:D etails](iaddrbook-details.md)。
    
 _pAddrBook_
  
> [in]用于打开条目标识符的通讯簿。 它不能为 NULL。
    
 _cbEntryID1_
  
> [in]  _lpEntryID1_ 参数指定的第一个条目标识符的字节计数。 
    
 _lpEntryID1_
  
> [in]指向表示要比较的通讯簿条目的第一个条目标识符的指针。
    
 _cbEntryID2_
  
> [in]  _lpEntryID2_ 参数指定的第二个条目标识符的字节计数。 
    
 _lpEntryID2_
  
> [in]指向比较中使用的第二个条目标识符的指针，该标识符表示要比较的通讯簿条目。
    
 _ulFlags_
  
> [in]保留;必须为零。
    
 _lpulResult_
  
> [out]指向包含比较结果的位置的指针。 
    

