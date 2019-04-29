---
title: STnefProblem
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.STnefProblem
api_type:
- COM
ms.assetid: 3fe651b7-0ddf-42fd-8277-9224505be1a8
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 19d20a3fb06f6a0a0671ba4bfd938da314001778
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33435178"
---
# <a name="stnefproblem"></a><span data-ttu-id="3f341-103">STnefProblem</span><span class="sxs-lookup"><span data-stu-id="3f341-103">STnefProblem</span></span>

  
  
<span data-ttu-id="3f341-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="3f341-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="3f341-105">包含有关在编码或解码传输中性封装格式 (TNEF) 流过程中出现的属性或属性处理问题的信息。</span><span class="sxs-lookup"><span data-stu-id="3f341-105">Contains information about a property or attribute processing problem that occurred during the encoding or decoding of a Transport Neutral Encapsulation Format (TNEF) stream.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="3f341-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="3f341-106">Header file:</span></span>  <br/> |<span data-ttu-id="3f341-107">Tnef</span><span class="sxs-lookup"><span data-stu-id="3f341-107">Tnef.h</span></span>  <br/> |
   
```cpp
typedef struct _STnefProblem
{
  ULONG ulComponent;
  ULONG ulAttribute;
  ULONG ulPropTag;
  SCODE scode;
} STnefProblem;

```

## <a name="members"></a><span data-ttu-id="3f341-108">Members</span><span class="sxs-lookup"><span data-stu-id="3f341-108">Members</span></span>

 <span data-ttu-id="3f341-109">**ulComponent**</span><span class="sxs-lookup"><span data-stu-id="3f341-109">**ulComponent**</span></span>
  
> <span data-ttu-id="3f341-110">发生问题的处理类型。</span><span class="sxs-lookup"><span data-stu-id="3f341-110">The type of processing during which the problem occurred.</span></span> <span data-ttu-id="3f341-111">如果在邮件处理过程中出现问题, **ulComponent**成员将设置为零。</span><span class="sxs-lookup"><span data-stu-id="3f341-111">If the problem occurred during message processing, the **ulComponent** member is set to zero.</span></span> <span data-ttu-id="3f341-112">如果在附件处理过程中出现问题, 则将**ulComponent**设置为等于相应附件的**PR_ATTACH_NUM** ([PidTagAttachNumber](pidtagattachnumber-canonical-property.md)) 值。</span><span class="sxs-lookup"><span data-stu-id="3f341-112">If the problem occurred during attachment processing, **ulComponent** is set equal to the corresponding attachment's **PR_ATTACH_NUM** ([PidTagAttachNumber](pidtagattachnumber-canonical-property.md)) value.</span></span>
    
 <span data-ttu-id="3f341-113">**ulAttribute**</span><span class="sxs-lookup"><span data-stu-id="3f341-113">**ulAttribute**</span></span>
  
> <span data-ttu-id="3f341-114">与**ulPropTag**成员指示的属性相关联的属性, 或者, 如果在解码封装块时出现 TNEF 处理问题, 则为下列值之一:</span><span class="sxs-lookup"><span data-stu-id="3f341-114">Attribute associated with the property indicated by the **ulPropTag** member or, when the TNEF processing problem occurs when decoding an encapsulation block, one of the following values:</span></span> 
    
 <span data-ttu-id="3f341-115">_attMAPIProps_</span><span class="sxs-lookup"><span data-stu-id="3f341-115">_attMAPIProps_</span></span>
  
> <span data-ttu-id="3f341-116">邮件级别</span><span class="sxs-lookup"><span data-stu-id="3f341-116">Message level</span></span>
    
 <span data-ttu-id="3f341-117">_attAttachment_</span><span class="sxs-lookup"><span data-stu-id="3f341-117">_attAttachment_</span></span>
  
> <span data-ttu-id="3f341-118">附件级别</span><span class="sxs-lookup"><span data-stu-id="3f341-118">Attachment level</span></span>
    
 <span data-ttu-id="3f341-119">**ulPropTag**</span><span class="sxs-lookup"><span data-stu-id="3f341-119">**ulPropTag**</span></span>
  
> <span data-ttu-id="3f341-120">导致 TNEF 处理问题的属性的属性标记, 但在解码封装块时出现问题, 在此情况下将**ulPropTag**设置为零。</span><span class="sxs-lookup"><span data-stu-id="3f341-120">Property tag of the property that caused the TNEF processing problem, except when the problem occurs when decoding an encapsulation block, in which case **ulPropTag** is set to zero.</span></span> 
    
 <span data-ttu-id="3f341-121">**scode**</span><span class="sxs-lookup"><span data-stu-id="3f341-121">**scode**</span></span>
  
> <span data-ttu-id="3f341-122">指示处理过程中遇到的问题的错误值。</span><span class="sxs-lookup"><span data-stu-id="3f341-122">Error value indicating the problem encountered during processing.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="3f341-123">说明</span><span class="sxs-lookup"><span data-stu-id="3f341-123">Remarks</span></span>

<span data-ttu-id="3f341-124">如果在处理属性或属性的过程中不会生成**STnefProblem**结构, 则在假定该属性或属性的处理成功的情况下, 应用程序可以继续。</span><span class="sxs-lookup"><span data-stu-id="3f341-124">If an **STnefProblem** structure is not generated during the processing of an attribute or property, the application can continue under the assumption that the processing of that attribute or property succeeded.</span></span> <span data-ttu-id="3f341-125">仅当在封装块解码过程中出现问题时, 才会发生此异常。</span><span class="sxs-lookup"><span data-stu-id="3f341-125">The only exception occurs when the problem arose during decoding of an encapsulation block.</span></span> <span data-ttu-id="3f341-126">在这种情况下, 将停止对与块相对应的组件进行解码, 并在另一个组件中继续解码。</span><span class="sxs-lookup"><span data-stu-id="3f341-126">In this case, the decoding of the component corresponding to the block is stopped and decoding is continued in another component.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="3f341-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3f341-127">See also</span></span>



[<span data-ttu-id="3f341-128">STnefProblemArray</span><span class="sxs-lookup"><span data-stu-id="3f341-128">STnefProblemArray</span></span>](stnefproblemarray.md)
  
[<span data-ttu-id="3f341-129">PidTagAttachNumber 规范属性</span><span class="sxs-lookup"><span data-stu-id="3f341-129">PidTagAttachNumber Canonical Property</span></span>](pidtagattachnumber-canonical-property.md)


[<span data-ttu-id="3f341-130">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="3f341-130">MAPI Structures</span></span>](mapi-structures.md)

