---
title: SMAPIVerb
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.SMAPIVerb
api_type:
- COM
ms.assetid: 45066528-2447-4178-aaa3-7513ed0b3ba4
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 4d060d62deb685b4691846c2b8e48a82ae3195ea
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778845"
---
# <a name="smapiverb"></a><span data-ttu-id="66d12-103">SMAPIVerb</span><span class="sxs-lookup"><span data-stu-id="66d12-103">SMAPIVerb</span></span>

  
  
<span data-ttu-id="66d12-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="66d12-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="66d12-105">描述 MAPI 动词。</span><span class="sxs-lookup"><span data-stu-id="66d12-105">Describes a MAPI verb.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="66d12-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="66d12-106">Header file:</span></span>  <br/> |<span data-ttu-id="66d12-107">Mapiform.h</span><span class="sxs-lookup"><span data-stu-id="66d12-107">Mapiform.h</span></span>  <br/> |
   
```cpp
typedef struct
{
  ULONG lVerb;
  LPSTR szVerbname;
  DWORD fuFlags;
  DWORD grfAttribs;
  ULONG ulFlags; /* Either 0 or MAPI_UNICODE */
} SMAPIVerb, FAR * LPMAPIVERB;

```

## <a name="members"></a><span data-ttu-id="66d12-108">成员</span><span class="sxs-lookup"><span data-stu-id="66d12-108">Members</span></span>

 <span data-ttu-id="66d12-109">**lVerb**</span><span class="sxs-lookup"><span data-stu-id="66d12-109">**lVerb**</span></span>
  
> <span data-ttu-id="66d12-110">表示传递给[IMAPIForm::DoVerb](imapiform-doverb.md)的动作代码。</span><span class="sxs-lookup"><span data-stu-id="66d12-110">Code representing the verb that is passed to [IMAPIForm::DoVerb](imapiform-doverb.md).</span></span> <span data-ttu-id="66d12-111">标准谓词 Exchform.h 的头文件中定义。</span><span class="sxs-lookup"><span data-stu-id="66d12-111">Standard verbs are defined in the header file Exchform.h.</span></span>
    
 <span data-ttu-id="66d12-112">**szVerbname**</span><span class="sxs-lookup"><span data-stu-id="66d12-112">**szVerbname**</span></span>
  
> <span data-ttu-id="66d12-113">显示在窗体菜单上显示动作的名称。</span><span class="sxs-lookup"><span data-stu-id="66d12-113">Display name of the verb as it appears on the form menu.</span></span>
    
 <span data-ttu-id="66d12-114">**fuFlags**</span><span class="sxs-lookup"><span data-stu-id="66d12-114">**fuFlags**</span></span>
  
> <span data-ttu-id="66d12-115">谓词的标志。</span><span class="sxs-lookup"><span data-stu-id="66d12-115">Flags for the verb.</span></span>
    
 <span data-ttu-id="66d12-116">**grfAttribs**</span><span class="sxs-lookup"><span data-stu-id="66d12-116">**grfAttribs**</span></span>
  
> <span data-ttu-id="66d12-117">谓词的属性。</span><span class="sxs-lookup"><span data-stu-id="66d12-117">Attributes of the verb.</span></span> 
    
 <span data-ttu-id="66d12-118">**ulFlags**</span><span class="sxs-lookup"><span data-stu-id="66d12-118">**ulFlags**</span></span>
  
> <span data-ttu-id="66d12-119">标志指示谓词的显示名称的格式。</span><span class="sxs-lookup"><span data-stu-id="66d12-119">Flag indicating the format of the verb's display name.</span></span> <span data-ttu-id="66d12-120">可以设置以下标记：</span><span class="sxs-lookup"><span data-stu-id="66d12-120">The following flag can be set:</span></span>
    
<span data-ttu-id="66d12-121">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="66d12-121">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="66d12-122">Unicode 格式的显示名称。</span><span class="sxs-lookup"><span data-stu-id="66d12-122">The display name is in Unicode format.</span></span> <span data-ttu-id="66d12-123">如果未设置 MAPI_UNICODE 标志的显示名称是 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="66d12-123">If the MAPI_UNICODE flag is not set, the display name is in ANSI format.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="66d12-124">备注</span><span class="sxs-lookup"><span data-stu-id="66d12-124">Remarks</span></span>

<span data-ttu-id="66d12-125">**SMAPIVerb**结构作为中的以下方法的参数传递：</span><span class="sxs-lookup"><span data-stu-id="66d12-125">The **SMAPIVerb** structure is passed as a parameter in the following methods:</span></span> 
  
- [<span data-ttu-id="66d12-126">IMAPIFormContainer::ResolveMultipleMessageClasses</span><span class="sxs-lookup"><span data-stu-id="66d12-126">IMAPIFormContainer::ResolveMultipleMessageClasses</span></span>](imapiformcontainer-resolvemultiplemessageclasses.md)
    
- [<span data-ttu-id="66d12-127">IMAPIFormMgr::ResolveMultipleMessageClasses</span><span class="sxs-lookup"><span data-stu-id="66d12-127">IMAPIFormMgr::ResolveMultipleMessageClasses</span></span>](imapiformmgr-resolvemultiplemessageclasses.md)
    
## <a name="see-also"></a><span data-ttu-id="66d12-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="66d12-128">See also</span></span>



[<span data-ttu-id="66d12-129">CbMessageClassArray</span><span class="sxs-lookup"><span data-stu-id="66d12-129">CbMessageClassArray</span></span>](cbmessageclassarray.md)


[<span data-ttu-id="66d12-130">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="66d12-130">MAPI Structures</span></span>](mapi-structures.md)

