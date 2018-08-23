---
title: IContabAdminRemoveStore
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IContabAdmin.RemoveStore
api_type:
- COM
ms.assetid: 2a5fcf5c-8a5a-4774-b8c9-1ac1ff27947d
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 2ec8a28dc52e2aa1f1fa63410b6bd6c13fb5bd57
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22583986"
---
# <a name="icontabadminremovestore"></a>IContabAdmin::RemoveStore

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
删除联系人通讯簿 (CAB) 指定由给定的条目 ID 从通讯簿层次结构。
  
```cpp
HRESULT RemoveStore(
ULONG cbEntryID, 
LPENTRYID lpEntryID
);
```

## <a name="parameters"></a>参数

 _cbEntryID_
  
> [in]在_lpEntryID_参数指向的项标识符的字节数。 
    
 _lpEntryID_
  
> [in]指向要打开的对象的项标识符的指针。
    

