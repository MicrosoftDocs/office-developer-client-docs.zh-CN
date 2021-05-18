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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33421912"
---
# <a name="sizeddtblbutton"></a><span data-ttu-id="8a5ab-103">SizedDtblButton</span><span class="sxs-lookup"><span data-stu-id="8a5ab-103">SizedDtblButton</span></span>

  
  
<span data-ttu-id="8a5ab-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="8a5ab-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="8a5ab-105">创建一个命名结构，其中包含用于描述按钮和指定长度的标签的 [DTBLBUTTON](dtblbutton.md) 结构。</span><span class="sxs-lookup"><span data-stu-id="8a5ab-105">Creates a named structure that includes a [DTBLBUTTON](dtblbutton.md) structure for describing a button and a label of a specified length.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="8a5ab-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="8a5ab-106">Header file:</span></span>  <br/> |<span data-ttu-id="8a5ab-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="8a5ab-107">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="8a5ab-108">相关结构：</span><span class="sxs-lookup"><span data-stu-id="8a5ab-108">Related structure:</span></span>  <br/> |<span data-ttu-id="8a5ab-109">**DTBLBUTTON**</span><span class="sxs-lookup"><span data-stu-id="8a5ab-109">**DTBLBUTTON**</span></span> <br/> |
   
```cpp
SizedDtblButton (n, u)
```

## <a name="parameters"></a><span data-ttu-id="8a5ab-110">参数</span><span class="sxs-lookup"><span data-stu-id="8a5ab-110">Parameters</span></span>

 <span data-ttu-id="8a5ab-111">_n_</span><span class="sxs-lookup"><span data-stu-id="8a5ab-111">_n_</span></span>
  
> <span data-ttu-id="8a5ab-112">要包含在新结构中的标签的长度。</span><span class="sxs-lookup"><span data-stu-id="8a5ab-112">Length of the label to be included in the new structure.</span></span>
    
 <span data-ttu-id="8a5ab-113">_u_</span><span class="sxs-lookup"><span data-stu-id="8a5ab-113">_u_</span></span>
  
> <span data-ttu-id="8a5ab-114">新结构的名称。</span><span class="sxs-lookup"><span data-stu-id="8a5ab-114">Name for the new structure.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="8a5ab-115">备注</span><span class="sxs-lookup"><span data-stu-id="8a5ab-115">Remarks</span></span>

<span data-ttu-id="8a5ab-116">新结构由以下成员创建：</span><span class="sxs-lookup"><span data-stu-id="8a5ab-116">The new structure is created with the following members:</span></span>
  
```
DTBLBUTTON dtblbutton;
TCHAR lpszLabel[n];

```

## <a name="see-also"></a><span data-ttu-id="8a5ab-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8a5ab-117">See also</span></span>



[<span data-ttu-id="8a5ab-118">DTBLBUTTON</span><span class="sxs-lookup"><span data-stu-id="8a5ab-118">DTBLBUTTON</span></span>](dtblbutton.md)


[<span data-ttu-id="8a5ab-119">与结构相关的宏</span><span class="sxs-lookup"><span data-stu-id="8a5ab-119">Macros Related to Structures</span></span>](macros-related-to-structures.md)

