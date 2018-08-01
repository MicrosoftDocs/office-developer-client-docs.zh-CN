---
title: CbNewADRLIST
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.CbNewADRLIST
api_type:
- COM
ms.assetid: 9ec1bbaa-7707-4239-9994-21ad1116430b
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 0bbad04e728c9283df0a9b7ceb7a8e303f0595dc
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774628"
---
# <a name="cbnewadrlist"></a><span data-ttu-id="d85d0-103">CbNewADRLIST</span><span class="sxs-lookup"><span data-stu-id="d85d0-103">CbNewADRLIST</span></span>

  
  
<span data-ttu-id="d85d0-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="d85d0-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="d85d0-105">计算应分配的新[ADRLIST](adrlist.md)结构，其中包含的指定由[ADRENTRY](adrentry.md)结构的收件人数量的字节数。</span><span class="sxs-lookup"><span data-stu-id="d85d0-105">Computes the number of bytes that should be allocated for a new [ADRLIST](adrlist.md) structure that contains a specified number of recipients represented by [ADRENTRY](adrentry.md) structures.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="d85d0-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="d85d0-106">Header file:</span></span>  <br/> |<span data-ttu-id="d85d0-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="d85d0-107">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="d85d0-108">相关的结构：</span><span class="sxs-lookup"><span data-stu-id="d85d0-108">Related structure:</span></span>  <br/> |<span data-ttu-id="d85d0-109">**ADRLIST**</span><span class="sxs-lookup"><span data-stu-id="d85d0-109">**ADRLIST**</span></span> <br/> |
   
```cpp
CbNewADRLIST (_centries)
```

## <a name="parameters"></a><span data-ttu-id="d85d0-110">参数</span><span class="sxs-lookup"><span data-stu-id="d85d0-110">Parameters</span></span>

 <span data-ttu-id="d85d0-111">__centries_</span><span class="sxs-lookup"><span data-stu-id="d85d0-111">__centries_</span></span>
  
> <span data-ttu-id="d85d0-112">要包含在新的**ADRLIST**结构**ADRENTRY**结构的计数。</span><span class="sxs-lookup"><span data-stu-id="d85d0-112">Count of **ADRENTRY** structures to be included in the new **ADRLIST** structure.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="d85d0-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d85d0-113">See also</span></span>



[<span data-ttu-id="d85d0-114">ADRLIST</span><span class="sxs-lookup"><span data-stu-id="d85d0-114">ADRLIST</span></span>](adrlist.md)
  
[<span data-ttu-id="d85d0-115">ADRENTRY</span><span class="sxs-lookup"><span data-stu-id="d85d0-115">ADRENTRY</span></span>](adrentry.md)


[<span data-ttu-id="d85d0-116">与结构相关的宏</span><span class="sxs-lookup"><span data-stu-id="d85d0-116">Macros Related to Structures</span></span>](macros-related-to-structures.md)

