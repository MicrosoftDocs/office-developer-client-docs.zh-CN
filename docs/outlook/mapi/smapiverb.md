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
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 3ef284a2c036abb9eac10ecf33de4adbf61f3c54
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33410957"
---
# <a name="smapiverb"></a><span data-ttu-id="27e2d-103">SMAPIVerb</span><span class="sxs-lookup"><span data-stu-id="27e2d-103">SMAPIVerb</span></span>

  
  
<span data-ttu-id="27e2d-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="27e2d-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="27e2d-105">描述 MAPI 动词。</span><span class="sxs-lookup"><span data-stu-id="27e2d-105">Describes a MAPI verb.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="27e2d-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="27e2d-106">Header file:</span></span>  <br/> |<span data-ttu-id="27e2d-107">Mapiform.h</span><span class="sxs-lookup"><span data-stu-id="27e2d-107">Mapiform.h</span></span>  <br/> |
   
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

## <a name="members"></a><span data-ttu-id="27e2d-108">Members</span><span class="sxs-lookup"><span data-stu-id="27e2d-108">Members</span></span>

 <span data-ttu-id="27e2d-109">**lVerb**</span><span class="sxs-lookup"><span data-stu-id="27e2d-109">**lVerb**</span></span>
  
> <span data-ttu-id="27e2d-110">表示传递给 [IMAPIForm：:D oVerb 谓词的代码](imapiform-doverb.md)。</span><span class="sxs-lookup"><span data-stu-id="27e2d-110">Code representing the verb that is passed to [IMAPIForm::DoVerb](imapiform-doverb.md).</span></span> <span data-ttu-id="27e2d-111">标准动作在头文件 Exchform.h 中定义。</span><span class="sxs-lookup"><span data-stu-id="27e2d-111">Standard verbs are defined in the header file Exchform.h.</span></span>
    
 <span data-ttu-id="27e2d-112">**szVerbname**</span><span class="sxs-lookup"><span data-stu-id="27e2d-112">**szVerbname**</span></span>
  
> <span data-ttu-id="27e2d-113">在窗体菜单上显示动词的显示名称。</span><span class="sxs-lookup"><span data-stu-id="27e2d-113">Display name of the verb as it appears on the form menu.</span></span>
    
 <span data-ttu-id="27e2d-114">**fuFlags**</span><span class="sxs-lookup"><span data-stu-id="27e2d-114">**fuFlags**</span></span>
  
> <span data-ttu-id="27e2d-115">动词标记。</span><span class="sxs-lookup"><span data-stu-id="27e2d-115">Flags for the verb.</span></span>
    
 <span data-ttu-id="27e2d-116">**grfAttribs**</span><span class="sxs-lookup"><span data-stu-id="27e2d-116">**grfAttribs**</span></span>
  
> <span data-ttu-id="27e2d-117">动词动作的属性。</span><span class="sxs-lookup"><span data-stu-id="27e2d-117">Attributes of the verb.</span></span> 
    
 <span data-ttu-id="27e2d-118">**ulFlags**</span><span class="sxs-lookup"><span data-stu-id="27e2d-118">**ulFlags**</span></span>
  
> <span data-ttu-id="27e2d-119">指示动词动词的用法格式显示名称。</span><span class="sxs-lookup"><span data-stu-id="27e2d-119">Flag indicating the format of the verb's display name.</span></span> <span data-ttu-id="27e2d-120">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="27e2d-120">The following flag can be set:</span></span>
    
<span data-ttu-id="27e2d-121">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="27e2d-121">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="27e2d-122">该显示名称采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="27e2d-122">The display name is in Unicode format.</span></span> <span data-ttu-id="27e2d-123">如果未MAPI_UNICODE，则显示名称为 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="27e2d-123">If the MAPI_UNICODE flag is not set, the display name is in ANSI format.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="27e2d-124">备注</span><span class="sxs-lookup"><span data-stu-id="27e2d-124">Remarks</span></span>

<span data-ttu-id="27e2d-125">**SMAPIVerb** 结构在下列方法中作为参数传递：</span><span class="sxs-lookup"><span data-stu-id="27e2d-125">The **SMAPIVerb** structure is passed as a parameter in the following methods:</span></span> 
  
- [<span data-ttu-id="27e2d-126">IMAPIFormContainer::ResolveMultipleMessageClasses</span><span class="sxs-lookup"><span data-stu-id="27e2d-126">IMAPIFormContainer::ResolveMultipleMessageClasses</span></span>](imapiformcontainer-resolvemultiplemessageclasses.md)
    
- [<span data-ttu-id="27e2d-127">IMAPIFormMgr::ResolveMultipleMessageClasses</span><span class="sxs-lookup"><span data-stu-id="27e2d-127">IMAPIFormMgr::ResolveMultipleMessageClasses</span></span>](imapiformmgr-resolvemultiplemessageclasses.md)
    
## <a name="see-also"></a><span data-ttu-id="27e2d-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="27e2d-128">See also</span></span>



[<span data-ttu-id="27e2d-129">CbMessageClassArray</span><span class="sxs-lookup"><span data-stu-id="27e2d-129">CbMessageClassArray</span></span>](cbmessageclassarray.md)


[<span data-ttu-id="27e2d-130">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="27e2d-130">MAPI Structures</span></span>](mapi-structures.md)

