---
title: MAPIOFFLINE_CREATEINFO
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 539aa31d-7dec-4dbb-93f7-fa060c43565a
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: a9b11b134f5d4a32a5a55008f557821d74b474bc
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32357125"
---
# <a name="mapiofflinecreateinfo"></a>MAPIOFFLINE_CREATEINFO

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
此结构与[HrCreateOfflineObj](hrcreateofflineobj.md)一起使用。
  
```cpp
typedef struct
{
  ULONG      ulSize;
  ULONG      ulCreateFlags;
  LPCWSTR      pwszProfileName;
  ULONG      ulCapabilities;
  const GUID*      pGUID;
  const GUID*      pInstance;
  IMAPIOfflineMgr*    pParent;
  IUnknown*      pMAPISupport;
  MAPIOFFLINE_AGGREGATEINFO*  pAggregateInfo;
  MAPIOFFLINE_CONNECTINFO*  pConnectInfo;
} MAPIOFFLINE_CREATEINFO;
```

## <a name="members"></a>Members

 **ulSize**
  
> 结构的大小。
    
 **ulCreateFlags**
  
> 它必须为0。
    
 **pwszProfileName**
  
> 配置文件的名称。
    
 **ulCapabilities**
  
> 以下功能标志的位掩码。
    
|||
|:-----|:-----|
|MAPIOFFLINE_CAPABILITY_OFFLINE  <br/> |脱机对象能够脱机。  <br/> |
|MAPIOFFLINE_CAPABILITY_ONLINE  <br/> |脱机对象能够联机。  <br/> |
   
 **pGUID**
  
> 指向一个 GUID 的指针, 该 GUID 用于从其他脱机对象中唯一标识此类型的脱机对象。 GUID_GlobalState 是指全局脱机对象, 对象可将其用作父对象。
    
 **pInstance**
  
> 指向唯一标识此脱机对象的 GUID 的指针。 它用于消除来自其他对象的这两个脱机对象的歧义。
    
 **pParent**
  
> 指向脱机对象的指针, 该对象是此脱机对象的父对象, 其更改将继承此脱机对象。
    
 **pMAPISupport**
  
>  标识将使用此脱机对象的 MAPI 支持对象。 例如, 如果此脱机对象用于跟踪存储的脱机状态和联机状态, 则这就是存储支持对象。 但是, 如果这是一个不支持对象的对象的脱机对象, 则它可以为 NULL。 
    
 **pAggregateInfo**
  
> 指向 MAPIOFFLINE_AGGREGATEINFO 结构的指针。 有关详细信息, 请参阅[MAPIOFFLINE_AGGREGATEINFO](mapioffline_aggregateinfo.md)。
    
 **pConnectInfo**
  
> 必须为 null。
    
## <a name="see-also"></a>另请参阅



[HrCreateOfflineObj](hrcreateofflineobj.md)
  
[MAPIOFFLINE_AGGREGATEINFO](mapioffline_aggregateinfo.md)

