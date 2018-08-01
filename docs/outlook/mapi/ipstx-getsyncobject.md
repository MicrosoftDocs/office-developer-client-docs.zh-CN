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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 44261e5ac296004fd113d4c9123b99c482bcb732
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776065"
---
# <a name="ipstxgetsyncobject"></a><span data-ttu-id="1fdc1-103">IPSTX::GetSyncObject</span><span class="sxs-lookup"><span data-stu-id="1fdc1-103">IPSTX::GetSyncObject</span></span>

  
  
<span data-ttu-id="1fdc1-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="1fdc1-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="1fdc1-105">启动同步会话，并获取相关联的**[IOSTX](iostxiunknown.md)** 接口。</span><span class="sxs-lookup"><span data-stu-id="1fdc1-105">Starts a synchronization session and gets the associated **[IOSTX](iostxiunknown.md)** interface.</span></span> 
  
```cpp
HRESULT GetSyncObject( 
   IOSTX **ppostx 
);
```

## <a name="parameters"></a><span data-ttu-id="1fdc1-106">参数</span><span class="sxs-lookup"><span data-stu-id="1fdc1-106">Parameters</span></span>

 <span data-ttu-id="1fdc1-107">_ppostx_</span><span class="sxs-lookup"><span data-stu-id="1fdc1-107">_ppostx_</span></span>
  
>  <span data-ttu-id="1fdc1-108">[输出]指向要获取的**IOSTX**接口的指针。</span><span class="sxs-lookup"><span data-stu-id="1fdc1-108">[out] Pointer to the **IOSTX** interface to get.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="1fdc1-109">说明</span><span class="sxs-lookup"><span data-stu-id="1fdc1-109">Remarks</span></span>

<span data-ttu-id="1fdc1-110">呼叫者必须确保同时在多个线程上不同步的相同的文件夹。</span><span class="sxs-lookup"><span data-stu-id="1fdc1-110">The caller must ensure that the same folder is not synchronized at the same time on more than one thread.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="1fdc1-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1fdc1-111">See also</span></span>



[<span data-ttu-id="1fdc1-112">IPSTX::EmulateSpooler</span><span class="sxs-lookup"><span data-stu-id="1fdc1-112">IPSTX::EmulateSpooler</span></span>](ipstx-emulatespooler.md)
  
[<span data-ttu-id="1fdc1-113">IPSTX::GetLastError</span><span class="sxs-lookup"><span data-stu-id="1fdc1-113">IPSTX::GetLastError</span></span>](ipstx-getlasterror.md)

