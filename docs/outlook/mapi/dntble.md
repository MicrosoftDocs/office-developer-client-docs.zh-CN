---
title: DNTBLE
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 10fb1650-6c3e-f467-91cd-48e5ddd82827
description: 上次修改时间： 2012 年 7 月 5 日
ms.openlocfilehash: 41a61bd05bd511888aeab756166016813f4dceb8
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25391946"
---
# <a name="dntble"></a><span data-ttu-id="6aa0b-103">DNTBLE</span><span class="sxs-lookup"><span data-stu-id="6aa0b-103">DNTBLE</span></span>

  
  
<span data-ttu-id="6aa0b-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="6aa0b-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="6aa0b-105">在[下载表状态](download-table-state.md)期间，从服务器下载文件夹的内容的信息。</span><span class="sxs-lookup"><span data-stu-id="6aa0b-105">Information for downloading the contents of a folder from the server during the [download table state](download-table-state.md).</span></span> <span data-ttu-id="6aa0b-106">此下载的过程使用 Microsoft Exchange 增量更改同步 (ICS)。</span><span class="sxs-lookup"><span data-stu-id="6aa0b-106">This downloading process uses Microsoft Exchange Incremental Change Synchronization (ICS).</span></span> <span data-ttu-id="6aa0b-107">ICS 的详细信息，请参阅[ICS 评价标准](https://msdn.microsoft.com/library/aa579252%28EXCHG.80%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="6aa0b-107">For more information on ICS, see [ICS Evaluation Criteria](https://msdn.microsoft.com/library/aa579252%28EXCHG.80%29.aspx).</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="6aa0b-108">快速信息</span><span class="sxs-lookup"><span data-stu-id="6aa0b-108">Quick info</span></span>

```cpp
struct DNTBLE 
{ 
    UINT cEntNew; 
    UINT cEntMod; 
    UINT cEntRead; 
    UINT cEntDel; 
};
```

## <a name="members"></a><span data-ttu-id="6aa0b-109">Members</span><span class="sxs-lookup"><span data-stu-id="6aa0b-109">Members</span></span>

 <span data-ttu-id="6aa0b-110">_cEntNew_</span><span class="sxs-lookup"><span data-stu-id="6aa0b-110">_cEntNew_</span></span>
  
> <span data-ttu-id="6aa0b-111">[输出]添加到本地存储的项目数。</span><span class="sxs-lookup"><span data-stu-id="6aa0b-111">[out] Number of items added to the local store.</span></span> <span data-ttu-id="6aa0b-112">Outlook 时使用 ICS 下载期间填充此值。</span><span class="sxs-lookup"><span data-stu-id="6aa0b-112">Outlook populates this value during the downloading when using ICS.</span></span>
    
 <span data-ttu-id="6aa0b-113">_cEntMod_</span><span class="sxs-lookup"><span data-stu-id="6aa0b-113">_cEntMod_</span></span>
  
> <span data-ttu-id="6aa0b-114">[输出]修改对本地存储的项目数。</span><span class="sxs-lookup"><span data-stu-id="6aa0b-114">[out] Number of items modified on the local store.</span></span> <span data-ttu-id="6aa0b-115">Outlook 时使用 ICS 下载期间填充此值。</span><span class="sxs-lookup"><span data-stu-id="6aa0b-115">Outlook populates this value during the downloading when using ICS.</span></span>
    
 <span data-ttu-id="6aa0b-116">_cEntRead_</span><span class="sxs-lookup"><span data-stu-id="6aa0b-116">_cEntRead_</span></span>
  
> <span data-ttu-id="6aa0b-117">[输出]读取或上本地存储标记为未读的项目数。</span><span class="sxs-lookup"><span data-stu-id="6aa0b-117">[out] Number of items read or marked unread on the local store.</span></span> <span data-ttu-id="6aa0b-118">Outlook 时使用 ICS 下载期间填充此值。</span><span class="sxs-lookup"><span data-stu-id="6aa0b-118">Outlook populates this value during the downloading when using ICS.</span></span>
    
 <span data-ttu-id="6aa0b-119">_cEntDel_</span><span class="sxs-lookup"><span data-stu-id="6aa0b-119">_cEntDel_</span></span>
  
> <span data-ttu-id="6aa0b-120">[输出]对本地存储删除的项目数。</span><span class="sxs-lookup"><span data-stu-id="6aa0b-120">[out] Number of items deleted on the local store.</span></span> <span data-ttu-id="6aa0b-121">Outlook 时使用 ICS 下载期间填充此值。</span><span class="sxs-lookup"><span data-stu-id="6aa0b-121">Outlook populates this value during the downloading when using ICS.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="6aa0b-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6aa0b-122">See also</span></span>



[<span data-ttu-id="6aa0b-123">关于复制状态计算机</span><span class="sxs-lookup"><span data-stu-id="6aa0b-123">About the Replication State Machine</span></span>](about-the-replication-state-machine.md)
  
[<span data-ttu-id="6aa0b-124">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="6aa0b-124">MAPI Constants</span></span>](mapi-constants.md)
  
[<span data-ttu-id="6aa0b-125">DNTBL</span><span class="sxs-lookup"><span data-stu-id="6aa0b-125">DNTBL</span></span>](dntbl.md)

