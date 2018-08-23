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
ms.openlocfilehash: ffac4328401b8afbc07eb650ea6c08da5f9c51b2
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22594493"
---
# <a name="mapiofflinecreateinfo"></a>MAPIOFFLINE_CREATEINFO

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
此结构用于[HrCreateOfflineObj](hrcreateofflineobj.md)。
  
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
  
> 它必须是 0。
    
 **pwszProfileName**
  
> 配置文件的名称。
    
 **ulCapabilities**
  
> 以下功能标志位掩码。
    
|||
|:-----|:-----|
|MAPIOFFLINE_CAPABILITY_OFFLINE  <br/> |脱机对象都能够脱机。  <br/> |
|MAPIOFFLINE_CAPABILITY_ONLINE  <br/> |能够上网的脱机对象。  <br/> |
   
 **pGUID**
  
> 指向用于唯一标识此类型的其他脱机对象从脱机对象的 GUID。 GUID_GlobalState 指全局脱机对象的对象可用作父对象。
    
 **pInstance**
  
> 用于唯一标识此脱机对象的 guid 的指针。 它用于消除歧义此脱机对象从其他对象。
    
 **pParent**
  
> 对脱机对象的父级的脱机对象，它的指针更改此脱机对象将继承。
    
 **pMAPISupport**
  
>  标识的将使用此脱机对象的 MAPI 支持对象。 例如，如果脱机使用此对象以跟踪存储脱机和联机状态，则这是存储支持对象。 但是，如果这是具有不支持对象的对象的脱机对象它可以是 NULL。 
    
 **pAggregateInfo**
  
> 指向 MAPIOFFLINE_AGGREGATEINFO 结构的指针。 有关详细信息，请参阅[MAPIOFFLINE_AGGREGATEINFO](mapioffline_aggregateinfo.md)。
    
 **pConnectInfo**
  
> 必须为空。
    
## <a name="see-also"></a>另请参阅



[HrCreateOfflineObj](hrcreateofflineobj.md)
  
[MAPIOFFLINE_AGGREGATEINFO](mapioffline_aggregateinfo.md)

