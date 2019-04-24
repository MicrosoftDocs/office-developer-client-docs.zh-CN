---
title: IPSTXGetSyncObject
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IPSTX.GetSyncObject
api_type:
- COM
ms.assetid: b93dae79-4305-9a3a-7b93-42319f7e26ba
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 31ef1f5c6af498f042ab766ae90fcfbce805700a
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32315083"
---
# <a name="ipstxgetsyncobject"></a><span data-ttu-id="293ef-103">IPSTX::GetSyncObject</span><span class="sxs-lookup"><span data-stu-id="293ef-103">IPSTX::GetSyncObject</span></span>

  
  
<span data-ttu-id="293ef-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="293ef-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="293ef-105">启动同步会话并获取关联的**[IOSTX](iostxiunknown.md)** 接口。</span><span class="sxs-lookup"><span data-stu-id="293ef-105">Starts a synchronization session and gets the associated **[IOSTX](iostxiunknown.md)** interface.</span></span> 
  
```cpp
HRESULT GetSyncObject( 
   IOSTX **ppostx 
);
```

## <a name="parameters"></a><span data-ttu-id="293ef-106">参数</span><span class="sxs-lookup"><span data-stu-id="293ef-106">Parameters</span></span>

 <span data-ttu-id="293ef-107">_ppostx_</span><span class="sxs-lookup"><span data-stu-id="293ef-107">_ppostx_</span></span>
  
>  <span data-ttu-id="293ef-108">排除指向要获取的**IOSTX**接口的指针。</span><span class="sxs-lookup"><span data-stu-id="293ef-108">[out] Pointer to the **IOSTX** interface to get.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="293ef-109">注解</span><span class="sxs-lookup"><span data-stu-id="293ef-109">Remarks</span></span>

<span data-ttu-id="293ef-110">调用方必须确保同一个文件夹不会同时在多个线程上同步。</span><span class="sxs-lookup"><span data-stu-id="293ef-110">The caller must ensure that the same folder is not synchronized at the same time on more than one thread.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="293ef-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="293ef-111">See also</span></span>



[<span data-ttu-id="293ef-112">IPSTX::EmulateSpooler</span><span class="sxs-lookup"><span data-stu-id="293ef-112">IPSTX::EmulateSpooler</span></span>](ipstx-emulatespooler.md)
  
[<span data-ttu-id="293ef-113">IPSTX::GetLastError</span><span class="sxs-lookup"><span data-stu-id="293ef-113">IPSTX::GetLastError</span></span>](ipstx-getlasterror.md)

