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
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: e274e24d9aff30bb39b1865306477164d413d9a8
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33416970"
---
# <a name="smapiforminfoarray"></a><span data-ttu-id="a65c9-103">SMAPIFormInfoArray</span><span class="sxs-lookup"><span data-stu-id="a65c9-103">SMAPIFormInfoArray</span></span>

  
  
<span data-ttu-id="a65c9-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="a65c9-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="a65c9-105">包含指向表单信息对象的指针数组。</span><span class="sxs-lookup"><span data-stu-id="a65c9-105">Contains an array of pointers to form information objects.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="a65c9-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="a65c9-106">Header file:</span></span>  <br/> |<span data-ttu-id="a65c9-107">Mapiform</span><span class="sxs-lookup"><span data-stu-id="a65c9-107">Mapiform.h</span></span>  <br/> |
|<span data-ttu-id="a65c9-108">相关宏:</span><span class="sxs-lookup"><span data-stu-id="a65c9-108">Related macro:</span></span>  <br/> |[<span data-ttu-id="a65c9-109">CbMAPIFormInfoArray</span><span class="sxs-lookup"><span data-stu-id="a65c9-109">CbMAPIFormInfoArray</span></span>](cbmapiforminfoarray.md) <br/> |
   
```cpp
typedef struct
{
  ULONG cForms;
  LPMAPIFORMINFO aFormInfo[MAPI_DIM];
} SMAPIFormInfoArray, FAR * LPSMAPIFORMINFOARRAY;

```

## <a name="members"></a><span data-ttu-id="a65c9-110">Members</span><span class="sxs-lookup"><span data-stu-id="a65c9-110">Members</span></span>

 <span data-ttu-id="a65c9-111">**cForms**</span><span class="sxs-lookup"><span data-stu-id="a65c9-111">**cForms**</span></span>
  
> <span data-ttu-id="a65c9-112">由**aFormInfo**成员指向的数组中的指针计数。</span><span class="sxs-lookup"><span data-stu-id="a65c9-112">Count of pointers in the array pointed to by the **aFormInfo** member.</span></span> 
    
 <span data-ttu-id="a65c9-113">**aFormInfo**</span><span class="sxs-lookup"><span data-stu-id="a65c9-113">**aFormInfo**</span></span>
  
> <span data-ttu-id="a65c9-114">指向指向表单信息对象的指针的数组的指针。</span><span class="sxs-lookup"><span data-stu-id="a65c9-114">Pointer to an array of pointers to form information objects.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="a65c9-115">说明</span><span class="sxs-lookup"><span data-stu-id="a65c9-115">Remarks</span></span>

<span data-ttu-id="a65c9-116">在以下方法中, **SMAPIFormInfoArray**结构作为参数传递:</span><span class="sxs-lookup"><span data-stu-id="a65c9-116">The **SMAPIFormInfoArray** structure is passed as a parameter in the following methods:</span></span> 
  
- [<span data-ttu-id="a65c9-117">IMAPIFormMgr::ResolveMultipleMessageClasses</span><span class="sxs-lookup"><span data-stu-id="a65c9-117">IMAPIFormMgr::ResolveMultipleMessageClasses</span></span>](imapiformmgr-resolvemultiplemessageclasses.md)
    
- [<span data-ttu-id="a65c9-118">IMAPIFormMgr::CalcFormPropSet</span><span class="sxs-lookup"><span data-stu-id="a65c9-118">IMAPIFormMgr::CalcFormPropSet</span></span>](imapiformmgr-calcformpropset.md)
    
- [<span data-ttu-id="a65c9-119">IMAPIFormMgr::SelectMultipleForms</span><span class="sxs-lookup"><span data-stu-id="a65c9-119">IMAPIFormMgr::SelectMultipleForms</span></span>](imapiformmgr-selectmultipleforms.md)
    
- [<span data-ttu-id="a65c9-120">IMAPIFormContainer::ResolveMultipleMessageClasses</span><span class="sxs-lookup"><span data-stu-id="a65c9-120">IMAPIFormContainer::ResolveMultipleMessageClasses</span></span>](imapiformcontainer-resolvemultiplemessageclasses.md)
    
## <a name="see-also"></a><span data-ttu-id="a65c9-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a65c9-121">See also</span></span>



[<span data-ttu-id="a65c9-122">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="a65c9-122">MAPI Structures</span></span>](mapi-structures.md)

