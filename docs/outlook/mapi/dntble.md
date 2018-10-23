---
title: DNTBLE
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 10fb1650-6c3e-f467-91cd-48e5ddd82827
description: 上次修改时间：2012 年 7 月 5 日
ms.openlocfilehash: 41a61bd05bd511888aeab756166016813f4dceb8
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25391946"
---
# <a name="dntble"></a><span data-ttu-id="95f95-103">DNTBLE</span><span class="sxs-lookup"><span data-stu-id="95f95-103">DNTBLE</span></span>

  
  
<span data-ttu-id="95f95-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="95f95-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="95f95-105">在[下载表状态](download-table-state.md)期间从服务器下载文件夹内容的信息。</span><span class="sxs-lookup"><span data-stu-id="95f95-105">Information for downloading the contents of a folder from the server during the [download table state](download-table-state.md).</span></span> <span data-ttu-id="95f95-106">这一下载过程使用 Microsoft Exchange 增量更改同步 (ICS)。</span><span class="sxs-lookup"><span data-stu-id="95f95-106">This downloading process uses Microsoft Exchange Incremental Change Synchronization (ICS).</span></span> <span data-ttu-id="95f95-107">有关 ICS 的详细信息，请参阅 [ICS 评估条件](https://msdn.microsoft.com/library/aa579252%28EXCHG.80%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="95f95-107">For more information on ICS, see [ICS Evaluation Criteria](https://msdn.microsoft.com/library/aa579252%28EXCHG.80%29.aspx).</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="95f95-108">快速信息</span><span class="sxs-lookup"><span data-stu-id="95f95-108">Quick Info</span></span>

```cpp
struct DNTBLE 
{ 
    UINT cEntNew; 
    UINT cEntMod; 
    UINT cEntRead; 
    UINT cEntDel; 
};
```

## <a name="members"></a><span data-ttu-id="95f95-109">成员</span><span class="sxs-lookup"><span data-stu-id="95f95-109">Members</span></span>

 <span data-ttu-id="95f95-110">_cEntNew_</span><span class="sxs-lookup"><span data-stu-id="95f95-110">_cEntNew_</span></span>
  
> <span data-ttu-id="95f95-111">[传出] 添加到本地存储的项数。</span><span class="sxs-lookup"><span data-stu-id="95f95-111">[out] Number of items added to the local store.</span></span> <span data-ttu-id="95f95-112">Outlook 在下载期间使用 ICS 时填充此值。</span><span class="sxs-lookup"><span data-stu-id="95f95-112">Outlook populates this value during the downloading when using ICS.</span></span>
    
 <span data-ttu-id="95f95-113">_cEntMod_</span><span class="sxs-lookup"><span data-stu-id="95f95-113">_cEntMod_</span></span>
  
> <span data-ttu-id="95f95-114">[传出] 本地存储上已修改的项数。</span><span class="sxs-lookup"><span data-stu-id="95f95-114">[out] Number of items modified on the local store.</span></span> <span data-ttu-id="95f95-115">Outlook 在下载期间使用 ICS 时填充此值。</span><span class="sxs-lookup"><span data-stu-id="95f95-115">Outlook populates this value during the downloading when using ICS.</span></span>
    
 <span data-ttu-id="95f95-116">_cEntRead_</span><span class="sxs-lookup"><span data-stu-id="95f95-116">_cEntRead_</span></span>
  
> <span data-ttu-id="95f95-117">[传出] 本地存储上已读或标记为未读的项数。</span><span class="sxs-lookup"><span data-stu-id="95f95-117">[out] Number of items read or marked unread on the local store.</span></span> <span data-ttu-id="95f95-118">Outlook 在下载期间使用 ICS 时填充此值。</span><span class="sxs-lookup"><span data-stu-id="95f95-118">Outlook populates this value during the downloading when using ICS.</span></span>
    
 <span data-ttu-id="95f95-119">_cEntDel_</span><span class="sxs-lookup"><span data-stu-id="95f95-119">_cEntDel_</span></span>
  
> <span data-ttu-id="95f95-120">[传出] 本地存储上已删除的项数。</span><span class="sxs-lookup"><span data-stu-id="95f95-120">[out] Number of items deleted on the local store.</span></span> <span data-ttu-id="95f95-121">Outlook 在下载期间使用 ICS 时填充此值。</span><span class="sxs-lookup"><span data-stu-id="95f95-121">Outlook populates this value during the downloading when using ICS.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="95f95-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="95f95-122">See also</span></span>



[<span data-ttu-id="95f95-123">关于复制状态机</span><span class="sxs-lookup"><span data-stu-id="95f95-123">About the Replication State Machine</span></span>](about-the-replication-state-machine.md)
  
[<span data-ttu-id="95f95-124">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="95f95-124">MAPI constants</span></span>](mapi-constants.md)
  
[<span data-ttu-id="95f95-125">DNTBL</span><span class="sxs-lookup"><span data-stu-id="95f95-125">DNTBL</span></span>](dntbl.md)

