---
title: HrCreateOfflineObj
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 04d57c1d-ce91-42ce-9f0f-00563092f6f4
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 0a34c441a473154a43a107b4236ccc259d327dba
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32348053"
---
# <a name="hrcreateofflineobj"></a>HrCreateOfflineObj

**适用于**：Outlook 2013 | Outlook 2016 
  
 创建一个 MAPI 脱机对象, 该对象由提供程序和存储区使用, 以便在对象处于联机和脱机状态时通知 MAPI。 
  
|||
|:-----|:-----|
|导出者:  <br/> |Msmapi32  <br/> |
|实现者：  <br/> |Outlook  <br/> |
|调用者：  <br/> |客户端  <br/> |
   
```cpp
STDAPI HrCreateOfflineObj(
ULONG ulFlags,
MAPIOFFLINE_CREATEINFO* pCreateInfo,
IMAPIOfflineMgr** ppOffline
);
```

## <a name="parameters"></a>参数

_ulFlags_
  
> 实时它必须为0。
    
_pCreateInfo_
  
> 实时指向**MAPIOFFLINE_CREATEINFO**结构的指针, 该结构包含创建脱机对象所需的信息。 
    
_ppOffline_
  
> 排除指向**IMAPIOfflineMgr**接口的指针。 
    
## <a name="return-value"></a>返回值

无。
  
HrOpenOfflineObj
  
## <a name="example"></a>示例

```cpp
// create/get global offline object to use as parent.
 ZeroMemory(&OfflineCreateInfo, sizeof(OfflineCreateInfo));
  OfflineCreateInfo.ulSize = sizeof(OfflineCreateInfo);
  OfflineCreateInfo.ulCreateFlags = 0;
  OfflineCreateInfo.pwszProfileName = pszProfileName;
  OfflineCreateInfo.ulCapabilities = ulCapabilities;
  OfflineCreateInfo.pGUID = &GUID_GlobalState;
  OfflineCreateInfo.pInstance = NULL;
  OfflineCreateInfo.pParent = NULL;
  OfflineCreateInfo.pMAPISupport = NULL;
  OfflineCreateInfo.pAggregateInfo = NULL;
  OfflineCreateInfo.pConnectInfo = NULL;
// Create an offline object for the provider with global as parent.
  ZeroMemory(&OfflineCreateInfo, sizeof(OfflineCreateInfo));
  OfflineCreateInfo.ulSize = sizeof(OfflineCreateInfo);
  OfflineCreateInfo.ulCreateFlags = 0;
  OfflineCreateInfo.pwszProfileName = pszProfileName;
  OfflineCreateInfo.ulCapabilities = ulCapabilities;
  OfflineCreateInfo.pGUID = pGuid;
  OfflineCreateInfo.pInstance = pInstance;
  OfflineCreateInfo.pParent = pGlobalOfflineMgr;
  OfflineCreateInfo.pMAPISupport = NULL;
  OfflineCreateInfo.pAggregateInfo = NULL;
  OfflineCreateInfo.pConnectInfo = NULL;
  // create store offline object which aggregates with the store object and has provider offline object as parent.
  ZeroMemory(&OfflineCreateInfo, sizeof(OfflineCreateInfo));
  OfflineCreateInfo.ulSize = sizeof(OfflineCreateInfo);
  OfflineCreateInfo.ulCreateFlags = 0;
  OfflineCreateInfo.pwszProfileName = pszProfileName;
  OfflineCreateInfo.ulCapabilities = ulCapabilities;
  OfflineCreateInfo.pGUID = NULL;
  OfflineCreateInfo.pInstance = NULL;
  OfflineCreateInfo.pParent = m_pProviderOfflineMgr;
  OfflineCreateInfo.pMAPISupport = pMAPISup;
  OfflineCreateInfo.pAggregateInfo = &AggregateInfo;
  OfflineCreateInfo.pConnectInfo = NULL;
  ZeroMemory(&AggregateInfo, sizeof(AggregateInfo));
  AggregateInfo.ulSize = sizeof(AggregateInfo);
  AggregateInfo.pOuterObj = (IMsgStore *)this;
  AggregateInfo.pRefTrackRoot = NULL;

```

## <a name="see-also"></a>另请参阅

- [MAPIOFFLINE_AGGREGATEINFO](mapioffline_aggregateinfo.md)
- [MAPIOFFLINE_CREATEINFO](mapioffline_createinfo.md)

