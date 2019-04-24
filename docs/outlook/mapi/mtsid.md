---
title: MTSID
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.MTSID
api_type:
- COM
ms.assetid: 3d9bc643-332f-4c8e-83e6-ce9b15711945
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 96da91acec741322e6c07c64555171d35f0f7e00
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32342768"
---
# <a name="mtsid"></a><span data-ttu-id="de693-103">MTSID</span><span class="sxs-lookup"><span data-stu-id="de693-103">MTSID</span></span>

  
  
<span data-ttu-id="de693-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="de693-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="de693-105">包含 X. 400 邮件传输系统 (MTS) 条目标识符。</span><span class="sxs-lookup"><span data-stu-id="de693-105">Contains an X.400 message transport system (MTS) entry identifier.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="de693-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="de693-106">Header file:</span></span>  <br/> |<span data-ttu-id="de693-107">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="de693-107">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="de693-108">相关宏:</span><span class="sxs-lookup"><span data-stu-id="de693-108">Related macros:</span></span>  <br/> |<span data-ttu-id="de693-109">[CbMTSID](cbmtsid.md)、 [CbNewMTSID](cbnewmtsid.md)</span><span class="sxs-lookup"><span data-stu-id="de693-109">[CbMTSID](cbmtsid.md), [CbNewMTSID](cbnewmtsid.md)</span></span> <br/> |
   
```cpp
typedef struct
{
  ULONG cb;
  BYTE abEntry[MAPI_DIM];
} MTSID, FAR *LPMTSID;

```

## <a name="members"></a><span data-ttu-id="de693-110">Members</span><span class="sxs-lookup"><span data-stu-id="de693-110">Members</span></span>

 <span data-ttu-id="de693-111">**cb**</span><span class="sxs-lookup"><span data-stu-id="de693-111">**cb**</span></span>
  
> <span data-ttu-id="de693-112">数组中由**abEntry**成员描述的字节数。</span><span class="sxs-lookup"><span data-stu-id="de693-112">Count of bytes in the array described by the **abEntry** member.</span></span> 
    
 <span data-ttu-id="de693-113">**abEntry**</span><span class="sxs-lookup"><span data-stu-id="de693-113">**abEntry**</span></span>
  
> <span data-ttu-id="de693-114">包含 MTS 条目标识符数据的字节数组。</span><span class="sxs-lookup"><span data-stu-id="de693-114">Byte array that contains the MTS entry identifier data.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="de693-115">注解</span><span class="sxs-lookup"><span data-stu-id="de693-115">Remarks</span></span>

<span data-ttu-id="de693-116">**MTSID**结构仅用于 MAPI 条目标识符的 X. 400 映射。</span><span class="sxs-lookup"><span data-stu-id="de693-116">The **MTSID** structure is used only for X.400 mappings of MAPI entry identifiers.</span></span> <span data-ttu-id="de693-117">它对应于 MAPI [FLATENTRY](flatentry.md)结构。</span><span class="sxs-lookup"><span data-stu-id="de693-117">It corresponds to the MAPI [FLATENTRY](flatentry.md) structure.</span></span> 
  
<span data-ttu-id="de693-118">MTS 标识符的格式与 MAPI 条目标识符或二进制属性值相同。</span><span class="sxs-lookup"><span data-stu-id="de693-118">An MTS identifier has the same format as a MAPI entry identifier or a binary property value.</span></span> <span data-ttu-id="de693-119">MTS 标识符在取消延迟的邮件时尤其有用。</span><span class="sxs-lookup"><span data-stu-id="de693-119">MTS identifiers can be particularly useful for canceling deferred messages.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="de693-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="de693-120">See also</span></span>



[<span data-ttu-id="de693-121">FLATENTRY</span><span class="sxs-lookup"><span data-stu-id="de693-121">FLATENTRY</span></span>](flatentry.md)
  
[<span data-ttu-id="de693-122">FLATMTSIDLIST</span><span class="sxs-lookup"><span data-stu-id="de693-122">FLATMTSIDLIST</span></span>](flatmtsidlist.md)


[<span data-ttu-id="de693-123">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="de693-123">MAPI Structures</span></span>](mapi-structures.md)

