---
title: SMessageClassArray
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.SMessageClassArray
api_type:
- COM
ms.assetid: 05f8c191-db2b-4174-8b3c-a9fdabfe6ac8
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 01563e3655d42abc62ea88a12f2878e5d81129d7
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778844"
---
# <a name="smessageclassarray"></a><span data-ttu-id="ffaae-103">SMessageClassArray</span><span class="sxs-lookup"><span data-stu-id="ffaae-103">SMessageClassArray</span></span>

  
  
<span data-ttu-id="ffaae-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="ffaae-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="ffaae-105">包含指向邮件类字符串的数组。</span><span class="sxs-lookup"><span data-stu-id="ffaae-105">Contains an array of pointers to message class strings.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="ffaae-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="ffaae-106">Header file:</span></span>  <br/> |<span data-ttu-id="ffaae-107">Mapiform.h</span><span class="sxs-lookup"><span data-stu-id="ffaae-107">Mapiform.h</span></span>  <br/> |
|<span data-ttu-id="ffaae-108">相关的宏：</span><span class="sxs-lookup"><span data-stu-id="ffaae-108">Related macro:</span></span>  <br/> |[<span data-ttu-id="ffaae-109">CbMessageClassArray</span><span class="sxs-lookup"><span data-stu-id="ffaae-109">CbMessageClassArray</span></span>](cbmessageclassarray.md) <br/> |
   
```cpp
typedef struct 
{
  ULONG cValues;
  LPCSTR aMessageClass[MAPI_DIM];
} SMessageClassArray, FAR * LPSMESSAGECLASSARRAY;

```

## <a name="members"></a><span data-ttu-id="ffaae-110">Members</span><span class="sxs-lookup"><span data-stu-id="ffaae-110">Members</span></span>

 <span data-ttu-id="ffaae-111">**cValues**</span><span class="sxs-lookup"><span data-stu-id="ffaae-111">**cValues**</span></span>
  
> <span data-ttu-id="ffaae-112">该数组中的邮件类字符串指针的计数。</span><span class="sxs-lookup"><span data-stu-id="ffaae-112">Count of message class string pointers in the array.</span></span>
    
 <span data-ttu-id="ffaae-113">**aMessageClass**</span><span class="sxs-lookup"><span data-stu-id="ffaae-113">**aMessageClass**</span></span>
  
> <span data-ttu-id="ffaae-114">指向邮件类字符串的数组。</span><span class="sxs-lookup"><span data-stu-id="ffaae-114">Array of pointers to message class strings.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="ffaae-115">说明</span><span class="sxs-lookup"><span data-stu-id="ffaae-115">Remarks</span></span>

<span data-ttu-id="ffaae-116">**SMessageClassArray**结构作为中的以下方法的参数传递：</span><span class="sxs-lookup"><span data-stu-id="ffaae-116">The **SMessageClassArray** structure is passed as a parameter in the following methods:</span></span> 
  
- [<span data-ttu-id="ffaae-117">IMAPIFormContainer::ResolveMultipleMessageClasses</span><span class="sxs-lookup"><span data-stu-id="ffaae-117">IMAPIFormContainer::ResolveMultipleMessageClasses</span></span>](imapiformcontainer-resolvemultiplemessageclasses.md)
    
- [<span data-ttu-id="ffaae-118">IMAPIFormMgr::ResolveMultipleMessageClasses</span><span class="sxs-lookup"><span data-stu-id="ffaae-118">IMAPIFormMgr::ResolveMultipleMessageClasses</span></span>](imapiformmgr-resolvemultiplemessageclasses.md)
    
## <a name="see-also"></a><span data-ttu-id="ffaae-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ffaae-119">See also</span></span>



[<span data-ttu-id="ffaae-120">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="ffaae-120">MAPI Structures</span></span>](mapi-structures.md)

