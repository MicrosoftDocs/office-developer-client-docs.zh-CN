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
ms.openlocfilehash: 868f38eaf52d3d0a3787623983a4a587de8fdc3b
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775273"
---
# <a name="icontabadminremovestore"></a><span data-ttu-id="3e023-103">IContabAdmin::RemoveStore</span><span class="sxs-lookup"><span data-stu-id="3e023-103">IContabAdmin::RemoveStore</span></span>

  
  
<span data-ttu-id="3e023-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="3e023-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="3e023-105">删除联系人通讯簿 (CAB) 指定由给定的条目 ID 从通讯簿层次结构。</span><span class="sxs-lookup"><span data-stu-id="3e023-105">Removes the Contact Address Book (CAB) specified by the given entry ID from the address book hierarchy.</span></span>
  
```cpp
HRESULT RemoveStore(
ULONG cbEntryID, 
LPENTRYID lpEntryID
);
```

## <a name="parameters"></a><span data-ttu-id="3e023-106">参数</span><span class="sxs-lookup"><span data-stu-id="3e023-106">Parameters</span></span>

 <span data-ttu-id="3e023-107">_cbEntryID_</span><span class="sxs-lookup"><span data-stu-id="3e023-107">_cbEntryID_</span></span>
  
> <span data-ttu-id="3e023-108">[in]在_lpEntryID_参数指向的项标识符的字节数。</span><span class="sxs-lookup"><span data-stu-id="3e023-108">[in] The byte count in the entry identifier pointed to by the  _lpEntryID_ parameter.</span></span> 
    
 <span data-ttu-id="3e023-109">_lpEntryID_</span><span class="sxs-lookup"><span data-stu-id="3e023-109">_lpEntryID_</span></span>
  
> <span data-ttu-id="3e023-110">[in]指向要打开的对象的项标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="3e023-110">[in] A pointer to the entry identifier of the object to open.</span></span>
    

