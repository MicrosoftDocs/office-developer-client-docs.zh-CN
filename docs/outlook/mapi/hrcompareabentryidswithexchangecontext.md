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
ms.openlocfilehash: eb91f4998f94ffafbc33b6024228945f7c91cf43
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22564988"
---
# <a name="hrcompareabentryidswithexchangecontext"></a>HrCompareABEntryIDsWithExchangeContext

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
比较多个 Exchange 配置文件中的安全地两个地址簿**Entryid** 。 此函数是[IAddrBook::CompareEntryIDs](iaddrbook-compareentryids.md)替换函数。
  
|||
|:-----|:-----|
|头文件：  <br/> |abhelp.h  <br/> |
|通过实现：  <br/> |MAPI  <br/> |
|调用：  <br/> |客户端应用程序和服务提供商  <br/> |
   
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
  
> [in]登录**IMAPISession**。 它不能为 NULL。
    
 _pEmsmdbUID_
  
> [in]指向标识包含 Exchange 通讯簿提供程序，此函数应该使用要显示的项标识符的详细信息的 Exchange 服务**emsmdbUID**的指针。 如果传入的项标识符不是 Exchange 通讯簿提供程序条目标识符，则忽略此参数，并函数调用与[IAddrBook::Details](iaddrbook-details.md)相似之处。 如果此参数为 NULL 或零 MAPIUID，此函数的行为类似[IAddrBook::Details](iaddrbook-details.md)。
    
 _pAddrBook_
  
> [in]通讯簿用于打开的项标识符。 它不能为 NULL。
    
 _cbEntryID1_
  
> [in]第一个条目标识符_lpEntryID1_参数指定的字节数。 
    
 _lpEntryID1_
  
> [in]一个指向代表通讯簿条目进行比较的第一个条目标识符。
    
 _cbEntryID2_
  
> [in]第二个条目标识符_lpEntryID2_参数指定的字节数。 
    
 _lpEntryID2_
  
> [in]一个指向代表通讯簿条目，以比较比较中使用的第二个条目标识符。
    
 _ulFlags_
  
> [in]保留;必须为零。
    
 _lpulResult_
  
> [输出]指向包含的比较结果的位置的指针。 
    

