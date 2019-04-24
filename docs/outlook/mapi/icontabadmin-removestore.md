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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 4865c1c867dd73514ab22ac4e8da628caf154ee7
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32339268"
---
# <a name="icontabadminremovestore"></a><span data-ttu-id="743f6-103">IContabAdmin::RemoveStore</span><span class="sxs-lookup"><span data-stu-id="743f6-103">IContabAdmin::RemoveStore</span></span>

  
  
<span data-ttu-id="743f6-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="743f6-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="743f6-105">从通讯簿层次结构中删除由给定条目 ID 指定的联系人通讯簿 (CAB)。</span><span class="sxs-lookup"><span data-stu-id="743f6-105">Removes the Contact Address Book (CAB) specified by the given entry ID from the address book hierarchy.</span></span>
  
```cpp
HRESULT RemoveStore(
ULONG cbEntryID, 
LPENTRYID lpEntryID
);
```

## <a name="parameters"></a><span data-ttu-id="743f6-106">参数</span><span class="sxs-lookup"><span data-stu-id="743f6-106">Parameters</span></span>

 <span data-ttu-id="743f6-107">_cbEntryID_</span><span class="sxs-lookup"><span data-stu-id="743f6-107">_cbEntryID_</span></span>
  
> <span data-ttu-id="743f6-108">实时条目标识符中由_lpEntryID_参数指向的字节数。</span><span class="sxs-lookup"><span data-stu-id="743f6-108">[in] The byte count in the entry identifier pointed to by the  _lpEntryID_ parameter.</span></span> 
    
 <span data-ttu-id="743f6-109">_lpEntryID_</span><span class="sxs-lookup"><span data-stu-id="743f6-109">_lpEntryID_</span></span>
  
> <span data-ttu-id="743f6-110">实时指向要打开的对象的条目标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="743f6-110">[in] A pointer to the entry identifier of the object to open.</span></span>
    

