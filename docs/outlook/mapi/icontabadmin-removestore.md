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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33435416"
---
# <a name="icontabadminremovestore"></a><span data-ttu-id="30e92-103">IContabAdmin::RemoveStore</span><span class="sxs-lookup"><span data-stu-id="30e92-103">IContabAdmin::RemoveStore</span></span>

  
  
<span data-ttu-id="30e92-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="30e92-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="30e92-105">从通讯簿层次结构中删除 (CAB) 指定的联系人通讯簿。</span><span class="sxs-lookup"><span data-stu-id="30e92-105">Removes the Contact Address Book (CAB) specified by the given entry ID from the address book hierarchy.</span></span>
  
```cpp
HRESULT RemoveStore(
ULONG cbEntryID, 
LPENTRYID lpEntryID
);
```

## <a name="parameters"></a><span data-ttu-id="30e92-106">参数</span><span class="sxs-lookup"><span data-stu-id="30e92-106">Parameters</span></span>

 <span data-ttu-id="30e92-107">_cbEntryID_</span><span class="sxs-lookup"><span data-stu-id="30e92-107">_cbEntryID_</span></span>
  
> <span data-ttu-id="30e92-108">[in]  _lpEntryID_ 参数指向的条目标识符中的字节计数。</span><span class="sxs-lookup"><span data-stu-id="30e92-108">[in] The byte count in the entry identifier pointed to by the  _lpEntryID_ parameter.</span></span> 
    
 <span data-ttu-id="30e92-109">_lpEntryID_</span><span class="sxs-lookup"><span data-stu-id="30e92-109">_lpEntryID_</span></span>
  
> <span data-ttu-id="30e92-110">[in]指向要打开的对象的条目标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="30e92-110">[in] A pointer to the entry identifier of the object to open.</span></span>
    

