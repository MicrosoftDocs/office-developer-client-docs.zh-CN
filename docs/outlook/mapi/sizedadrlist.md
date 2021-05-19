---
title: SizedADRLIST
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.SizedADRLIST
api_type:
- COM
ms.assetid: 5c64d74a-83a7-4122-b1d1-fcca0f4a6cdb
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: c35a1eb54b29c04bc8eed453272b59aae0ea737e
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33423459"
---
# <a name="sizedadrlist"></a><span data-ttu-id="00d36-103">SizedADRLIST</span><span class="sxs-lookup"><span data-stu-id="00d36-103">SizedADRLIST</span></span>

<span data-ttu-id="00d36-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="00d36-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="00d36-105">定义具有指定 [名称的 ADRLIST](adrlist.md) 结构，其中包含指定数量的 [ADRENTRY](adrentry.md) 结构。</span><span class="sxs-lookup"><span data-stu-id="00d36-105">Defines an [ADRLIST](adrlist.md) structure with the specified name that contains a specified number of [ADRENTRY](adrentry.md) structures.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="00d36-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="00d36-106">Header file:</span></span>  <br/> |<span data-ttu-id="00d36-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="00d36-107">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="00d36-108">相关结构：</span><span class="sxs-lookup"><span data-stu-id="00d36-108">Related structure:</span></span>  <br/> |<span data-ttu-id="00d36-109">**ADRLIST**</span><span class="sxs-lookup"><span data-stu-id="00d36-109">**ADRLIST**</span></span> <br/> |
   
```cpp
SizedADRLIST (_centries,_name)
```

## <a name="parameters"></a><span data-ttu-id="00d36-110">参数</span><span class="sxs-lookup"><span data-stu-id="00d36-110">Parameters</span></span>

<span data-ttu-id="00d36-111">_ _centries_</span><span class="sxs-lookup"><span data-stu-id="00d36-111">_ _centries_</span></span>
  
> <span data-ttu-id="00d36-112">要 **包含在新 ADRLIST 结构的 ADRENTRY** 结构计数。 </span><span class="sxs-lookup"><span data-stu-id="00d36-112">Count of **ADRENTRY** structures to be included in the new **ADRLIST** structure.</span></span> 
    
<span data-ttu-id="00d36-113">_ _name_</span><span class="sxs-lookup"><span data-stu-id="00d36-113">_ _name_</span></span>
  
> <span data-ttu-id="00d36-114">新 **ADRLIST 结构** 的名称。</span><span class="sxs-lookup"><span data-stu-id="00d36-114">Name for the new **ADRLIST** structure.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="00d36-115">备注</span><span class="sxs-lookup"><span data-stu-id="00d36-115">Remarks</span></span>

<span data-ttu-id="00d36-116">**SizedADRLIST** 宏允许您定义在数组长度要求已知时具有显式边界的收件人列表。</span><span class="sxs-lookup"><span data-stu-id="00d36-116">The **SizedADRLIST** macro lets you define a recipient list that has explicit bounds when array length requirements are known.</span></span> <span data-ttu-id="00d36-117">以下代码演示如何将 **SizedADRLIST** 宏的结果强制转换到 **ADRLIST** 结构指针：</span><span class="sxs-lookup"><span data-stu-id="00d36-117">The following code shows how to cast the result of the **SizedADRLIST** macro to an **ADRLIST** structure pointer:</span></span> 
  
```cpp
lpADRList = (LPADRLIST) &SizedADRList;
```

## <a name="see-also"></a><span data-ttu-id="00d36-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="00d36-118">See also</span></span>

- [<span data-ttu-id="00d36-119">ADRLIST</span><span class="sxs-lookup"><span data-stu-id="00d36-119">ADRLIST</span></span>](adrlist.md)
- [<span data-ttu-id="00d36-120">ADRENTRY</span><span class="sxs-lookup"><span data-stu-id="00d36-120">ADRENTRY</span></span>](adrentry.md)
- [<span data-ttu-id="00d36-121">与结构相关的宏</span><span class="sxs-lookup"><span data-stu-id="00d36-121">Macros Related to Structures</span></span>](macros-related-to-structures.md)

