---
title: SMAPIFormInfoArray
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.SMAPIFormInfoArray
api_type:
- COM
ms.assetid: f5eeb75d-debb-4ac1-b239-e8e852460ce0
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 6389bbf2094f51711d80896db0db9862059826cc
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778833"
---
# <a name="smapiforminfoarray"></a><span data-ttu-id="2bbbb-103">SMAPIFormInfoArray</span><span class="sxs-lookup"><span data-stu-id="2bbbb-103">SMAPIFormInfoArray</span></span>

  
  
<span data-ttu-id="2bbbb-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="2bbbb-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="2bbbb-105">包含指向窗体信息对象的数组。</span><span class="sxs-lookup"><span data-stu-id="2bbbb-105">Contains an array of pointers to form information objects.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="2bbbb-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="2bbbb-106">Header file:</span></span>  <br/> |<span data-ttu-id="2bbbb-107">Mapiform.h</span><span class="sxs-lookup"><span data-stu-id="2bbbb-107">Mapiform.h</span></span>  <br/> |
|<span data-ttu-id="2bbbb-108">相关的宏：</span><span class="sxs-lookup"><span data-stu-id="2bbbb-108">Related macro:</span></span>  <br/> |[<span data-ttu-id="2bbbb-109">CbMAPIFormInfoArray</span><span class="sxs-lookup"><span data-stu-id="2bbbb-109">CbMAPIFormInfoArray</span></span>](cbmapiforminfoarray.md) <br/> |
   
```cpp
typedef struct
{
  ULONG cForms;
  LPMAPIFORMINFO aFormInfo[MAPI_DIM];
} SMAPIFormInfoArray, FAR * LPSMAPIFORMINFOARRAY;

```

## <a name="members"></a><span data-ttu-id="2bbbb-110">成员</span><span class="sxs-lookup"><span data-stu-id="2bbbb-110">Members</span></span>

 <span data-ttu-id="2bbbb-111">**cForms**</span><span class="sxs-lookup"><span data-stu-id="2bbbb-111">**cForms**</span></span>
  
> <span data-ttu-id="2bbbb-112">计数的数组中的指针指向由**aFormInfo**成员。</span><span class="sxs-lookup"><span data-stu-id="2bbbb-112">Count of pointers in the array pointed to by the **aFormInfo** member.</span></span> 
    
 <span data-ttu-id="2bbbb-113">**aFormInfo**</span><span class="sxs-lookup"><span data-stu-id="2bbbb-113">**aFormInfo**</span></span>
  
> <span data-ttu-id="2bbbb-114">为数组对窗体信息对象的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="2bbbb-114">Pointer to an array of pointers to form information objects.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="2bbbb-115">备注</span><span class="sxs-lookup"><span data-stu-id="2bbbb-115">Remarks</span></span>

<span data-ttu-id="2bbbb-116">**SMAPIFormInfoArray**结构作为中的以下方法的参数传递：</span><span class="sxs-lookup"><span data-stu-id="2bbbb-116">The **SMAPIFormInfoArray** structure is passed as a parameter in the following methods:</span></span> 
  
- [<span data-ttu-id="2bbbb-117">IMAPIFormMgr::ResolveMultipleMessageClasses</span><span class="sxs-lookup"><span data-stu-id="2bbbb-117">IMAPIFormMgr::ResolveMultipleMessageClasses</span></span>](imapiformmgr-resolvemultiplemessageclasses.md)
    
- [<span data-ttu-id="2bbbb-118">IMAPIFormMgr::CalcFormPropSet</span><span class="sxs-lookup"><span data-stu-id="2bbbb-118">IMAPIFormMgr::CalcFormPropSet</span></span>](imapiformmgr-calcformpropset.md)
    
- [<span data-ttu-id="2bbbb-119">IMAPIFormMgr::SelectMultipleForms</span><span class="sxs-lookup"><span data-stu-id="2bbbb-119">IMAPIFormMgr::SelectMultipleForms</span></span>](imapiformmgr-selectmultipleforms.md)
    
- [<span data-ttu-id="2bbbb-120">IMAPIFormContainer::ResolveMultipleMessageClasses</span><span class="sxs-lookup"><span data-stu-id="2bbbb-120">IMAPIFormContainer::ResolveMultipleMessageClasses</span></span>](imapiformcontainer-resolvemultiplemessageclasses.md)
    
## <a name="see-also"></a><span data-ttu-id="2bbbb-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2bbbb-121">See also</span></span>



[<span data-ttu-id="2bbbb-122">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="2bbbb-122">MAPI Structures</span></span>](mapi-structures.md)

