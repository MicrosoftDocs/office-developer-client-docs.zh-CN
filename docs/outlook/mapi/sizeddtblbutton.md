---
title: SizedDtblButton
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.SizedDtblButton
api_type:
- COM
ms.assetid: ee73ced9-14d8-4a30-9b9f-d54ed9c3a454
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: a7d62d29638ae234667eb33a8103fb3a716afc32
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32282759"
---
# <a name="sizeddtblbutton"></a><span data-ttu-id="9ba6f-103">SizedDtblButton</span><span class="sxs-lookup"><span data-stu-id="9ba6f-103">SizedDtblButton</span></span>

  
  
<span data-ttu-id="9ba6f-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="9ba6f-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="9ba6f-105">创建一个命名的结构, 其中包含用于描述按钮和指定长度的标签的[DTBLBUTTON](dtblbutton.md)结构。</span><span class="sxs-lookup"><span data-stu-id="9ba6f-105">Creates a named structure that includes a [DTBLBUTTON](dtblbutton.md) structure for describing a button and a label of a specified length.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="9ba6f-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="9ba6f-106">Header file:</span></span>  <br/> |<span data-ttu-id="9ba6f-107">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="9ba6f-107">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="9ba6f-108">相关结构:</span><span class="sxs-lookup"><span data-stu-id="9ba6f-108">Related structure:</span></span>  <br/> |<span data-ttu-id="9ba6f-109">**DTBLBUTTON**</span><span class="sxs-lookup"><span data-stu-id="9ba6f-109">**DTBLBUTTON**</span></span> <br/> |
   
```cpp
SizedDtblButton (n, u)
```

## <a name="parameters"></a><span data-ttu-id="9ba6f-110">参数</span><span class="sxs-lookup"><span data-stu-id="9ba6f-110">Parameters</span></span>

 <span data-ttu-id="9ba6f-111">_n_</span><span class="sxs-lookup"><span data-stu-id="9ba6f-111">_n_</span></span>
  
> <span data-ttu-id="9ba6f-112">要包含在新结构中的标签的长度。</span><span class="sxs-lookup"><span data-stu-id="9ba6f-112">Length of the label to be included in the new structure.</span></span>
    
 <span data-ttu-id="9ba6f-113">_u_</span><span class="sxs-lookup"><span data-stu-id="9ba6f-113">_u_</span></span>
  
> <span data-ttu-id="9ba6f-114">新结构的名称。</span><span class="sxs-lookup"><span data-stu-id="9ba6f-114">Name for the new structure.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="9ba6f-115">注解</span><span class="sxs-lookup"><span data-stu-id="9ba6f-115">Remarks</span></span>

<span data-ttu-id="9ba6f-116">新结构是使用以下成员创建的:</span><span class="sxs-lookup"><span data-stu-id="9ba6f-116">The new structure is created with the following members:</span></span>
  
```
DTBLBUTTON dtblbutton;
TCHAR lpszLabel[n];

```

## <a name="see-also"></a><span data-ttu-id="9ba6f-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9ba6f-117">See also</span></span>



[<span data-ttu-id="9ba6f-118">DTBLBUTTON</span><span class="sxs-lookup"><span data-stu-id="9ba6f-118">DTBLBUTTON</span></span>](dtblbutton.md)


[<span data-ttu-id="9ba6f-119">与结构相关的宏</span><span class="sxs-lookup"><span data-stu-id="9ba6f-119">Macros Related to Structures</span></span>](macros-related-to-structures.md)

