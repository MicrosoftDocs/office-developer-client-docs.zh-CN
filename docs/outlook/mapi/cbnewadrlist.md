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
ms.openlocfilehash: 898876863223aefa868fd37deced2948bd5a5694
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22569748"
---
# <a name="cbnewadrlist"></a><span data-ttu-id="b39cd-103">CbNewADRLIST</span><span class="sxs-lookup"><span data-stu-id="b39cd-103">CbNewADRLIST</span></span>

  
  
<span data-ttu-id="b39cd-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="b39cd-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="b39cd-105">计算应分配的新[ADRLIST](adrlist.md)结构，其中包含的指定由[ADRENTRY](adrentry.md)结构的收件人数量的字节数。</span><span class="sxs-lookup"><span data-stu-id="b39cd-105">Computes the number of bytes that should be allocated for a new [ADRLIST](adrlist.md) structure that contains a specified number of recipients represented by [ADRENTRY](adrentry.md) structures.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="b39cd-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="b39cd-106">Header file:</span></span>  <br/> |<span data-ttu-id="b39cd-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="b39cd-107">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="b39cd-108">相关的结构：</span><span class="sxs-lookup"><span data-stu-id="b39cd-108">Related structure:</span></span>  <br/> |<span data-ttu-id="b39cd-109">**ADRLIST**</span><span class="sxs-lookup"><span data-stu-id="b39cd-109">**ADRLIST**</span></span> <br/> |
   
```cpp
CbNewADRLIST (_centries)
```

## <a name="parameters"></a><span data-ttu-id="b39cd-110">参数</span><span class="sxs-lookup"><span data-stu-id="b39cd-110">Parameters</span></span>

 <span data-ttu-id="b39cd-111">__centries_</span><span class="sxs-lookup"><span data-stu-id="b39cd-111">__centries_</span></span>
  
> <span data-ttu-id="b39cd-112">要包含在新的**ADRLIST**结构**ADRENTRY**结构的计数。</span><span class="sxs-lookup"><span data-stu-id="b39cd-112">Count of **ADRENTRY** structures to be included in the new **ADRLIST** structure.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="b39cd-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b39cd-113">See also</span></span>



[<span data-ttu-id="b39cd-114">ADRLIST</span><span class="sxs-lookup"><span data-stu-id="b39cd-114">ADRLIST</span></span>](adrlist.md)
  
[<span data-ttu-id="b39cd-115">ADRENTRY</span><span class="sxs-lookup"><span data-stu-id="b39cd-115">ADRENTRY</span></span>](adrentry.md)


[<span data-ttu-id="b39cd-116">与结构相关的宏</span><span class="sxs-lookup"><span data-stu-id="b39cd-116">Macros Related to Structures</span></span>](macros-related-to-structures.md)

